# Streaming Assets\(old method\)

Unity copies any files placed in the folder called **StreamingAssets** \(case-sensitive\) in a Unity Project verbatim to a particular folder on the target machine. To retrieve the folder, use the [Application.streamingAssetsPath](https://docs.unity3d.com/ScriptReference/Application-streamingAssetsPath.html) property. It’s always best to use `Application.streamingAssetsPath` to get the location of the **StreamingAssets** folder, as it always points to the correct location on the platform where the application is running.

The location returned by `Application.streamingAssetsPath` varies per platform:

* Most platforms \(Unity Editor, Windows, Linux players, PS4, Xbox One, Switch\) use `Application.dataPath + "/StreamingAssets"`,
* macOS player uses `Application.dataPath + "/Resources/Data/StreamingAssets"`,
* iOS uses `Application.dataPath + "/Raw"`,
* Android uses files inside a compressed **APK** /JAR file, `"jar:file://" + Application.dataPath + "!/assets"`.

To read streaming Assets on platforms like Android and **WebGL**  
, where you cannot access streaming Asset files directly, use [UnityWebRequest](https://docs.unity3d.com/ScriptReference/Networking.UnityWebRequest.html). For an example, see [Application.streamingAssetsPath](https://docs.unity3d.com/ScriptReference/Application-streamingAssetsPath.html).

On many platforms, the streaming assets folder location is read-only; you can not modify or write new files there at runtime. Use [Application.persistentDataPath](https://docs.unity3d.com/ScriptReference/Application-persistentDataPath.html) for a folder location that is writable.

**Note**: .dll and script files located in the **StreamingAssets** folder don’t participate in the script compilation. 

