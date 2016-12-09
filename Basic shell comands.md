#Basic shell comands

 All basic things for newbie server admins should know.

##Navigation

1. How to move into another directory

		$ cd [another directory]

	example: move to directory “download”

		cd download
		
2. How to go to home directory

		cd ~

3. How go to the last directory you were in

		cd -
	
4. How to go up a directory level

		cd ..

5. How to show the full path of the current directory
Use this command to find out where are you currently in.
		
		pwd

6. How to list files and/or directories in a directory

		ls (just type ls and hit enter)

7. How to list all files and information

		ls -al

8. How to list all files ending with certain extension

		ls *.ext
		
	example:
	
		ls *.php

9. How to list all files and folders with detailed information including file size

		ls -alh

10. How to quit and exit SSH client

		exit
		
##FILE MANAGEMENT

1. How to copy and rename file
	
	Use this command to copy and rename a file

		cp [filename] [new filename]

	example: we’ll rename banner.jpg to banner728px.jpg

		cp banner.jpg banner728px.jpg

	example: we’ll cope banner.jpg to a folder called “ads”

		cp banner.jpg ads/banner.jpg
	
	example: copying and renaming at once

		cp banner.jpg ads/banner728px.jpg
	
	ps: original file will remain, it is just copied.

2. How to move and rename file

	Use this command to move and rename file
		
		mv [old filename] [new filename]

	example: moving a file to another directory

		mv banner.jpg ads/banner.jpg

	example: moving a file to another directory and renaming it at once
	
		mv banner.jpg ads/banner728px.jpg

	ps: original file will be deleted as it was moved to another location
	
	pps: you can also move a folder

	example: moving “image” folder to “media” folder
	
		mv image/ media
	example: moving “image” folder to upper directory

		mv image/ ..
		
3. How to delete / remove a file

		rm [file name]
	example:
		
		rm banner.jpg

4. How to delete / remove all files in current directory
		
		rm *

5. How to delete files with certain extension

		rm *.extension
	
	example: remove all files with .jpg extension
	
		rm *.jpg

6. How to copy a folder with all files and folders in it

		cp -r [directory] [new directory]

7. How to create new folder

		mkdir [folder name]
	example:

		mkdir image

8. How to search for a file starting within current directory

		find . -name [filename] -print

	example: find a file called “banner.jpg” in current folder

		find . -name banner.jpg -print

9. How to search for text within a file

		grep [text] [filename]
	
	example: find the word “sidebar” in file index.php

		grep sidebar index.php
		
10. Create a file

		touch
			
	Use the touch command to create different files 	and file extensions (you can later edit them)

		touch index.php

##Compressing Decompressing

1. Compressing folders

		zip -r foldername.zip foldername
	
	Example:

		zip -r newfolder.zip newfolder

2. Decompressing folders

		unzip

	Example:

		unzip newfolder.zip

3. Compressing folders using tar -czvf

		tar -czvf foldername.tar.gz foldername

	Example:

		tar -czvf wp-content.tar.gz wp-content

4. Decompressing folders using tar -czvf

		tar -xvf foldername.tar.gz

	Example:

		tar -xvf wp-content.tar.gz


##Permission & Owner

###`chmod` change file permission

	chmod [permission type] [file/folder name]

Example:

	chmod 777 config.php
	
Change permissions of folder and all files inside

	chmod -r 777 config/

This command comes in handy when you want to change file permissions of an entire folder including it’s contents.

Available permission type: (below is not command)
First number is for the owner, second for the group, and third for everyone.

| Number| Permissions           |
|:-----:|:--------------------- |
|7      | Read + Write + Execute|
|6      | Read + Write          |
|5      | Read + Execute        |
|4      | Read                  |
|3      | Write + Execute       |
|2      | Write                 |
|1      | Execute               |
|0      | All access denied     |
 
####Defoult value

| Type   | Permissions | Discription |
| ------ | ----------- | ----------- |
| Folder | 755         | **rwxr-xr-x** </br> </br> The owner (user) can do everything. Group and everyone else can only read directories and come into them, but they are not allowed to write, edit and delete them |
| Files  | 644         | **rw-r--r-** </br> </br> The owner (user) can read and modify files. The owner can not execute files. All not allowed to change and execut files. Everyone can only read.


### `chown ` change file owner	

		$ chown owner-user file
		$ chown owner-user:owner-group file
		$ chown owner-user:owner-group directory
		$ chown options owner-user:owner-group file

Example:

	chown admin:admin config.php
	
Change the owner of `/foo` and subfiles to `root`, run:
		
	chown -R root /foo