+++
title = "Game Development"
template = "article.html"
[extra]
banner = "banner.webp"
+++

## Project Odyssey
<figure>
{{ youtube(id="pkb_lgo67Bw") }}
<figcaption>This video is from an earlier iteration of the game, the combat system has been rewritten now and the mechanics are significantly more polished now.</figcaption>
</figure>

<!-- {{% center %}} -->
### [Game Link](https://www.roblox.com/games/18585084767/combat-test)
<!-- {{% center %}} -->

Project Odyssey is a multiplayer open-world fighting game made using the Roblox platform. The game is centered around players creating customized characters which they can upgrade in levels, abilities, and items. Additionally, there is a mechanic that permanently deletes a character after it dies a certain number of times creating high-stake and emergent gameplay for player versus environment and player versus player interactions.

The game is currently undergoing a *total redesign*. I have rewritten the underlying combat code and much of the underlying server structure. This was done by integrating a central state machine to switch client state based on input and send signals for server moves like attacking and rolling. These then can update the server state, which dictates the interactions between clients. This approach has greatly reduced the time to create an MVP of the combat system, which was super important to get the game in the hands of testers.

### Why Roblox?
Roblox as a platform does have its limitations. The biggest limitation is the lack of ability to edit some aspects of the base game. I can’t edit what certain settings do, only enable or disable them. This makes it challenging to optimize games or change the behavior of certain keybinds without completely rewriting the system. For example, I couldn’t edit the default look of the inventory without completely rewriting it, which led me to use a third-party inventory script.

However, the online nature of the platform *completely makes it worth it* to develop games on it. The platform handles advertising, payment, and server hosting for you so I can focus on getting the game created. It also has a preestablished audience that you can tap in. It also has plenty of documentation on its coding system, whether that be official or third party.

### Reflections
While this project is still ongoing, I've learned a lot along the way. The most important lesson I've learned is that you should get a MVP in the hands of players as soon as possible. My first iteration of the game started with me building an island to play on before I even started the combat system. For a combat game, this was a massive mistake that led to me spending too much time doing unimportant tasks instead of building what actually mattered, the combat.

My second iteration of the game started off well, I started with the combat, but decided that I would try to implement other things like a server browser or elements instead. And while I did get this into the hands of players, it was not my main focus. And, this was a mistake, I would get too far without the combat being polished enough. I would realize this during a playtest after a few months of working on the game, there were a lot of bugs and the root causes of them were buried deep within the system. If I wanted to fix the bugs, I would need to rewrite everything because everything was built on a flawed system.

So, for my third iteration, I've removed all the other stuff and have focused on designing a fighting game first. Every week, I playtest the game with friends, getting their opinions on the new mechanics that I've added. And, while this has added a lot of work rewriting code and fixing bugs, the game feels astronomically more polished and fun.

### Future
I have a current goal of getting a beta for Winter break. This will allow me a lot of time to test it with other people and will allow me to fix most of the current bugs. I'm probably about 30% of the way there, the base combat system is done but I haven't implemented much of the customizability (extra weapon types, more moves, etc.). As I get further into the rewrite, however, I will start to reintegrate the working code from Version 2, which will help me move a lot quicker.

## Project Mercenary

{{ youtube(id="NBiffNYAWgg") }}

Project Mercenary is a 3D first-person-shooter game where the player’s role is a mercenary. The primary objective is for the player to adventure through space while fulfilling contracts with each contract providing a different area to explore and a new chapter of the story. The central plot provides a cohesive narrative throughout the story as the player grows from a lower ranked mercenary to one of the best in the galaxy.

Most of the movement systems are completed, including the state machine for walking, running, slide, crouch, and dash movements. The weapon system is complete for the two basic weapon types (gun and melee).

This game has been put on hold so that I could focus on Project Odyssey's rewrite.
