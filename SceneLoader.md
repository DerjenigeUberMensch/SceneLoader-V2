# Scene Loader V2

[Insert Text Here]

## Basic Usage

1.

2.
3.

## SceneLoader

| Variable | Default Value | Description |
| ----------------------------------- |



// TODO
| Function   | Arg | Return | Description |
| ----------------------------------- |
| PreLoad()  | scene | | |
| Load()     | | | | 
| Unload()   | | | | 

static public SceneLoaderAsync Unload(string scene, bool UnloadReadyOnlyScene = false)
static public bool LoadScene(SceneLoaderAsync loader)
static public SceneLoaderAsync PreLoadScene(string scene)

## SceneLoaderAsync

| Variable     | Default Value | Description                                                                                                                         |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| LoadProgress | 0f            | Load Progress for the current running async operation, ranges from 0 to 100f where 100f is complete.                                |
| IsWaiting    | false         | Some operations may halt or be user set to halt, this tracks that, with true being a halting operation, false otherwise.            |
| WaitTime     | 0f            | Time to wait before starting the operation, this is for whoever needs that for whatever reason.                                     |


| Function     | Return | Description                                                                                                                                |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| IsConsumed() | bool   | Checks if the async operation was consumed by another Instance, this is useful for concurrent scene managment.                             |
| IsLoading()  | bool   | Checks if the async operation is still loading.                                                                                            |
| IsReady()    | bool   | Checks when the operation is ready to be consumed, via Load() this will be set to true, otherwise false, this is the same as !IsLoading(). |
| IsLoaded()   | bool   | Checks if the async operation has loaded in.                                                                                               |