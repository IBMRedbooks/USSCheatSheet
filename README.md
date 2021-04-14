# Unix System Services CheatSheet
The z/OS operating system has a Unix interface in addition to the traditional TSO interface. Details can be found [here](https://en.wikipedia.org/wiki/UNIX_System_Services). Many z/OS systems programmers are unused to working in the Unix shell and have a hard time getting around in the Unix shell. Additionally, the default shell on USS is not a bash shell so help provided by traditional Unix users is sometimes deceptive. This page is intended to provide z/OS Systems Programmers (AKA Sysprogs) a cheat sheet that they can use to do most of the tasks they would need to accomplish on z/OS USS. Contributions come from Sysprogs in multiple companies. Detail for each of these commands can be found in the [Unix System Services Command Reference](https://www-01.ibm.com/servers/resourcelink/svc00100.nsf/pages/zOSV2R3SA232280/$file/bpxa500_v2r3.pdf).



| USS "Command" | Description                                                                                                                                   |
|---------------|-----------------------------------------------------------------------------------------------------------------------------------------------|
|<img width="400"/> chattr +a *filename*| Change attributes of the file *filename* to make it APF authorized. Other attributes could be set as well.|
| chtag -t -c IBM-1047 *filename*| Tag *filename* as an EBCIDIC. The chtag allows you to tell z/OS how the file is encoded.|
| chtag -t -c ISO8859-1 *filename* | Tag *filename* as an ASCII file. The chtag allows you to tell z/OS how the file is encoded.|
| df -kP | Display free space in the filesystems -k makes sure the numbers are in 1K (instead of 512 bytes. P means show fomplete info (including percentages |
| ls -lta | List the files in the current directory -l makes sure it shows data like permissions, -t sorts by time and -a shows . info|
| ls -ET | List the files in the current directory -E shows extended attributes (like APF authorization) and T shows file tagging (is it ASCII, EBCIDIC, or Binary)|
| mkdir | Create a directory. The file system is hierarchical. This will create a directory in the current directory. |
| rm * | Remove a file. With the * it will remove all of the files in the current directory |
| rm -R * | Remove all of the files in this directory and recurse down any directories and remove files from them too|
| type *name* | Show the location of the executable known as *name*. Very useful when you want to make sure you are executing the right code.|
