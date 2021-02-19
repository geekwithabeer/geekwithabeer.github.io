Using ffmpeg to embed an arbitrary timestamp to a video:

    .\ffmpeg -i "input.mp4" -crf 23 -vf "drawtext=fontfile=/Windows/Fonts/Arial.ttf: fontsize=72:fontcolor=white: box=1:boxcolor=black@0.4: text='%{pts\:gmtime\:1613749467}'" "output.mp4"
   
where 1613749467 is the epoch time at the start of the video.   
