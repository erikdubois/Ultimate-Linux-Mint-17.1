# Ultimate Linux Mint 17.1 Cinnamon


![Screenshots](http://erikdubois.be/wp-content/uploads/2015/05/final_linuxmint171.png)


![Screenshots](http://erikdubois.be/wp-content/uploads/2015/02/pimp_linux_mint.jpg)

This is my way of working when installing a new operating system.

	1 Updates, drivers and kernels
	2 Software and patches
	3 Change settings to my liking
	4 Fun stuff


#What can you do if the script does not execute?

Since I sometimes forget to make the script executable, I include here what you can do to solve that.

A script can only run when it is marked as an executable.

	ls -al 

Above code will reveal if a script has an "x". X meaning executable.
Google "chmod" and "execute" and you will find more info.

For now if this happens, you should apply this code in the terminal and add the file name.

	chmod +x typeyourfilename

Then you can execute it by typing

	./typeyourfilename




#1 Kernel, Nvidia and Cinnamon

As described at http://erikdubois.be/linux/the-ultimate-linux-mint-update I try to get the latest of everything. This attitude tends to break things. You have been warned. But the best way to learn about linux.

The first time I suggest you follow the steps in the article.

I have written a script to automate my installation. 

You have a choice. 

	- kernel 3.x
	- kernel 4.x

If you want to install a kernel 3.x or a kernel 4.x, I have to take a different approach for my hardware. Therefor I have split it up in two files.

	- ./kernel_3_X the_ultimate_Linux_Mint_update_vx.sh 
	- ./kernel_4_X_the_ultimate_Linux_Mint_update_vx.sh 

The only reason is that my hardware, the nvidia driver and kernel 4 are not compatible at the time of writing.
You can read about that at 

http://erikdubois.be/linux/linux-mint-17-1-and-the-linux-4-0-kernel

Do not forget to type "./" in front of the name.

You can run any of these scripts by downloading the zip file from github. Go to the download folder and right-click to Extract here.
Go inside the folder and right-click <b>in a blank space</b> to go to the terminal. Now your terminal is opened in this extracted folder.

Type in the terminal

	- ./kernel_3_X the_ultimate_Linux_Mint_update_vx.sh 
	
	or 
	
	- ./kernel_4_X_the_ultimate_Linux_Mint_update_vx.sh 


The very latest cinnamon version will be installed on your system by adding the following repository.

	sudo add-apt-repository -y ppa:gwendal-lebihan-dev/cinnamon-nightly
	sudo apt-get update 
	sudo apt-get install cinnamon -y

Nvidia drivers will <b>NOT</b> be installed as they are very specific to your hardware. But checkout the code.
This code can be uncommented.

	# sudo add-apt-repository -y ppa:xorg-edgers/ppa
	# sudo apt-get update
	# sudo apt-get install nvidia-340 -y (for example)

Check on Nvidia.com which driver you should use.

Wait for the installation and reboot.

#2 Software installation

We start the installation script of all the needed software in the same way as above. I made a distinction between 17.1 and 17.2. At time of writing we have a release candidate. 


	- ./script_to_install_Linux_mint_17_1_def_vxx.sh


Do not forget to type "./" in front of the name.


And a specific script for samba (sharing of maps on your home network) if you need it. This script is NOT necessary. Linux Mint shares folders just fine. If you need a program to have an oversight of all the shared maps. This is the one. 

	sudo apt-get install system-config-samba


#3 Changing settings


ZSH and Oh-my-sh
-----------------------
I like bash but I prefer zsh. So let us install that in the script

./install_zsh.sh

Go and find that hidden file .zshrc (CTRL+H) and edit it

Change

into

ZSH_THEME="random"

Latest script will take care of that automatically.


Google Drive
----------------
I do not need to have the google drive on my computer but if you do

sudo add-apt-repository ppa:thefanclub/grive-tools -y

sudo apt-get update

sudo apt-get install grive-tools -y



Antivirus
------------------
There is no need to have an antivirus but if you want to scan your windows files


sudo sh -c 'echo "deb http://download.bitdefender.com/repos/deb/ bitdefender non-free" >> /etc/apt/sources.list'

wget http://download.bitdefender.com/repos/deb/bd.key.asc

sudo apt-key add bd.key.asc

sudo apt-get update

sudo apt-get install bitdefender-scanner-gui


More info at http://linuxaria.com/howto/bitdefender-a-good-antivirus-for-linux-system


Folder nemo-scripts
------------------
Move the content of the folder nemo-scripts to the hidden folder ~/.gnome2/nemo-scripts/
and change to your liking. These are quick fixes and one backup script to a Backup folder.

But if you are using the <b>latest nemo</b> you have to place them in your home folder in 
~/local/share/nemo/scripts. Nemo has an extra menu "Plugins".



Plank
------------------
Start plank from the menu. Right-click the plank and choose preferences and put in on top. I choose as theme transparent.
But there are more themes out there if you want.
If you want to autostart this everytime.
Type in the menu " startup". Start startup applications.
Add application and choose plank or do it the old way and point to /usr/bin/plank.


Mscore fonts
---------------
If you miss the microsoft fonts ... Verdana, Courrier, Comic, Arial, ...

sudo apt-get install ttf-mscorefonts-installer -y



#4 Fun stuff

Themes and Icons
-----------------

The most fun goes in changing the look of your system. 

I have gathered a lot of themes, icons and cursors I like and bundled them here.

https://github.com/erikdubois/themes-icons-pack


The matrix
-----------

Matrix (screen with green letters as seen in the movie)

sudo apt-get install cmatrix

Try cmatrix -b



Aurora Conky
---------------
	

Aurora is a collection of conky's I like. 

Download it from http://sourceforge.net/projects/auroraconkytheme/.

Installation is described at 

http://erikdubois.be/category/conky

In this downloadfolder you will find an installationscript as well i.e. Auto_LinuxMint_Rebecca_cinnamon_aurora.sh


But basically unpack the zip file. Change the name of the unpacked folder to "Aurora" and make the hidden folder .conky and place it in in there.

Install conky-manager that will make life easy.

	sudo add-apt-repository -y ppa:teejee2008/ppa
	sudo apt-get update
	sudo apt-get install conky-manager

Start up conky-manager and choose the conky to your liking.



You should arrive at something similar depending on theme and icons choices: 

![Screenshots](http://erikdubois.be/wp-content/uploads/2015/05/final_linuxmint171.png)


![Screenshots](http://erikdubois.be/wp-content/uploads/2015/02/pimp_linux_mint.jpg)



Then you take the script apart and you write your own code.

This github script is explained more in depth on my website.

http://erikdubois.be/linux/the-ultimate-linux-mint-update

------------------------------------
#But that is the fun in Linux.

You can do whatever <b>Y O U</b> want.

Share the knowledge.
------------------------------------



