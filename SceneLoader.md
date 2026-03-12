# Scene Loader V2

[Insert Text Here]

## Basic Usage

1.

2.
3.

## SceneLoader

// TODO
| Function     | Args | Return | Description |
|--------------|------------------------------------------------------------------------|------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| PreLoad()    | Scene scene \| string sceneName \| int buildIndex, float waitTime = 0f | SceneLoaderAsync | Preloads a scene to be used in LoadScene(), it updates several variables in SceneLoaderAsync, and can be used to make load screens, or see when load it, etc...  |
| LoadScene()  | SceneLoaderAsync loader                                                |  bool            | Loads a scene, returns true if we sucessfully consumed the SceneLoaderAsync handler, false otherwise, if it returns false it is most likely that some other script consumed this token already, no side effects if passed in more than once. |
| Unload()     | Scene scene \| string scenenName \| int buildIndex, bool UnloadReadyOnlyScene = false     | SceneLoaderAsync | Unloads a scene |


## SceneLoaderAsync

| Function     | Args   | Return | Description                                                                                                                                |
|--------------|--------|--------|--------------------------------------------------------------------------------------------------------------------------------------------|
| IsConsumed() | N/A    | bool   | Checks if the async operation was consumed by another Instance, this is useful for concurrent scene managment.                             |
| IsLoading()  | N/A    | bool   | Checks if the async operation is still loading.                                                                                            |
| IsReady()    | N/A    | bool   | Checks when the operation is ready to be consumed, via Load() this will be set to true, otherwise false, this is the same as !IsLoading(). |
| IsLoaded()   | N/A    | bool   | Checks if the async operation has loaded in.                                                                                               |

| Variable     | Default Value | Description                                                                                                                         |
|--------------|---------------|-------------------------------------------------------------------------------------------------------------------------------------|
| LoadProgress | 0f            | Load Progress for the current running async operation, ranges from 0 to 100f where 100f is complete.                                |
| IsWaiting    | false         | Some operations may halt or be user set to halt, this tracks that, with true being a halting operation, false otherwise.            |
| WaitTime     | 0f            | Time to wait before starting the operation, this is for whoever needs that for whatever reason.                                     |
