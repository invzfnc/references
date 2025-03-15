Download audio as m4a file
`yt-dlp -o "%(title)s.m4a" -x --audio-format m4a link`

Get highest audio quality, embed metadata and thumbnail (cropped to square), save as m4a file
`yt-dlp --embed-thumbnail --convert-thumbnails jpg --ppa "ffmpeg: -c:v mjpeg -vf crop=\"'if(gt(ih,iw),iw,ih)':'if(gt(iw,ih),ih,iw)'\"" --add-metadata -f "bestaudio/best" --extract-audio --audio-format m4a -o "%(title)s.%(ext)s" "url"`