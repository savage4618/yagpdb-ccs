# THIS IS A WORK IN PROGRESS


# YOU probably shouldn't use it yet.


`joinmessage.yagcc` adds new users only to db entry. If a user leaves and rejoins, they will not get added a second time. (as I typed this up, I realized there is a leave message action that should remove the existing users, also eliminating duplicates `¯\_(ツ)_/¯`)

`leavemessage.yagcc` removes members that leave from the database.

`mainCC.yagcc` there are currently a couple of configurable variables:
- $shoutoutchannel : 
  - set this to `nil` if you want the message to be sent where you ran the command
  - set to a channel id if you want it to send to a specific channel
- $message : I made it so the CC currently takes the `.StrippedMsg` from the trigger as the "welcome" message, because I didn't want a static/generic welcome message when I ran it, but you can change this variable to be whatever you would like `¯\_(ツ)_/¯`
## IF YOU *__DO__* WANT A STATIC WELCOME MESSAGE
- you need to remove the `{{$Args := parseArgs 1 "" (carg "string" "Welcome message")}}` line as it will make your command not run unless you give it a message.

Currently, the `maincc.yagcc` command is set up to run via a `Trigger` command type, but it could be easily modified to be ran as an `interval` CC. I felt the interval route took away the personalization that could be added, so I didn't pursue this.

Once the main CC runs, the database entires are deleted, leaving a clean slate for the next members who join. 

---
# YOU NEED ALL 3 PIECES OF CODE FOR THIS SYSTEM TO WORK CORRECTLY
