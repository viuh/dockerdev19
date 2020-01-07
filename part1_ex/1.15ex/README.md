# Purpose

Simple script for downloading a videofile from imgur or youtube (etc.). Utilizes the youtube-dl (available at https://yt-dl.org) which has been 'dockerized'.
Available at https://hub.docker.com/r/viuh/ytdl .

# Execution

Pull the image and run it e.g. via:

    docker pull viuh/ytdl

    docker run viuh/ytdl https://www.youtube.com/watch?v=CmztPezLBKc


Downloaded file is put at the directory where the script is run.

