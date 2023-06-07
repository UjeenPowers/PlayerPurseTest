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

## Configuring the Plugin
To change the method of saving purse data, you can modify the StoreMethod in PlayerPurseSettings. Follow the steps below:

Open the PlayerPurseSettings scriptable object.
Locate the StoreMethod field and choose the desired method of storing purse data.
There are four predefined store methods available:

1. PlayerPrefs: This method saves the data to the Unity PlayerPrefs system. Please note that this method has limitations defined by the device being used. If you plan to store a large set of data, it is recommended to use one of the latter methods.

2. JsonText: This method saves the data as a readable .txt file.

3. JsonBin: This method saves the data as a binary file.

4. Server: This method is not yet implemented but is intended to send data to a server.

If you choose the simple method of instantiation, you can find the appropriate scriptable object by following the link provided in the prefab.
