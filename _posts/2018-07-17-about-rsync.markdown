One thing I encountered after rsync huge amount of data to our new disks is that it recopied a lot of files. So the fix is to use the --size-only option.

But I still dunno why the speed significantly slows down.

Update: When using rsync, note that if there were any output at login, like
quota warning, rsync will report an error that reads "Is you shell clean". Rerun
rsync for like 3 times and it will start download.
