---
layout: post
title:  "Friday Facts #57: Task Scheduling"
date:   2020-11-20 00:00:00 -0700
author: lone-pine
#categories: new-city friday-facts

image: /assets/images/57/57_hundreds_of_thousands.png
description: Look to the Future

---

{% include image.html class="caption-bottom"
  url="/assets/images/57/57_wall_street.png"
%}

Lone Pine:

It's said that a person's perception of a game's performance is more influenced by a few slow frames than many fast frames. If 90% of frames are sub 10ms (equivalent to 100 FPS), but the remaining 10% are over 20ms (equivalent to less than 50 FPS), that will be perceived as worse than a constant 50 FPS.

That was the impetus behind this week's highlight feature, the task scheduler. Every frame, the game does a number of tasks: collect and process user input, update the game state in various ways, interpolate and position all the vehicles, interact with various threads, update and render the UI, and collect all the render data to be transmitted to OpenGL.

Many of these tasks can be delayed until future frames. The game state does not need to be updated all at once, and some things only need to happen a few times a second, not every frame. Other tasks might suddenly take a very long time, such as autosaving or updating the satmap.

The task scheduler keeps a record of how long each task takes, on average, and knows which tasks can be delayed. It tries to make a frame in about the same amount of time that the last few frames took, on average. The scheduler determines a deadline for a frame, and any task that is likely to go past the deadline, and that can be delayed, will be left on the queue for a future frame. Tasks also have a maximum time in the queue, so they will be performed eventually.

Originally, I used a simple average, what mathematicians call an arithmetic mean, to estimate how long a task takes. However, we are really concerned about worst case performance, not average. So I switched to a geometric mean, which is an alternative to the arithmetic mean that is biased towards larger (worse) values.

The geometric mean is based on the log of the value, so a 100ms task will be represented as -1, which equals log10(.1 seconds), and a 1ms task will be represented as -3, which equals log10(.001 seconds). To prevent infinite and undefined values, tasks are considered to take a minimum of 0.01 milliseconds.

The estimate is also a moving estimate -- every time a task is run, I take 2% of how long the task took, plus 98% of the previous estimate. This allows the task scheduler to account for changes over time.

{% include image.html class="caption-bottom"
  url="/assets/images/57/57_hundreds_of_thousands.png"
  description="Hundreds of Thousands"
%}

When I implemented the task scheduler, I immediately noticed that one task took over 16ms every frame, sinking any hope of getting 60 FPS (on my machine, with that particular city.) That task was entity culling -- the process of filtering the entities (rendered objects) to only those visible by the camera. With hundreds of thousands of buildings in a city, and many more objects of different types, it's no surprise that this is an expensive operation for us.

I started working on a new entity culling algorithm that is higher performance and can be spun off into its own thread (or potentially even multiple threads.) I'll have more on this topic in a future post.

As for the task scheduler, I'm still learning how to use it. As I tune it up, and find more things in the game that need to be optimized, I'm confident the game will get even faster.

---

{% include image.html class="caption-bottom"
  url="/assets/images/57/57_donuts.png"
  description="Donut."
%}

Gainos:

Hello everyone, some time since I wrote something here so I wanted to talk with the community again. As I was thinking about what to write here I realized that even making a short section on Friday Facts can be pretty challenging to me. And there isn’t only one reason for that, but one of the main reasons why that is so difficult to me is the language itself. For those of you that don’t know, I’m from Brazil and my native language is portuguese. Currently, all other team members have English as their native language.

Personally, I don’t feel like writing or even speaking in english has been a big blocker for me, but it did make things more difficult. This isn’t the first international team that I work with but the issue is still there and I can still feel it sometimes. Not only the language barrier but mostly the cultural difference can be felt very frequently. When other team members mention some event happening in their countries or use specific expressions I don’t always follow and that’s fine. I have already learned so much from them regarding culture and language.

I don’t remember at which point exactly I could say that I was reasonably fluent in English but I do remember where it started: video games. It was always that interesting character in games with some impactul sentences or those walls of text that I wanted so much to understand that made me start learning. I never did any sort of English class other than the classes I had in High School and before that. I saw a sentence and an object and then suddenly, I understood what that word meant. Or, at least, It meant something to me.

Does that affect me in my work on game development? It does, sometimes, but I can say that I clearly understand all the tasks given me and I can answer feedback with relevant opinions. What’s my point with all of this? It’s that I have learned so much from being able to speak another language and I had access to so much more info about any subject after doing so.

And I won’t stop here, or at least, I hope I don’t. There are so many more languages from around the world that I hope to get a least a little feel for. I hope to understand enough to continue on my learning journey and become a better artist and most of all, a happier, more knowledgeable person.

Gainos out.

---

{% include image.html class="caption-bottom"
  url="/assets/images/57/57_snow_storm.png"
%}

Alternate version in portuguese

Gainos:

Olá a todos, faz algum tempo desde que eu escrevi algo aqui então eu queria falar de novo com a comunidade. Enquanto eu pensava no que escrever na minha parte eu percebi que até escrever algo no blog pode ser desafiador para mim. Não existe uma única razão para isso mas um dos principais motivos é o idioma em si. Para aqueles que não sabem, eu sou do Brasil e o Português é o meu idioma nativo. Atualmente, todos os outros integrantes da equipe tem inglês como língua materna.

Eu não sinto que escrever ou até falar em inglês tenha sido um grande desafio para mim, mas isso torna tudo um pouco mais complicado. Essa não é a primeira equipe internacional com que eu trabalho, mas ainda assim eu sinto a diferença às vezes. Não apenas a diferença do idioma mas a diferença cultural também é nítida. Quando outros integrantes da equipe mencionam coisas relevantes no seu país ou usam expressões complicadas eu nem sempre entendo e até aí, tudo bem. Eu já aprendi tanto no meu tempo aqui sobre outras culturas e idioma.

Eu não me lembro exatamente em que ponto eu teria me considerado fluente, mas eu me lembro onde eu comecei a aprender: com jogos em meu computador. Coisas como um personagem com falas interessantes ou histórias longas e cheias de detalhes me fizeram querer aprender o idioma. Eu nunca fiz nenhum curso específico de inglês além das aulas que eu tive no Ensino Médio e Ensino Fundamental. Nos jogos, eu via um objeto e uma palavra ao lado e, de repente, a palavra fazia sentido. Ou, pelo menos, o sentido que eu dava a ela.

O meu idioma afeta o meu trabalho? Sim, as vezes, mas eu posso dizer que eu claramente entendo todas as tarefas que eu recebo e tento me engajar com a comunidade frequentemente, e estou totalmente disposto a responder perguntas sobre o jogo em português, caso necessário. Qual o meu ponto em escrever tudo isso? O meu ponto é que eu aprendi muito a partir do momento que eu sabia um segundo idioma e eu tive acesso a muito mais informação. Informação que me ajudou a me tornar um artista.
E eu não vou parar por aqui ou, pelo menos, eu espero que não. Ainda existem muitos idiomas ao redor do mundo que eu tenho interesse em aprender. Eu espero entender o suficiente para continuar na minha jornada e me tornar um artista melhor. E, mais importante ainda, uma pessoa mais feliz e interessante.

---

Questions? Comments? Feedback on the game? Sound off on our [Discord]{:target="_blank"}.

As always, we're incredibly thankful for our great community across the web. We love seeing the hard work and attention to detail you pour into your cities, and it inspires us every day to keep building. Thank you again for your support.

If you want to play the game and haven't got it yet, head over to our [Steam page]{:target="_blank"}. We're also on [Reddit]{:target="_blank"} and [Twitter]{:target="_blank"}. Give us a follow if you haven't, and we'll keep you up to date on what's new with NewCity!

[Discord]:  http://discord.gg/cz6t4J5
[Steam page]: https://store.steampowered.com/app/1067860/NewCity/
[Reddit]: https://www.reddit.com/r/NewCity
[Twitter]: https://twitter.com/lone_pine_games











