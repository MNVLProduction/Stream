# MNVL OBS Documentation

# Introduction

This document is designed to explain all of the parts necessary for running an MNVL stream on the fairly customized OBS setup we use. It will include necessary plugins, files, and settings, along with a general list of all the graphics, with relevant links where applicable. Good luck.

# Files

Files will typically be stored in our [Google Drive](https://drive.google.com/open?id=1cNF68wn-kXjlx2QH5dtkShpefhH7IOFY). All files should be here. That being said, school logos as well as code will be stored on Github. There are two Github organizations for MNVL, one for [Development](https://github.com/MNVLDev) and one for [Stream Files](https://github.com/MNVLProduction). These should be tracked through time and updated accordingly.

# Dependencies

## OBS plugins

- [Audio monitor](https://obsproject.com/forum/resources/audio-monitor.1186/)  
- [Move transition](https://obsproject.com/forum/resources/move.913/)  
- [Transition Table](https://obsproject.com/forum/resources/transition-table.1174/)  
- [Advanced Scene Switcher](https://obsproject.com/forum/resources/advanced-scene-switcher.395/)  
- [SceneTree](https://obsproject.com/forum/resources/scene-tree-folder-plugin-for-obs-studio.1500/)\*  
- [Source Plugin](https://obsproject.com/forum/resources/source-copy.1261/)


\* Known to be unstable, can cause errors. Not strictly necessary (but very helpful)

## Applications

- [VLC (64Bit)](https://www.videolan.org/vlc/)  
- SADI (Custom spreadsheet program)  
- [Virtual Audio Cable](https://vb-audio.com/Cable/)

## Services

- [VDO Ninja (Web app)](https://vdo.ninja/)  
- [Restream](https://restream.io/)  
- Google Spreadsheets

# File Structure

While your file structure is a personal choice, keeping the same file structure as other producers will help immensely with sharing, troubleshooting, and keeping track of your files. The file structure should be the same as downloading the folder directly from the drive. This should be:

- MNVL  
  - Stream  
    - Casters  
    - Game  
      - RL  
      - VAL  
      - LOL  
      - FN  
      - SSBU  
      - MC  
      - …  
    - Break  
    - Sponsors  
      - Videos  
      - Graphics

# OBS Configuration

## Settings

This section refers to all the necessary changes in the OBS Settings menu, accessed by clicking Settings under Controls or navigating to File-\>Settings. If a setting is not listed, its default is fine and it does not need to be changed.

### Stream

| Setting | Value |
| :---- | :---- |
| Service | Restream.io |

### Output

| Setting | Value |
| :---- | :---- |
| Output Mode | Advanced |
| Video Encoder | NVIDIA NVENC H.264 or AMD |
| Rescale Output | Disabled |
| Bitrate | 4000 Kbps \- 8000 Kbps |

### Audio

| Setting | Value |
| :---- | :---- |
| Desktop Audio | Disabled |
| Mic/Aux Audio | Disabled |
| Monitoring Device | YOUR HEADPHONES |

### Video

| Setting | Value |
| :---- | :---- |
| Base Resolution | 1920x1080 |
| Output Resolution | 1920x1080 |
| Common FPS Values | 59.94 \- 60 |

### Advanced

| Setting | Value |
| :---- | :---- |
| Stream Delay | Enable \- Disable |
| Duration | 90s-180s |

## Tools

This section refers to all the configuration necessary under the Tools button in the top menu bar. This section will include configuration for plugins included in the OBS Tools menu. Not all plugins will be configured here, so refer to the specific plugin documentation for more info.

### Websocket Server Settings

| Setting | Value |
| :---- | :---- |
| Enable WebSocket Server | Enabled |
| Server Port | 4455 |
| Server Password\* | obswsserver |

\* The server password is set to obswsserver due to certain MNVL-specific tools depending on this password. This is subject to change. To enter a new password, select the dots and type it directly into the Server Password input box. To verify the password, click Show Connect Info

### Advanced Scene Switcher

TODO

## Docks

### Enabled Options

This section lists the docks/dock options you should enable under the Docks menu. All of the other docks that aren’t listed can be left at their default. 

- Full-Height Docks  
- Audio Monitor  
- Scenetree

### Custom Browser Docks (VDO.Ninja)

In order to integrate VDO.Ninja into your OBS instance directly, select **Custom Browser Docks** in the Docks menu. Name your VDO dock “VDO.Ninja”, and set the url to the director view of your VDO room. This will look something like “[https://vdo.ninja/?director=MNVL](https://vdo.ninja/?director=MNVL)”. This will open a custom browser dock with your VDO director view, and allow you to manage VDO from there. For info on managing VDO, refer to the VDO documentation later in this document.

## Misc

### Display OBS Virtual Camera in VDO.Ninja browser dock

OBS does not support this natively. In order to enable this function, find the shortcut you use to open OBS, right-click on it and click **Properties**. In the **Target** field, after the file path and outside of the quotations, add **\--enable-media-stream**. This will allow you to use your OBS virtual cam inside of your VDO.Ninja Dock

### Enable zooming on the OBS canvas

To zoom on the OBS canvas, right-click on the canvas, outside of the viewport. Hover over **Preview Scaling**, and select **Canvas (1920x1080)**. This will allow you to zoom and pan the canvas by holding space and clicking/scrolling.

# OBS Scene Collection Setup

This section describes how to set up and configure your Scenes and Sources. Maintaining a Scene setup that is the same as your other producers has all the same benefits as doing it for files. Essentially, it is very helpful. This includes Scene names, settings, Source names, Source settings, actions, and automations.

## Scenes

Scenes are the essential building block of OBS, and describe how your stream looks at any given time. Having a solid scene setup will make your streams easier, smoother, and look better.

### Scene Structure

This section refers to both scene names, as well as a scene structure that may be created by Scenetree. Even without Scenetree, maintaining good names and an organized structure is incredibly important for keeping your streams easy and mistake-free. The recommended scene structure looks something like:

- Main  
  - Starting  
  - StartingVideo  
  - Casters  
  - CastersInterview  
  - CastersL3  
  - Game  
  - BreakVideo  
  - Break  
  - Ending  
- Nested Scenes  
  - CasterGraphics  
  - CasterInterview  
  - UpcomingGames  
  - SeasonStandings  
  - GameOverlay  
  - SponsorGraphics  
  - …

### Nested Scenes

**Nested Scenes** are one of the most important concepts to master in OBS. Nested Scenes function as groups of scenes that you can manage under one source. OBS’s actual Groups have a number of issues and should not be used, but Nested Scenes will come to your rescue. 

To create a Nested Scene

### Scene Transitions