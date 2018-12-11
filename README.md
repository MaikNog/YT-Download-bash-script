# YT-Download-bash-script
A bash script for Macintosh with parameters for learning bash scripting

# Preparation and Setup
0. Install your downloader tool of choice. For learning I use: youtube-dl

1. Extend your bash_profile with a shortcut to use the scriptfile anywhere in the file system

    Bash profile location: ~/.bash_profile
    
    Enter an alias:      alias mp3YT="bash ./mp3fromYT.sh"

# Main Script
Scriptname : mp3fromYT.sh

# I want my downloads on the same place, independent of where I run this script
cd ~/Downloads/___Music/

# The next line works, but its static to MP3 conversion.
# youtube-dl $1 -x --audio-format mp3


# Next todo: Work on the if/then, so I can choose MP3 or MP4 download
if $2 == mp3
        then youtube-dl $1 -x --audio-format $2
  else if $2 == mp4
        then youtube-dl $1 -f, --format $2
