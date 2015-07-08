### If its critical error (Green screen) and you have mounted hdd ###

You can obtain log in directory _/media/hdd_ in format _enigma2\_crash\_xxxxxxxxxx.log_. There can be more of them, send me the most recently created.

### If its not a critical error, or you dont have mounted hdd, you can create log like this ###


You have to connect to satellite receiver by telnet and set in console following commands:

  * **init 4** - turns off enigma2
  * **enigma2 2> /tmp/e2.log** -turns on enigma2 and log is writing into  _/tmp/e2.log_
Now you need to get to your problem/error. As soon as you do that you can exit enigma2(in case its not critical error).
  * **killall enigma2** - turns off enigma2
  * **init 3** - enigma2 will be started in default mode

Finally log is in the _/tmp/e2.log_ file.