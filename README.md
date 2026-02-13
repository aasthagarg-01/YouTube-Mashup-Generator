# YouTube Mashup Generator (Command-Line Project)

## Overview

This project implements a command-line based YouTube mashup generator using Python. The program automates the process of downloading multiple videos of a specified singer, extracting audio from each video, trimming each audio clip to a fixed duration, and merging them into a single output mashup file.

The objective of this project is to demonstrate command-line argument handling, file processing, multimedia manipulation, and integration of external Python libraries.

---

## Problem Statement

Given the following inputs from the command line:

- Singer Name  
- Number of Videos (N > 10)  
- Audio Duration in seconds (Y > 20)  
- Output File Name  

The program must:

1. Download N YouTube videos related to the given singer.
2. Convert each downloaded video into MP3 format.
3. Extract the first Y seconds from each audio file.
4. Merge all trimmed audio clips into a single output mashup file.

---

## Methodology

### Step 1: Video Downloading

The program uses the `yt_dlp` library to:

- Search YouTube for the specified singer.
- Download the required number of videos.
- Store the downloaded files inside a `videos/` directory.

---

### Step 2: Video to Audio Conversion

Using the `moviepy` library:

- Each downloaded `.mp4` file is processed.
- Audio is extracted and saved as `.mp3`.
- Converted audio files are stored in the `audios/` directory.

---

### Step 3: Audio Trimming

Using the `pydub` library:

- The first Y seconds of each audio file are extracted.
- Trimmed audio files are stored in the `trimmed/` directory.

---

### Step 4: Audio Merging

- All trimmed audio clips are concatenated sequentially.
- The final merged output is exported as a single MP3 file.
- The output file name is specified by the user during execution.

---

## Input Validation

The program includes the following validation checks:

- Ensures the correct number of command-line arguments is provided.
- Ensures `NumberOfVideos` is an integer greater than 10.
- Ensures `AudioDuration` is an integer greater than 20.
- Handles runtime exceptions during downloading, conversion, trimming, and merging.

---

## How to Run

The program must be executed from the command line using the following format:

```
python 102313059.py "<SingerName>" <NumberOfVideos> <AudioDuration> <OutputFileName>
```

### Example

```
python 102313059.py "Arijit Singh" 15 30 mashup.mp3
```

---

## Technologies Used

- Python  
- yt_dlp  
- moviepy  
- pydub  
- ffmpeg  
- Command-line Interface (CLI)  

---

## Conclusion

This project demonstrates practical implementation of multimedia processing using Python. It integrates external libraries to automate YouTube video retrieval, audio extraction, trimming, and merging. The final output is a custom mashup file generated based on user-provided parameters.
