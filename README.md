Late December to Early January
-	Install the necessary software (Python, gcc, Jython, Eclipse, ADT)
-	Familiarize with the software and MonkeyRunner and MonkeyHelper
-	Read Reran paper to understand their approach to recording and replaying
-	Was difficult to install and run gcc, but managed to get it done eventually.

Mid-January-Mid-February
-	Getting Reran to run properly on computer
1.	Obtaining recordedEvents log
-	Was able to obtain a recordedEvents file using the getEvent Android tool
-	Example of a line of code for recordedEvents (time stamp, name of device, type, code value)
-	[   12038.799108] /dev/input/event0: 0003 0000 00000157
-	A detailed description of the code can be found on https://github.com/mingyuan-xia/MonkeyHelper/wiki/_pages
2.	Using Translate.java to translate the events
-	Created a java.jar file of translate.java
-	Pushed the translate.java file onto the Android device and was able to obtain a translatedEvents file
-	The translatedEvents file was not the correct file due to bugs in the code
o	The space character of “ “ was used, but did not work, so I change the space to “//s+”
o	There were other minor tweaks to the code
o	After the code was fixed, the translatedEvents file worked nicely.
-	Was able to translate
[   12038.799108] /dev/input/event0: 0003 0000 00000157
into 0,0,3,0,336
-	The format is identical (time stamp, name of device, type, code value)
3.	Using replay.c to replay translatedEvents onto the Android
-	It was very difficult to install gcc cross-compiler on a mac
-	Installed the cross-compiler onto a PC, compiled replay.c on a windows computer and then transferred the compiled file onto a Mac
-	The cross compiler was installed from this website. Sourcery CodeBench for ARM Lite on Linux. https://sourcery.mentor.com/GNUToolchain/release2450
-	There was an error, ./replay: not executable: magic 7F45, which meant that the compiled file using the cross compiler was not recognized by the android device

Mid-February to Present
-	Read and understood translate.java and wrote a python equivalent of the program. (able to translate recordedEvents.txt to translatedEvents.txt)
-	Reading and Understanding replay.c to eventually write a python equivalent
Finally, integrate and merge the two python programs and communicate with MonkeyRunner and MonkeyHel
