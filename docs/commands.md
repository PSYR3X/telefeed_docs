# Commands

Every command has some variables in common. Below you will find their meaning so you can use them. You can run every command without arguments and it will return its help menu.

* <b>PHONE_NUMBER</b> -> Phone number for the command to act upon
* <b>REDIRECTIONID</b> -> When you create redirections, you give them an ID to reference in other commands. When a comand asks you for <b>REDIRECTIONID</b> it means it wants the name/title you used when you created the redirection.
* <b>ACTION</b> -> What action to do for the command. Commands like <b>/transformation</b> and <b>/redirection</b> have an add and remove <b>ACTION</b>
* <b>FEATURE</b> -> Commands like <b>/transformation</b> have a FEATURE argument which is used to tell the bot what feature of the command you want to use.

<b>Every <u>Example Command</u> you see in this documentation is using <u>dummy values</u> so don't copy and paste it.</b>

## Connect

```nohighlight
/connect PHONE_NUMBER
```

This command is used for connecting telegram accounts with <b>TeleFeed</b>. You need to run this first before trying to run other commands since they rely on you having a number connected.

####Command example:

```nohighlight
Connecting to TeleFeed with PHONE_NUMBER: 2759205517
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
```

This command is used for setting up redirections for <b>TeleFeed</b>. This command should be run after you have already connected a telegram account with [/connect](/commands/#connect) command

You can use the [/chats](/commands/#chats) command to get channel/users/groups ID's for use with this command

####Command example:

```nohighlight
Setting up redirection with REDIRECTIONID: group1 on PHONE_NUMBER: 2759205517
/redirection add group1 on 2759205517

Removing redirection with REDIRECTIONID: group1 on PHONE_NUMBER: 2759205517
/redirection remove group1 on 2759205517

Showing all active redirections on PHONE_NUMBER: 2759205517
/redirection 2759205517
```

After typing the command you will be asked to enter ID's of the channel/groups/users you want to use as <b>SOURCE</b> and <b>TARGET</b>. 

<b>The right syntax to type it is as:</b>  
<b>SOURCE</b> - <b>TARGET</b>

Where <b>SOURCE</b> is the channel/user/group you want to redirect messages from and <b>TARGET</b> is the channel/group/user you want to redirect message into.

####Syntax example:

```nohighlight
Redirect messages from SOURCE: 708415014 to TARGET:642797040
708415014 - 642797040

Redirect messages from SOURCE: 53469647 to TARGET:20801978
53469647 - 20801978

Redirect messages from SOURCE: 25492601 to TARGET:86782810
25492601 - 86782810
```


<b>Min Source/Target Number:</b> -2147483648  
<b>Max Source/Target Number:</b> 2147483647

## Transformation

```nohighlight
/transformation ACTION FEATURE REDIRECTIONID on PHONE_NUMBER
```

This command is used for setting up transformations for your redirections on <b>TeleFeed</b>. This command should be run after you have already connected a telegram account with <b>/connect</b> command and have one or more redirections active.

With this command you can change messages format, remove words from messages or remove lines if <b>keyword</b> is in it.

### Format Feature:

This feature is used to change the output format for the message. Basically you can add text on the message and have it output like that (for example a header or footer etc)

#### Command Example

```nohighlight
/transformation add format group1 on 2759205517
/redirection format 2759205517
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

[[message]]

Inserted Footer from Telefeed
```

TeleFeed will look at this and replace <b>[[message]]</b> with the actual <b>message</b> and we will get the output we desire.

<b>Tip:</b> To change format you can just run the same command again.

### Remove Lines Feature:

This feature is used to remove lines from the message. You will use keywords to check message lines and if a keyword or one of the keywords (if multiple) is found on the line, TeleFeed will remove that line from the final result.

#### Command example

```nohighlight
/transformation add removeLines group1 on 2759205517
/redirection remove removeLines group1 on 2759205517
/redirection removeLines 2759205517
```

After typing the command you will be asked to enter which keywords you want to look for in the message. You can enter multiple lines so the bot looks for multiple keywords etc.

#### Syntax example

```nohighlight
good, bad
apple
```

The setup we made above will look on every message if a line has the keyword <b>apple</b> (only) or if a line has the keywords <b>good</b> and <b>bad</b> (both) and remove it.

<b>Important:</b> This command is not used for removing keywords from the message, what it does is remove the whole line if it contains the keyword. For removing just the keyword you will need to use the <b>next</b> feature


### Power Feature:

This is one of the most powerful feature this bot has. It is used to remove and change keywords from the message. You can use <b>regex</b> with this feature

<b>Important:</b> You need to be careful with this command since it insert some wrong syntax (like wrong regex) it will stop message from redirecting. To fix it you just need to remove power feature.

#### Command example

```nohighlight
/transformation add power group1 on 2759205517
/transformation power group1 on 2759205517
```

#### Syntax example

Change <b>app</b> to <b>bot</b> (REGEX ENABLED)

```nohighlight
app=bot
```

Change <b>telegram.me</b> or <b>tm.me</b> to <b>test.com</b> (REGEX ENABLED)

    (telegram\.me|tm\.me)\/\w+=test.com

Use regex to match <b>gray</b> or <b>grey</b> and change it to <b>red</b>

```nohighlight
gr[ae]y=red
```

Unshort urls, match <b>tag</b> (query) and change it to <b>client1</b> 
URL functions have <b>REGEX DISABLED</b> by default. To use URL functions you need to have a bitly token setup. You can do it via the [/bitly](/commands/#bitly) command.

```nohighlight
url:tag=client1
```

Match <b>2+1=3</b> and change it to <b>2+2=4</b> (REGEX DISABLED)

```nohighlight
"2+1=3","2+2=4"
```

Match every <b>url</b> or <b>@mention</b> and change it to <b>@tg_feedbot</b>

```nohighlight
(@|www|https?)\S+=@tg_feedbot
```

Remove word <b>red</b> from the message

```nohighlight
red=
```

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


## Whitelist

You can set a list of words or regex patterns that tell the bot <b>to process message</b> you receive from source channel <b>only if it has at least one</b> of the whitelisted word or regex pattern match.

```nohighlight
/Whitelist REDIRECTIONID on <b>PHONE_NUMBER</b>
```

####Command example:

```nohighlight
Whitelist for REDIRECTIONID: group1 on PHONE_NUMBER: 2759205517
/whitelist group1 on 2759205517
```

<b>TeleFeed</b> will ask you to input the keywords you want to whitelist.

####Syntax example:

The synax for this command is the same as [/transformation](/commands/#power-feature) <b>power feature</b>

Process messages only if it has the word <b>bad</b> in it. (REGEX DISABLED)
```nohighlight
"bad"
```

Process messages only if it has the any <b>@mention</b> on it.
```nohighlight
@\S+
```
<b>Tip:</b> To disable regex just wrap the word in quotes such as the word <b>bad</b> becomes <b>"bad"</b>  
<b>Tip:</b> To use regex effectivity, test your regex on [regex101.com](https://regex101.com)  
Make sure to use the <b>Python Flavor</b> otherwise your regex will not work on <b>TeleFeed</b>

## Blacklist

You can set a list of words or regex patterns which tells the bot that <b>if the message received</b> from source channel has any of the blacklisted words or regex pattern match the bot should <b>ignore</b> that <b>message</b> and do not process it even if it passes all other conditions.

```nohighlight
/Whitelist REDIRECTIONID on <b>PHONE_NUMBER</b>
```

This command uses the same syntax as the [/whitelist](/commands/#whitelist) command

## Chats

This command is used to get a list of groups, bots, channels or users ID's for use [/redirection](/commands/#redirection) command.

```nohighlight
/chats PHONE_NUMBER
```

####Command example:

```nohighlight
Getting chats for PHONE_NUMBER: 2759205517
/chats 2759205517
```

## Translate

This command is used for setting up translation for your redirection groups.

```nohighlight
/translate SRC DEST REDIRECTIONID on PHONE_NUMBER
/translate remove REDIRECTIONID on PHONE_NUMBER
```

####Command example:

```nohighlight
Translate from src=English to dest=Italian for REDIRECTIONID=grp1 on PHONE_NUMBER=2759205517
/translate en it grp1 on 2759205517

Remove translate setup for REDIRECTIONID=grp1 on PHONE_NUMBER=2759205517
/translate en it grp1 on 2759205517
```

* <b>SRC</b>  -> Language you want to translate from
* <b>DEST</b> -> Language you want to translate into

####Language Code for using this command

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

## Bitly

This command is used for configuring bitly access for <b>TeleFeed</b>

```nohighlight
/bitly TOKEN
```

####Command example:

```nohighlight
Getting chats for PHONE_NUMBER: 2759205517
/chats 43nafkiynmy7pn7lkqgiuwn6krquwisvjsdbgf
```

## Delay

This command is used for setting up delays for your redirections.

```nohighlight
/delay VALUE REDIRECTIONID on PHONE_NUMBER
```

####Command example:

```nohighlight
Delay REDIRECTIONID: group_1 by Value: 120sec on PHONE_NUMBER: 2759205517
/delay 120 group1 on 2759205517

Delay all redirections by Value: 120sec on PHONE_NUMBER: 2759205517
/delay 120 group1 on 2759205517
```

## Settings

This command will show you a menu which you can use to control your redirections functions.

```nohighlight
/settings
```

#### Redirection SubMenu

Can be found within the [/settings](/commands/#settings) command.  
Used for controlling how the TeleFeed functions.

<b>Here are the options you can change on this menu:</b>

* <b>Process Reply:</b> Turn this on if you want <b>TeleFeed</b> to reply to its own messages
* <b>Process Edit:</b> Turn this on if you want <b>TeleFeed</b> to edit messages if they got edited in the <b>SOURCE</b>
* <b>Process Delete:</b> Turn this on if you want <b>TeleFeed</b> to remove messages if they got removed in the <b>SOURCE</b>
* <b>Process Me:</b> Turn this on if you want <b>TeleFeed</b> to redirect your own messages from <b>SOURCE</b>
* <b>Process Forward:</b> Turn this on if you want <b>TeleFeed</b> to <b>FORWARD</b> message instead of writting them as <b>user</b>


#### Filters SubMenu

Can be found within the [/settings](/commands/#settings) command.  
Used for filtering messages on <b>TeleFeed</b>

You can turn it <b>ON</b> if you don't want message to pass with that filter or <b>OFF</b> if you want them to pass.


#### Cleaner SubMenu

Can be found within the [/settings](/commands/#settings) command.  
Same as filters menu but with this menu instead of filtering the message, it deletes the content it founds.

For example, if you turn on <b>photo</b> in this menu. It will delete photo's from every media and just redirect the text.


## Config

This command is used to get a message with your active configuration. You can use it for when you don't know what redirections, filters, cleaners etc you have active.

```nohighlight
/config
```
