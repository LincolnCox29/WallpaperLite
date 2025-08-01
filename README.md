# WallpaperLite-CLI

**Set videos as your Windows desktop wallpaper** using VLC's lightweight engine. Perfect for animated backgrounds with minimal resource usage.

```ascii
██╗    ██╗██████╗ ██╗
██║    ██║██╔══██╗██║
██║ █╗ ██║██████╔╝██║
██║███╗██║██╔═══╝ ██║
╚███╔███╔╝██║     ███████╗
 ╚══╝╚══╝ ╚═╝     ╚══════╝
```

## 📌 Features
- Hardware-accelerated video playback (DXVA2)
- Seamless desktop integration via `WorkerW` injection
- Loop playback with audio disabled
- Windows 10/11 support
- <300 LOC core implementation

## ⚙️ Requirements
- **Windows 10/11** (Build 22h2+)
- Video file in supported format (MP4, Webm, etc.)

## 🚀 Installation
1. Download latest release
2. Extract `wallpaperLite-CLI.exe` and `VLCmin` folder to same directory
3. Run via command line:
```bash
wallpaperLite-CLI.exe C:\path\to\your\video.mp4
```

## 🛠 Technical Implementation
```mermaid
graph LR
    A[CLI Launch] --> B[Find WorkerW]
    B --> C[Load VLCmin DLLs]
    C --> D[Initialize VLC Player]
    D --> E[Attach to Desktop]
    E --> F[Video Playback]
```

Key components:
- **WorkerW injection** for desktop integration
- **Dynamic VLC loading** via `LoadLibrary()`
- **HWND attachment** to desktop window
- **Minimal VLC runtime** (~15MB)

## 🐛 Known Limitations
- No volume control (audio disabled)
- Requires console window to remain open
- Single monitor support only
- No playback controls
