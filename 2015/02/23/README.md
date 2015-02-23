30 кадров 41-42 секунд
# Кодирование видео
ffmpeg -framerate 1 -pattern_type glob -i '*.png' -c:v libx264 -pix_fmt yuv420p out.mp4


ffmpeg  -pattern_type glob  -i 'IMG_*.png' \
-acodec libvorbis -ac 2 -ab 0k -ar 33600 -framerate 1/2.5 -vf fps=5 -pix_fmt yuv420p \
-b:v 900k IMG_.webm

ffmpeg  -pattern_type glob  -i 'IMG_*.png' \
-acodec libvorbis -ac 2 -ab 0k -ar 33600 -framerate 10 -pix_fmt yuv420p \
-b:v 900k IMG_.webm

# рабочее решение!

ffmpeg -i 201502231242.mov -c:v libx264 -vf "fps=25,format=yuv420p" 201502231242.mp4

ffmpeg  -i 201502231242.mov \
 -framerate 10 -pix_fmt yuv420p \
201502231242.webm

ffmpeg -i 201502231242.mov \
-vcodec h264 -quality good -vf "fps=5" \
201502231242.flv

# zapac_43.mp3

ffmpeg -framerate 1/1.43 -pattern_type glob -i '*.png' -i zapac_43.mp3 -vcodec h264 -quality good -ac 2 -ab 64k -ar 44100 -vf "fps=5" -t 43 -ss 0 201502231242.flv

ffmpeg -framerate 1/1.43 -pattern_type glob -i '*.png' -i zapac_43.mp3 -ac 2 -ab 64k -ar 44100 -c:v libx264 -strict -2 -vf "fps=5,format=yuv420p" -t 45 -ss 0 201502231242.mp4

ffmpeg -framerate 1/1.43 -pattern_type glob -i '*.png' -i zapac_43.mp3 -acodec libvorbis -ac 2 -ab 64k -ar 22050 -strict -2 -vf "fps=5,format=yuv420p" -t 43 -ss 0 201502231242.webm

# _ghost_-_reverie_41.mp3

ffmpeg -framerate 1/1.41 -pattern_type glob -i '*.png' -i _ghost_-_reverie_41.mp3 -vcodec h264 -quality good -ac 2 -ab 64k -ar 44100 -vf "fps=5" -t 41 -ss 0 201502231243.flv

ffmpeg -framerate 1/1.41 -pattern_type glob -i '*.png' -i _ghost_-_reverie_41.mp3 -ac 2 -ab 64k -ar 44100 -c:v libx264 -strict -2 -vf "fps=5,format=yuv420p" -t 45 -ss 0 201502231243.mp4

ffmpeg -framerate 1/1.41 -pattern_type glob -i '*.png' -i _ghost_-_reverie_41.mp3 -acodec libvorbis -ac 2 -ab 64k -ar 22050 -strict -2 -vf "fps=5,format=yuv420p" -t 41 -ss 0 201502231243.webm
