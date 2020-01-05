%% convert video to audio
ffmpeg -i input.mp4 -vn audio_only.ogg

%% remove audio
ffmpeg -i example.mkv -c copy -an example-nosound.mkv

%% concat reverse of video (no audio)
ffmpeg -i input.mp4 -filter_complex "[0:v]reverse,fifo[r];[0:v][r] concat=n=2:v=1 [v]" -map "[v]" output.mp4

%%overlay image
ffmpeg -i video.mp4 -i image.png -filter_complex "[0:v][1:v] overlay" output.mp4
