
# Role SlowMode CC System Information  

## Both CCs will need to be added in order for this system to work properly.  

### The RoleSlowMode_AddtoUser.yagcc has some configurable values:  
- $removetime  
  - defaulted to 3600 seconds (1 hour)  
  - set duration in seconds.  
- $roleID  
  - defaulted to a non-ID value, you must change this to the SlowMode RoleID you create (read further down this README file)  
- $alertstaff  
  - defaulted to `true`  
  - allowed values are `true` and `false`  
    - `true` will alert the other staff members of your server that the slowmode role has been applied and when it will be removed.  
    - `false` will not alert other staff  
- $staffchannel  
  - if $alertstaff is set to `true`, this must be set to the staff channel ID  

### The MessageHandler also has configurable values:  
- $cooldown  
  - defaulted to 60 seconds  
  - set duration in seconds  
- $sendDM  
  - default value is `true`  
  - allowed values are `true` or `false`  
    - if `true`, a DM will be sent to the offending user when they are on cooldown.  
    - if `false`, no DM will be sent.  

## Prerequisites  

- Make a new role on your server. I call mine "SlowMode". I didn't change any settings for the role, and I don't have the role separate from other online members.  
  - Copy down this role's RoleID  

## Install  

- Add the 2 CCs to your server using the [YAGPDB.xyz Control Panel](https://yagpdb.xyz/manage)  
- verify configurable values on each CC  
- make sure to set the message handler's `required roles` to be the same as the "SlowMode" role you created in the prerequisites.  
