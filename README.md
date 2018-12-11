# YT-Download-bash-script
A bash script for Macintosh with parameters for learning bash scripting

# Preparation and Setup
0. Install a tool of choice. For learning I use: youtube-dl

1. Extend your bash_profile with a shortcut to use the scriptfile anywhere in the file system

    Bash profile location: ~/.bash_profile
    Enter an alias:      alias mp3YT="bash ./mp3fromYT.sh"
    
2. Create a new (script) file: mp3fromYT.sh
    The extension .sh makes it a shell script.
    
3. Make the script executable: chmod +x mp3fromYT.sh



# Main Script
Scriptname : mp3fromYT.sh

# Details of the script
# I want my downloads on the same place, independent of where I run this script
cd ~/Downloads/

# Use an if/elif/then condition to adjust download option; user can enter a second parameter when executing the script.
# Currently supported: MP3 and MP4 (and empty/no second parameter).

# If no second parameter is given, then gives a textual warning and downloads the youtube-dl default

if [ "$2" = "mp3" ]
        then youtube-dl "$1" -x --audio-format "$2"
  elif [ "$2" = "mp4" ]
        then youtube-dl "$1" -f  "$2"
  elif [ -z "$2" ]
        then echo "Specify MP3 or MP4 as second argument; will download default now" && youtube-dl "$1"
fi



# Full script:
cd ~/Downloads/

if [ "$2" = "mp3" ]
        then youtube-dl "$1" -x --audio-format "$2"
  elif [ "$2" = "mp4" ]
        then youtube-dl "$1" -f  "$2"
  elif [ -z "$2" ]
        then echo "Specify MP3 or MP4 as second argument; will download default now" && youtube-dl "$1"
fi


# Helpful tools & Learnings
A) https://www.shellcheck.net/ ; One can check the shell script while typing.

B) Empty space around [ and ] are needed. 
C) Putting parameter in "" helps with word splits or globbering.

