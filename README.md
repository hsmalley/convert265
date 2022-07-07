# convert265

Script to convert media to x264

Edit the path for the find command in the normal one.

To make it even more faster you'll want to run this kinda like this...

parallel ./parallel_convert_265 . ::: $(find /mnt/ -maxdepth 25 -regex ".*\.\(mkv\|mp4\|wmv\|flv\|webm\|mov\|avi\|m4v\)")

