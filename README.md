# PlayerPurseTest

PlayerPurseTest is a small Unity plugin designed to help you store and interact with player currencies in your Unity projects.

## Installation Instructions

1. Download the provided `.unitypackage` file.
2. Import the package into your Unity project by selecting "Assets" → "Import Package" → "Custom Package" in the Unity Editor.
3. Locate the downloaded `.unitypackage` file and follow the prompts to import the package.

## Usage Guide

To start using PlayerPurseTest, follow these steps:

1. Instantiate a plugin in your project using one of the following methods:

    a. Simple Way:
    - Add the prefab called "PlayerPurse" from the plugin directory to the first scene of your project.
    - You can then access the purse from anywhere in your project by using `PlayerPurseBridge.PlayerPurse`.

    b. More Appropriate Way:
    - Instantiate an instance of the `PlayerPurse` class in your project.
    - Run the `Initialize` method with a `PlayerPurseSettings` scriptable object to configure the purse, the scriptable object can be found in the plugion directory,
    but you are free to copy or move as needed.

2. The main interface for interacting with the PlayerPurseTest plugin is defined as follows:

{
    
    void SaveState(); //Saves current state of a purse using selected method form settings
    
    void LoadState(); //Loads state of a purse using selected method from settings
    
    int GetEntry(string id); //Returns a value of entry with id, if entry is not found returns 0
    
    void SetEntry(string id, int value); //Create or rewrite an entry with specified id
}

## Configuring the plugin
In order to change the method of saving purse data you should change the StoreMethod in PlayerPurseSettings.
If you choose the simple method of instantiation the appropriate scriptable object can be found by following the link in prefab.
There are 4 possible store methods predefined currently:
    1. PlayerPrefs - saves the data to player prefs, this method have some limits that are defined by the used device. If a large set of data is planned to be stored i recommend to use one of the latter methods.
    2. JsonText - saves the data as a readable .txt file.
    3. JsonBin - saves the data as a binary file.
    4. Server - not yet implemented, supposed to send data to a server.
