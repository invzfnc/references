**Adjust audio volume**
`ffmpeg -i <input name> -filter:a "volume=3" <output name>`
`ffmpeg -i <input name> -filter:a "volume=10dB" <output name>`

**Skip part in front (Seek to)**
`ffmpeg -i <input name> -to 60 -c copy <output_name>`

**Delay audio**
`ffmpeg -i input.ogg -af "adelay=<x>s:all=true" out.ogg` 
\<x> in seconds

**Crop video length**
`ffmpeg --ss 00:00:01 -i video.mp4 -to 00:02:20 -c copy out.mp4`

**Speed up video**
`ffmpeg -i video.mp4 -filter:v "setpts=0.5*PTS" out.mp4`

**Concatenate video (listed file)**
`ffmpeg -f concat -i video-list.txt -c copy out.mp4`


https://gist.github.com/steven2358/ba153c642fe2bb1e47485962df07c730#ffmpeg-cheat-sheet