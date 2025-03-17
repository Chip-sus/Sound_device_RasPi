# This is application development ver 1.1

This application offers a possibility to turn a Raspberry Pi into a sound device. The 
application comes with 2 functions: a sound collector and a test tone generator.

## List of content:
	1. Configuration Instructions
	2. Installation Instructions
	3. Operation Instructions
	4. List of Files
	5. Copyright / Copyleft
	6. Contact Information
	7. Credits and Acknowledgements 


## 1. Configuration Instructions:
	Write on Linux, Raspbian OS in C language
	Use libcurl
	Use Raspberry Pi, soundcard, SD card, speakers, microphone
	
## 2. Installation Instructions:
	Set-up Raspbian OS in your SD card:
		Insert SD-card adapter into the SD-card slot of your PC or card-reader, 
			the system will inform you a USB storage device is available
		Go to website: https://www.raspberrypi.org/downloads/noobs/ and dowload
			ZIP file of "Noobs" and open
		Copy everything to your SD card
		Go to http://www.cc.puv.fi/~e1800961/ then dowload the instruction: RPi3boot.docx
			and follow the instruction

## 3. Operation Instructions:
	### SOUND COLLECTOR:
		You need a soundcard with Microphone connected to the raspberry pi

		Run "cd AppDev" command
		Run "make clean" command to remove all the previous compiled files to the origin
		Run "nano sound.h" command, choose whether using Developing mode or not by use the
			#define DEBUG or not
		Run "make" command to recompile the files needed
		Run "./sound.out" command to run the sound collector
		Use Crtl+C command to stop the program
		Run "clear" command to clear the screen

	### TEST TONE GENERATOR:
		You need a soundcard with Speakers connected to the raspberry pi

		Run "cd AppDev" command
        Run "make clean" command to remove all the previous compiled files to the origin
		Run "make" command to recompile the files needed
		Run "./sound.out .." while .. is any argument to run the test tone generator
		Choose numbers of channel 1 or 2
		If 2, choose the Left and Right frequency for 2 speakers, else choose 1 frequency
		Choose the duration of sound(from 1 to 10 sec)
		Then the testTone.wav is generated
		Now you should copy the generated testTone.wav to a remote sever by using 
			"scp testTone.wav yourEmail@zxc.zxc.zxc:." command
		Now connect to your remote account to listen to the testTone.wav

## 4. List of Files:
	makefile: for cleaning and compile files
	main.c: main structure with functions and display
	README: file about instructions
	screen.c: c file for displaying bar chart for sound level
	screen.h: defines for screen.c
	sound.h: defines for sound.c
	sound.c: c file containing functions for showing information of collected sound
		and for the test tone generator
	comm.h: defines for comm.c
	comm.c: c file contains function definition for sendDATA(), this function will 
		calculate 16000 sample for 8 pieces of Faster decibel values and send them 
		using curl library function to an URL
	sound.php: show details of tracking sound information on sever

## 5. Copyleft

## 6. Contact Information:
	Author: Huy Gia Hoang
	Contributor: Huy Hoang with the help of Dr. Gao Chao
	Email: huyhoanghp.office@gmail.com

## 7. Credits and Acknowledgements:
	Special thank to Doctor Gao Chao for helping me to complete this project
	
