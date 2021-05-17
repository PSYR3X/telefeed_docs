# General Questions

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
    <td style=";">Forward channel without bot join</td>
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

### Can I forward replies and deletes?

1.   First run the command [/settings](/commands/#settings)
2.   Choose which number you want to change settings on
3.   Choose which setup you want to change settings on
4.   Choose redirection
5.   Toggle <b>Process Reply On</b> or <b>Process Delete On</b>

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
