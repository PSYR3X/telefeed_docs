# Known Limitations
## Performance Sucks! Why can't I send 1000 messages at once?

Probably most of you don't know but telegram api has limitations on the number of requests we can do at once. Sending lots of requests at once <B>is possible</B> if you want your account to keep getting <b>temporary</b> or <b>permanently</b> banned by telegram.  

__Our bot has the highest performance you can ever get from any bot of this kind__

## I enable "Process Forward" and now /transformation doesn't work.

This is a known <b>limitation of Telegram API</b>. We can't do anything about it (since its not something broken on our side).

There's a solution to this which you can setup with our bot. Follow the <b>instructions</b> below.

__We will use the following Dummy values for showing this setup!__  
__SOURCE:__ 1238728137  
__DUMMY_TARGET:__ 213812387  
__TARGET:__ 1230821390   


__1.__ First you will need to setup a redirection from your <b>SOURCE</b> chat/user/bot to a <B>dummy</B> channel as <B>TARGET</B>  

```nohighlight
## Command
/redirection add dummy_setup on 2759205517

## Input
1238728137 - 213812387
```

__2.__ Now you will setup another redirection using the dummy channel as <B>SOURCE</B> and the chat/user/bot you want the message to end to as <b>TARGET</b>  

```nohighlight
## Command
/redirection add real_grp on 2759205517

## Input
213812387 - 1230821390
```

__3.__ After setting both <B>redirections</B>. You will need to use the <b>/settings</b> command. Enable <b>Process Forward</b> for <B>real_grp</B> and your done here.  
__4.__ Now if you want to use <B>/transformation</B>, you can just use it with the REDIRECTIONID as <b>dummy_setup</b>

What this setup basically does is processing messages without <b>Process Forward</b> to a dummy channel then you <b>can forward the modified message</b> from there to your actual channel/group/user etc.
