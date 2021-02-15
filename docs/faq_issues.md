# Issues Questions

## Sometimes bot stops forwarding messages. Why does this happens?

There are three reason TeleFeed can stop forwarding messages.

1.   We are doing an update. When this happens TeleFeed goes down for about 30 seconds to 5 minute
2.   You have stopped TeleFeed manually and probably forgot to turn it on. You can check this out using [/config](/commands/#config) command. Make sure <b>running</b> shows <b>Yes</b> 
3.   You probably messed up with features such as [/whitelist](/commands/#whitelist), [/blacklist](/commands/#blacklist) and  [/transformation](/commands/#transformation). When used incorrectly they can easily stop your TeleFeed account.

## TeleFeed shows Running as Off

Most of the times when users ask us why their forwarding is not working is because TeleFeed is not running. To check this you can use the [/config](/commands/#config) command. If it says <b>Running: No</b> then it means that TeleFeed is not running. 

If teleFeed is not running, use the command <b>/settings</b>, choose your phone number account and then navigate through the button <b>Bot Settings</b> and click <b>Start</b>


<div class="flex_on flex_jst_around">
<div class="flex_size-50 flex_collapse_900">
<p style="margin-bottom: -10px;"><b >TeleFeed not running, stopped manually ( Bad )</b></p>
```nohighlight
Phone Number: 2759205517
Hosted On: Server 1

Running: No
Stopped Manually: Yes

Plan: Pro
Paid On: Feb 08, 2021 22:40
Expires On: Mar 08, 2021 22:40

--------------------

REDIRECTIONID: group1
Source: 708415014
Target: 642797040
Enable: True
```

</div>
<div class="flex_size-50 flex_collapse_900">
<p style="margin-bottom: -10px;"><b >TeleFeed Running ( Good )</b></p>
```nohighlight
Phone Number: 2759205517
Hosted On: Server 1

Running: Yes


Plan: Pro
Paid On: Feb 08, 2021 22:40
Expires On: Mar 08, 2021 22:40

--------------------

REDIRECTIONID: group1
Source: 708415014
Target: 642797040
Enable: True
```
</div>
</div>
## Sometimes messages return in bad formats from original, such as after using Emoji Cleaner. How to fix? 

We are aware of this issue and normally it happens when a word or character is changed close to a link or mention. This causes the mention, link tag to move position and causes bad styling. Here's an example.

<div class="flex_on">
<div class="flex_size-33">
<p style="margin-bottom: -12px;"><u><b style="font-size: 105%; ">Original Message</b></u></p>
<p>Simplify you work with TeleFeed</br>
<span>&#9745;</span>Check TeleFeed at: <a href="#">bit.ly/telefeed</a></br>
<a href="#">@tg_feedbot</a>
</p>
</div>
<div class="flex_size-33">
<p style="margin-bottom: -12px;"><u><b style="font-size: 105%; ">Removed Emoji (No style Fix)</b></u></p>
<p>Simplify you work with TeleFeed</br>
Check TeleFeed at: b<a href="#">it.ly/telefeed</a></br>
<a href="#">@</a>tg_feedbot
</p>
</div>
<div class="flex_size-33">
<p style="margin-bottom: -12px;"><u><b style="font-size: 105%; ">Removed Emoji (Style Fix)</b></u></p>
<p>Simplify you work with TeleFeed</br>
Check TeleFeed at: <a href="#">bit.ly/telefeed</a></br>
<a href="#">@tg_feedbot</a>
</p>
</div>
</div>

This command should only be used when its needed since it can cause issues. One drawback of this command is that it creates links even if the text is not a link. This means if you have two text that are the same, one linked and the other not, both will result with links after turning on <b>Style Fix</b>

<p style="margin-bottom: -15px;"><b style="font-size: 115%; ">How to turn Style Fix on?</b></p>
1.   First run the command [/settings](/commands/#settings)
2.   Choose which number you want to change settings on
3.   Choose which setup you want to change settings on
4.   Choose redirection
5.   Toggle <b>Style Fix On</b>


## Channel Access Error. What did I do wrong?

There are three causes to this problem.

1.   You lost access to that <b>Chat.</b> Some example can be when you are removed from that chat or TeleFeed cannot write into it (in case its a Source Chat Error)
2.   Telegram chat ID's can change sometimes and this caused the error. This is known to happen on <b>Groups</b> changing to <b>Supergroups</b> and their <b>Chat ID</b> changes with them. This causes TeleFeed problems because it cannot find that chat anymore given the <b>Old ID</b>
3.   In rare cases the <b>Chat ID</b> stays the same but Telegram does not return any chat from it. The way to tell this is when you get this error and when you try to checkout /chats, you cannot find the Chat ID in question but you have every access on it (such as you can view the Chat or you can write on it in case its a Source Chat)

## Delete is not reliable. Why?

The way TeleFeed works is as a bridge between Telegram and the user. Basically TeleFeed never actually knows what the message is and what messages does a chat contains. 

Unlike Edit, telegram does not always send the Delete event to TeleFeed when that happens. We are not sure why and when this happens but we do however know about it.

There's nothing we can do about this since TeleFeed does not check messages by itself and relies on Telegram to tell him what to do.

## TeleFeed stops working everyday, need to restart.

So first of all, check every issue above and make sure everything is correctly configured such as <b>Running: Yes</b> and every setup you have shows up as <b>Enabled: Yes</b>

Now, we are aware of an issue which affects a small number of our user base. This issue has to do with Telegram closing TeleFeed connection without telling. This causes TeleFeed to keep waiting for new messages while it will never get any. This is one of the reason users with this problem can fix it by restarting TeleFeed.

The only fix to this is changing to another server location such as <b>Server 2</b>. This can be done using <b>/settings > Bot Settings > Change Server</b> | This has worked for most users with this issue. The reason this can work is because <b>Server 1</b> has a higher load and higher connection to Telegram which might result in Telegram terminating a few of them. The second server can only be used by Paid Users and has higher resources and a limit on how many users can be there. This is to ensure a better connection with Telegram and performance for all our Paid Users.

## Messages are delayed. What can I do?

TeleFeed currently uses at max 300 ms to process a message. This means the delay TeleFeed adds itself to a forward is at max 300 ms. There are a few features which can add up to 20 second delay depending on the message such as /action (will delay when it waits for the message to show after the button is clicked), /transformation power (will delay in case the user is using bitly and its waiting for bitly api).

There are a few cases which we now that might cause delays in users forwarding setups.

### Delay from big channels, groups
From our tests we have noticed that a group such as <b>Binance English</b> which has around 200,000 members, causes a delay of up to 40 seconds. This happens from <b>Telegram</b> side and there's nothing TeleFeed can do

### Delay in peak times for Free Users
TeleFeed uses two server to connect with Telegram so we can offer better service to our users. Free users currently reside on <b>Server 1</b>. We have noticed that in peak hours, telegram might start dropping connections to some users on Server 1 or delaying messages. This does not happen on Server 2 because we have capped the amount of users that can be on that server at once. If any user is looking for the best TeleFeed performance, we suggest buying any <b>Paid Plan</b> such as <b>Basic Plan</b> and switch to server 2 to get the highest speed possible.


## I was trying out /whitelist or /blacklist and now redirections do not work. What can I do?

You probably messed up the regex while using /whitelist or /blacklist and now the messages do not pass because of that. The way to fix this is by simple clearing all your settings for that command. Refer to [/whitelist](/commands/#whitelist) or [/blacklist](/commands/#blacklist) to learn how to use them.

## I was trying out /transformation and now messages format is totally wrong. What can I do?

You can clear /transformation command using the following syntax

```nohighlight
/transformation remove REDIRECTIONID on PHONE_NUMBER
```

It will remove every config you have on that group using /transformation

You can read more about this on the command help over at [/transformation](/commands/#transformation)

## My Telegram account got banned, limited. What can I do?

First of all we want to let you know that its impossible for TeleFeed to get your account banned. We have rigorously tested TeleFeed and <b>None</b> of our accounts were every banned.

We do however know that if someone uses a VOIP phone number, there's a chance to get banned using TeleFeed. Reason for this is that VOIP accounts are limited by Telegram the moment they join the platform. This was confirmed by Telegram itself so there's nothing we can do.

TeleFeed is a tool to gather information into one channel or split your channels into multiple channels. If you use to it spam Users and Groups, you will defenitly get banned. This is not because of using TeleFeed but because you will get reported and often resulting in a ban for your account.

If you use TeleFeed as it was intended we can guarantee you that your account will never get banned.
