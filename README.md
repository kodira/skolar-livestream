# skolar-livestream
Files for a sponsored livestream. Two raspberry pis streaming to live.skolar.de

## On raspberry pi

raspivid \
 -mm matrix \      # metering mode
 -w 1280 -h 720 \  # size
 -fps 20 \         # frame per second
 -g 40 \           # Frames without I-frame
 -t 0 \            # Timeout
 -pf high \        # H264 profile (high -> best)
 -lev 4 \          # H264 profile level
 -b 500000 \       # Bitrate
 -o - | ffmpeg \
 -y \              # Overwrite
 -f h264 \         # Format
 -i - \            # Input from stdin
 -c:v copy \       # Video codec -> just copy not transform
 -map 0:0 \        # Map input stream 0 to output stream 0
 -f flv \          # Output format
 rtmp://live.skolar.de/stream/test

