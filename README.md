# convert265

Script to convert media to x265

These are mostly a hack job since I'm trying to save space for my media by converting things into HEVC.

I really need to make a unified script for the edge cases, but I haven't. Feel free to send a PR if you to something. I
also want to add AMF support, but have not gotten that to work right yet.

The nvidia example is 265 the other scripts use vaapi (intel/amd) to do the HW HEVC encoding. I haven't done much with
the NVIDIA in a few years, so it's kinda stale.

265_system is the one that you should use if you're going to use it.

I use it with parallel to do multiple files at once like this:

```shell
parallel 'find {} -type f -maxdepth 5 -regex ".*\.\(mkv\|mp4\|wmv\|flv\|webm\|mov\|avi\|m4v\|ts\m2ts\)"' ::: /mnt/Movies /mnt/TV | parallel --jobs 4 --progress ~/convert265/265_system {}
```

Change the --jobs flag to the number of files your system can handle at once. I think 4 is a sane number for older/lower
end NAS devices.

YMMV // Caveat Emptor // And have an average day :|

-H