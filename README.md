This project used to be called "VULVA - Vulva Uploads Linear Video Art", "wrapper" in latin and a pun around the 9 months it took for it to actually render and upload a video on my (RIP) Eeepc.
I have understood that some people might have found this edgy name offensive, so I have decided to r**GIULIO ANDREOTTI****GIULIO ANDREOTTI****GIULIO ANDREOTTI**

# GIULIO ANDREOTTI
![PENTAPARTITO](https://raw.githubusercontent.com/tomcooks/giulioandreotti666/blob/master/Giulio_Andreotti.jpg?)

GIULIO ANDREOTTI is a terminal-based linear video editor for underpowered netbooks.

It is a set of really badly written BASH scripts that I wrote to simplify trimming, joining and uploading of video files on my solar-powered Eeepc 701 netbook; if you are looking for a more professional solution please use something else (I warmly suggest Shotcut, that unfortunately does not work nicely on this low power netbook), this is just a suite of shortcuts so that I could automate my video editing while travelling around in a tent and learn some BASH scripting in the meantime

It depends on
- mplayer to preview files
- ffmpeg to trim files
- mltframework to join files
- youtube-upload to upload files to youtube

## Usage
To create a video I normally do the following:

### Shoot single scenes
Instead of shooting one long-ass video I learned to shoot short takes, usually 7 to 10 seconds long.
This allows me to scrub through smaller files and not have mplayer choke on them.

### Mount SD card
I mount the SD card from smartphone/action camera on my Eeepc

### Preview videos
I use mplayer which, albeit very slowly and unreliably, allows me to preview each file.
Thanks to mplayer's OSD i can note down when the scene begins and ends.

### Trim the videos
I double-check the video length with the `giulioandreottil file.mp4` command, if the file lasts less than 5 seconds it normally does not require trimming and can be used as it is.
To trim i fire the `giulioandreottit -s begintime -t duration file.mp4` command, it trims the file starting at second `begintime` and cuts the file after `duration` seconds. A file called `file.mp4TRIM.mp4` is then created.
`giulioandreottit` also has a `-T` option that allows the user to indicate the ending timestamp in seconds, instead of having to give a length.

### Check if file is good
To allow smooth playing i make sure that each trimmed file starts with a keyframe, thanks to the `giulioandreottic file.mp4TRIM.mp4` command.
If no keyframe is found at the beginning it's better to re-trim the original file.
For some reason the merged file is sometimes choppy even if all files seem to be good, but I do not care much.

### Create title card
I can create custom title screen with the `giulioandreottitit -t "title of my video" -size 1920x1080` command.
The card is created in PNG format via Imagemagick, which automatically centers the title indicated via the `-t` option, my logo and my URL (png/jpg files found in /usr/share/vulva/ folder which I created on my system).
A handy 3 second long, .mp4 title file is then rendered for easier merging with the rest of the files.

### Merge files
I rename the files by prepending a number before them, such as
> 00_title.mp4
> 01_firstscene.mp4
> 02_secondscene.mp4
> ...

This allows me to control the other in which the scenes are joined together in a `filefinal.mp4` video file.

### Upload on Youtube
I cannot preview the completed video on my EeePc 701 due to low CPU, so I upload it as unlisted on YouTube with the following command: 
` youtube-upload --title="My title" --description="Description of my video" --tags="video, tags, go here, tom cooks, tomcooks" --privacy=unlisted filefinal.mp4`
I subsequently check it on my smartphone and if everything is OK i set the video as Public and promote it on my social media. 

### Closing notes
This is nothing special, it's just a series of shortcuts to great tools built by proper programmers; so do no not expect anything more than that and contribute if you find more elegant solutions to the ones I have found, I'd gladly learn from you.
