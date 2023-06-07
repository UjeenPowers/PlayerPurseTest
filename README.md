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
    - You can then access the purse from anywhere in your project by using `PlayerPurseBridge.PlayerPurse` statically.

    b. More Appropriate Way:
    - Instantiate an instance of the `PlayerPurse` class in your project.
    - Run the `Initialize` method with a `PlayerPurseSettings` scriptable object to configure the purse.

2. The main interface for interacting with the PlayerPurseTest plugin is defined as follows:

public interface IPlayerPurse
{
    void Initialize(PlayerPurseSettings playerPurseSettings);
    
    void SaveState(); //Saves current state of a purse using selected method form settings
    
    void LoadState(); //Loads state of a purse using selected method from settings
    
    int GetEntry(string id); //Returns a value of entry with id, if entry is not found returns 0
    
    void SetEntry(string id, int value); //Create or rewrite an entry with specified id
}
