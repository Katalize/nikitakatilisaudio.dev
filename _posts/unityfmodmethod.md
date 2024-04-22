[III. Methodology](https://sites.google.com/view/nikitakatilisportfolio/игра-на-unity-fmod#h.dfdo4118bbp)[3.1 Selected Sound Design Techniques](https://sites.google.com/view/nikitakatilisportfolio/игра-на-unity-fmod#h.g2zhn6s49yg6)[3.2 Tools Used For Game Development](https://sites.google.com/view/nikitakatilisportfolio/игра-на-unity-fmod#h.id1whk3klimv)[3.3 Game Development](https://sites.google.com/view/nikitakatilisportfolio/игра-на-unity-fmod#h.5jqral1yuj0g)[3.4 Sound Design and Implementation](https://sites.google.com/view/nikitakatilisportfolio/игра-на-unity-fmod#h.rsf3zlaeetpd)

**III. Methodology**
--------------------

Based on the main question of the dissertation, this experimental design aims to collect quantitative data on the effectiveness of certain sound design techniques in inducing fear, anxiety and suspense in horror video games without relying on other gameplay elements. This chapter will present the methodological approach and provide detailed descriptions of techniques studied, game development and audio implementation, approaches to measuring fear, anxiety and suspense, as well as the procedure itself.

### **3.1 Selected Sound Design Techniques**

Based on the information gathered in the secondary research, the effectiveness of _ambiguity_, the _startle effect (jumpscares)_ and _unpleasant sounds_ was tested in causing fear, anxiety and suspense. These approaches were chosen due to the fact, that their realisation in a game does not necessarily require any ‘scary’ visual stimuli or gameplay elements. Techniques such as _forewarning_ by their definition need a presence of a dangerous enemy or something potentially dangerous to the avatar in the game, making it much harder to judge the effectiveness of audio on its’ own, as those elements can influence the levels of the abovementioned emotions. Additionally, the combination of selected approaches was tested, as in commercial game scenarios sound designers rely on multiple techniques at once in order to scare the player and increase the levels of anxiety and suspense.

### **3.2 Tools Used For Game Development**

In order to develop the game for testing, a free personal license of a cross-platform game engine _Unity_ (version 2021.3.8f1) was acquired (_see Figure 3.1)_. While there are many other engines, such as _Unreal Engine 5_ or _Godot_, Unity has an extensive library of user-generated assets, such as 3D models, scripts, particle effects and others. Additionally, due to its’ popularity, there are great amounts of educational resources and pre-developed solutions, which greatly helped in the development process.

**Figure 3.1** Unity project of the game.

As Unity uses C# as its main scripting and programming language, a lightweight code editor software _Visual Studio Code_ was used for scripting audio and other game-related events.

Since Unity’s first-party audio engine is quite limited in functionality ‘out of the box’, a middleware audio solution _FMOD Studio_ was integrated into the project. It provides sound designers with multiple streamlined tools for implementing audio into the game, such as randomisation, real-time signal processing, mix states and others.

For sound design and audio editing, _Steinberg Nuendo 12_ digital audio workstation (DAW) was used, because it provided a much more convenient workflow when rendering multiple audio files, which is essential when working in-game audio. Third-party VST plugins, such as digital synthesisers and audio processing units were used. Additionally, a DAW _Bitwig Studio_ was used for music composition.

### **3.3 Game Development**

As this research primarily focused on the emotional effects of sound design in video games, it was very important to conduct the testing in a video game environment in order for the results to be well founded, so a similar approach was adopted from Garner, Abdel-Nabi and Grimshaw’s 2010 study.

A video game was developed, which consisted of 5 visually identical levels (also referred to as _areas_) with different soundscapes (see _Appendix A_ for a demonstration video, game download link and screenshots). At the start of the game, players are spawned on a platform, where 5 blue portals are located. After walking through one of these portals, the playable character is randomly teleported to one of these 5 areas. The gamers are tasked to complete each level by collecting pluses and reaching the red portal located in the house, which brings them back to the platform. After each blue portal is used - it disappears, so in order to fully complete the game, all of them must be gone. The main difference in the level design compared to the above-mentioned study is that the levels were designed in a linear, corridor-like fashion. This was done in order to provide participants with a clear direction of where they should go, making it harder to get lost (see _Figure 3.2_.).

**Figure 3.2** The designed completion path of the level.

As immersion is an important factor for experiencing emotions when playing a game, immersive video game techniques from chapter **2.2.3** were utilised. First of all, a first-person camera perspective was implemented, which theoretically can make the players feel as if they are part of the game world. Secondly, additional interactable points of interest were scattered throughout the level, highlighted by green floating orbs, such as talkable NPCs, playable piano and guitar, as well as others, making the world feel ‘alive’. Thirdly, non-scary diegetic and transdiegetic ‘effect’ and ‘zone’ sounds were implemented across all areas with ambience and control-related functions to provide audiovisual synchronicity. These sounds include but are not limited to, footsteps, which react to different materials, plus pick-up sounds, teleportation audio cues, the hum of air conditioning units, wind, the buzz of flies and many others. Also, all of these sounds are processed by a reverb plugin, which changes its parameters depending on the player's location, thus making the soundscape sound more ‘realistic’. The above-mentioned tactics should at least engross the player, and at best provide total immersion.

Additionally, a great deal of attention was given to the visual and aesthetic fidelity of the game in order to make it reminiscent of survival horror games in order to “encourage any negative player valence to be fear-related” (Garner, Grimshaw and Nabi, 2010). Each area was composed of 592 manually placed props, particle effects and light sources in order to create a visual mood and atmosphere, similar to titles such as Left 4 Dead (Valve, 2008) and Observer (Bloober Team, 2007). To further enhance the visual quality and set a darker mood, the game was set at night (see Figure 3.3).

**Figure 3.3** Exemplary screenshot of the game visuals.

The controls used to move the avatar were adopted from a typical first-person shooter layout designed for a PC keyboard and mouse. This was done to ensure “gameplay accessibility” (Garner, Grimshaw and Nabi, 2010). While a gamepad might have been a more suitable choice for providing immersion, as players can regulate the movement speed using the analogue sticks, these types of peripherals are much harder to adapt to for non-experienced players.

### **3.4 Sound Design and Implementation**

A total of 42 unique audio events were created in FMOD Studio (see Figure 3.4), composed of 334 unique sound effects, which were designed and edited in Steinberg Nuendo 12 (see _Appendix B_ for additional screenshots). The number of designed sound effects greatly exceeds the number of events to make sure that the players do not experience “listening fatigue through repetition” (Jacobsen, 2018) of sounds, which may potentially ruin immersion. 8 C# Unity scripts were written in order to dynamically trigger sounds in the game (see _Appendix C_ for a GitHub link and exemplary scripts).

**Figure 3.4** FMOD Studio project.

In order to test the effectiveness of selected sound design techniques in inducing fear, anxiety and suspense, _Area 1_ consisted only of non-scary sounds which were made to immerse the player into the game world and were present in all other levels. In the test, this area served as a reference point for base levels of anxiety, suspense and fear, which values were compared to other areas.

_Area 2_ tested the technique of _unpleasant_ sounds. In order to do so, a dynamic non-linear multilayered musical piece was composed in Bitwig Studio. It consisted of highly dissonant, atonal and unpleasant orchestral phrases, drones and other layers, similar to music in Dead Space (Visceral Games, 2008). It later was implemented into FMOD Studio and integrated into the game (see _Figure 3.5_). The music would dynamically change in timbre, volume and intensity, becoming more unpleasant, based on the location of the player throughout the level.

**Figure 3.5** Music integration in FMOD Studio.

_Area 3_ tested the technique of _‘sudden effect’_. 3 high-volume sound effects would be triggered when the player walked past a dumpster in the alleyway ( a localised loud bang followed by menacing laughter, designed to sound like it was coming from a dumpster) (see _Figure 3.6_); when picking up a plus sign next to a house (a loud female scream); when exploring the room in the house (a flock of crows suddenly flying away accompanied by a transient low bass tone). These sounds were implemented in a way to catch players off guard, as this is the only area where these sounds are triggered.

**Figure 3.6** FMOD event for one of the jumpscares.

_Area 4_ tested the _ambiguity_ technique. Using FMOD’s Scatterer Instrumen (see _Figure 3.7_), which randomly triggers sounds at different coordinates in the game world (using panning, volume and other parameters), acousmatic sounds of rustling, screeching, door knocks, wall bangs, menacing laughter, kid screams and others were implemented. They would be randomly triggered at different locations, constantly changing their perceived location in the acoustic space, making sounds ambiguous. All sounds were played at medium or low volume. It is important to note, that this FMOD plugin does not utilise binaural processing.

**Figure 3.7** FMOD event for one of the ambiguous sounds.

_Area 5_ combined all of the above-mentioned techniques, with slight alterations to the location of triggers for jumpscares as well as some other changes, to make the audio mix less cluttered.

The game’s audio was mixed to follow the ASWG-R001 standard, which requires the game audio to be normalized to an average “target level of -24 (±2) LKFS” (LUFS) and “not exceed -1 dBTP” (dB True Peak) (Audio Standards Working Group, 2013) measured over the playthrough. According to the FMOD Studio _Loudness Meter_ plugin, the average loudness value was -23.2 LUFS integrated, with the loudest sounds (jumpscares) reaching -9 LUFS short-term.