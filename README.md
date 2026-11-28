# FlowTube

**FlowTube** is a Windows **freeware** desktop application that helps you browse YouTube using a controlled browser window, automatically detect and extract metadata from videos you open, and convert audio into trimmed, properly tagged, and artwork-embedded audio files.

> - **Download installer from **[FlowTube Webpage on itch.io](https://fk-software.itch.io/flowtube)**(`https://fk-software.itch.io/flowtube`):**
>     - Direct link to **[latest FlowTube Windows installer on itch.io](https://fk-software.itch.io/flowtube/purchase)** (`https://fk-software.itch.io/flowtube/purchase`).
> - **Download via the itch Desktop App:**
>     - Install the [itch Desktop App](https://itch.io/app)(`https://itch.io/app`).
>     - Search for **FlowTube** (by fk_software) inside the app and click **Install** (installs `flowtube-windows.zip`).
> - **Watch Trailer:** **[FlowTube Video Overview on Vimeo](https://vimeo.com/1149476776?fl=pl&fe=sh)**(`https://vimeo.com/1149476776?fl=pl&fe=sh`)
> - **Release Notes:** View full version history in [`CHANGELOG.md`](CHANGELOG.md).

<img width="1920" height="1080" alt="FlowTubeDescribed" src="https://github.com/user-attachments/assets/e5db9683-9ff7-41ee-867f-7befcd19ee1e" />

---

## Key Features
* **Multi-Browser Support (v1.5):** Works with Chrome, Brave, Firefox, Edge, and Safari via `app_config.ini`.
* **Manual Browsing & Auto-Detection:** FlowTube does not automate YouTube navigation—you browse manually, and FlowTube detects the video URL, title, channel, and artist only when you open a video.
* **3-Slot Queue System:** Manage, edit, and prepare up to three audio downloads simultaneously.
* **Automatic Metadata & Cover Art:** Searches free online databases for track tags and legally redistributable (e.g., Creative Commons) cover art, generates a local placeholder cover if none is found, or lets you paste custom artwork directly from your clipboard (`Ctrl + V`).
* **Precision Audio Trimming & Conversion:** Cut tracks down to the millisecond (start and end times), convert formats via FFmpeg, and embed ID3 tags and cover art automatically.

---

## How It Works

### 1. Browser Interaction
1. FlowTube launches a controlled browser window and opens YouTube.
2. You browse freely (you remain solely responsible for your browsing and download choices).
3. When you open a YouTube video, FlowTube automatically:
   * Detects the video URL, title, channel name, and artist name.
   * Combines them into a search query displayed in the FlowTube interface.
   * Searches free databases for matching album/track metadata and Creative Commons cover art (falling back to a locally generated placeholder if none is found).
<img width="959" height="418" alt="image" src="https://github.com/user-attachments/assets/36fa553a-6552-4ab6-8612-b837f67d4ad8" />

### 2. Top Toolbar Controls
* **REPLAY:** Opens Windows Media Player and plays FlowTube's download history.
* **CONFIG:** Opens `app_config.ini` so you can customize settings such as output file format or browser profiles. *(Restart FlowTube after saving changes.)*
<img width="1920" height="940" alt="image" src="https://github.com/user-attachments/assets/e62e2a01-b823-482f-a41f-010b07907a63" />


### 3. Download Slots (3 Available)
Each of the three download slots provides the following controls:
* **Filename Entry:** Sets the output filename (default format: `Artist - TITLE - Artist, feat,`) and acts as the search query for metadata lookups.
* **Metadata Entries:** Displays and lets you edit tags (`Track Title`, `Album`, `Artist`, etc.). The `No.` field sets the album track index (single integer).
* **Time Entries (`m`, `s`):** Trims the final audio from start to end time (supports milliseconds).
  * **Left (West) inputs:** Start time (`m`, `s`).
  * **Right (East) inputs:** End time (`m`, `s`).
* **Search Button:** Searches free online databases using the Filename query and populates standardized metadata entries (falls back to the search argument if no match is found).
* **Image Button:** Searches free online databases for matching cover art based on Title, Album, and Artist. Downloads both the image and its license file if a free-licensed image is found, or generates a local placeholder cover.
  * **Clipboard Shortcut (`Ctrl + V`):** While the FlowTube window is focused, press `Ctrl + V` to paste an image directly from your clipboard as the slot's cover art.
* **Download Button:** Retrieves the audio via an external downloader, checks `app_config.ini` for your preferred output format, converts via FFmpeg, trims the audio, embeds ID3 tags and cover art, and writes the final file (and any cover license file) to your chosen output folder or the fallback directory (`/AppDataDir/downloader/loaded/`).

---

## Application Data Layout

### Installation Directory (`InstallDir/FlowTube/`)
```text
InstallDir/FlowTube/
 ├─ About.txt
 ├─ FlowTube.exe
 ├─ FlowTube_LICENSE.txt
 ├─ README.txt
 ├─ VERSION.txt
 ├─ data/
 │   ├─ static_media/          # Toolbar icons & placeholder artwork (*.png, *.ico)
 │   └─ downloader/
 │       └─ ffmpeg/            # Optional internal FFmpeg build (configurable in app_config.ini)
 ├─ _internal/                 # Internal application libraries & resources (*.dll, *.pyd, *.zip)
 └─ licenses/                  # Third-party dependency licenses (*.LICENSE.txt)
```

### Runtime User Data (`AppDataDir/` — created on first launch)
```text
AppDataDir/
 ├─ app_config.ini             # User configuration (browser choice, output format, paths)
 ├─ DTH.txt                    # Download history
 ├─ FlowTube_Browser_Profiles/ # Browser profile data (path configurable in app_config.ini)
 ├─ downloader/
 │   ├─ loaded/                # Fallback directory for final audio files
 │   └─ loads/                 # Temporary working directory (Cover_Art.png, License_Cover_Art.txt)
 ├─ logs/                      # Application logs (*Logs*.txt)
 └─ slots/                     # Cached thumbnails & metadata for Slot0, Slot1, and Slot2
```

---

## Third-Party Licenses & Credits
* **Dependencies:** FlowTube includes a `licenses/` directory containing all required third-party license files. This build uses **FFmpeg** and related libraries; corresponding licenses are located in `InstallDir/data/downloader/ffmpeg/`.
* **Startup Intro Music:** *"Blue Skies"* by Alegend — [Free To Use](https://freetouse.com/music) (Royalty-Free Music).

---

## License, Privacy & Legal Disclaimer

### FlowTube Freeware License
FlowTube is provided as **freeware** (`Copyright (c) 2026 Florian Knecht`). Redistribution is permitted **only in its complete, original, and unmodified form**. See [`LICENSE.txt`](LICENSE.txt) (`FlowTube_LICENSE.txt`) for full terms.

### Privacy Policy
Read the full FlowTube Privacy Policy here: **[FlowTube Privacy Policy](https://github.io)**

### Legal Note on Downloads
FlowTube provides tools for processing audio from internet sources and **does not verify copyright status or download legality**. It is the **user's sole responsibility** to ensure that any downloaded media complies with applicable copyright laws in their jurisdiction.

---

## Author & Contact
* **Author:** Florian Knecht
* **Email:** Florian.Knecht.Software@outlook.com
* **Official Page:** [fk-software.itch.io/flowtube](https://fk-software.itch.io/flowtube)
