---
title: /implementation
layout: page
permalink: /implementation
---

<hr class="dotted-line">

<h1><mark style="background-color: lightgrey;">Unity + FMOD Pet Project for Master's Thesis</mark> </h1>

<hr class="dotted-line">

This game was created as a methodological approach for a master's thesis on the topic of **"Causing Suspense, Anxiety and Fear Using Sound Design in Video Games"** (2022), which investigated the effectiveness of different sound design approaches in evoking the aforementioned emotions. The player must go through the same level several times, with the soundscape changes in each playthrough.

I developed the game entirely in **Unity**. **FMOD** was used to integrate sound assets and logic. 334 unique sound effects were created in Steinberg Nuendo 12, from which 42 events were assembled in FMOD, including music. 8 C# scripts were written for implementation purposes. More details about the project can be found at the links below.

<iframe width="100%" height="563" src="https://www.youtube.com/embed/orgws-fVfX4?si=dghqg9PRBwYc9My3" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

* **[Read more on the development of the game](posts/unityfmodmethod)** 
* **[Read the full thesis](https://drive.google.com/file/d/1QXvPdk2z_lEcTkXImmOrjOj41hH9j0hL/view)**
* **[Download game on ITCH.IO](https://katalize.itch.io/causing-suspense-anxiety-and-fear-using-sound-design-in-video-games)** 
* **[Github repo](https://github.com/Katalize/Causing-Suspense-Anxiety-And-Fear-Using-Sound-Design-In-Video-Games)**

<hr class="dotted-line">
<hr class="dotted-line">

<h1><mark style="background-color: lightgrey;">Unreal Engine 5 + Wwise Pet Project for Personal Study</mark> </h1>

<hr class="dotted-line">

In 2022 I developed a game prototype using **Unreal Engine 5 and Wwise**, focusing on the technical implementation of various audio systems using the Blueprints system, and also paying special attention to integration with Wwise. 

This prototype version implements a **comprehensive occlusion system** (*adapted from Quantum Break*) that uses line traces to generate an occlusion coefficient for use as a game parameter in Wwise. 

The Foley system sends events to Wwise when the player's mesh colliders collide, thus simulating the rubbing of elbows against the torso. I have also written from scratch stamina and health systems that are used in Wwise as game parameters. All of the above can be seen in the video demonstration.

<iframe width="100%" height="563" src="https://www.youtube.com/embed/cV2R0VJZ8PM?si=D0JWDFbwM7txBR7U" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; &cc_load_policy=1; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen ></iframe>

<hr class="dotted-line">

