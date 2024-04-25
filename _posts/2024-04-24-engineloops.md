---
layout: post
title: "Engine Loop Creation using Pyrespeeder and iZotope RX"
slug: engine-loop-creation
date: 2024-04-24
description: Learn how to create engine loops yourself!
---
<hr class="dotted-line">
<h2><mark style="background-color: lightgrey;">Engine Loop Creation using Pyrespeeder and iZotope RX</mark> </h2> 
<hr class="dotted-line">

_Massive thank you to my collegue and friend_ **Tyoma Makeev** _for introducing me to Pyrespeeder. This guide would not be here without him, so please go check out his_ [website](https://tyoma.io/)!

<img src="https://i.redd.it/b0kkctsxlpa41.jpg" alt="RPM formula" width="100%">

Design and implementation of a good sounding vehicle is very difficult. The sound of a car consists of a myriad of layers such as the engine itself (engine and exhaust), turbo, tyres, suspension, etc.. All of them need to work well together, react to the player's input and game’s simulation. Making matters worse, there is barely any available information online. Each of these building blocks can be studied in extreme depths, but in this blog post I would like to shine a light on a way of creating engine loops without the use of game-ready granular synths such as REV by CrankcaseAudio 

Before I continue, I would like to warn you that this process is not ideal, and has its own setbacks (such as being time consuming).

<hr class="dotted-line">

<h1><mark style="background-color: lightgrey;">Tools</mark> </h1>

<hr class="dotted-line">

Okay then! First of all, I would like to provide a list of necessary software (some of it open source and free, some of it is paid).

1. Your DAW of choice (I use Reaper) (paid or free)
2. iZotope RX 10 (paid/ subscription)
3. [Pyaudiorestoration](https://github.com/HENDRIX-ZT2/pyaudiorestoration) (open source and free)
4. IDE with Python support (I use PyCharm)

<hr class="dotted-line">

<h1><mark style="background-color: lightgrey;">Source</mark> </h1>

<hr class="dotted-line">

After obtaining all the necessary software, it is time to find an engine recording. It is best to use _ramp_ type recordings, as they consist of all the RPMs of an engine both onload (throttle engaged) and offload (throttle disengaged). For this blog, I will be using a Mitsubishi exhaust take from _Soundly_. 

<img src="/media/EngineLoops/WaveformRamp.jpg" alt="WaveformRamp" width="100%">

After the files are obtained, put these recordings into your DAW and start chopping up your audio into small sections or create regions for rendering later on (I prefer regions). Make sure to pay attention to the frequency contents of the chops you are making and try to make sure the response does not change too much, as it can lead to problems further on.

After the choppage is done, bounce the resulting files (do not forget to name them!) and proceed to the next step. I will be using only one snippet of the recording for demonstration purposes.

<hr class="dotted-line">
<audio controls>
  <source src="/media/EngineLoops/Original.wav" type="audio/wav">
  Your browser does not support the audio element.
</audio>
<p style="font-size: 12px; text-align: center;">Extracted snippet of the recording</p>
<hr class="dotted-line">



<hr class="dotted-line">

<h1><mark style="background-color: lightgrey;">Pitch Flattening</mark> </h1>


**[Pyaudiorestoration](https://github.com/HENDRIX-ZT2/pyaudiorestoration)** has a great little module called **pyrespeeder**. It was mainly developed to remove wow and flutter from vinyl recordings (by adjusting sample rate to keep the pitch stable) but it turns out that it is a great tool for engine loop creation. 

Load one of your files (_by the way you can load multichannel audio, so make sure to use this feature by writing all the mic positions into one sound file!_). Set all the settings as seen on the screenshot, zoom in into the fundamental frequency (or any other prominent stable harmonic) and draw a line on it by dragging your mouse while holding Ctrl. **Wa-bang!** Pyrespeeder has detected the frequency changes. Press Ctrl+R and the processed file will be rendered. Rinse and repeat for all the files.

<img src="/media/EngineLoops/PseepdSettings.jpg" alt="PseepdSettings" width="100%">

<audio controls>
  <source src="/media/EngineLoops/PitchFix.wav" type="audio/wav">
  Your browser does not support the audio element.
</audio>
<p style="font-size: 12px; text-align: center;">Processed file from Pyrespeeder, notice pitching noise</p>
<hr class="dotted-line">




While writing this blog post I have found out that **iZotope RX 10 Advanced** is capable of doing the exact same thing as [Pyaudiorestoration](https://github.com/HENDRIX-ZT2/pyaudiorestoration) by utilising **Wow & Flutter** module set to Wow with _Wow rate_ set to **slow**. While this is a game changer for me, you cannot get this module in standard edition available by subscription. But if you have access to this software, use this method instead. 
 
<hr class="dotted-line">

<h1><mark style="background-color: lightgrey;">Loop Creation</mark> </h1>

<hr class="dotted-line">

After all the files are processed, you might have noticed that the upper spectrum noise is behaving weird. This is one of the biggest downsides of this method (not present when using RX 10 Wow and Flutter). This happens due to the fact that noise is static in pitch (_duh_). In order to fix this, get the noise layer from the unprocessed file and combine it with a flattened one by using EQs. This is now fixed!

<img src="/media/EngineLoops/EQs.jpg" alt="PseepdSettings" width="100%">

<audio controls>
  <source src="/media/EngineLoops/FixedPitchAndNoise.wav" type="audio/wav">
  Your browser does not support the audio element.
</audio>
<p style="font-size: 12px; text-align: center;">With noise layered on top</p>
<hr class="dotted-line">

Now, it is time to learn about looping techniques. First one is the **reverse method**. Copy paste the audio file and reverse it. Trim the items at their zero crossing file and invert the phase if needed. Don’t waste your time on trying to crossfade them (you can but it is a tedious process). Consolidate two files together and open them in RX. Use the Spectral Repair module in replace mode to patch the loop point. This usually works. If it doesn't - play with other modules such as de-click.

<img src="/media/EngineLoops/ReverseLoop.jpg" alt="ReverseLoop" width="100%">

The second one is **cutting the file in the middle at a zero crossing** and moving the left side to the right. Again, do not crossfade them and use RX in the way described above.

Put the final file into the RX again and use Spectral repair to fix weird and uneven frequencies. 

<img src="/media/EngineLoops/FinalLoopRX.jpg" alt="FinalLoopRX" width="100%">

<audio controls>
  <source src="/media/EngineLoops/Loop.wav" type="audio/wav">
  Your browser does not support the audio element.
</audio>
<p style="font-size: 12px; text-align: center;">Wowzers, just listen to this loop!</p>
<hr class="dotted-line">


**Congratulations!** You have created a stable engine loop ready for implementation. 

<hr class="dotted-line">

<h1><mark style="background-color: lightgrey;">Recommendations and Further Reading </mark> </h1>

<hr class="dotted-line">


After you have processed all files, you need to find the RPM of the loop. Use this [article](https://medium.com/analytics-vidhya/using-exhaust-sound-recordings-to-calculate-engine-rpm-93d54d8a1010) to help you calculate it based on the fundamental frequency. 

The implementation of engine loops in Wwise is superbly explained by Arto Koivisto in this [blog](https://blog.audiokinetic.com/en/loop-based-car-engine-design-with-wwise-part-2/).

Engine loops are only a starting point for creating a good sounding car engine. If the vehicle physics in your game do not realistically simulate engine RPMs, you might have to create transmission, wobble and rev limiter logic yourself. Do not ignore this, as otherwise the engine will sound boring and unrealistic. Also think about how suspension might affect the RPMs. This [blogpost](https://blog.audiokinetic.com/en/make-racing-engine-sound-based-on-rev2/) by Xu Wei is great learning material!

Additionally, I would recommend doing these things to make your car engine sound great!

- **Use the engine noise that we used in loop creation as a separate layer in your audio middleware**, with its volume driven by how hard the throttle is pressed. This way you gain more control on the sound design aspect of things.
- **Generate lower harmonic layers using additive synthesis** and mix them in your audio middleware. This will ensure that a) there are bass and sub frequencies always present; b) it just sounds better!
- Do not forget about **turbo and transmission whine**, blow offs, etc!
- Drive engine volume, high and low frequency EQ shelves by player’s speed to make the sound less fatiguing (_cars are loud and can get annoying quickly_!)
<p></p>

Have fun and good sound designing!

<hr class="dotted-line">