{%set action = "<a href='#commands-arguments-meaning'>action</a>" %}
{%set redirectionid = "<a href='#commands-arguments-meaning'>redirectionid</a>" %}
{%set feature = "<a href='#commands-arguments-meaning'>feature</a>" %}
{%set phonenumber = "<a href='#commands-arguments-meaning'>phonenumber</a>" %}
{%set amount = "<a href='#commands-arguments-meaning'>amount</a>" %}

# Commands

In this documentation you will find every TeleFeed command and examples on how to use them. We suggest you read this documentation from the start so you can learn more about each feature TeleFeed supports. Every <u>Example Command</u> you see in this documentation is using <u>dummy values</u> so don't copy and paste it.

#### Commands Arguments Meaning

* <b>PhoneNumber:</b> Used to specify which <b>connected account</b> you want to use the command on.
* <b>RedirectionID:</b> Used to specify on which <b>redirection setup</b> you want to use.
* <b>Action:</b> Used to specify what you want to do with the command. Supported actions are <b>Add, Remove, Change</b> and <b>Clear</b>.
* <b>Feature</b> Some commands contain more than one feature inside. With this argument you need to specify which feature you want to use.
* <b>Amount</b> Specify the amount in numbers for the given command. Commands such as /delay use this argument to specify seconds.


## Connect

This command is used for connecting telegram accounts with <b>TeleFeed</b>. You need to run this first before trying to run other commands since they rely on you having a number connected.

!!! Example "Command"
    <p style="font-size: 16px">/connect  {{phonenumber}}</p>


<b  style="font-size: 115%;">Command Example</b>

<p style="margin-bottom: -13px; font-size: 14px;">Connecting to TeleFeed with PHONE_NUMBER=<b>2759205517</b></b></p>
```nohighlight
/connect 2759205517
```

Connecting to <b>TeleFeed</b> with the number 2759205517  
Remember to always add your <b>country prefix</b> otherwise the connection might fail.

After you type the command with your <b>OWN TELEGRAM PHONE NUMBER</b>, <b>TeleFeed</b> will ask you to enter the code that you got from telegram (Its a 5 digit code number).

Make sure to follow every instruction from <b>TeleFeed</b> (such as when it asks you to enter the code with aa in front).

If you are using a <b>Two Factor Authentication</b> you will be asked to enter that too.

**Important:** Whenever you enter a code on this command make sure you add **aa** in front such as the code **52234** becomes **aa52234**. Same thing applies to **2FA**


## Redirection

```nohighlight
/redirection ACTION REDIRECTIONID on PHONE_NUMBER
/redirection PHONE_NUMBER
```

This command is used for setting up redirections for <b>TeleFeed</b>. This command should be run after you have already connected a telegram account with [/connect](/commands/#connect) command

You can use the [/chats](/commands/#chats) command to get channel/users/groups ID's for use with this command

<b  style="font-size: 115%;">Command Example</b>


<p style="margin-bottom: -13px; font-size: 14px;">Setting up redirection with REDIRECTIONID=<b>group1</b> on PHONE_NUMBER=<b>2759205517</b></p>
```nohighlight
/redirection add group1 on 2759205517
```

<p style="margin-bottom: -13px; font-size: 14px;">Removing redirection with REDIRECTIONID=<b>group1</b> on PHONE_NUMBER=<b>2759205517</b></p>
```
/redirection remove group1 on 2759205517
```

<p style="margin-bottom: -13px; font-size: 14px;">Changing redirection with REDIRECTIONID=<b>group1</b> on PHONE_NUMBER=<b>2759205517</b></p>
```
/redirection change group1 on 2759205517
```


<p style="margin-bottom: -13px; font-size: 14px;">Showing all active redirections on PHONE_NUMBER=<b>2759205517</b></p>
```
/redirection 2759205517
```

After typing the command you will be asked to enter ID's of the channel/groups/users you want to use as <b>SOURCE</b> and <b>DESTINATION</b>. 

<b>The right syntax to type it is as:</b>  
<b>SOURCE</b> - <b>DESTINATION</b>

Where <b>SOURCE</b> is the channel/user/group you want to redirect messages from and <b>DESTINATION</b> is the channel/group/user you want to redirect message into.

<b  style="font-size: 115%;">Syntax Example</b>

```nohighlight
Redirect messages from SOURCE: 708415014 to DESTINATION:642797040
708415014 - 642797040

Redirect messages from multiple SOURCES to DESTINATION
53469647,708415014 - 20801978

Redirect messages from SOURCE to Multiple DESTINATIONS
20801978 - 53469647,708415014 
```


<b>Min Source/Destination Number:</b> -2147483648  
<b>Max Source/Destination Number:</b> 2147483647

## Redirection Settings

This menu is used for controlling redirection setttings such as <b>reply, edit, delete and more</b>

To reach this first you will need to type [/settings](/commands/#settings) on <b>TeleFeed</b>, then click on <b>2759205517</b> to open settings menu for <b>2759205517 phone number</b>. Now click on <b>group1</b> so you can access the setup settings. Finally the <b>Redirection Menu</b> will show up and you can proceed by clicking on it

<p style="margin-bottom: 5px;"><b style="font-size: 115%; ">Available Options:</b></p>

* <b>Process Reply:</b> Turn this <b>ON</b> if you want to properly <b>process replies</b>
* <b>Process Edit:</b> Turn this <b>ON</b> if you want to edit messages if they got edited in the <b>SOURCE</b>
* <b>Process Delete:</b> Turn this <b>ON</b> if you want to remove messages if they got removed in the <b>SOURCE</b>
* <b>Process Me:</b> Turn this <b>ON</b> if you want to redirect your own messages from <b>SOURCE</b>
* <b>Process Forward:</b> Turn this <b>ON</b> if you want to <b>FORWARD</b> messages instead of writting them as <b>user</b>
* <b>Process Raw:</b> Turn this <b>ON</b> if you want to post <b>raw text</b> messages.
* <b>Process Duplicates:</b> Turn this <b>OFF</b> if you want to <b>block duplicate messages</b> from forwarding.
* <b>Fix Bad Style:</b> Turn this <b>On</b> if you get <b>weird links coloring</b> after using [/transformation](/commands/#transformation).

## Filters

This menu is used to filter messages by type. Using it will tell TeleFeed which messages you want <b>to process</b> and which ones <b>to ignore</b>

To reach this first you will need to type [/settings](/commands/#settings) on <b>TeleFeed</b>, then click on <b>2759205517</b> to open settings menu for <b>2759205517 phone number</b>. Now click on <b>group1</b> so you can access the setup settings. Finally the <b>Filters Menu</b> will show up and you can proceed by clicking on it

<p style="margin-bottom: -13px; font-size: 14px;">Access <b>Filters Menu</b> for REDIRECTIONID: <b>group1</b> on PHONE_NUMBER: <b>2759205517</b></p>
```nohighlight
/settings > 2759205517 > group1 > Filters
```

<p style="margin-bottom: 5px;"><b style="font-size: 115%; ">Available Filters:</b></p>

* <b>Audio:</b> Turn this <b>ON</b> if you want to <b>ignore audio messages</b>
* <b>Videos:</b> Turn this <b>ON</b> if you want to <b>ignore video messages</b>
* <b>Voicenotes:</b> Turn this <b>ON</b> if you want to <b>ignore voicenotes messages</b>
* <b>Animations:</b> Turn this <b>ON</b> if you want to <b>ignore message</b> that <b>contain animations (gif etc)</b> 
* <b>Photos:</b> Turn this <b>ON</b> if you want to <b>ignore photo messages</b>
* <b>Stickers:</b> Turn this <b>ON</b> if you want to <b>ignore sticker messages</b>
* <b>Document:</b> Turn this <b>ON</b> if you want to <b>ignore document messages</b>
* <b>Text:</b> Turn this <b>ON</b> if you want to <b>ignore messages</b> that <b>contain text</b>
* <b>Caption:</b> Turn this <b>ON</b> if you want to <b>ignore messages</b> that <b>contain captions</b>
* <b>Forwards:</b> Turn this <b>ON</b> if you want to <b>ignore "Forwarded from" messages</b>
* <b>Reply:</b> Turn this <b>ON</b> if you want to <b>ignore reply messages</b>

<b>Tip:</b> You can choose to filter for <b>multiple conditions at once</b> by keeping them <b>on</b>


## Cleaner

This menu is used to remove text, video, photo etc from messages if the <b>conditions match.</b> It's basically <b>Filters</b> but instead of ignoring or allowing messages, <b>it removes the content it matches</b>

To reach this first you will need to type [/settings](/commands/#settings) on <b>TeleFeed</b>, then click on <b>2759205517</b> to open settings menu for <b>2759205517 phone number</b>. Now click on <b>group1</b> so you can access the setup settings. Finally the <b>Cleaner Menu</b> will show up and you can proceed by clicking on it

<p style="margin-bottom: -13px; font-size: 14px;">Access <b>Filters Menu</b> for REDIRECTIONID: <b>group1</b> on PHONE_NUMBER: <b>2759205517</b></p>
```nohighlight
/settings > 2759205517 > group1 > Cleaner
```

<p style="margin-bottom: 5px;"><b style="font-size: 115%; ">Available Cleaners:</b></p>

* <b>Audio:</b> Turn this <b>ON</b> if you want to <b>remove audio from messages</b>
* <b>Videos:</b> Turn this <b>ON</b> if you want to <b>remove video from messages</b>
* <b>Voicenotes:</b> Turn this <b>ON</b> if you want to <b>remove voicenotes from messages</b>
* <b>Animations:</b> Turn this <b>ON</b> if you want to <b>remove animations (gif, etc) from messages</b>
* <b>Photos:</b> Turn this <b>ON</b> if you want to <b>remove photo from messages</b>
* <b>Stickers:</b> Turn this <b>ON</b> if you want to <b>remove sticker from messages</b>
* <b>Document:</b> Turn this <b>ON</b> if you want to <b>remove document from messages</b>
* <b>Text:</b> Turn this <b>ON</b> if you want to <b>remove text from messages</b>
* <b>Caption:</b> Turn this <b>ON</b> if you want to <b>remove caption from messages</b>

<b>Tip:</b> Same as <b>Filters</b>, you can keep <b>on</b> multiple conditions at once


## Transformation

```nohighlight
/transformation ACTION FEATURE REDIRECTIONID on PHONE_NUMBER
```



This command is used for setting up transformations for your redirections on <b>TeleFeed</b>. This command should be run after you have already connected a telegram account with <b>/connect</b> command and have one or more redirections active.

With this command you can change messages format, remove words from messages or remove lines if <b>keyword</b> is in it.

<b  style="font-size: 115%;">Command Example</b>

<p style="margin-bottom: -13px; font-size: 14px;"><b>Add (format|power|removeLines) on group1</b></p>
```nohighlight
/transformation add format group1 on 2759205517
/transformation add power group1 on 2759205517
/transformation add removeLines group1 on 2759205517
```

<p style="margin-bottom: -13px; font-size: 14px;"><b>Remove (format|power|removeLines) on group1</b></p>
```nohighlight
/transformation remove format group1 on 2759205517
/transformation remove power group1 on 2759205517
/transformation remove removeLines group1 on 2759205517
```

<p style="margin-bottom: -13px; font-size: 14px;"><b>Show active transformations for grp1 on 2759205517</b></p>
```nohighlight
/transformation active grp1 on 2759205517
```

<p style="margin-bottom: -13px; font-size: 14px;"><b>Show active transformations on 2759205517</b></p>
```nohighlight
/transformation active on 2759205517
```

<p style="margin-bottom: -13px; font-size: 14px;"><b>Clear grp1 transformations on 2759205517</b></p>
```nohighlight
/transformation clear grp1 on 2759205517
```

<p style="margin-bottom: -13px; font-size: 14px;"><b>Clear transformations on 2759205517</b></p>
```nohighlight
/transformation clear on 2759205517
```

### 1. Format Feature

This feature is used to change the output format for the message. Basically you can add text on the message and have it output like that (for example a header or footer etc)

<b  style="font-size: 115%;">Command Example</b>

```nohighlight
/transformation add format group1 on 2759205517
/transformation format 2759205517
```

After typing the command you will be asked to enter how you want to message to output as.  
In this example we will show how to turn the message.

```nohighlight
Lorem Ipsum is simply dummy text of the printing and typesetting industry. 
Lorem Ipsum has been the industrys standard dummy text ever since the 1500s, 
when an unknown printer took a galley of type and 
scrambled it to make a type specimen book.
```

<b>into</b>

```nohighlight
Inserted Header from Telefeed

Lorem Ipsum is simply dummy text of the printing and typesetting industry. 
Lorem Ipsum has been the industrys standard dummy text ever since the 1500s, 
when an unknown printer took a galley of type and 
scrambled it to make a type specimen book.

Inserted Footer from Telefeed
```

<b>The syntax we need to use to make the changes as shown above is as follow.</b>

```nohighlight
Inserted Header from Telefeed

[[Message.Text]]

Inserted Footer from Telefeed
```

TeleFeed will look at this and replace <b>[[Message.Text]]</b> with the actual <b>message</b> and we will get the output we desire.  

<p style="margin-bottom: 5px; font-size: 115%"><b>You can use the following keywords:</b></p>

* <b>[[PROCESS_EMPTY]]</b> -> Normally <b>format</b> will ignore empty messages (media etc). If you add this <b>variable</b> then it will start <b>formatting</b> empty messages. This can be used for adding <b>USERNAME</b>, <b>GROUP_NAME</b> on <b>MEDIA</b>

* <b>[[Message.Text]]</b> -> The source message <b>text</b> content  
* <b>[[Message.Group]]</b> -> The source message <b>group</b> name  

* <b>[[Message.Username]]</b> -> The user <b>Username</b> that sent the message  
* <b>[[Message.First_Name]]</b> -> The user <B>First Name</b> that sent the message  
* <b>[[Message.Last_Name]]</b> -> The user <b>Last Name</b> that sent the message  

* <b>[[Message.File.Filename]]</b> -> The source message <b>file</b> filename
* <b>[[Message.File.File_Size]]</b> -> The source message <b>file</b> filesize  
* <b>[[Message.File.File_Ext]]</b> -> The source message <b>file</b> file extension  


<b>Tip:</b> To change format you can just run the same command again.
<b>Tip:</b> This command does not work well with emoji and icon characters. You can use them but this command result might not be correctly in that case.

### 2. Remove Lines Feature

This feature is used to remove lines from the message. You will use keywords to check message lines and if a keyword or one of the keywords (if multiple) is found on the line, TeleFeed will remove that line from the final result.

<b  style="font-size: 115%;">Command Example</b>

```nohighlight
/transformation add removeLines group1 on 2759205517
/transformation remove removeLines group1 on 2759205517
/transformation removeLines 2759205517
```

After typing the command you will be asked to enter which keywords you want to look for in the message. You can enter multiple lines so the bot looks for multiple keywords etc.

<b  style="font-size: 115%;">Syntax Example</b>

```nohighlight
good, bad
apple
```

The setup we made above will look on every message if a line has the keyword <b>apple</b> (only) or if a line has the keywords <b>good</b> and <b>bad</b> (both) and remove it.

<b>Important:</b> This command is not used for removing keywords from the message, what it does is remove the whole line if it contains the keyword. For removing just the keyword you will need to use the <b>next</b> feature


### 3. Power Feature

This is one of the most powerful feature this bot has. It is used to remove and change keywords from the message. You can use <b>regex</b> with this feature

<b>Important:</b> You need to be careful with this command since it insert some wrong syntax (like wrong regex) it will stop message from redirecting. To fix it you just need to remove power feature.

<b  style="font-size: 115%;">Command Example</b>

```nohighlight
/transformation add power group1 on 2759205517
/transformation power group1 on 2759205517
```

<b  style="font-size: 115%;">Syntax Example (Simple)</b>

Use the syntax as shown below when you want to replace words or full paragraphs.

Change <b>red</b> to <b>blue</b>

```nohighlight
"red","blue"
```

Change <b>22</b> to <b>40</b>

```nohighlight
"22","40"
```

Change <b>2+1=3</b> to <b>2+2=4</b>

```nohighlight
"2+1=3","2+2=4"
```

Remove keyword <b>red</b> from the message

```nohighlight
"red",""
```

Change paragraph <b>I do not like this text</b> to <b>This is better</b>

```nohighlight
"I do not like this text","This is better"
```

<b  style="font-size: 115%;">Syntax Example (Advanced)</b>

Use the syntax as shown below when you want to achive result that is not possible with the simple syntax. This syntax uses regex to replace words and keywords. 

<b>Do not use this syntax if you do not know regex because bad usage can stop your redirection.</b>

Change <b>telegram.me</b> or <b>tm.me</b> to <b>test.com</b>

```nohighlight
(telegram\.me|tm\.me)\/\w+=test.com
```

Use regex to match <b>gray</b> or <b>grey</b> and change it to <b>red</b>

```nohighlight
gr[ae]y=red
```

Unshort urls, match <b>tag</b> (query) and change it to <b>client1</b> 

```nohighlight
url:tag=client1
```


Match every <b>url</b> or <b>@mention</b> and change it to <b>@tg_feedbot</b>

```nohighlight
(@|www|https?)\S+=@tg_feedbot
```

Remove word <b>red</b> from the message

You can use multiline configurations like. In that case the bot will try to match every line on the message and act on it.

```nohighlight
"2+1=3","2+2=4"
(@|www|https?)\S+=@tg_feedbot
```

After this <b>TeleFeed</b> will ask you for some <b>text</b> or you can <b>forward a message</b>.  
Then <b>TeleFeed</b> will run your <b>POWER Syntax</b> on that message and return you the result.  
This way you will know if you have written the right syntax for what you need.

If the result is correct you just have to click on the <b>Correct</b> button otherwise click <b>Incorrect</b> button.

<b>Tip:</b> To use regex effectivity, test your regex on [regex101.com](https://regex101.com)  
Make sure to use the <b>Python Flavor</b> otherwise your regex will not work on <b>TeleFeed</b>

### 4. Remove

You can use this command to remove configuration from power feature.

```nohighlight
## Syntax
/transformation remove FEATURE REDIRECTIONID on PHONE_NUMBER

## Example
/transformation remove power group1 on 2759205517
```

### 5. Clear configuration from /transformation

You can clear your current configuration on <b>/transformation</b> using the following syntax

```nohighlight
/transformation remove REDIRECTIONID on PHONE_NUMBER
```

It will remove every config you have with <b>format</b>, <b>removeLines</b> and <b>power</b> on that REDIRECTIONID 

### 6. Show Active Configuration

To show active configuration on <b>/transformation</b> you need to use the following syntax.
```nohighlight
/transformation active on PHONE_NUMBER
```

## Whitelist

You can set a list of words or regex patterns that tell the bot <b>to process message</b> you receive from source channel <b>only if it has at least one</b> of the whitelisted word or regex pattern match. When you use this command for adding a whitelist, TeleFeed will ask you for your input syntax. Make sure to use the right syntax by reading the examples below.

!!! Danger "Warning"
    <p style='font-size: 18px'>When this command is used incorrectly, it will cause redirections to stop working. Always make sure you use the right syntax when using whitelist. Make sure you check your regex with [regex101.com](https://regex101.com) before using them.</p>

!!! Example "Command"
    /whitelist {{action}} {{redirectionid}} on  {{phonenumber}}  
    /whitelist {{action}} on {{phonenumber}}


!!! Example "Command Example"
    <p style="margin-bottom: -13px;">Add whitelist for <b>group1</b> on <b>2759205517</b></p>
    ```nohighlight
    /whitelist add group1 on 2759205517
    ```

    <p style="margin-bottom: -13px;">Remove whitelist for <b>group1</b> on <b>2759205517</b></p>
    ```nohighlight
    /whitelist remove group1 on 2759205517
    ```

    <p style="margin-bottom: -13px;">Change whitelist for <b>group1</b> on <b>2759205517</b></p>
    ```nohighlight
    /whitelist change group1 on 2759205517
    ```

    <p style="margin-bottom: -13px;">Show active whitelist on <b>2759205517</b></p>
    ```nohighlight
    /whitelist active on 2759205517
    ```

    <p style="margin-bottom: -13px;">Clear all whitelist on <b>2759205517</b></p>
    ```nohighlight
    /whitelist clear on 2759205517
    ```

!!! Example "Input Syntax Example"
    The synax for this command is the same as [/transformation power feature](/commands/#power-feature)

    <p style="margin-bottom: -13px;">Process messages only if it has the word <b>bad</b> in it. <b>(REGEX DISABLED)</b></p>
    ```nohighlight
    "bad"
    ```

    <p style="margin-bottom: -13px;">Process messages only if it has the any <b>@mention</b> word on it. <b>(REGEX ENABLED)</b></p>
    ```nohighlight
    @\S+
    ```

!!! Tip "Tips"
    1. Normal keywords are faster than regex, so use them if you do not need regex.  
    2. To disable regex just wrap the word in quotes such as the word <b>bad</b> becomes <b>"bad"</b>  
    3. Make sure to use the <b>Python Flavor</b> otherwise your regex will not work on <b>TeleFeed</b>  
    4. To use regex effectivity, test your regex on [regex101.com](https://regex101.com)

## Blacklist

You can set a list of words or regex patterns which tells the bot that <b>if the message received</b> from source channel has any of the blacklisted words or regex pattern match the bot should <b>ignore</b> that <b>message</b> and do not process it even if it passes all other conditions. When you use this command for adding a blacklist, TeleFeed will ask you for your input syntax. Make sure to use the right syntax by reading the examples below.

!!! Danger "Warning"
    <p style='font-size: 18px'>When this command is used incorrectly, it will cause redirections to stop working. Always make sure you use the right syntax when using blacklist. Make sure you check your regex with [regex101.com](https://regex101.com) before using them.</p>

!!! Example "Command"
    /blacklist {{action}} {{redirectionid}} on  {{phonenumber}}  
    /blacklist {{action}} on {{phonenumber}}


!!! Example "Command Example"
    <p style="margin-bottom: -13px; ">Add blacklist for <b>group1</b> on <b>2759205517</b></p>
    ```nohighlight
    /blacklist add group1 on 2759205517
    ```

    <p style="margin-bottom: -13px; ">Remove blacklist for <b>group1</b> on <b>2759205517</b></p>
    ```nohighlight
    /blacklist remove group1 on 2759205517
    ```

    <p style="margin-bottom: -13px; ">Change blacklist for <b>group1</b> on <b>2759205517</b></p>
    ```nohighlight
    /blacklist change group1 on 2759205517
    ```

    <p style="margin-bottom: -13px; ">Show active blacklist on <b>2759205517</b></p>
    ```nohighlight
    /blacklist active on 2759205517
    ```

    <p style="margin-bottom: -13px; ">Clear all blacklist on <b>2759205517</b></p>
    ```nohighlight
    /blacklist clear on 2759205517
    ```

!!! Example "Input Syntax Example"
    The synax for this command is the same as [/transformation power feature](/commands/#power-feature)

    <p style="margin-bottom: -13px; ">Ignore messages only if it has the word <b>bad</b> in it. <b>(REGEX DISABLED)</b></p>
    ```nohighlight
    "bad"
    ```

    <p style="margin-bottom: -13px; font-size: 16px;">Ignore messages if it contains any <b>@mention</b> tag on it. <b>(REGEX ENABLED)</b></p>
    ```nohighlight
    @\S+
    ```

!!! Tip "Tips"
    1. Normal keywords are faster than regex, so use them if you do not need regex.  
    2. To disable regex just wrap the word in quotes such as the word <b>bad</b> becomes <b>"bad"</b>  
    3. Make sure to use the <b>Python Flavor</b> otherwise your regex will not work on <b>TeleFeed</b>  
    4. To use regex effectivity, test your regex on [regex101.com](https://regex101.com)

## Chats

This command is used to get a list of groups, bots, channels or users ID's for use [/redirection](/commands/#redirection) command.

```nohighlight
/chats PHONE_NUMBER
```

<b  style="font-size: 115%;">Command Example</b>

<p style="margin-bottom: -13px; font-size: 14px;">Getting chats for PHONE_NUMBER: <b>2759205517</b></p>
```nohighlight
/chats 2759205517
```

## Bot Settings

On this menu you will find settings such as <b>Start</b>, <b>Stop</b>, <b>Performance Rate</b> and more.

<p style="margin-bottom: 5px;"><b style="font-size: 115%; ">Available Options:</b></p>

* <b>Start:</b> Used to <b>start</b> TeleFeed
* <b>Stop:</b> Used to <b>stop</b> TeleFeed
* <b>Disconnect Account:</b> This removes your account from TeleFeed. When you use <b>Disconnect Account</b>, TeleFeed will not login into your account unless you use <b>[/connect](/commands/#connect)</b> again
* <b>Export:</b> You can use this option to <b>Export</b> TeleFeed configuration so you can import it on another account.
* <b>Import:</b> After using <b>Export</b>, you will need to import the configuration for usage. You can use this option to import any <b>TeleFeed configuration</b>
* <b>Improve Performance:</b> This option increases TeleFeed Performance. The reason this option is <b>OFF</b> by default is because using it will cause TeleFeed to <b>forward messages out of order.</b> If you do not care about message order, turning this setting <b>ON</b> will <b>increase performance</b> by a <b>big margin</b>
* <b>Burst Mode:</b> This option controls message rate for TeleFeed. Message rate means the number of messages TeleFeed can send at once. If this option is set to <b>HIGH (default)</b> then TeleFeed will use its max rate for sending messages. Sometimes this might cause <b>Telegram Account Limited Error</b>  which is why we offer a way to lower this rate.


<b>Tip:</b> <b>Telegram Account Limited Error</b> is an error which happens when an account sends many messages at once. This does not cause any permanent issues with the account. When this error happens TeleFeed will not send any more messages via the account. This is because Telegram gives an <b>Temporary Wait Limit</b> so TeleFeed will need to for that to expire before it sends another message.


## Action

This command can be used to bypass bots which hide messages or get content from Telegram official GmailBot. Right now this command can bypass both <b>alert</b> & <b>text rewrite</b> modes

```nohighlight
/action ACTION REDIRECTIONID on PHONE_NUMBER
```

<b  style="font-size: 115%;">Command Example</b>

<p style="margin-bottom: -13px; font-size: 14px;">Add Action group1 on 2759205517</p>
```nohighlight
/action add group1 on 2759205517
```

<p style="margin-bottom: -13px; font-size: 14px;">Remove Action from group1 on 2759205517</p>
```nohighlight
/action remove group1 on 2759205517
```

<p style="margin-bottom: -13px; font-size: 14px;">Remove all Actions from group1 on 2759205517</p>
```nohighlight
/action clear group1 on 2759205517
```

<b>TeleFeed</b> will then ask you to about the button title. You do not need to fully match the name, for example if you want TeleFeed to click a button with title <b>▼ Read More</b>, you can just specify <b>Read More</b> and TeleFeed will match it.

## Translate

This command is used for setting up translation for your redirection groups.

```nohighlight
/translate SRC DEST REDIRECTIONID on PHONE_NUMBER
/translate remove REDIRECTIONID on PHONE_NUMBER
```

* <b>SRC</b>  -> Language you want to translate from
* <b>DEST</b> -> Language you want to translate into

<b  style="font-size: 115%;">Command Example</b>

<p style="margin-bottom: -13px; font-size: 14px;">Translate from src=<b>English</b> to dest=<b>Italian</b> for REDIRECTIONID=<b>group1</b> on PHONE_NUMBER=<b>2759205517</b></p>
```nohighlight
/translate en it group1 on 2759205517
```

<p style="margin-bottom: -13px; font-size: 14px;">Remove translate setup for REDIRECTIONID=<b>group1</b> on PHONE_NUMBER=<B>2759205517</B></p>
```
/translate remove group1 on 2759205517
```

<b  style="font-size: 115%;">Language Code for using this command</b>

```nohighlight
'af': 'afrikaans',
'sq': 'albanian',
'am': 'amharic',
'ar': 'arabic',
'hy': 'armenian',
'az': 'azerbaijani',
'eu': 'basque',
'be': 'belarusian',
'bn': 'bengali',
'bs': 'bosnian',
'bg': 'bulgarian',
'ca': 'catalan',
'ceb': 'cebuano',
'ny': 'chichewa',
'zh-cn': 'chinese (simplified)',
'zh-tw': 'chinese (traditional)',
'co': 'corsican',
'hr': 'croatian',
'cs': 'czech',
'da': 'danish',
'nl': 'dutch',
'en': 'english',
'eo': 'esperanto',
'et': 'estonian',
'tl': 'filipino',
'fi': 'finnish',
'fr': 'french',
'fy': 'frisian',
'gl': 'galician',
'ka': 'georgian',
'de': 'german',
'el': 'greek',
'gu': 'gujarati',
'ht': 'haitian creole',
'ha': 'hausa',
'haw': 'hawaiian',
'iw': 'hebrew',
'hi': 'hindi',
'hmn': 'hmong',
'hu': 'hungarian',
'is': 'icelandic',
'ig': 'igbo',
'id': 'indonesian',
'ga': 'irish',
'it': 'italian',
'ja': 'japanese',
'jw': 'javanese',
'kn': 'kannada',
'kk': 'kazakh',
'km': 'khmer',
'ko': 'korean',
'ku': 'kurdish (kurmanji)',
'ky': 'kyrgyz',
'lo': 'lao',
'la': 'latin',
'lv': 'latvian',
'lt': 'lithuanian',
'lb': 'luxembourgish',
'mk': 'macedonian',
'mg': 'malagasy',
'ms': 'malay',
'ml': 'malayalam',
'mt': 'maltese',
'mi': 'maori',
'mr': 'marathi',
'mn': 'mongolian',
'my': 'myanmar (burmese)',
'ne': 'nepali',
'no': 'norwegian',
'ps': 'pashto',
'fa': 'persian',
'pl': 'polish',
'pt': 'portuguese',
'pa': 'punjabi',
'ro': 'romanian',
'ru': 'russian',
'sm': 'samoan',
'gd': 'scots gaelic',
'sr': 'serbian',
'st': 'sesotho',
'sn': 'shona',
'sd': 'sindhi',
'si': 'sinhala',
'sk': 'slovak',
'sl': 'slovenian',
'so': 'somali',
'es': 'spanish',
'su': 'sundanese',
'sw': 'swahili',
'sv': 'swedish',
'tg': 'tajik',
'ta': 'tamil',
'te': 'telugu',
'th': 'thai',
'tr': 'turkish',
'uk': 'ukrainian',
'ur': 'urdu',
'uz': 'uzbek',
'vi': 'vietnamese',
'cy': 'welsh',
'xh': 'xhosa',
'yi': 'yiddish',
'yo': 'yoruba',
'zu': 'zulu',
'fil': 'Filipino',
'he': 'Hebrew'
```

__This command will not work if you use wrong language codes.__


## Clone

This command is used for cloning (mirror) chats/channels or users messages from SOURCE to DESTINATION

```nohighlight
/clone SOURCE DESTINATION on PHONE_NUMBER
/clone SOURCE DESTINATION LIMIT on PHONE_NUMBER
```

* <b>SOURCE</b>  -> Chat/User you want to clone messages from
* <b>DESTINATION</b> -> Chat/User you want to clone messages into

If you have a redirection setup with the same ID's (SOURCE, DESTINATION) when using this command. It will use the your redirection setup (transformation, filtering) when applying this command.

<b  style="font-size: 115%;">Command Example</b>

<p style="margin-bottom: -13px; font-size: 14px;">Clone from SOURCE=<b>2759205517</b> to DESTINATION=<b>28887387</b> on PHONE_NUMBER=<b>2759205517</b></p>
```nohighlight
/clone 2759205517 28887387 on 2759205517
```


<p style="margin-bottom: -13px; font-size: 14px;">Clone from SOURCE=<b>2759205517</b> to DESTINATION=<b>28887387</b> with LIMIT=<b>200</b> on PHONE_NUMBER=<b>2759205517</b></p>
```
/clone 2759205517 28887387 200 on 2759205517
```
__Warning!__  
Because this commands sends a high amount of messages in a short time it will cause temporary limits from telegram servers. Basically when this happens you will not be able to send any message from this account for <b>5 minutes</b> to <b>1 hour</b> depending on the limit.

You will get a notification from the bot when such a limit is encountered (You will also notice yourself since you will not be able to send any message when that happens). There's no way around this other than not using this command.

__Important:__ When using this command, the bot might delay message redirection for your setups.

## Global
The [/global](/commands/#global) command can be used to apply globally one specific configuration. This command works only for the features shown below.

```nohighlight
/global ACTION REDIRECTIONID on PHONE_NUMBER
```

<p style="margin-bottom: -13px; font-size: 14px;">Make group1 <b>configuration</b> global on 2759205517</p>
```
/global add group1 on 2759205517
```

<p style="margin-bottom: -13px; font-size: 14px;">Remove group1 <b>configuration</b> from global on 2759205517</p>
```
/global remove group1 on 2759205517
```

<b>Supported Features Globally</b>
```
Transformation
Translate
Watermark
Action
Whitelist & Blacklist
Filters & Cleaners
```


## Scheduler

You can define start and stop time for each of your redirection setup using this command.

!!! Example "Command"
    /scheduler {{ action }} {{ redirectionid }} on {{ phonenumber }}

!!! Example "Command Example"
    <p style="margin-bottom: -13px;">Add schdule for <b>group1</b> on <b>2759205517</b></p>
    ```nohighlight
    /scheduler add group1 on 2759205517
    ```

    <p style="margin-bottom: -13px;">Remove schdule for <b>group1</b> on <b>2759205517</b></p>
    ```nohighlight
    /scheduler remove group1 on 2759205517
    ```

    <p style="margin-bottom: -13px;">Clear all schedules for <b>2759205517</b></p>
    ```nohighlight
    /scheduler clear on 2759205517
    ```

</br>
After running the above commands <b>you will be asked</b> to input the time that you want TeleFeed to turn on and off your setups.
Here are a few example syntax on how to do this.  
</br>

!!! Example "Input Syntax Example "
    <p style="margin-bottom: -13px; font-size: 14px;">Start at <b>12:30</b> and Stop at <b>2:30</b></p>
    ```nohighlight
    12:30 - 2:30
    ```

    <p style="margin-bottom: -13px; font-size: 14px;">Start at <b>09:00</b> and Stop at <b>21:00</b></p>
    ```nohighlight
    9:00 - 21:00
    ```
</br>
That's all. Now TeleFeed will (based on first example) <b>turn on</b> group1 <b>at 12:30</b> and <b>turn off at 2:30</b>

## Selectusers

You can set a list of <b>user id s</b> to tell the bot <b>to process messages</b> you receive from source channel <b>only if it matches at least one</b> of the <b>user id's</b> on the list. 


!!! Example "Command"
    /selectusers {{ action }} {{ redirectionid }} on {{ phonenumber }}

!!! Example "Command Example"
    <p style="margin-bottom: -13px;">Add for <b>group1</b> on <b>2759205517</b></p>
    ```nohighlight
    /selectusers add group1 on 2759205517
    ```

    <p style="margin-bottom: -13px;">Remove for <b>group1</b> on <b>2759205517</b></p>
    ```nohighlight
    /selectusers remove group1 on 2759205517
    ```

    <p style="margin-bottom: -13px;">Remove <b>everything</b> on <b>2759205517</b></p>
    ```nohighlight
    /selectusers clear on 2759205517
    ```

</br>
After running <b>"/selectusers add group1 on 2759205517"</b>, <b>you will be asked</b> to input a list of <b>users id's</b>. Input the user you want to allow messages from. Separate them using commads <b>,</b> for multiple users.  
</br>

!!! Example "Input Syntax Example "
    ```nohighlight
    6516516,651651651,16516516
    ```

</br>
That's all. Now every time you receive a message on <b>group1 SOURCE</b>, TeleFeed will check if the user who sent the message is allowed based on your user ID's input. If so it will process the message otherwise it will ignore it.  

## Bitly

This command is used for configuring bitly access for <b>TeleFeed</b>

!!! Example "Command"
    /bitly key

!!! Example "Command Example"
    <p style="margin-bottom: -13px;">Setting bitly api with <b>43nafkiynmy7pn7lkqgiuwn6krquwisvjsdbgf</b></p>
    ```nohighlight
    /bitly 43nafkiynmy7pn7lkqgiuwn6krquwisvjsdbgf
    ```

## Watermark

You can use this command to add a watermark to every media that <b>TeleFeed</b> forwards.

!!! Example "Command"
    /watermark {{ action }} {{ redirectionid }} on {{ phonenumber }}

!!! Example "Command Example"
    <p style="margin-bottom: -13px;"><b>Add Watermark group1 on 2759205517</b></p>
    ```nohighlight
    /watermark add group1 on 2759205517
    ```

    <p style="margin-bottom: -13px;"><b>Remove Watermark group1 on 2759205517</b></p>
    ```nohighlight
    /watermark remove group1 on 2759205517
    ```

    <p style="margin-bottom: -13px;"><b>Remove all watermarks from 2759205517</b></p>
    ```nohighlight
    /watermark clear on 2759205517
    ```

!!! Info "Information"
    1. This command can cause redirection to run slower because TeleFeed will need to generate the watermark before it sends the message


## PlanSwap

This command is used to exchange plans between phone numbers. You can use this to move your paid plan from one number to another. 

!!! Example "Command"
    ```nohighlight
    /planswap SOURCE_PHONE_NUMBER DESTINATION_PHONE_NUMBER
    ```

!!! Example "Command Example"
    <p style="margin-bottom: -13px"><b>Exchange Plan from 27505517 to 32529517</b></p>
    ```nohighlight
    /planswap 27505517 32529517
    ```
!!! Warning "Important"
    1. This command <b>has a fee of 1 day</b> for each usage. This means that when you move a <b>31 Days Pro Plan</b> from 27505517, you will get <b>30 Days of Pro Plan</b> on 32529517
    2. The <b>source number</b> needs to be connected with your account for <b>planswap</b> to work.
    3. The <b>destination number</b> needs to be in <b>Free Plan</b> for <b>planswap</b> to work.

## Delay

This command is used for setting up delays for your redirections. When delay is active, TeleFeed will schedule messages and send them later.

!!! Example "Command"
    /delay {{ amount }} {{ redirectionid }} on {{ phonenumber }}  
    /delay {{ amount }} on {{ phonenumber }}

!!! Example "Command Example"
    <p style="margin-bottom: -13px">Delay <b>group_1</b> by <b>120 seconds</b> on <b>2759205517</b></p>
    ```nohighlight
    /delay 120 group1 on 2759205517
    ```

    <p style="margin-bottom: -13px">Delay all redirections by <b>120 seconds</b> on <b>2759205517</b></p>
    ```
    /delay 120 on 2759205517
    ```

!!! Tip "Tips"
    1. Setting delay to 0 will remove it


## Config

This command is used to get a message with your active configuration. You can use it for when you don't know what redirections, filters, cleaners etc you have active.

!!! Example "Command"
    /config

## Clear

This command is used to clear your active configuration. Everything including [/redirection](/commands/#redirection) setups will be removed. TeleFeed will still keep your number connected so you can configure it again.

!!! Example "Command"
    /clear {{phonenumber}}  

## Settings

This command will show you a menu which you can access <b>[Bot Settings](/commands/#bot-settings), [Redirection Settings](/commands/#redirection-settings), [Filters Menu](/commands/#filters) and [Cleaners Menu](/commands/#cleaner)</b>
