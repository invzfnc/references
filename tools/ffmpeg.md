**Adjust audio volume**
`ffmpeg -i <input name> -filter:a "volume=3" <output name>`
`ffmpeg -i <input name> -filter:a "volume=10dB" <output name>`

**Skip part in front (Seek to)**
`ffmpeg -i <input name> -to 60 -c copy <output_name>`

**Delay audio**
`ffmpeg -i input.ogg -af "adelay=<x>s:all=true" out.ogg` 
\<x> in seconds

**Crop video length**
`ffmpeg -ss 00:00:01 -i video.mp4 -to 00:02:20 -c copy out.mp4`

**Speed up video**
`ffmpeg -i video.mp4 -filter:v "setpts=0.5*PTS" out.mp4`

**Concatenate video (listed file)**
`ffmpeg -f concat -i video-list.txt -c copy out.mp4`

**Add subtitle/captions**
`ffmpeg -i in.mp4 -vf "subtitles=captions.sbv:force_style='Fontname=Calibri,OutlineColour=&H808080,BorderStyle=3,FontSize=16'" out.mp4`

**Overlay video to bottom right of base video with padding of 10 pixels**
`ffmpeg -i base.mp4 -vf "movie=overlay.mp4,scale=500:-1[inner];[in][inner]overlay=main_w-(overlay_w+10):main_h-(overlay_h+10)" out.mp4`

**Converting .mkv to .gif with high quality**
`ffmpeg -y -i input.mkv -filter_complex "fps=15,split[v1][v2]; [v1]palettegen=stats_mode=full [palette]; [v2][palette]paletteuse=dither=sierra2_4a" -vsync 0 output.gif`
https://stackoverflow.com/questions/42980663/ffmpeg-high-quality-animated-gif

https://gist.github.com/steven2358/ba153c642fe2bb1e47485962df07c730#ffmpeg-cheat-sheet