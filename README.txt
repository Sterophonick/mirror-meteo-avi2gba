---------------ALL YOU NEED TO KNOW ABOUT HOW TO CREAT GBA VIDEO---------------
-------------------------------------------------------------------------------
several version of METEO (Project Comet) are included. Meteo is used to convert video 
files to .gba roms

METEO 1.3.1 - English Translation by Mike_Haggar
necessary for 256mb Multicart videos  
Videos must be in .avi, .mpg, .mpeg, .wmv, or .asf format 
from my testing DIVX and MPEG1 are the only video codecs that work reliably (MPEG1 
is better for longer or multicart) and MP2 or MP3 audio codecs (MP2 is better for 
longer or multicart)


Meteo 1.4.0 - English Translation by ? Sterophonick ?
better compression as long as it fits on 16mb or 32mb flash carts
More codecs supported 


Meteo 1.5.0 - English Translation by kran27
same functionality as 1.4.0 but with better ui and translation and the ability 
to exceed the 32mb hard limit (WILL NOT BE FLASHABLE SINCE THE GBA CAN ONLY 
ADDRESS 32mb AT A TIME)
------------------------------------------------------------------------------

HOW TO STEPS: 

1. Download or create the video of your choice using the method of your choice.
2. use FFMEG to convert the video to .mpg using the following code: ffmpeg -i Input -c:v mpeg1video -c:a mp2 -vf "scale=240:160:force_original_aspect_ratio=decrease,pad=240:160:(ow-iw)/2:(oh-ih)/2" -b:v 2M -b:a 384k -af "loudnorm,volume=8.0" Output.mpg
where the Input and output are full file strings 
(i.e " "C:\Users\YourName\Downloads\Video.mpg" ")
	* if you must... use  https://video.online-convert.com/convert-to-avi to 
	covert the video to a file that will work (but not reliably for multicart)
3. Open Meteo 
4. In the top box (Movie File) browse for the output.mpg file 
5. In the next box (GBA ROM File) browse or type in and select the destination of 
your GBA ROM include the file name and .gba 
6. (optional) In the next box (ROM Title), give the ROM an internal name that will 
be recognized by the cart reader.
7. Configure the Bitrate and Conversion Settings (see below sweet spots or just 
tinker with it) 
8. Click Process and wait. If the resulting file is too big (bigger than 32mb) you 
will get an "Input File Error". Try again with another configuration. 
9. Drag the resulting rom.gba file onto the gbafix.exe program which will patch
the rom to be aboe to be written to flash cartridges. 
10. If you are creating a multi cart with up to 8x 32mb roms you will need to 
either manually copy and past the code into the blank multicart menu files or use 
the patches for without menus. To patch use the include lips rom patcher. on the 
multicart left and right can navigate between video rom files (no other navigation 
currently possible)
11. (optional, but come on, if you are doing this then you are going to do this 
step) upload onto a flash cartridge
12. Enjoy!

Credits: DarkFader, gameboy-advance.net, inside-cap, Mike_Haggar, Sterophonick, 
BennVenn, and probably a bunch of others I am forgetting 
-------------------------------------------------------------------------------
Some "Sweet Spots" for compression:

Great quality: This is the best way to view trailers and clips, but only allows one on a 256 MBit cartridge
Bitrate: 60
Framerate: 15 fps
Settings: No trim, manual resize 240x160, 4x dither
Average maximum amount of minutes: 8 minutes

Nice quality: These settings are best to store multiple trailers and clips, yet still having very nice quality
Bitrate: 28
Framerate: 12 fps
Settings: No trim, manual resize 216x144, 4x dither
Average maximum amount of minutes: 15 minutes

Lesser quality: These settings can hold most episodes, and still looking great for such a long movie
Bitrate: 12
Framerate: 7.5 fps
Settings: No trim, manual resize 204x136, 4x dither
Average maximum amount of minutes: 25 minutes

Compression quality: The longest recording time with still acceptable video
Bitrate: 8
Framerate: 6 fps
Settings: No trim, manual resize 192x128, 4x dither
Average maximum amount of minutes: 31 minutes