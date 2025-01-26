### This system handles kicking of users if they didn't agree to the rules within a certain amount of time. This can be helpful to avoid idle users or bots that don't "verify"

### Prerequisites:
 - `verified` or equivalent role (save the role id for later)
 - `Kick` moderation action must be enabled.


### Instructions to get started:

1. Create a verified role or "members" role and give it all the general permissions the @everyone role would typically have. Make sure that the @everyone has no permissions.
1. Create a rolemenu that gives the verified role in the desired channel (type ;rm in ⁠testing for a tutorial on how to do so).
1. Make sure to create permission overrides in the channel for the @everyone role so that users are able to view and react to the message.
1. Add the `KickCC.yagcc` as a `None` Trigger. Note the CCID. 
    1. change the `$roleID` variable to match the `verfied` role you created earlier.
1. Add the `JoinMessage.yagcc` into the Join Message (Notifications & Feeds > General > Join Message)
    1. change the configurable variables:
        1. `$ccID` to the KickCC you created earlier.
        1. `$channelID` to the logging channel you want the KickCC to run in
        1. `$time` to the amount of seconds you want to delay before executing the kick. It is defaulted to 7 days.
1. Add the `LeaveMessage.yagcc` into the Leave Message (Notifications & Feeds > General > Leave Message)
    - The Leave Mesasge code handles cleaning up of anyone that left the server before you sent the announcement message.
