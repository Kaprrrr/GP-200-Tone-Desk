Valeton Tone Desk
Oct 2, 2026 · @Papa
GP-200 Tone Desk is a free community tool for the Valeton GP-200 multi-effects pedal. You describe a song, Claude suggests a patch built from your own SnapTone (NAM) captures, User IRs and the pedal's built-in models, and Tone Desk writes that patch to the pedal over USB and checks it saved correctly.
Overview
Tone Desk is for GP-200 players who want a song's tone on the pedal without dialing every block by hand. It runs entirely in Chrome or Edge on your computer, with no account, no server and no uploads. It is not affiliated with or endorsed by Valeton or Hotone.
Current releases: v1.2.6 for Mac (a single HTML page) and v1.2.5 for Windows (a pedal-icon .exe launcher). Both use the same patch encoder, unchanged since v1.2.4. Tested with GP-200 firmware 1.8.
Features
The app has four tabs: Songs, SnapTones, Pedal, and Backup & About.
Tab
What you do there
Songs
Create a song (title, artist, part, your guitar and pickup, notes), get a patch from Claude or build it yourself, then send it to a preset slot. Edit, re-ask Claude, copy as text, share or delete.
SnapTones
Keep a library of the captures and User IRs loaded in each slot: what each really is, where it came from, and the knob settings that suit it.
Pedal
Connect to the GP-200 over USB MIDI. Capture and IR slots are read automatically.
Backup & About
Export or restore a JSON backup of songs and library; check the installed version.
Other features:
• Claude patch suggestions. "Copy prompt" builds a prompt with your song, your SnapTones and IRs, and every GP-200 model. Paste it into claude.ai (a free account works) and paste the JSON reply back; the patch loads at once.
• Safe send. Each send backs up the destination preset, writes the full patch (every knob and on/off state), then reads it back to verify. "Undo last send" restores the original, which can also be downloaded as a .prst file.
• Song output level. A per-song slider (0 to 100) on the final VOL block for matching volumes between songs by ear.
• Sharing. Export a song as a file and import songs others share.
• Official editor fallback. Export a patch file for use with Valeton's own editor.
• Jump to preset. One click selects the preset a song is saved in.
How it works
Tone Desk is a single-page web app bundled into one self-contained HTML file. It talks to the pedal through the browser's Web MIDI API (SysEx), and stores songs, the capture library and the undo backup in browser storage. Nothing leaves your computer except the prompt you paste into Claude yourself.
The top row happens in the browser and claude.ai; the bottom row is the USB transfer. If the backup cannot finish, nothing is written. If a read stalls, Tone Desk reconnects once and retries the read without repeating a write.
Getting started
You need a GP-200 (tested on firmware 1.8), a USB cable, and Chrome or Edge. Safari, iPhone and iPad cannot talk to USB MIDI devices.
1. Unzip the folder anywhere, such as Desktop or Documents.
2. Plug in the GP-200 over USB and close the official GP-200 editor. Only one program can talk to the pedal at a time.
3. Open Tone Desk:
    ◦ Windows: double-click GP-200 Tone Desk.exe (the pedal icon). It opens Edge, or Chrome if Edge is missing.
    ◦ Mac: Control-click GP-200 Tone Desk.html and choose Open With > Chrome or Edge.
4. On the Pedal tab, click Connect to GP-200 and allow MIDI access when the browser asks.
5. Fill in your captures on the SnapTones tab, then add songs on the Songs tab.
6. Pick a song, choose a destination preset under Send to pedal, and click Send. Keep the pedal connected until "Saved and verified" appears. You do not need to press SAVE on the pedal.
The Windows launcher is not code-signed, so Windows may show an unknown-publisher warning on first launch.
What ships
Each release is a ZIP with one folder, GP-200 Tone Desk/, holding two files.
Package
App file
Size
Notes
Windows v1.2.5
GP-200 Tone Desk.exe
595 KB
Launcher with the pedal icon; keeps the page address stable between updates
Mac v1.2.6
GP-200 Tone Desk.html
480 KB
The whole app in one self-contained page; nothing to install or approve
Both include READ ME FIRST.txt with setup, safety and upgrade notes. The source project is not in this folder, only the built releases and screenshots.
Limitations and known issues
• Upgrade from 1.2.3 or earlier. Older versions mapped some parameters by display position, which could swap delay time and feedback and cause loud noise. v1.2.4 fixed this; an offline audit covered all 322 model entries and 1,400 parameters, but not every effect has been tested by ear. Resend affected songs and check them at low volume.
• Mac hardware transfers with the corrected encoder still need testing on a real Mac. Windows transfers have been tested.
• Tempo sync is not supported in generated patches. Songs with Sync switches on are rejected before sending.
• One undo backup. Only the preset from the latest send is kept; download it as .prst to keep it longer.
• Captures must already be on the pedal. SnapTone and User IR choices point at loaded slots; Tone Desk does not upload captures.
• Browser-only data. Songs live in that browser on that computer. Export a backup before clearing browser data, switching browsers or moving the Mac HTML file.
• Level matching is by ear. The output slider does not measure loudness.
Credits
• USB MIDI messages documented by the phash/gp200editor project.
• SnapTone notes (knob ranges, EQ frequencies) from the community "GP200 Missing Manual".
