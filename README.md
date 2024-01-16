# Photon Tutorial

Why use Multiplayer? Well to make your games fun of course! 
You need to make your players want to play and multiplayer
is a way to do this.

This tutorial will outline how to use Photon PUN and how to get it working within Unity.

In this tutorial, you will learn how to:
* Setup Photon PUN 2.
* Make multiplayer work for your game.
* Expand for future requirements.

## Before you start

Prerequisites

Make sure that:
- You have a Photon Account
- You have a Unity Account.

## Part 1 - Setting Up

In part 1, you will set up Photon for Unity Development

1. Go to [Unity Asset Store](https://assetstore.unity.com/packages/tools/network/pun-2-free-119922)
   and add it to your assets.

2. Open the package manager in the Unity Editor, then extract and import it.
3. It will ask you for an App ID, which is what you will learn what to do in Part 2, DO NOT CLOSE THAT TAB.

## Part 2 - Photon

This is the second part of the tutorial:

1. Go to [Photon PUN 2](https://www.photonengine.com/pun)
and create a Photon PUN 2 project. 
2. Copy the App ID and paste into your Unity Project that Photon created a popup for.

## Part 3 - Connect to your Photon PUN 2 Server
In this part, you will connect to the server to be able to join and interact with servers.

1. Create a new c# class called `ConnectToServer.cs` and in a new scene called `Initialising` (which should be at build index 0), create an empty gameObject called `ConnectToServer`
2. Put in this code.
```
using System.Collections;
using System.Collections.Generic;
using UnityEngine;
using Photon.Pun;
using UnityEngine.SceneManagement;

public class ConnectToServer : MonoBehaviourPunCallbacks
{
    private void Start()
    {
        PhotonNetwork.ConnectUsingSettings();
    }

    public override void OnConnectedToMaster()
    {
        PhotonNetwork.JoinLobby();
    }

    public override void OnJoinedLobby()
    {
        SceneManager.LoadScene("Lobby");
    }
}
```
3. This code uses Photon's inbuilt `MonobehaviourPunCallbacks` class to connect you to the server as the game opens.
4. In the `OnJoinedLobby` method, change the whatever your "Main Menu" is called.
5. You can add text in the `Initialising` scene so the player does not feel like the game is doing nothing.

## Part 4 - Create And Join Rooms

In this part, you will be able to create and join rooms with your game.

1. Create a new c# class called `CreateAndJoinRooms.cs` and attach it to an Empty gameObject called `CreateAndJoinRooms` in your main menu.
2. Put in this code.
```
using System.Collections;
using System.Collections.Generic;
using UnityEngine;
using UnityEngine.UI;
using TMPro;
using UnityEngine.Windows;
using Photon.Pun;

public class CreateAndJoinRooms : MonoBehaviourPunCallbacks
{
public TMP_InputField createInput;
public TMP_InputField joinInput;

    public void CreateRoom()
    {
        PhotonNetwork.CreateRoom(createInput.text);
    }

    public void JoinRoom()
    {
        PhotonNetwork.JoinRoom(joinInput.text);
    }

    public override void OnJoinedRoom()
    {
        PhotonNetwork.LoadLevel("GameTestScene");
    }
}
```
3. This code uses Photon's inbuilt `MonobehaviourPunCallbacks` class to use their methods.
4. Assign the createInput to a TextMeshPro InputField and the joinInput to another one.
5. The createInput field will allow the Player to create a code that anyone can use to Join a lobby with. Same thing 
with the join input.
6. Change the name of the `GameTestScene` to whatever your Game Scene is.

## Part 5 - Instantiate the player's to the server scene.
This part wil allow the player to connect to a room and appear in it. 

1. In the `GameTestScene` ensure there are no Player gameObjects in there (make a prefab)
2. Create an empty gameObject called `SpawnPlayers` with the following code.
```
using System.Collections;
using System.Collections.Generic;
using UnityEngine;
using Photon.Pun;

public class SpawnPlayers : MonoBehaviourPunCallbacks
{
    public GameObject playerPrefab;

    public float minX, maxX, minZ, maxZ;



    void Start()
    {
        
        if (PhotonNetwork.IsConnected)
        {
            Vector3 randomPosition = new Vector3(Random.Range(minX, maxX), 1, Random.Range(minZ, maxZ));
            PhotonNetwork.Instantiate(playerPrefab.name, randomPosition, Quaternion.identity);

        }
    }

}
```
3. This script instantiates the player within the coordinate bounds minX, maxX, minZ and maxZ.
4. In the inspector assign the playerPrefab and assign the bounds.
5. This code can also be modified to work with items if wished.
6. Add A `PhotonView` component to your player and any server connected item. Also, add a `PhotonTransformView` and a `PhotonRigidbodyView`
if it has physics or moves.


## Part 6 - Fix The Bugs
If your game has multiple people with multiple cameras in the scene at once then this part is essential.
1. Create a c# class called `IsThisMine.cs` and put this simple code in it.
```
using System.Collections;
using System.Collections.Generic;
using UnityEngine;
using Photon.Pun;

public class IsThisMine : MonoBehaviour
{
    // Check if the item is owned by the local character
    // If it is, disable the item.
    private PhotonView photonView;

    private void Awake()
    {
        photonView = GetComponentInParent<PhotonView>();
    }
    private void Start()
    {
        if (photonView.IsMine == false)
        {
            this.gameObject.SetActive(false);
        }
    }

}
```
2. It simply checks for whether your local computer actually owns the component it is trying to control.
and if it does not, then it will set it to inactive locally.

### More things to add.
To all movement or related classes that need to be controlled locally, but have an effect on the server (like movement) add this simple if statement to fix it.
1. Make sure that you have a reference to the `PhotonView` of your gameObject.
```
public PhotonView photonView;
```
2. Then, add this code in methods (e.g moving)
```
if (photonView.IsMine) 
{
   // Put the method in here like the actuall movement script.
}
```

## What you've learned {id="what-learned"}

* In this tutorial you have learnt how to setup Photon PUN 2. 
* You have learnt how to put multiplayer into your game
* You have learnt how to sync characters across a server.

<seealso>
https://doc.photonengine.com/pun/current/getting-started/pun-intro
</seealso>
