# FAQ

Here you will find answers to every questions you might have about the bot and the way it works.

## General Questions

#### Why do I have to give account access to your bot?

There are many reasons why our bot needs account access and to cover them all here would be a long read so instead we will show you an example of features between a bot which can be used without account connection and our bot.


<table style="margin-bottom: 20px;">
  <tr>
    <th style="padding:10px 20px;">Features</th>
    <th style="padding:10px 20px;">Without Account</th>
    <th style="padding:10px 20px;">Us</th>
  </tr>
  <tr>
    <td style="padding:10px 20px;">Forward from channels</td>
    <td style="padding:10px 20px; text-align:center;">Yes</td>
    <td style="padding:10px 20px; text-align:center;">Yes</td>
  </tr>
  <tr>
    <td style="padding:10px 20px;">Forward Private Channel</td>
    <td style="padding:10px 20px; text-align:center;">Yes (if you can get the bot to join)</td>
    <td style="padding:10px 20px; text-align:center;">Yes</td>
  </tr>
  <tr>
    <td style="padding:10px 20px;">Forward channel without join</td>
    <td style="padding:10px 20px; text-align:center;">No</td>
    <td style="padding:10px 20px; text-align:center;">Yes</td>
  </tr>
  <tr>
    <td style="padding:10px 20px;">Forward User/Bot</td>
    <td style="padding:10px 20px; text-align:center;">No</td>
    <td style="padding:10px 20px; text-align:center;">Yes</td>
  </tr>
  <tr>
    <td style="padding:10px 20px;">Forward in Rewrite Mode</td>
    <td style="padding:10px 20px; text-align:center;">No (its a bot after all)</td>
    <td style="padding:10px 20px; text-align:center;">Yes</td>
  </tr>
  <tr>
    <td style="padding:10px 20px;">Read/Send message to every channel</td>
    <td style="padding:10px 20px; text-align:center;">No (Needs admin access)</td>
    <td style="padding:10px 20px; text-align:center;">Yes</td>
  </tr>
  <tr>
    <td style="padding:10px 20px;">One-Many, Many-One Redirections</td>
    <td style="padding:10px 20px; text-align:center;">No</td>
    <td style="padding:10px 20px; text-align:center;">Yes</td>
  </tr>
  <tr>
    <td style="padding:10px 20px;">Filtering</td>
    <td style="padding:10px 20px; text-align:center;">Probably (depends on the bot)</td>
    <td style="padding:10px 20px; text-align:center;">Yes</td>
  </tr>
  <tr>
    <td style="padding:10px 20px;">Whitelist/Blacklist</td>
    <td style="padding:10px 20px; text-align:center;">Probably (depends on the bot)</td>
    <td style="padding:10px 20px; text-align:center;">Yes</td>
  </tr>
  <tr>
    <td style="padding:10px 20px;">Text Manipulation</td>
    <td style="padding:10px 20px; text-align:center;">Probably (depends on the bot)</td>
    <td style="padding:10px 20px; text-align:center;">Yes</td>
  </tr>
</table>  


If you just need a bot to forward messages without <b>Rewrite Mode</b> and you have access to the channels you want to Forward From and To (you need to be a admin there) than you can use a bot without account access if that worries you. Our bot has many more advance features than any other bot but we do understand that users have their own privacy concerns.


#### Can I forward from a channel I don't have access?

<b>No.</b> This bot can only see channels you as a user can see. So basically if you don't have access to a channel, the bot cannnot forward from it.

#### Can I forward from a private channel?

Yes. You can forward from a private channel as long as you as a user are joined on that channel.

#### Can I add my own text format (beginning, end, change words, add words) of the forwarded message?

<B>Yes.</B> There are many features that allow you to have total control on how the forwarded message look. You can change the text format however you want using [/transformation](/commands/#transformation)</b>

#### Do I have control over what messages gets forwarded?

<b>Yes.</b> You have features such as [/settings](/commands/#settings)</b> where you can filter out which messages you want to <b>pass</b> or <b>not pass.</b> There's [/whitelist](/commands/#whitelist)</b> and [/blacklist](/commands/#blacklist)</b> which allows you to filter messages out based on <b>keywords</b> and [/selectusers](/commands/#selectusers)</b> which allows you to filter messages based on the user who sent them.

#### Can I choose which user (users) I want to allow messages from within a channel?

<b>Yes.</b> You can do that using [/selectusers](/commands/#selectusers)</b>

#### Can I filter out duplicates?

1.   First run the command [/settings](/commands/#settings)
2.   Choose which number you want to change settings on
3.   Choose which setup you want to change settings on
4.   Choose redirection
5.   Toggle <b>Process Duplicates Off</b>

#### Can I filter out myself?

1.   First run the command [/settings](/commands/#settings)
2.   Choose which number you want to change settings on
3.   Choose which setup you want to change settings on
4.   Choose redirection
5.   Toggle <b>Process Me Off</b>

#### I want to remove all links from source channel. How do I do that?

1.   First run the command [/settings](/commands/#settings)
2.   Choose which number you want to change settings on
3.   Choose which setup you want to change settings on
4.   Choose cleaner
5.   Toggle <b>Urls On</b>

#### I want to remove all mentions from source channel. How do I do that?

1.   First run the command [/settings](/commands/#settings)
2.   Choose which number you want to change settings on
3.   Choose which setup you want to change settings on
4.   Choose cleaner
5.   Toggle <b>Mention On</b>

#### I need to do some complex filtering, I think I need to use a regular expression. Could you please help me to set it up?

Sorry but we don't have time to consult you on regular expressions. Read an article online or just google your case and find a ready solution.

There is a very convenient instrument to test regular expressions: https://regex101.com. Set the Flavor to "python" and set the flag "Single line: Dot matches the new line". This will make it work in the same way as @tg_feedbot's matcher


#### I do not understand the documentation, video or help pages. Can you setup TeleFeed for me?

We are trying our best to make TeleFeed as user friendly as possible. If you think that something is lacking you are invited to contact us so we can improve it further. We cannot however setup users accounts ourself. If you are having issues finding some command you can contact us and we will gladly help.

#### Does this bot have any message limitation?

<b>No.</b> We don't have any message limitations in place.

#### Does this bot delay messages?

<b>No.</b> Our bot does not delay messages apart from user specified delay.

#### I want to move my paid plan to another account

You can use the [/planswap](/commands/#planswap) feature to move your <b>Paid Plan</b> to another account. Please refer to [/planswap](/commands/#planswap) documentation to learn how to use it.

## Issues Questions

#### Sometimes bot stops forwarding messages. Why does this happens?

There are three reason TeleFeed can stop forwarding messages.

1.   We are doing an update. When this happens TeleFeed goes down for about 30 seconds to 5 minute
2.   You have stopped TeleFeed manually and probably forgot to turn it on. You can check this out using [/config](/commands/#config) command. Make sure <b>running</b> shows <b>on</b> 
3.   You probably messed up with features such as [/whitelist](/commands/#whitelist), [/blacklist](/commands/#blacklist) and  [/transformation](/commands/#transformation). When used incorrectly they can easily stop your TeleFeed account.

#### I was trying out /whitelist or /blacklist and now redirections do not work. What can I do?

You probably messed up the regex while using /whitelist or /blacklist and now the messages do not pass because of that. The way to fix this is by simple clearing all your settings for that command. Refer to [/whitelist](/commands/#whitelist) or [/blacklist](/commands/#blacklist) to learn how to use them.

#### I was trying out /transformation and now messages format is totally wrong. What can I do?

You can clear /transformation command using the following syntax

```nohighlight
/transformation remove REDIRECTIONID on PHONE_NUMBER
```

It will remove every config you have on that group using /transformation

You can read more about this on the command help over at [/transformation](/commands/#transformation)

#### My Telegram account got banned, limited. What can I do?

First of all we want to let you know that its impossible for TeleFeed to get your account banned. We have rigorously tested TeleFeed and <b>None</b> of our accounts were every banned.

We do however know that if someone uses a VOIP phone number, there's a chance to get banned using TeleFeed. Reason for this is that VOIP accounts are limited by Telegram the moment they join the platform. This was confirmed by Telegram itself so there's nothing we can do.

TeleFeed is a tool to gather information into one channel or split your channels into multiple channels. If you use to it spam Users and Groups, you will defenitly get banned. This is not because of using TeleFeed but because you will get reported and often resulting in a ban for your account.

If you use TeleFeed as it was intended we can guarantee you that your account will never get banned.
