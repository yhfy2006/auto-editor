# Documentation

## Installing
Auto-Editor supports python version from 3.6.0 to the latest public build.

Auto-Editor needs either its pre-installed ffmpeg binaries or you to install ffmpeg on your own machine.
For Linux users, that is a requirement, however, installing is easy. Just run `sudo apt-get install ffmpeg libavformat-dev libavfilter-dev libavdevice-dev`

Then run:

```terminal
pip3 install -U auto-editor
```

If auto-editor does not get linked to the main files in your console. Try using pipx to fix it.

```terminal
pip3 install pipx
pipx install auto-editor
pipx ensurepath
# close and reopen your console
```

## Installing from Source
Sometimes, pip won't work, you want to downgrade to a very early version of auto-editor, or you're working on maintaining this project. In that case, you'll need to download and run the source code. Use git to download the repository then run \_\_main\_\_.py with python.


```terminal
git clone https://github.com/WyattBlue/auto-editor.git
cd auto-editor
python3 auto_editor/__main__.py example.mp4 [add your options here]
```


## All the Commands

Here's the help screen auto-editor prints out.

```terminal
usage: auto-editor [input] [options]

optional arguments:
  -h, --help            show this help message and exit

Basic Options:
  input                 the path to the file(s), folder, or url you want
                        edited.
  --frame_margin 6, -m 6
                        set how many "silent" frames of on either side of
                        "loud" sections be included.
  --silent_threshold 0.04, -t 0.04
                        set the volume that frames audio needs to surpass
                        to be "loud". (0-1)
  --video_speed 1, --sounded_speed 1, -v 1
                        set the speed that "loud" sections should be
                        played at.
  --silent_speed 99999, -s 99999
                        set the speed that "silent" sections should be
                        played at.
  --output_file [ [ ...]], -o [ [ ...]]
                        set the name(s) of the new output.

Advanced Options:
  --no_open             do not open the file after editing is done.
  --min_clip_length 3, -mclip 3
                        set the minimum length a clip can be. If a clip is
                        too short, cut it.
  --min_cut_length 6, -mcut 6
                        set the minimum length a cut can be. If a cut is
                        too short, don't cut
  --combine_files       combine all input files into one before editing.
  --preview             show stats on how the input will be cut.

Cutting Options:
  --cut_by_this_audio , -ca
                        base cuts by this audio file instead of the
                        video's audio.
  --cut_by_this_track 0, -ct 0
                        base cuts by a different audio track in the video.
  --cut_by_all_tracks, -cat
                        combine all audio tracks into one before basing
                        cuts.
  --keep_tracks_seperate
                        don't combine audio tracks when exporting.

Developer/Debugging Options:
  --my_ffmpeg           use your ffmpeg and other binaries instead of the
                        ones packaged.
  --version             show which auto-editor you have.
  --debug, --verbose    show helpful debugging values.

Export Options:
  --export_as_audio, -exa
                        export as a WAV audio file.
  --export_to_premiere, -exp
                        export as an XML file for Adobe Premiere Pro
                        instead of outputting a media file.
  --export_to_resolve, -exr
                        export as an XML file for DaVinci Resolve instead
                        of outputting a media file.

Size Options:
  --video_bitrate 250k, -vb 250k
                        set the number of bits per second for video.
  --audio_bitrate 160k, -ab 160k
                        set the number of bits per second for audio.
  --sample_rate 48000, -r 48000
                        set the sample rate of the input and output
                        videos.
  --video_codec copy, -vcodec copy
                        set the video codec for the output file.

Deprecated Options:
  --hardware_accel
```