## General Questions

### Why do I have to give account access to your bot?

There are many reasons why our bot needs account access and to cover them all here would be a long read so instead we will show you an example of features between a bot which can be used without account connection and our bot.


<table style="margin-bottom: 20px;">
  <tr>
    <th style="">Features</th>
    <th style=";">No Account</th>
    <th style=";">Us</th>
  </tr>
  <tr>
    <td style=";">Forward from public channels</td>
    <td style="; text-align:center;">Yes</td>
    <td style="; text-align:center;">Yes</td>
  </tr>
  <tr>
    <td style=";">Forward Private Channel</td>
    <td style="; text-align:center;">No</td>
    <td style="; text-align:center;">Yes</td>
  </tr>
  <tr>
    <td style=";">Forward channel without join</td>
    <td style="; text-align:center;">No</td>
    <td style="; text-align:center;">Yes</td>
  </tr>
  <tr>
    <td style=";">Forward User/Bot</td>
    <td style="; text-align:center;">No</td>
    <td style="; text-align:center;">Yes</td>
  </tr>
  <tr>
    <td style=";">Forward in Rewrite Mode</td>
    <td style="; text-align:center;">No (its a bot after all)</td>
    <td style="; text-align:center;">Yes</td>
  </tr>
  <tr>
    <td style=";">Read/Send message to every channel</td>
    <td style="; text-align:center;">No (Needs admin access)</td>
    <td style="; text-align:center;">Yes</td>
  </tr>
  <tr>
    <td style=";">One-Many, Many-One Redirections</td>
    <td style="; text-align:center;">No</td>
    <td style="; text-align:center;">Yes</td>
  </tr>
  <tr>
    <td style=";">Filtering</td>
    <td style="; text-align:center;">Probably (depends on the bot)</td>
    <td style="; text-align:center;">Yes</td>
  </tr>
  <tr>
    <td style=";">Whitelist/Blacklist</td>
    <td style="; text-align:center;">Probably (depends on the bot)</td>
    <td style="; text-align:center;">Yes</td>
  </tr>
  <tr>
    <td style="padding:10px 20px;">Text Manipulation</td>
    <td style="padding:10px 20px; text-align:center;">Probably (depends on the bot)</td>
    <td style="padding:10px 20px; text-align:center;">Yes</td>
  </tr>
</table>  


If you just need a bot to forward messages without <b>Rewrite Mode</b> and you have access to the channels you want to Forward From and To (you need to be a admin there) than you can use a bot without account access if that worries you. Our bot has many more advance features than any other bot but we do understand that users have their own privacy concerns.

### Is TeleFeed Free?

TeleFeed currently offers a <b>Free plan</b> and three <b>Paid Plans</b>. Users enjoy unlimited message forwarding in the free plan and up to 5 redirection setup. The only downside of the free plan is <b>advertisment</b>. TeleFeed posts advertisment messages on users Targets in the <b>Free Plan</b>. To remove the ads, the user can upgrade to <b>Basic Plan</b> for 7$ monthly payment.

<div class="faq-plans">
<div>
<p style="margin-bottom: 0px;"><u><b style="font-size: 105%; ">Free Plan</b></u></p>
<b>[x]</b> Ads</br>
<b>[x]</b> 5 Forwarding Setup</br>
<b>[x]</b> 5 Many to One ID's allowed
</div>

<div>
<p style="margin-bottom: 0px;"><u><b style="font-size: 105%; ">Basic Plan ( 7$ )</b></u></p>
<b>[x]</b> No Ads</br>
<b>[x]</b> 15 Forwarding Setup</br>
<b>[x]</b> 15 Many to One ID's allowed</br>
<b>[x]</b> Edit, Delete, Reply</br>
<b>[x]</b> Forward To Bots</br>
<b>[x]</b> Duplicate Filtering</br>
<b>[x]</b> Clone
</div>

<div>
<p style="margin-bottom: 0px;"><u><b style="font-size: 105%; ">Plus Plan ( 12$ )</b></u></p>
<b>[x]</b> Unlimited Redirections</br>
<b>[x]</b> Clone</br>
<b>[x]</b> Edit, Delete, Reply</br>
<b>[x]</b> Duplicate Filtering</br>
<b>[x]</b> Filters</br>
<b>[x]</b> Cleaners</br>
<b>[x]</b> Transformation (No Url Keys)</br>
<b>[x]</b> Scheduler</br>
<b>[x]</b> Delay
</div>

<div>
<p style="margin-bottom: 0px;"><u><b style="font-size: 105%; ">Pro Plan ( 15$ )</b></u></p>
<b>[x]</b> Unlimited Redirections</br>
<b>[x]</b> Clone</br>
<b>[x]</b> Edit, Delete, Reply</br>
<b>[x]</b> Duplicate Filtering</br>
<b>[x]</b> Filters</br>
<b>[x]</b> Cleaners</br>
<b>[x]</b> Transformation</br>
<b>[x]</b> Scheduler</br>
<b>[x]</b> Delay</br>
<b>[x]</b> Whitelist</br>
<b>[x]</b> Blacklist</br>
<b>[x]</b> Watermark</br>
<b>[x]</b> Action</br>
<b>[x]</b> SelectUsers
</div>
</div>

### Can I forward from a channel I don't have access?

<b>No.</b> This bot can only see channels you as a user can see. So basically if you don't have access to a channel, the bot cannnot forward from it.

### Can I forward from a private channel?

Yes. You can forward from a private channel as long as you as a user are joined on that channel.

### Can I add my own text format (beginning, end, change words, add words) of the forwarded message?

<B>Yes.</B> There are many features that allow you to have total control on how the forwarded message look. You can change the text format however you want using [/transformation](/commands/#transformation)</b>

### Do I have control over what messages gets forwarded?

<b>Yes.</b> You have features such as [/settings](/commands/#settings)</b> where you can filter out which messages you want to <b>pass</b> or <b>not pass.</b> There's [/whitelist](/commands/#whitelist)</b> and [/blacklist](/commands/#blacklist)</b> which allows you to filter messages out based on <b>keywords</b> and [/selectusers](/commands/#selectusers)</b> which allows you to filter messages based on the user who sent them.

### Can I choose which user (users) I want to allow messages from within a channel?

<b>Yes.</b> You can do that using [/selectusers](/commands/#selectusers)</b>

### Can I filter out duplicates?

1.   First run the command [/settings](/commands/#settings)
2.   Choose which number you want to change settings on
3.   Choose which setup you want to change settings on
4.   Choose redirection
5.   Toggle <b>Process Duplicates Off</b>

### Can I filter out myself?

1.   First run the command [/settings](/commands/#settings)
2.   Choose which number you want to change settings on
3.   Choose which setup you want to change settings on
4.   Choose redirection
5.   Toggle <b>Process Me Off</b>

### I want to remove all links from source channel. How do I do that?

1.   First run the command [/settings](/commands/#settings)
2.   Choose which number you want to change settings on
3.   Choose which setup you want to change settings on
4.   Choose cleaner
5.   Toggle <b>Urls On</b>

### I want to remove all mentions from source channel. How do I do that?

1.   First run the command [/settings](/commands/#settings)
2.   Choose which number you want to change settings on
3.   Choose which setup you want to change settings on
4.   Choose cleaner
5.   Toggle <b>Mention On</b>

### I need to do some complex filtering, I think I need to use a regular expression. Could you please help me to set it up?

Sorry but we don't have time to consult you on regular expressions. Read an article online or just google your case and find a ready solution.

There is a very convenient instrument to test regular expressions: https://regex101.com. Set the Flavor to "python" and set the flag "Single line: Dot matches the new line". This will make it work in the same way as @tg_feedbot's matcher


### I do not understand the documentation, video or help pages. Can you setup TeleFeed for me?

We are trying our best to make TeleFeed as user friendly as possible. If you think that something is lacking you are invited to contact us so we can improve it further. We cannot however setup users accounts ourself. If you are having issues finding some command you can contact us and we will gladly help.

### Does this bot have any message limitation?

<b>No.</b> We don't have any message limitations in place.

### Does this bot delay messages?

<b>No.</b> Our bot does not delay messages apart from user specified delay.

### I want to move my paid plan to another account

You can use the [/planswap](/commands/#planswap) feature to move your <b>Paid Plan</b> to another account. Please refer to [/planswap](/commands/#planswap) documentation to learn how to use it.

## Issues Questions

### Sometimes bot stops forwarding messages. Why does this happens?

There are three reason TeleFeed can stop forwarding messages.

1.   We are doing an update. When this happens TeleFeed goes down for about 30 seconds to 5 minute
2.   You have stopped TeleFeed manually and probably forgot to turn it on. You can check this out using [/config](/commands/#config) command. Make sure <b>running</b> shows <b>Yes</b> 
3.   You probably messed up with features such as [/whitelist](/commands/#whitelist), [/blacklist](/commands/#blacklist) and  [/transformation](/commands/#transformation). When used incorrectly they can easily stop your TeleFeed account.

### TeleFeed shows Running as Off

Most of the times when users ask us why their forwarding is not working is because TeleFeed is not running. To check this you can use the [/config](/commands/#config) command. If it says <b>Running: No</b> then it means that TeleFeed is not running. 

If teleFeed is not running, use the command <b>/settings</b>, choose your phone number account and then navigate through the button <b>Bot Settings</b> and click <b>Start</b>


<p style="margin-bottom: 0px;"><b style="font-size: 115%; ">TeleFeed not running, stopped manually</b></p>
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

<p style="margin-bottom: 0px;"><b style="font-size: 115%; ">TeleFeed Running</b></p>
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

### Channel Access Error. What did I do wrong?

There are three causes to this problem.

1.   You lost access to that <b>Chat.</b> Some example can be when you are removed from that chat or TeleFeed cannot write into it (in case its a Source Chat Error)
2.   Telegram chat ID's can change sometimes and this caused the error. This is known to happen on <b>Groups</b> changing to <b>Supergroups</b> and their <b>Chat ID</b> changes with them. This causes TeleFeed problems because it cannot find that chat anymore given the <b>Old ID</b>
3.   In rare cases the <b>Chat ID</b> stays the same but Telegram does not return any chat from it. The way to tell this is when you get this error and when you try to checkout /chats, you cannot find the Chat ID in question but you have every access on it (such as you can view the Chat or you can write on it in case its a Source Chat)

### TeleFeed stops working everyday, need to restart.

So first of all, check every issue above and make sure everything is correctly configured such as <b>Running: Yes</b> and every setup you have shows up as <b>Enabled: Yes</b>

Now, we are aware of an issue which affects a small number of our user base. This issue has to do with Telegram closing TeleFeed connection without telling. This causes TeleFeed to keep waiting for new messages while it will never get any. This is one of the reason users with this problem can fix it by restarting TeleFeed.

The only fix to this is changing to another server location such as <b>Server 2</b>. This can be done using <b>/settings > Bot Settings > Change Server</b> | This has worked for most users with this issue. The reason this can work is because <b>Server 1</b> has a higher load and higher connection to Telegram which might result in Telegram terminating a few of them. The second server can only be used by Paid Users and has higher resources and a limit on how many users can be there. This is to ensure a better connection with Telegram and performance for all our Paid Users.

### I was trying out /whitelist or /blacklist and now redirections do not work. What can I do?

You probably messed up the regex while using /whitelist or /blacklist and now the messages do not pass because of that. The way to fix this is by simple clearing all your settings for that command. Refer to [/whitelist](/commands/#whitelist) or [/blacklist](/commands/#blacklist) to learn how to use them.

### I was trying out /transformation and now messages format is totally wrong. What can I do?

You can clear /transformation command using the following syntax

```nohighlight
/transformation remove REDIRECTIONID on PHONE_NUMBER
```

It will remove every config you have on that group using /transformation

You can read more about this on the command help over at [/transformation](/commands/#transformation)

### My Telegram account got banned, limited. What can I do?

First of all we want to let you know that its impossible for TeleFeed to get your account banned. We have rigorously tested TeleFeed and <b>None</b> of our accounts were every banned.

We do however know that if someone uses a VOIP phone number, there's a chance to get banned using TeleFeed. Reason for this is that VOIP accounts are limited by Telegram the moment they join the platform. This was confirmed by Telegram itself so there's nothing we can do.

TeleFeed is a tool to gather information into one channel or split your channels into multiple channels. If you use to it spam Users and Groups, you will defenitly get banned. This is not because of using TeleFeed but because you will get reported and often resulting in a ban for your account.

If you use TeleFeed as it was intended we can guarantee you that your account will never get banned.
