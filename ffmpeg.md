# convert video to audio
ffmpeg -i input.mp4 -vn audio_only.ogg

# remove audio
ffmpeg -i example.mkv -c copy -an example-nosound.mkv

# concat reverse of video (no audio)
ffmpeg -i input.mp4 -filter_complex "[0:v]reverse,fifo[r];[0:v][r] concat=n=2:v=1 [v]" -map "[v]" output.mp4

# overlay image
ffmpeg -i video.mp4 -i image.png -filter_complex "[0:v][1:v] overlay" output.mp4

# overlay text
# scroll up from bottom of frame
# show text at center
ffmpeg -i video.mp4 -vf drawtext="text='asdf': fontsize=52: x=(w-text_w)/2: y=h-20*t" output.mp4

# scale to 1/4 size, preserve aspect ratio
ffmpeg -i input -vf scale=iw/4:-1 output

# for youtube
# Create a video with a still image (input.png) and an audio file (audio.m4a)
ffmpeg -loop 1 -framerate 2 -i input.png -i audio.m4a -c:v libx264 -preset medium -tune stillimage -crf 18 -c:a copy -shortest -pix_fmt yuv420p output.mkv
