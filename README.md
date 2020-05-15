# ParrelSync 
[![Release](https://img.shields.io/github/v/release/314pies/ParrelSync?include_prereleases)](https://github.com/314pies/ParrelSync/releases) [![License](https://img.shields.io/badge/license-MIT-green)](https://github.com/314pies/ParrelSync/blob/master/LICENSE.md) [![PRs Welcome](https://img.shields.io/badge/PRs-welcome-blue.svg)](https://github.com/314pies/ParrelSync/pulls) [![Downloads](https://img.shields.io/github/downloads/314pies/ParrelSync/total)](https://github.com/314pies/ParrelSync/releases) [![Downloads](https://img.shields.io/discord/710688100996743200)](https://discord.gg/TmQk2qG) 

ParrelSync is an Unity editor extension allow user to open several Unity editor instance of the same project. Which is very handy when it comes to multiplayer testing.  
<br>
![ShortGif](https://raw.githubusercontent.com/314pies/ParrelSync/master/Images/Showcase%201.gif)
<p align="center">
<b>Convenient miltiplayer testing: 
   Test multi-player gameplay without building the project
</b>
<br>
</p>

## Installation 
To install *ParrelSync*, download .unitypackage from the [latest release](https://github.com/314pies/ParrelSync/releases) and import it to your project.  
Parrel Sync should appreared in the menu item bar.

***Note:*** 
*It's always recommend to backup the project folder before importing ParrelSync.*

## Supported Platform
Currently, ParrelSync only support Windows editor.  
Please create a [feature request](https://github.com/314pies/ParrelSync/issues/new/choose) if you want Mac/Linux support to be added. 

ParrelSync has been tested with the following Unity version. However, it should also work with other versions as well.
* *2019.3.0f6*
* *2018.4.22f1*


## APIs
Except the handy UI interface, there's also some useful API for speeding up the multiplayer testing process.

Here's a basic example: 
```
if (ClonesManager.IsClone()) {
  // Connect to localhost if running in cloned editor
}
```
Check out [the doc](https://github.com/314pies/ParrelSync/wiki/List-of-APIs) to view the APIs list.

## How does it work?
ParrelSync linked clone's ```Asset```, ```Packages```, ```ProjectSettings``` folder to the  original project by creating a  [symbolic link](https://docs.microsoft.com/en-us/windows-server/administration/windows-commands/mklink), so that the cloned instance can refer back to the original folder and keep all the asset "sync".  Serialization and saving are also blocked on the cloned instance for proecting the original assets.
All cloned projects are be placed right next to the original project with suffix *"_clone"*. You should see something like this in the folder hierarchy. 
```
/ProjectName
/ProjectName_clone_0
/ProjectName_clone_1
...
```
## Discord Server
We have a [Discord server](https://discord.gg/TmQk2qG).

## Need Help?
Some common question and troubleshooting can be found under the [Troubleshooting & FAQs](https://github.com/314pies/ParrelSync/wiki/Troubleshooting-&-FAQs) page.  
You can also [create a question post](https://github.com/314pies/ParrelSync/issues/new/choose), or ask on [Discord](https://discord.gg/TmQk2qG) if you want a have some real-time conversation.

## Support this project 
A star will be appreciated :)

## Credits
This project is based on hwaet's [UnityProjectCloner](https://github.com/hwaet/UnityProjectCloner) , with bugs fixed and many more features added.
