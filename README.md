# Play chiptune (mod, s3m, it, xm files) on C# 

### 1. Import these in your main form
```
using System.IO;
using Un4seen.BassMOD;
```

### 2. Code for music to play in form load
```
string systempath;

systempath = Environment.SystemDirectory;
if ((File.Exists((systempath + "\\bassmod.dll")) == false)) {
  File.WriteAllBytes((systempath + "\\bassmod.dll"), YOURRESOURCE.BassMOD);
}

BassMOD.BASSMOD_Init(0, 44100, BASSInit.BASS_DEVICE_DEFAULT);
BassMOD.BASSMOD_MusicLoad(YOURRESOURCE.music, 0, 0, BASSMusic.BASS_MUSIC_LOOP);
BassMOD.BASSMOD_MusicPlay();
```


### Code for button stop music
```
BassMOD.BASSMOD_Free();
BassMOD.BASSMOD_MusicStop();
```
### Code for button play music
```
BassMOD.BASSMOD_Init(0, 44100, BASSInit.BASS_DEVICE_DEFAULT);
BassMOD.BASSMOD_MusicLoad(YOURRESOURCE.music, 0, 0, BASSMusic.BASS_MUSIC_LOOP);
BassMOD.BASSMOD_MusicPlay();
```
