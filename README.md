# Learning Log - Worksheet 13a

**Date:** 14 October 2026  
**Tools Learned:** FFmpeg and qrencode

## 1. What I Learned

Today I learned about two command line tools: FFmpeg and qrencode.

- **FFmpeg:** A tool used to convert video and audio files into desired format.
- **qrencode:** A tool used to generate QR codes from text and website links.

## 2. Commands I Used

### FFmpeg

Extract a single image from a video:

```bash
ffmpeg -i Nature.mp4 Nature.jpg
```

Convert a video into a GIF:

```bash
ffmpeg -i Nature.mp4 Nature.gif
```

Shorten the GIF to 2 seconds:

```bash
ffmpeg -i Nature.mp4 -t 2 Nature2.gif
```

Reduce the frame rate and image size:

```bash
ffmpeg -i Nature.mp4 -t 2 -vf "fps=10,scale=320:-1" Nature3.gif
```

### qrencode

Generate a QR code from text:

```bash
qrencode "Rishabh Agrawal" -o rishabh.png
```

Generate a QR code for my GitHub repository:

```bash
qrencode "https://github.com/rishabh1240/worksheet-12.git" -o worksheet_12.png
```

## 3. Errors I Faced and How I Fixed Them

**Error 1: FFmpeg error**

I forgot to use `-i` before the input video.

Error: `Output file does not contain any stream`

Fix: I added `-i` before the video filename.

### Error 2: Unsupported Output Format in FFmpeg

I tried to convert a video into an unsupported file format by using the `.xyz` extension.

**Command:**

```bash
ffmpeg -i Nature.mp4 Nature.xyz
```

**Error:**
```text
Unable to choose an output format for 'Nature.xyz'
```

**Reason:** FFmpeg could not recognize the output format because `.xyz` is not a supported video or image format.

**Fix:** I changed the output extension to a supported format such as `.gif`.

```bash
ffmpeg -i Nature.mp4 Nature.gif
```

### Error 3: Incorrect Video Filter in FFmpeg

I intentionally misspelled a filter name while using the `-vf` option.

**Command:**

```bash
ffmpeg -i Nature.mp4 -vf gfp Nature2.gif
```

**Error:**
```text
No such filter: 'gfp'
```

**Reason:** FFmpeg could not recognize the filter because `gfp` is not a valid filter name.

**Fix:** I replaced the incorrect filter with the valid `fps` filter.

```bash
ffmpeg -i Nature.mp4 -vf "fps=10" Nature2.gif
```

**What I learned:** FFmpeg requires valid output formats and correctly spelled filter names. Reading error messages helps identify and fix mistakes.

**Error 4: qrencode error**

I used `-u` instead of `-o`.

Error: `qrencode: invalid option -- u`

Fix: I replaced `-u` with `-o` to specify the output filename.

## 4. Five Steps for Learning a New Tool

1. Understand what the tool is used for.
2. Find the general structure of its commands.
3. Run the smallest working command.
4. Change one thing and observe the result.
5. Break the command intentionally and understand the error.

## 5. What I Want to Try Next

I want to learn how to add subtitles to videos using FFmpeg and create QR codes for different websites.

## 6. Conclusion

Today I learned how to use unfamiliar command line tools by reading their documentation, experimenting with commands, and fixing errors. I also learned how to record my work using Git and GitHub.