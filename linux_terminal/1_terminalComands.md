# **Comands**

[ man clear ] infos;
[ man man ] Manual pager utils;
man - an interface to the system reference manuals

whoami - print effective userid

clear - clear clears your screen if this is possible or ctrl + l;

pwd - print name of current/working directory.Who I'm right now (files, ..ets) /home/yosuf

ls - list directory contents

# **help cd : Change the shell working directory.**

cd Desktop/
cd ../../.. - level up to files cd ../ or cd../.. or cd../../..
cd ~ - user's home directory ( ~ <=== mean tilde) right alt + (a)keyword.
cd / - root absolute paths.

#

mkdir [OPTION] - make directories, create foulder.
touch [OPTION] - change file timestamps, create file .txt., .pdf, .jpg and ets.
rmdir - delete only empty directory.
rm [filename] - remove files or directory.
rm -v [files name] - explain what is being done.
rm -r [fouldername] - remove directories even with files inside.
rm -ri [nameFoulder/] - -i prompt before every removal, ask what you want remove y/n in foulder.
rm -rv [nameFoulder] - delete everything in directory and the same foulder in same time.
open . - open current directory
open [textfile] - open file in default editor
mv [currentfile] [renameFile] - move (rename) files => [first argument == what rename] [second argument what new name for the file]
mv [currentfile] ../name_directory/ - move file to the directory which we prefer the file should to go. The coma always after nameDirectory/
cp [currentfile] [nameNewFile] - copy files and directories
head [currentFIle] - Print the first 10 lines of each FILE to standard output. head [currentFIle] -n 100 => 100lines
tail [currentFIle] - Print the last 10 lines of each FILE to standard output.
date - print or set the system date and time

# **redirection**

data||any_command > [anyFileYouCreate] - (store any data to a file) if multipletimes, data will replacing the content in file
data||any_command >> [anyFile] - appending data, data will be not replacing

#

cat - concatenate files and print on the standard output
cat [OPTION]... [FILE]... --> example: cat now.txt today.txt SOMS.txt > everything.txt

# **DESCRIPTION less**

Less is a program similar to more(1), but it has many more
features. Less does not have to read the entire input
file before starting, so with large input files it starts
up faster than text editors like vi(1). Less uses termcap
(or terminfo on some systems), so it can run on a variety
of terminals. There is even limited support for hardcopy
terminals. (On a hardcopy terminal, lines which should be
printed at the top of the screen are prefixed with a
caret.)

less [anyfile] - opposite of more, more info ==> man less

echo "some text " - display a line of text
echo "some text" >> config.txt - make string text and same to some file as config.txt

# **wc - print newline, word, and byte counts for each file**

wc [filename]
wc -l --print the newline counts
wc someText.txt ==>
0 10 52 someText.txt.txt

# **piping aka symbol |**

Pipe je příkaz v Linuxu, který vám umožňuje používat dva nebo více příkazů tak,
že výstup jednoho příkazu slouží jako vstup pro další.
Stručně řečeno, výstup každého procesu přímo jako vstup do dalšího jako potrubí.
ůs -l | wc

# **sorts**

sort - sort lines of text files
sort -n [num.txt] - sorting numbers
sort -nr [num.txt] - sorting numbers reverse
sort -nu [num.txt] - sorting uniq number (no-repeat)
ls | sort

# **diff**

diff - compare files line by line
diff [oneFile] [anotherFile]

# **find**

find - search for files in a directory hierarchy
find . - looking for everyfile and foulders in our distionary
find -name ['*(anythink)*'] ==>[ * ], the mean anything
find -name ['*.txt*'] ==> find anything with root .txt .js .py and ..ets
find -type d ==> mean directory

# **grep**

grep searches for PATTERNS in each FILE.
grep, egrep, fgrep, rgrep - print lines that match patterns
grep [searchingText] [someFile.txt] - searching in spec. file;
grep -r [searchingText] . -searching inside all file's. Read all files under each directory.

# **du**

find sizes of files,dictionary on our machine.
du -h

#

df -h == report file system disk space usage, -h, --human-readable

# **history**

history - GNU History Library
history || ![numberInTerminal] == ! + number => mean history what we want printed
history | less
history | grep 'chicken'

# **ps**

ps displays information about a selection of the active processes.
ps - report a snapshot of the current processes.
ps ax - report all processes.

#

top - display Linux processes
kill - send a signal to a process
kill -l - List signal names.
ps a - show proces what runing
kill 9 [procesID] - brutal kill every process in my pc
killall - kill processes by name

# **jobs, bg, and fg - running things on background or frontground**

proces for example here :
find / -ctime 1 > allchanges.txt || top ==>(only for ilustration)mean find all(/) chances in 24h and printIt (>) in allchenges.txt:it maybe make infinit loop,how we can stop it ??
ctrl + c - stop all things
ctrl + z - suspended / pause process
wc allchanges -show us is how much lines we had actualy render from the proces in the file.
After the command ctrl + z we write jobs:
jobs
[1]+ Stopped (###########################) find / -ctime 1 > allchanges.txt
[2]+ Stopped (###########################) top
[1][2] is ID from the proccessing what we had suspended. After that we can use fb or bg.
fg 2 - will show us second proccess what we had suspended.We can use ctrl +z/c again.
jobs - will show us what we had suspended
--we had still (if we didnt stop (top) command process) process suspended and we can run it in front or backround.
again run: jobs - show us what is suspended
now we can use fg or bg: fg 1 or bg 1 or only bg (if we have only one process suspended).
In case we can use: fg 1 and we will see the proces, but we want that always? If no? We use: bg 1

# **& - The & makes the command run in the background.**

sleep - delay for a specified amount of time
sleep 50 - will make delay for 50s
sleep 50 & - will make sleeping on background, and we dont see that.
jobs
[1]+ Running (###################) sleep 50 &
jobs | ctrl +z / ctrl + c

# **gzip, gunzip, tar**

# **gzip compless individual file**

gzip, gunzip, zcat - compress or expand files
gzip -k [nameOfFile] - Keep (don't delete origin) input files
gzip -d [nameOfFile] - unzip my compress file,uncompress
gunzip [nameOfFile] - unzip file what we want aka allchanges.txt.gz
gzip -kv [allchanges.txt] - Verbose. Display the name and percentage reduction for each file compressed or decompressed.

# **tar -> grouping bunch of files together info a single file**

tar -cf archive.tar file1 file2 - c = create, f = file name (archive.tar),
tar -xf archive.tar - x = extract, f = file name(archive.tar)
tar -xf [archive.tar] -C [directory] -> -C = move the directory where we want.
tar -tf archive.tar - show us what name of files is inside our archive in our directory.
--- we can also zipin tar = gzip -k [archive.tar] ---
10K Aug 19 15:48 archive.tar
202 Aug 19 15:48 archive.tar.gz
---tar -xf archive.tar ---
result : archive.tar testinOne.txt testinTwo.txt

# **nano - Nano's ANOther editor, inspired by Pico**

nano [nameFile] -open in editor. Control the editor we use ctrl + (x,r, ..ets)
ctrl + w =>search for something what u looking for.
ctrl + s => save
ctrl + k => cut
ctrl + u => paste
nano [newtest.txt] =>create new file where we can write what we want.

# **xargs - build and execute command lines from standard input**

We had created file [testing] with couple of files player[n].txt and deathPlayer.txt where we have text of arguments.
With this argument which is represented in deathPlayer.txt we will want delete the others files.
cat deathPlayer.txt | xargs rm

# **ln**

ln - make links between files.
In the 1st form, create a link to TARGET with the name LINK_NAME.
In the 2nd form, create a link to TARGET in the current directory.
In the 3rd and 4th forms, create links to each TARGET in DIRECTORY.
example:

- mkdir Links
- cd Link
- echo "I AM ORIGINAL" > orginal.txt
- ln [orgin.txt] [hardlink.txt]
- echo " this is more stuff">> origin.txt
- cat hardlink.txt ==> I AM ORIGINAL; this is more stuff
  :remember hardlink.txt isnt copy
- rm orginal.txt
  cat hardlink.txt => still have the text

ln -s : soft link
ln -s [original.txt] [symlink.txt] :the symlink.txt had different color.

: ln -s is similar like hardlink (simple ln),but diffent is betwen removing file,
when in normal rm origin.txt out hardlink.txt holding our data, but in rm original in ln -s ,
out symlink.txt will be red,
cat symlink = cat: symlink.txt: No such file or directory

# **who - show who is logged on**

- Print information about users who are currently logged in.

# **su - switch user**

su [nameUser]

# **sudo -super user do**

sudo, sudoedit — execute a command as another user
nano /etc/hosts -open editor,but we havnt permision writing there something.
sudo nano /etc/hosts - sudo ask for password, and now we can rewriting what we want.(Dont do it, if u dont know what u do!!!)

# **passwd**

man passwd
passwd - chance password user.
sudo passwd [username]- chance password for any other users, in the same pc machine.

# **chown**

chown - change file owner and group
chown <owner><file>

# **understanding permissions**

ls- l
example:
lrwxrwxrwx 1 root root 7 Jun 20 19:57 bin -> usr/bin
drwxrwxr-x 4 yosuf yosuf 4096 Jul 9 11:00 git
drwxr-xr-x 3 root root 4096 Jun 20 20:00 home
drwxr-xr-x 3 root root 4096 Aug 10 18:22 media
-rw- -- - -- 1 root root 2147483648 Jun 20 19:57 swapfile

- (-)regular file
  d directory
  c character special file
  l symbolic link/sim link

- | Owner| Group | World
  -rwxr-xr-x 1 yosuf yosuf 8515 Jun 13 01:58 google-chrome.desktop
  (-) rw- | rw- |r--
  the first simbol mean - (dash)for file,d for dirrectory, l for sim link
  read r;
  w write, - no execute: - mean no permissions / dash symbol;
  x file can be treated as a program to be executed;

-| Owner |
-| rwx | --
In the abowe example, we see that the file's
owner had read, write, AND executed permissions.
No one else has any access

# **chmod - change file mode bits**

chmod g-r [nameFile] - change mod permission groud-read [filename];
chmod o-r [nameFile] - change mod permission others-read [filename];
chmod o-rwx [nameFile] - change mod others-read-write-execute subtract permissions [filename];
chmod a+rwx [nameFile] - change mod all-read-write-execute permissions [filename];
chmod a-x [nameFile] - change mod all-execute remove execute for allpermissions [filename];
chmod a=r [nameFile] - change mod all equal only read permissions [filename];
