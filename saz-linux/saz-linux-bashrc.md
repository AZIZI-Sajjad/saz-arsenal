# saz-linux-bashrc

#plateform/linux
#target/local
#cat/PRIVESC
#cat/PERSIST
#cat/AZIZI-Sajjad
#tag/linux-bashrc

## linux-bashrc - ~/.bashrc Add backup fonction backupdir
```
    backupdir() {
        current_time=$(date +"%Y-%m-%d-%Hh%M-%Ss")
        src="</path/to/source/dir>"
        destdir="</path/to/destination/dir/Backup>-${current_time}"
        mkdir -p "$dest" && scp -r "$src" "$dest"
        echo "Backup completed -> Source : $src To Desrtination : $dest"
    }
```

## linux-bashrc - ~/.bashrc Add backup fonction backupfile
```
    backupfile() {
            current_time=$(date +"%Y-%m-%d-%Hh%M-%Ss")
            src="</path/to/source/file>"
            destdir="</path/to/destination/dir/Backup>-${current_time}"
            destfile="</path/to/destination/dir/Backup>-${current_time}/<destinationFileName>"
            mkdir -p "$dest" && scp -r "$src" "$destfile"
            echo "Backup completed -> Source : $src To Desrtination : $dest"
    }
```
