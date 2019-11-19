# archivalTool
This application auto archives files

Files associated with app:
["Archive App.exe"]["config_settings.ini"]["logging_info.txt"]

[CONFIG_SETTINGS.INI]
'''This file allows for settings changes associated with the application'''
[1] ROOT: the root filepath associated with the destination, where final destination will be found in year > month folder.

[2] LOGGING: the filepath of original logging file is stored. 

[3] INTERVAL: sleep_interval is how long (in seconds) the program should sleep before running again.

+++ IF INTERVAL = 0, THE PROGRAM WILL STOP AFTER A SINGLE RUN +++

[USAGE]
[1] When application is initiated, a window (all black) pops up with the title of the absolute filepath of the folder the application was ran from. 
[1A] In order for the program to loop, this window should be minimized and ignored. Thus, for strictly manual runs, close the window after ~5 seconds (max time needed for program to finish). 

[LOGGING]
[1] Information is logged at an INFO level. 
[2] The data stored here tracks how many files were ran out of total files checked and UTC time.

[APPLICATION]
[1] Running code essentially accomplishes the following:

+ Checks the last date modified of every file in 'Endpoint'
+ If last date modified is greater than 2 weeks ago, the code will retrieve -
	+ destination path (Archive01)
	+ find current year action is taking place
	+ converts last date modified into a string format (%m_%b %Y)
	+ converts information - destination path + current year + last date modified into a final absolute destination path
	+ moves file to path

[2] Programs sleeps for x amount of seconds. During which, no processing is occuring or memory in use. 

< INTERVAL TABLE >
1 hr = 3600
24 hrs = 86400
Run Once = 0
