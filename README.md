# RTIViewerManifest
A simple manifest file for RTIViewer that will override system scaling in Windows 10 for high DPI displays

On some computers with High DPI displays the RTIViewer program doesn't scale up properly, leaving the buttons too small and the text no longer fits on them, as below:

![Non-scaled window](https://i.imgur.com/FZ7X5Ww.png)

To fix this we need to tell Windows 10 not to try and scale up the program intelligently, but to run it at its native resolution and magnify the whole thing. This may leave icons and text a little blurry, but it makes the program usable.
 
To do this we download the manifest file linked in this github project, then move this manifest file to the same place that you installed RTIViewer; usually `C:/Program Files/RTIViewer` by default.
 
Then we need to tell Windows to look for manifest files when opening programs. To do this we open regedit.exe by pressing the windows key, typing run, pressing Enter, typing `regedit`, and pressing enter. We then use regedit to find the registry subkey `HKEY_LOCAL_MACHINE > SOFTWARE > Microsoft > Windows > CurrentVersion > SideBySide` in the left sidebar, then right-click in the main window and select `New > DWORD (32 bit) Value`.

![regedit window](https://i.imgur.com/xHjOoqc.png)

Name this `PreferExternalManifest` then press enter, before right-clicking it and choosing Modify. Give it a decimal value of `1`, then press Okay and close regedit.
 
Now when you restart or reopen RTIViewer it should obey system scaling.

![Scaled window](https://i.imgur.com/MmCvlOW.png)
