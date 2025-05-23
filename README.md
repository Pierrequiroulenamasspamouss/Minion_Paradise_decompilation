# This project is im pause for the moment. Reason : University

# Minion_Paradise_decompilation
Have you ever tried to play that game to find it closed years ago ?

# Why
I recently discovered that I still had the app on my old phone, so I tried to launch it to see how the game was, because(of course) nostalgia, and was stuck on an endless "loading"

I know nothing about C# and unity projects, even less with compatible SDKs and android development, but knowing how easy it was to convert a unity project into an apk file, I thought I could try to find how the code works and remove that stupid request to aserver that shut down years ago, to maybe emulate that server or disable it's usage, because of what I remember, most of the game was played locally.

I decompiled the file with AssetRipper and gor a very promising sucess, knowing it is a unity built game.

# How
I'm trying too understand the inner workings of C# so I thougth that even if I don't succeed, either someone more competent could continue the work for me, or I would understand the inner workings of how the game works.

# What I currently discovered
- The game is made in Unity, and is compatible with Unity v5.3.5p4
- The project uses the Assets library FMOD (that has been customized)
- Even if the file `\ExportedProject\Assets\Scripts\Assembly-CSharp\Facebook\Unity\FacebookSdkVersion.cs` says the Facebook JDK is v7.6.0, it is not, since `ExportedProject\Assets\Scripts\Assembly-CSharp\Facebook\Unity\FB.cs` uses `using Facebook.Unity.Editor;` that is only available on SDK v6.2.2 and below (not supported on Facebook JDK 7.0.0 and up)
- There is an extra file to remove that conflicts with the unity version on location `ExportedProject\Assets\Plugins\Unity.dll` . This is the one you have to remove. 
- I cannot compile anything, because `Facebook.Unity.Editor` is currently not working.
- There is also an issue where the simple packages like `Directory.Delete(path2, true);` do not work, and I do not know why.

# What to do right now 
- Find a way to use the correct Facebook JDK, that would divide by four the number of compilation errors (most errors are related to that.)  

# The assets are already viewable if you want: 
- [Sounds]('https://placeholder.com') 
- [General assets]('https://placeholder.com')
- [Unity assets]('https://placeholder.com')
