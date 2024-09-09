<p align="center"><a><img src="learnyst.png"></a></p>
<h1 align="center" style="font-size: value;">Learnyst Downloader</h1>

## Requirements
+ [Python 3.12](https://www.python.org/)
+ [L3 CDM](https://forum.videohelp.com/threads/408031)

## Installation
+ Install the requirements: `python -m pip install -r requirements.txt`
+ Download and Install Playwright Chromium `playwright install chromium`
+ Place either the `mp4decrypt` or `shaka-packager` binary in the `bin` directory. Make sure they're named correctly.
+ Place either the `ffmpeg` or `mkvmerge` binary in the `bin` directory. Make sure they're named correctly.
+ Place your CDM in the `cdm` folder

## Usage
Enter your `authToken` cookie when first starting the program

> [!NOTE]  
> Enter the full URL, even if you're downloading PDFs, as they're not downloaded automatically along with the video.

```ruby
usage: python learnyst.py [-h] --url URL [--debug]

Author: github.com/DevLARLEY

options:
  -h, --help    show this help message and exit
  --url URL     Full course URL
  --debug, --d  Print debug information
```

## Example output
```ruby
[INFO]: Verifying token...
[INFO]: Requesting course id...
[INFO]: Requesting course data...
[INFO]: Content Type => ENCRYPTED_VIDEO
[INFO]: Getting signed URL...
[LOG] Installed Player Polyfills
[LOG] EmeEncryptionSchemePolyfill: EME not found
[LOG] McEncryptionSchemePolyfill: Waiting to detect encryptionScheme support.
[INFO]: Getting license request...
[INFO]: Requesting lst license...
[INFO]: Decrypting lst license...
[INFO]: Setting lst license...
[INFO]: Setting drm data...
[INFO]: Decrypting file...
[LOG] Reading input data...
[LOG] Decryption started...
[LOG] Returning...
[INFO]: Downloading vHQStream.mp4...
100% [........................................................................] 53729798 / 53729798
[INFO]: Downloading aStream.mp4...
100% [........................................................................] 23104604 / 23104604
[INFO]: Decrypting vHQStream.mp4 (this can take a while)...
[LOG] Reading input data...
[LOG] Decryption started...
[LOG] Warning: Enlarging memory arrays, this is not fast! 16777216,53870592
[LOG] Warning: Enlarging memory arrays, this is not fast! 53870592,64684032
[LOG] Returning...
[INFO]: Decrypting aStream.mp4 (this can take a while)...
[LOG] Reading input data...
[LOG] Decryption started...
[LOG] Returning...
[INFO]: Getting license request...
[INFO]: Requesting lgdrm license...
[INFO]: Decrypting lgdrm license...
[INFO]: Decrypting using mp4decrypt...
[INFO]: Decrypting using mp4decrypt...
[INFO]: Muxing using mkvmerge...
Warning: Quicktime/MP4 reader: Track ID 0 has more than one FourCC. Only using the first one (0x61766331 "avc1": AVC/H.264/MPEG-4p10) and not this one (0x61766331 "avc1": AVC/H.264/MPEG-4p10).
Warning: Quicktime/MP4 reader: Track ID 0 has more than one FourCC. Only using the first one (0x6d703461 "mp4a": AAC) and not this one (0x6d703461 "mp4a": AAC).
[INFO]: Decrypted Video/Audio => <video>.mkv
```