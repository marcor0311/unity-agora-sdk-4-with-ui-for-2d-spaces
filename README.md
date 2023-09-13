# Unity Integration with Agora SDK 4 for 2D Spaces with UI

This tutorial will guide you through integrating the Agora SDK into your Unity project to create a 2D space with an interactive User Interface (UI) that supports real-time communication. This guide assumes you are using Unity version 2021.3.5f1 and Agora Video SDK for Unity version 4.2.2.

## Prerequisites

Before getting started, make sure you have the following:

- Unity 2021.3.5f1 installed.
- Agora Video SDK for Unity 4.2.2.
- Agora Account

## Project Setup

### 1. Create a Unity Project:

- Open Unity Hub, select "Projects," and click "New Project."
- Choose the 3D template and click "Create Project."
- Open your newly created project in Unity.

### 2. Integrate Video SDK:

- Add to your assets the latest Agora Video SDK for Unity from the [Unity Asset Store](https://assetstore.unity.com/packages/tools/video/agora-video-sdk-for-unity-134502).
- In Unity, go to "Window" > "Package Manager" > "My Assets."
- Find the Agora Video SDK, click "Download," and then "Import."

## Implement the User Interface

For your Unity game, you'll need to create a user interface with local and remote video views, as well as buttons for joining and leaving a channel.

### 1. Add Join and Leave Buttons:

- Right-click "Sample Scene" in the Unity hierarchy.
- Choose "UI" > "Canvas" to create an overlay for buttons and cameras.
- In the Canvas Inspector, set "Render Mode" to "Screen Space - Overlay" and "UI Scale Mode" to "Constant Pixel Size."
- Right-click the Canvas, select "UI" > "Button - TextMeshPro" to create buttons.
- Rename the first button to "Leave" and adjust its position (Pos X: -350, Pos Y: -172).
- Change the button's text to "Leave."
- Create a second button named "Join" and adjust its position (Pos X: -350, Pos Y: -172).
- Change the text of the "Join" button to "Join."

### 2. Add Local and Remote Video Views:

- Create a Raw Image for the local video by right-clicking the "Canvas," choosing "UI," and selecting "Raw Image."
- Rename it to "LocalView" and adjust its position and size (Pos X: -250, Pos Y: 0, Width: 250, Height: 250).
- Create another Raw Image for the remote video named "RemoteView" and position it accordingly (Pos X: 250, Pos Y: 0, Width: 250, Height: 250).

![canvas](https://github.com/marcor0311/unity-agora-sdk-4-with-ui-for-2d-spaces/assets/110083517/8a85b97e-d4eb-4ff7-a826-d034be056d2f)
![UIAgora](https://github.com/marcor0311/unity-agora-sdk-4-with-ui-for-2d-spaces/assets/110083517/14f70932-7a0e-42a4-bcd8-4123556092fb)

### 3. Script

The script is in this repository in "Code" > AgoraUnityUI.cs 

Simply add it to the canvas as a Component.
It is important that using your Agora Account you create an Agora project and fill these with the values generated in the Agora console.
```
// Fill in your app ID.
private string _appID = "";
// Fill in your channel name.
private string _channelName = "";
// Fill in the temporary token you obtained from Agora Console.
private string _token = "";
```

This user interface setup enables you to display local and remote video streams and control video calling interactions in your Unity game. The "LocalView" displays the local user's video, while the "RemoteView" shows the external user's video.
