---
title: "The AI Developer Is Here"
date: 2024-08-31T14:01:51+01:00
draft: false
tags: ['coding', 'ai']
---

A couple of years ago I spent some time to learn Python basics. I had spent enough time with Python the language, but not the community, tooling and libraries. I wanted to complete a project so I could see what developing with python *feels* like. It took me few weekends to get a project running - using FastAPI, SQLite, SQLalchemy, and NextJS for the front-end. In the end, I had a web application, with a UI, a RESTful API, a data model, ability to store that in a database, support basic migrations, and using Docker to deploy the whole thing in containers. I didn't pace myself as the goal was learning rather than speed, and it took me a few weekends to complete.

Today, I did all of that in 15 minutes. I did it using [Cursor](https://www.cursor.com/) - the recently released AI editor which uses a large language model to do the coding for you. I didn't write a single line of code.

I haven't been this impressed by a new tool or language in the last decade. I have been doing software development for 17 years now, although less hands-on in the last 5-6, and although I've had plenty of "wow" moments experiencing different tech for the first time, nothing has compared to Cursor. I am fully sold on AI assistants.

Cursor is an IDE. It's a fork of VS Code (a great editor itself). The team who created it made it standalone rather than a plugin, so they can control the full experience themselves. I think that was a great decision, because it is a completely different experience. While it's still a text editor, what you do most of the time is chat to the AI, not write code. The code is written by the LLM ([Claude 3.5 Sonnet](https://www.anthropic.com/news/claude-3-5-sonnet) in this case), and you just need to give it the prompts, and control where the generated output goes. I had to select which file to apply each snippet to, but I'm sure soon you won't have to do this either. What blew me away wasn't just the fact that this is possible. Many other AI coding tools have made the job of creating a basic app easier recently. Github Copilot has become a standard in every developer's toolbox. But Cursor stands out in two important aspects.

First, it generates entire folder structures and applications, rather than just auto-completing what you write, or operating on single files. I think this is the first in the industry and a game-changer. For many people new to coding, half the effort and confusion is in setting up the right files, folder structure and congfiguration. That's hard when you don't know what you're doing. Cursor automatically does that for you. 

![Cursor - starting prompt](/images/Cursor-first-prompt.png)

Second, Cursor was able to debug, diagnose and fix problems encountered during the process. The initial application didn't run out-of-the-box and there were some mistakes in the code. But after asking it why and giving it an error message, the LLM was able to correctly diagnose the problem and offer a solution. This happened multiple times through my session; once to fix a CORS issue, other times to deal with some NextJS rendering convention. When the code writing was done, I even asked the editor to pre-fill some sample data in the DB so I can see how the UI looks without having to do that myself. Not only did it do that, it suggested using SqlAlchemy's migration capabilities, so you don't have to do that multiple times and the data is pre-seeded only if empty. This stuff is non-trivial.

![Cursor debugging](/images/Cursor-debugging.png)
![Cursor fixing a CORS issue](/images/Cursor-CORS.png)
![Cursor data pre-seeding](/images/Cursor-db-seeding.png)

All of this goes way beyond just predicting the next line of code. I think we're at the start of a revolution in how we create software. Does this mean software developer jobs disappear tomorrow? No, I don't think so[^1]. I just think it will enable people who have no idea how to code to write entire apps themselves. Cursor won't create and maintain enterprise-grade applications by itself, but it will fulfil the needs of the majority of hobby projects. It will enable product managers to test how things work with customers quickly.

I plan to start using Cursor as the default for any new hobby project. Given this is barely the first version, I can't wait to see how it will evolve and what new things it will enable for software engineers. I wouldn't be surprised if it entirely transforms the IDE as a concept. 

[^1]: I subsequently wrote another post about this: [Gen AI Will Not Kill Developer Jobs]({{< ref "/posts/gen-ai-will-not-kill-developer-jobs" >}} )