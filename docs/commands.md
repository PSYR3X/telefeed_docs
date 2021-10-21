<link href="https://vjs.zencdn.net/7.15.4/video-js.css" rel="stylesheet" />
<script src="https://vjs.zencdn.net/7.15.4/video.min.js"></script>

{%set action = "<a href='#commands-arguments-meaning'>action</a>" %}
{%set redirectionid = "<a href='#commands-arguments-meaning'>redirectionid</a>" %}
{%set feature = "<a href='#commands-arguments-meaning'>feature</a>" %}
{%set phonenumber = "<a href='#commands-arguments-meaning'>phonenumber</a>" %}
{%set amount = "<a href='#commands-arguments-meaning'>amount</a>" %}
{%set source = "<a href='#commands-arguments-meaning'>source</a>" %}
{%set destination = "<a href='#commands-arguments-meaning'>destination</a>" %}
{%set limit = "<a href='#commands-arguments-meaning'>limit</a>" %}

{% macro message_preview(before, after) -%}
<div class="flex_on flex_jst_around">
    <div class="flex_size-50 flex_collapse_900">
    <p style="margin-bottom: -10px;margin-bottom: 5px;"><u><b >Before Feature</b></u></p>
        {{ before }}
    </div>
    <div class="flex_size-50 flex_collapse_900">
        <p style="margin-bottom: -10px;margin-bottom: 5px;"><u><b>After Feature</b></u></p>
        {{ after }}
    </div>
</div>
{%- endmacro %}

{% macro center_explain(text) -%}
<p class="centered_text">{{ text }}</p>
{%- endmacro %}

# Commands

In this documentation you will find every TeleFeed command and examples on how to use them. We suggest you read this documentation from the start so you can learn more about each feature TeleFeed supports. Every <u>Example Command</u> you see in this documentation is using <u>dummy values</u> so don't copy and paste it.

#### Commands Arguments Meaning

* <b>PhoneNumber:</b> Used to specify which <b>connected account</b> you want to use the command on.
* <b>RedirectionID:</b> Used to specify on which <b>redirection setup</b> you want to use.
* <b>Action:</b> Used to specify what you want to do with the command. Supported actions are <b>Add, Remove, Change</b> and <b>Clear</b>.
* <b>Feature</b> Some commands contain more than one feature inside. With this argument you need to specify which feature you want to use.
* <b>Amount</b> Specify the amount in numbers for the given command. Commands such as /delay use this argument to specify seconds.
* <b>Source</b>  -> The destination chat you want to use the TeleFeed command with. Can be user, bot, channel, group or supergroup.
* <b>Destination</b> -> The destination chat you want to use the TeleFeed command with. Can be user, bot, channel, group or supergroup.
* <b>Limit</b> -> Clone command specific argument. Used to limit the number of message the clone commands processes.


## Connect

This command is used for connecting telegram accounts with <b>TeleFeed</b>. You need to run this first before trying to run other commands since they rely on you having a number connected.

!!! Example "Command"
    <p style="font-size: 16px">/connect  {{phonenumber}}</p>


!!! Example "Command Example"
    <p style="margin-bottom: -13px;">Connecting to TeleFeed with <b>2759205517</b></b></p>
    ```nohighlight
    /connect 2759205517
    ```

!!! warning "Careful"
    * Remember to always add your <b>country prefix</b> otherwise the connection might fail.
    * Whenever you enter a code on this command make sure you add **aa** in front such as the code **52234** becomes **aa52234**. Same thing for <b>Two Factor Authentication</b>


## Redirection
<div class="intruction_wrapper">
<div class="text">
<p>This command is used for setting up redirections for <b>TeleFeed</b>. This command should be run after you have already connected a telegram account with <a href='#connect'>connect</a> command.
</p></div>
<video
id="my-video"
class="video video-js vjs-big-play-centered"
controls
preload="auto"
width="640"
height="264"
data-setup="{}"
>
<source src="https://telegrambotting.com/static/video/out.mp4" type="video/mp4" />
<p class="vjs-no-js">
To view this video please enable JavaScript, and consider upgrading to a
web browser that
<a href="https://videojs.com/html5-video-support/" target="_blank"
>supports HTML5 video</a
>
</p>
</video>
</div>

!!! Info "Command Information"
    * This commands needs input from the [/chats](/commands/#chats)
    * You can only use source and destination id's you find via [/chats](/commands/#chats)
    * <b>RedirectionID</b> is the nickname you want to give to your setup. Do not use numbers you get from [/chats](/commands/#chats) in this field or Telegram chat names. This variable is used to define a nickname so you can identify your setup later on every TeleFeed command.

!!! Example "Command"
    /redirection {{ action }} {{ redirectionid }} on {{ phonenumber }}
    /redirection {{ phonenumber }}

!!! Example "Command Example"
    <p style="margin-bottom: -13px;">Setting up redirection with <b>group1</b> on <b>2759205517</b></p>
    ```nohighlight
    /redirection add group1 on 2759205517
    ```

    <p style="margin-bottom: -13px;">Removing redirection with <b>group1</b> on <b>2759205517</b></p>
    ```
    /redirection remove group1 on 2759205517
    ```

    <p style="margin-bottom: -13px;">Changing redirection with <b>group1</b> on <b>2759205517</b></p>
    ```
    /redirection change group1 on 2759205517
    ```

    <p style="margin-bottom: -13px;">Showing all active redirections on <b>2759205517</b></p>
    ```
    /redirection 2759205517
    ```

{{ center_explain('After typing <b>/redirection add group1 on 2759205517</b> you will be asked to enter id\'s of chat you want to use as <b>SOURCE</b> and <b>DESTINATION</b>. Please make sure to use the right syntax when input id\'s as shown below.') }}

!!! Example "Input Syntax"
    <b>SOURCE</b> - <b>DESTINATION</b>

{{ center_explain('Where <b>SOURCE</b> is the user, bot, channel or group you want to redirect messages from and <b>DESTINATION</b> is the user, bot, channel or group you want to redirect message into.') }}

!!! Example "Input Syntax Example"
    Redirect messages from <b>708415014</b> to <b>642797040</b>
    ```
    708415014 - 642797040
    ```

    Redirect messages from multiple <b>sources</b> to <b>destination</b>
    ```
    53469647,708415014 - 20801978
    ```

    Redirect messages from <b>one source</b> to <b>multiple destinations</b>
    ```
    20801978 - 53469647,708415014
    ```

!!! warning "Syntax Limitations"
    * ID's can only be numbers
    * You can only use <b>-</b> once
    * You should never repeat the same setup
    * ID's should be higher than <b>0</b> and lower than <b>2147483647</b>
    * You should never use the <b>same ID</b> in both <b>source</b> and <b>destination</b>

## Redirection Settings

This menu is used for controlling redirection setttings such as <b>reply, edit, delete and more</b>

!!! info "Instructions"
    To reach this first you will need to type [/settings](/commands/#settings) on <b>TeleFeed</b>, then click on <b>2759205517</b> to open settings menu for <b>2759205517 phone number</b>. Now click on <b>group1</b> so you can access the setup settings. Finally the <b>Redirection Menu</b> will show up and you can proceed by clicking on it

!!! Abstract "Options Explained"
    * <b>Process Reply:</b> Turn this <b>ON</b> if you want to properly <b>process replies</b>
    * <b>Process Edit:</b> Turn this <b>ON</b> if you want to edit messages if they got edited in the <b>SOURCE</b>
    * <b>Process Delete:</b> Turn this <b>ON</b> if you want to remove messages if they got removed in the <b>SOURCE</b>
    * <b>Process Me:</b> Turn this <b>ON</b> if you want to redirect your own messages from <b>SOURCE</b>
    * <b>Process Forward:</b> Turn this <b>ON</b> if you want to <b>FORWARD</b> messages instead of writting them as <b>user</b>
    * <b>Process Raw:</b> Turn this <b>ON</b> if you want to post <b>raw text</b> messages.
    * <b>Process Duplicates:</b> Turn this <b>OFF</b> if you want to <b>block duplicate messages</b> from forwarding.
    * <b>Delay Spread Mode:</b> Turn this <b>On</b> if you want [/delay](/commands/#delay) to work based on last message sent. This will spread messages when they come at once instead of delaying them all together.

## Filters

This menu is used to filter messages by type. Using it will tell TeleFeed which messages you want <b>to process</b> and which ones <b>to ignore</b>

!!! info "Instructions"
    To reach this first you will need to type [/settings](/commands/#settings) on <b>TeleFeed</b>, then click on <b>2759205517</b> to open settings menu for <b>2759205517 phone number</b>. Now click on <b>group1</b> so you can access the setup settings. Finally the <b>Filters Menu</b> will show up and you can proceed by clicking on it

!!! Abstract "Options Explained"
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

!!! tip "Tip"
    You can choose to filter for <b>multiple conditions at once</b> by keeping them <b>on</b>


## Cleaner

This menu is used to remove text, video, photo etc from messages if the <b>conditions match.</b> It's basically <b>Filters</b> but instead of ignoring or allowing messages, <b>it removes the content it matches</b>

!!! info "Instructions"
    To reach this first you will need to type [/settings](/commands/#settings) on <b>TeleFeed</b>, then click on <b>2759205517</b> to open settings menu for <b>2759205517 phone number</b>. Now click on <b>group1</b> so you can access the setup settings. Finally the <b>Cleaner Menu</b> will show up and you can proceed by clicking on it

!!! Abstract "Options Explained"
    * <b>Audio:</b> Turn this <b>ON</b> if you want to <b>remove audio from messages</b>
    * <b>Videos:</b> Turn this <b>ON</b> if you want to <b>remove video from messages</b>
    * <b>Voicenotes:</b> Turn this <b>ON</b> if you want to <b>remove voicenotes from messages</b>
    * <b>Animations:</b> Turn this <b>ON</b> if you want to <b>remove animations (gif, etc) from messages</b>
    * <b>Photos:</b> Turn this <b>ON</b> if you want to <b>remove photo from messages</b>
    * <b>Stickers:</b> Turn this <b>ON</b> if you want to <b>remove sticker from messages</b>
    * <b>Document:</b> Turn this <b>ON</b> if you want to <b>remove document from messages</b>
    * <b>Text:</b> Turn this <b>ON</b> if you want to <b>remove text from messages</b>
    * <b>Caption:</b> Turn this <b>ON</b> if you want to <b>remove caption from messages</b>

!!! tip "Tip"
    You can choose <b>multiple conditions at once</b> by keeping them <b>on</b>


## Transformation

This command is used for setting up transformations for your redirections on <b>TeleFeed</b>. This command should be run after you have already connected a telegram account with <b>/connect</b> command and have one or more redirections active. With this command you can change messages format, remove words from messages or remove lines if <b>keyword</b> is in it.

!!! Example "Command"
    /transformation {{ action }} {{ feature }} {{ redirectionid }} on {{ phonenumber }}

!!! Example "Command Example"
    <p style="margin-bottom: -13px;"><b>Add (format|power|removeLines) on group1</b></p>
    ```nohighlight
    /transformation add format group1 on 2759205517
    /transformation add power group1 on 2759205517
    /transformation add removeLines group1 on 2759205517
    ```

    <p style="margin-bottom: -13px;"><b>Remove (format|power|removeLines) on group1</b></p>
    ```nohighlight
    /transformation remove format group1 on 2759205517
    /transformation remove power group1 on 2759205517
    /transformation remove removeLines group1 on 2759205517
    ```

    <p style="margin-bottom: -13px;"><b>Show active transformations for grp1 on 2759205517</b></p>
    ```nohighlight
    /transformation active grp1 on 2759205517
    ```

    <p style="margin-bottom: -13px;"><b>Show active transformations on 2759205517</b></p>
    ```nohighlight
    /transformation active on 2759205517
    ```

    <p style="margin-bottom: -13px;"><b>Clear grp1 transformations on 2759205517</b></p>
    ```nohighlight
    /transformation clear grp1 on 2759205517
    ```

    <p style="margin-bottom: -13px;"><b>Clear transformations on 2759205517</b></p>
    ```nohighlight
    /transformation clear on 2759205517
    ```

### Format Feature

This feature is used to change the output format for the message. Basically you can add text on the message and have it output like that (for example a header or footer etc)

!!! info "Information"
    * To change format you can just run the same command again.


!!! Example "Command Example"
    <p style="margin-bottom: -13px;">Add <b>format</b> for <b>group1</b> on <b>2759205517</b></p>
    ```
    /transformation add format group1 on 2759205517
    ```

    <p style="margin-bottom: -13px;">Remove <b>format</b> for <b>group1</b> on <b>2759205517</b></p>
    ```
    /transformation remove format group1 on 2759205517
    ```

{{ center_explain("After typing the command you will be asked to enter how you want to message to output as. Below we are previewing one example of this command.") }}
{{ message_preview("Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industrys standard dummy text ever since the 1500s.", "<b>Header Inserted By TeleFeed</b></br>Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industrys standard dummy text ever since the 1500s.</br><b>Footer Inserted By TeleFeed</b>") }}

!!! Example "Above Transformation Example"
    Inserted Header from Telefeed
    <b>[[Message.Text]]</b>
    Inserted Footer from Telefeed

{{ center_explain('TeleFeed will look at this and replace <b>"[[Message.Text]]"</b> with the actual <b>message</b> and add top and bottom text which will output the example above.') }}

!!! Example "Keywords Supported"
    * <b>[[PROCESS_EMPTY]] =></b> Normally <b>format</b> will ignore empty messages (media etc). If you add this <b>variable</b> then it will start <b>formatting</b> empty messages. This can be used for adding <b>USERNAME</b>, <b>GROUP_NAME</b> on <b>MEDIA</b>

    * <b>[[Message.Text]] =></b> The source message <b>text</b> content
    * <b>[[Message.Group]] =></b> The source message <b>group</b> name

    * <b>[[Message.Username]] =></b> The user <b>Username</b> that sent the message
    * <b>[[Message.First_Name]] =></b> The user <B>First Name</b> that sent the message
    * <b>[[Message.Last_Name]] =></b> The user <b>Last Name</b> that sent the message

    * <b>[[Message.File.Filename]] =></b> The source message <b>file</b> filename
    * <b>[[Message.File.File_Size]] =></b> The source message <b>file</b> filesize
    * <b>[[Message.File.File_Ext]] =></b> The source message <b>file</b> file extension


### Remove Lines Feature

This feature is used to remove lines from the message. You will use keywords to check message lines and if a keyword or one of the keywords (if multiple) is found on the line, TeleFeed will remove that line from the final result.

!!! Example "Command Example"
    <p style="margin-bottom: -13px;">Add <b>removeLines</b> for <b>group1</b> on <b>2759205517</b></p>
    ```
    /transformation add removeLines group1 on 2759205517
    ```

    <p style="margin-bottom: -13px;">Remove <b>removeLines</b> for <b>group1</b> on <b>2759205517</b></p>
    ```
    /transformation remove removeLines group1 on 2759205517
    ```


{{ center_explain('After typing the command you will be asked to enter which keywords you want to look for in the message. You can enter multiple lines so the bot looks for multiple keywords etc.') }}


!!! Example "Input Syntax Example"
    good, bad
    apple

{{ center_explain('The setup we made above will look on every message if a line has the keyword <b>apple</b> (only) or if a line has the keywords <b>good</b> and <b>bad</b> (both) and remove it.') }}

!!! question "Important!"
    This command is not used for removing keywords from the message, what it does is remove the whole line if it contains the keyword. For removing just the keyword you will need to use the <b>next</b> feature called <b>Power</b>


### Power Feature

This is one of the most powerful feature this bot has. It is used to remove and change keywords from the message. You can use <b>regex</b> with this feature

!!! Example "Command Example"
    <p style="margin-bottom: -13px;">Add <b>power</b> for <b>group1</b> on <b>2759205517</b></p>
    ```
    /transformation add power group1 on 2759205517
    ```

    <p style="margin-bottom: -13px;">Remove <b>power</b> for <b>group1</b> on <b>2759205517</b></p>
    ```
    /transformation power group1 on 2759205517
    ```

!!! Info "Input Syntax Example ( Simple )"
    <b>Use the syntax as shown below when you want to replace words or full paragraphs.</b>


    <p style="margin-bottom: -13px;">Change <b>red</b> to <b>blue</b></p>
    ```nohighlight
    "red","blue"
    ```

    <p style="margin-bottom: -13px;">Change <b>22</b> to <b>40</b></p>
    ```nohighlight
    "22","40"
    ```

    <p style="margin-bottom: -13px;">Change <b>2+1=3</b> to <b>2+2=4</b> ( text only, not math )</p>
    ```nohighlight
    "2+1=3","2+2=4"
    ```

    <p style="margin-bottom: -13px;">Remove keyword <b>red</b> from the message</p>
    ```nohighlight
    "red",""
    ```

    <p style="margin-bottom: -13px;">Change paragraph <b>I do not like this text</b> to <b>This is better</b></p>
    ```nohighlight
    "I do not like this text","This is better"
    ```

!!! Info "Input Syntax Example ( Advanced )"

    Use the syntax as shown below when you want to achive result that is not possible with the simple syntax. This syntax uses regex to replace words and keywords and you can do everything you want with the message if you know regex.

    <b>We do not support usage of regex, you are on your own if you decide to use regex.
    Only use it if you know what you are doing.</b>

    <p style="margin-bottom: -13px;">Change <b>telegram.me</b> or <b>tm.me</b> to <b>test.com</b></p>
    ```nohighlight
    (telegram\.me|tm\.me)\/\w+=test.com
    ```

    <p style="margin-bottom: -13px;">Use regex to match <b>gray</b> or <b>grey</b> and change it to <b>red</b></p>
    ```nohighlight
    gr[ae]y=red
    ```

    <p style="margin-bottom: -13px;">Unshort urls, match <b>tag</b> (query) and change it to <b>client1</b> </p>
    ```nohighlight
    url:tag=client1
    ```

    <p style="margin-bottom: -13px;">Match every <b>url</b> or <b>@mention</b> and change it to <b>@tg_feedbot</b></p>
    ```nohighlight
    (@|www|https?)\S+=@tg_feedbot
    ```

!!! Info "Multiple rules"
    To apply <b>multiple transformation</b> rules at once you just need to place them in a newline

    ```nohighlight
    "2+1=3","2+2=4"
    "red",""
    (@|www|https?)\S+=@tg_feedbot
    url:tag=client1
    ```


{{ center_explain('After inputing the syntax above, <b>TeleFeed</b> will ask you for some <b>text</b> or <b>forwarded message</b> so it can run <b>Power Transformation</b> and show you the result.') }}

!!! tip "Tips!"
    * To use regex effectivity, test your regex on [regex101.com](https://regex101.com)
    * Make sure to use the <b>Python Flavor</b> otherwise your regex will not work on <b>TeleFeed</b>
    * Make sure there regex <b>flags</b> <b>global, multiline</b> and <b>single line</b> are enabled when you build your regex via [regex101.com](https://regex101.com) otherwise it will not work with TeleFeed
    * This feature supports <b>Telegram Styling</b> including <b>Bold</b>, <i>Italic</i>, <a href="#">Link</a> etc

## Whitelist

You can set a list of words or regex patterns that tell the bot <b>to process message</b> you receive from source channel <b>only if it has at least one</b> of the whitelisted word or regex pattern match. When you use this command for adding a whitelist, TeleFeed will ask you for your input syntax. Make sure to use the right syntax by reading the examples below.

!!! info "Important Information"
    * Using <b>Simple Syntax</b> will match words partially. This means that when you whitelist the word <b>"es"</b>, it will allow every message containing b<b>es</b>t, r<b>es</b>t, t<b>es</b>t because each of them have the word <b>"es"</b> within.
    * If you want to match words fully, please use the regex example we have provided on <b>Advanced Syntax Panel</b>
    * Make sure to use the <b>Python Flavor</b> with [regex101.com](https://regex101.com) otherwise your regex will not work on <b>TeleFeed</b>


!!! Danger "Warning"
    When this command is used incorrectly, it will cause redirections to stop working. Always make sure you use the right syntax when using whitelist and do use regex only <b>if necessary.</b> Make sure you build your regex with [regex101.com](https://regex101.com) before inserting them into TeleFeed.

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

!!! Info "Input Syntax Example ( Simple )"
    <p style="margin-bottom: -13px;">Process messages only if it has the word <b>bad</b> in it</b></p>
    ```nohighlight
    "bad"
    ```

    <p style="margin-bottom: -13px;">Process messages only if it has the word <b>advertisment</b> in it</b></p>
    ```
    "advertisment"
    ```

    <p style="margin-bottom: -13px;">Allowing <b>multiple words</b> is possible with newlines</p>
    ```
    "This is a match"
    "math"
    "earphones"
    ```

!!! Info "Input Syntax Example ( Advanced )"
    Use the syntax as shown below when you want to achive result that is not possible with the simple syntax. This syntax uses regex to search for words and its more powerful than Simple Syntax.

    <b>We do not support usage of regex, you are on your own if you decide to use regex.
    Only use it if you know what you are doing.</b>

    <p style="margin-bottom: -13px;">Process messages only if it has the any <b>@mention</b> word on it.</p>
    ```nohighlight
    @\S+
    ```

    <p style="margin-bottom: -13px;">Process messages only if it has any "telegram links"</b></p>
    ```nohighlight
    (telegram\.me|tm\.me)\/\w+
    ```

    <p style="margin-bottom: -13px;">Process messages only if it has the word <b>black</b> or <b>white</b></p>
    ```nohighlight
    (black|white)
    ```

    <p style="margin-bottom: -13px;">Process messages only if it has the word <b>es</b> fully ( refer to <b>Important Information</b> )</p>
    ```nohighlight
    \bes\b
    ```

## Blacklist

You can set a list of words or regex patterns which tells the bot that <b>if the message received</b> from source channel has any of the blacklisted words or regex pattern match the bot should <b>ignore</b> that <b>message</b> and do not process it even if it passes all other conditions. When you use this command for adding a blacklist, TeleFeed will ask you for your input syntax. Make sure to use the right syntax by reading the examples below.

!!! info "Important Information"
    * Using <b>Simple Syntax</b> will match words partially. This means that when you blacklist the word <b>"es"</b>, it will block every message containing b<b>es</b>t, r<b>es</b>t, t<b>es</b>t because each of them have the word <b>"es"</b> within.
    * If you want to match words fully, please use the regex example we have provided on <b>Advanced Syntax Panel</b>
    * Make sure to use the <b>Python Flavor</b> with [regex101.com](https://regex101.com) otherwise your regex will not work on <b>TeleFeed</b>


!!! Danger "Warning"
    When this command is used incorrectly, it will cause redirections to stop working. Always make sure you use the right syntax when using whitelist and do use regex only <b>if necessary.</b> Make sure you build your regex with [regex101.com](https://regex101.com) before inserting them into TeleFeed.

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

!!! Info "Input Syntax Example ( Simple )"
    <p style="margin-bottom: -13px;">Block messages only if it has the word <b>bad</b> in it</b></p>
    ```nohighlight
    "bad"
    ```

    <p style="margin-bottom: -13px;">Block messages only if it has the word <b>advertisment</b> in it</b></p>
    ```
    "advertisment"
    ```

    <p style="margin-bottom: -13px;">Blocking <b>multiple words</b> is possible with newlines</p>
    ```
    "This is a match"
    "math"
    "earphones"
    ```

!!! Info "Input Syntax Example ( Advanced )"
    Use the syntax as shown below when you want to achive result that is not possible with the simple syntax. This syntax uses regex to search for words and its more powerful than Simple Syntax.

    <b>We do not support usage of regex, you are on your own if you decide to use regex.
    Only use it if you know what you are doing.</b>

    <p style="margin-bottom: -13px;">Block messages only if it has the any <b>@mention</b> word on it.</p>
    ```nohighlight
    @\S+
    ```

    <p style="margin-bottom: -13px;">Block messages only if it has any "telegram links"</b></p>
    ```nohighlight
    (telegram\.me|tm\.me)\/\w+
    ```

    <p style="margin-bottom: -13px;">Block messages only if it has the word <b>black</b> or <b>white</b></p>
    ```nohighlight
    (black|white)
    ```

    <p style="margin-bottom: -13px;">Block messages only if it has the word <b>es</b> fully ( refer to <b>Important Information</b> )</p>
    ```nohighlight
    \bes\b
    ```


## Bot Settings

On this menu you will find settings such as <b>Start</b>, <b>Stop</b>, <b>Performance Rate</b> and more.

!!! Abstract "Options Explained"
    * <b>Start:</b> Used to <b>start</b> TeleFeed
    * <b>Stop:</b> Used to <b>stop</b> TeleFeed
    * <b>Disconnect Account:</b> This removes your account from TeleFeed. When you use <b>Disconnect Account</b>, TeleFeed will not login into your account unless you use <b>[/connect](/commands/#connect)</b> again
    * <b>Configuration Backups:</b> TeleFeed stores configuration backups every 4 hours. This menu will allow you to restore your configuration.
    * <b>Improve Performance:</b> This option increases TeleFeed Performance. The reason this option is <b>OFF</b> by default is because using it will cause TeleFeed to <b>forward messages out of order.</b> If you do not care about message order, turning this setting <b>ON</b> will <b>increase performance</b> by a <b>big margin</b>
    * <b>Burst Mode:</b> This option controls message rate for TeleFeed. Message rate means the number of messages TeleFeed can send at once. If this option is set to <b>HIGH (default)</b> then TeleFeed will use its max rate for sending messages. Sometimes this might cause <b>Telegram Account Limited Error</b>  which is why we offer a way to lower this rate.
    * <b>Change Server:</b> This option allows you to move to <b>Premium TeleFeed Server</b>. This server will offer better performance and stability.
    * <b>Notifications:</b> This menu allows you to choose if you want TeleFeed to send you notifications.


!!! Info "Information"
    <b>Telegram Account Limited Error</b> is an error which happens when an account sends many messages at once. This does not cause any permanent issues with the account. When this error happens TeleFeed will not send any more messages via the account. This is because Telegram gives an <b>Temporary Wait Limit</b> so TeleFeed will need to for that to expire before it sends another message.


## Action

This command can be used to bypass bots which hide messages or get content from Telegram official GmailBot. Right now this command can bypass both <b>alert</b> & <b>text rewrite</b> modes

!!! Info "Important Information"
    * This command works in <b>case sensitive</b> mode so if you write <b>click me</b> and the button title is <b>Click Me</b>, TeleFeed will not click it.

    * This command will match buttons title partially. This means that you can use an input like <b>Read More</b> to match the button title <b>▼ Read More</b>

!!! Example "Command"
    /action {{ action }} {{ redirectionid }} on {{ phonenumber }}

!!! Example "Command Example"
    <p style="margin-bottom: -13px;">Add Action <b>group1</b> on <b>2759205517</b></p>
    ```nohighlight
    /action add group1 on 2759205517
    ```

    <p style="margin-bottom: -13px;">Remove Action from <b>group1</b> on <b>2759205517</b></p>
    ```nohighlight
    /action remove group1 on 2759205517
    ```

    <p style="margin-bottom: -13px;">Remove all Actions from <b>group1</b> on <b>2759205517</b></p>
    ```nohighlight
    /action clear group1 on 2759205517
    ```


!!! Info "Input Syntax Example"
    Input the name of the button that you want TeleFeed to click one. The title should be case sensitive.

    ```nohighlight
    Read more
    ```

{{ center_explain('After inputing the syntax above, <b>TeleFeed</b> will check every message and if a button matches the keyword <b>"Read more"</b> fully or partially, it will click that button and get the resulting message.') }}

## Translate

This command is used for setting up translation for your redirection groups.

!!! Info "Information"
    <b>SRC:</b> The language code you want to translate from
    <b>DEST:</b> The language code you want to translate into

    <b>Refer to Language Code panel for supported languages code</b>

!!! Example "Command"
    /translate SRC DEST {{ redirectionid }} on {{ phonenumber }}
    /translate remove {{ redirectionid }} on {{ phonenumber }}


!!! Example "Command Example"
    <p style="margin-bottom: -13px;">Translate from <b>English</b> to <b>Italian</b> for <b>group1</b> on <b>2759205517</b></p>
    ```nohighlight
    /translate en it group1 on 2759205517
    ```

    <p style="margin-bottom: -13px;">Remove translate setup for <b>group1</b> on <b>2759205517</b></p>
    ```
    /translate remove group1 on 2759205517
    ```

!!! Info "Supported Language Code"
    * <b>auto =></b> Auto Detect Language,
    * <b>af =></b> afrikaans,
    * <b>sq =></b> albanian,
    * <b>am =></b> amharic,
    * <b>ar =></b> arabic,
    * <b>hy =></b> armenian,
    * <b>az =></b> azerbaijani,
    * <b>eu =></b> basque,
    * <b>be =></b> belarusian,
    * <b>bn =></b> bengali,
    * <b>bs =></b> bosnian,
    * <b>bg =></b> bulgarian,
    * <b>ca =></b> catalan,
    * <b>ceb</b> => cebuano,
    * <b>ny =></b> chichewa,
    * <b>zh-cn =></b> chinese (simplified),
    * <b>zh-tw =></b> chinese (traditional),
    * <b>co =></b> corsican,
    * <b>hr =></b> croatian,
    * <b>cs =></b> czech,
    * <b>da =></b> danish,
    * <b>nl =></b> dutch,
    * <b>en =></b> english,
    * <b>eo =></b> esperanto,
    * <b>et =></b> estonian,
    * <b>tl =></b> filipino,
    * <b>fi =></b> finnish,
    * <b>fr =></b> french,
    * <b>fy =></b> frisian,
    * <b>gl =></b> galician,
    * <b>ka =></b> georgian,
    * <b>de =></b> german,
    * <b>el =></b> greek,
    * <b>gu =></b> gujarati,
    * <b>ht =></b> haitian creole,
    * <b>ha =></b> hausa,
    * <b>haw =></b> hawaiian,
    * <b>iw =></b> hebrew,
    * <b>hi =></b> hindi,
    * <b>hmn</b> => hmong,
    * <b>hu =></b> hungarian,
    * <b>is =></b> icelandic,
    * <b>ig =></b> igbo,
    * <b>id =></b> indonesian,
    * <b>ga =></b> irish,
    * <b>it =></b> italian,
    * <b>ja =></b> japanese,
    * <b>jw =></b> javanese,
    * <b>kn =></b> kannada,
    * <b>kk =></b> kazakh,
    * <b>km =></b> khmer,
    * <b>ko =></b> korean,
    * <b>ku =></b> kurdish (kurmanji),
    * <b>ky =></b> kyrgyz,
    * <b>lo =></b> lao,
    * <b>la =></b> latin,
    * <b>lv =></b> latvian,
    * <b>lt =></b> lithuanian,
    * <b>lb =></b> luxembourgish,
    * <b>mk =></b> macedonian,
    * <b>mg =></b> malagasy,
    * <b>ms =></b> malay,
    * <b>ml =></b> malayalam,
    * <b>mt =></b> maltese,
    * <b>mi =></b> maori,
    * <b>mr =></b> marathi,
    * <b>mn =></b> mongolian,
    * <b>my =></b> myanmar (burmese),
    * <b>ne =></b> nepali,
    * <b>no =></b> norwegian,
    * <b>ps =></b> pashto,
    * <b>fa =></b> persian,
    * <b>pl =></b> polish,
    * <b>pt =></b> portuguese,
    * <b>pa =></b> punjabi,
    * <b>ro =></b> romanian,
    * <b>ru =></b> russian,
    * <b>sm =></b> samoan,
    * <b>gd =></b> scots gaelic,
    * <b>sr =></b> serbian,
    * <b>st =></b> sesotho,
    * <b>sn =></b> shona,
    * <b>sd =></b> sindhi,
    * <b>si =></b> sinhala,
    * <b>sk =></b> slovak,
    * <b>sl =></b> slovenian,
    * <b>so =></b> somali,
    * <b>es =></b> spanish,
    * <b>su =></b> sundanese,
    * <b>sw =></b> swahili,
    * <b>sv =></b> swedish,
    * <b>tg =></b> tajik,
    * <b>ta =></b> tamil,
    * <b>te =></b> telugu,
    * <b>th =></b> thai,
    * <b>tr =></b> turkish,
    * <b>uk =></b> ukrainian,
    * <b>ur =></b> urdu,
    * <b>uz =></b> uzbek,
    * <b>vi =></b> vietnamese,
    * <b>cy =></b> welsh,
    * <b>xh =></b> xhosa,
    * <b>yi =></b> yiddish,
    * <b>yo =></b> yoruba,
    * <b>zu =></b> zulu,
    * <b>fil =></b> Filipino,
    * <b>he =></b> Hebrew

## Clone

This command is used for cloning (mirror) chats/channels or users messages from SOURCE to DESTINATION

!!! Info "Important Information"
    * If you have a redirection setup with the same ID's (SOURCE, DESTINATION) when using this command. It will use every feature you have currently configured on that setup.
    * When using this command with an current setup, that setup will not be able to send any new message until /clone finishes.
    * When using this command, the bot might delay message redirection for your setups.

!!! Warning "Warning"
    * Because this commands sends a high amount of messages in a short time it will cause temporary limits from telegram servers. Basically when this happens you will not be able to send any message from this account for <b>5 minutes</b> to <b>1 hour</b> depending on the limit.

    * You will get a notification from the bot when such a limit is encountered (You will also notice yourself since you will not be able to send any message when that happens). There's no way around this other than not using this command.


!!! Example "Command"
    /clone {{ source }} {{ destination }} on {{ phonenumber }}
    /clone {{ source }} {{ destination }} {{ limit }} on {{ phonenumber }}

!!! Example "Command Example"
    <p style="margin-bottom: -13px;">Clone from <b>2759205517</b> to <b>28887387</b> on <b>2759205517</b></p>
    ```nohighlight
    /clone 2759205517 28887387 on 2759205517
    ```

    <p style="margin-bottom: -13px;">Clone from <b>2759205517</b> to <b>28887387</b> with LIMIT=<b>200</b> on <b>2759205517</b></p>
    ```
    /clone 2759205517 28887387 200 on 2759205517
    ```

## Global
The /global command can be used to apply globally one specific configuration. This command works only for the features shown below.

!!! Info "Supported Features"
    - [x] Transformation
    - [x] Translate
    - [x] Watermark
    - [x] Action
    - [x] Whitelist & Blacklist
    - [x] Filters & Cleaners

!!! Example "Command"
    /global {{ action }} {{ redirectionid }} on {{ phonenumber }}

!!! Example "Command Example"
    <p style="margin-bottom: -13px;">Make <b>group1</b> configuration global on <b>2759205517</b></p>
    ```
    /global add group1 on 2759205517
    ```

    <p style="margin-bottom: -13px;">Remove group1 <b>configuration</b> from global on 2759205517</p>
    ```
    /global remove group1 on 2759205517
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

{{ center_explain('After running the above commands <b>you will be asked</b> to input the time that you want TeleFeed to turn on and off your setups.
Here are a few example syntax on how to do this.') }}

!!! Example "Input Syntax Example "
    <p style="margin-bottom: -13px;">Start at <b>12:30</b> and Stop at <b>2:30</b></p>
    ```nohighlight
    12:30 - 2:30
    ```

    <p style="margin-bottom: -13px;">Start at <b>09:00</b> and Stop at <b>21:00</b></p>
    ```nohighlight
    9:00 - 21:00
    ```

{{ center_explain('In this case, TeleFeed will <b>turn on</b> group1 <b>at 12:30</b> and <b>turn off at 2:30</b>') }}

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

{{ center_explain('After running <b>/selectusers add group1 on 2759205517</b>, <b>you will be asked</b> to input a list of <b>users id\'s</b>. Input the user you want to allow messages from. Separate them using commads <b>,</b> for multiple users.') }}

!!! Example "Input Syntax Example "
    ```nohighlight
    6516516,651651651,16516516
    ```

{{ center_explain("Now every time you receive a message on <b>group1 SOURCE</b>, TeleFeed will check if the user who sent the message is allowed based on your <b>user id's input.</b> If so it will process the message otherwise it will ignore it.") }}

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

!!! Info "Information"
    * This command can cause redirection to run slower because TeleFeed will need to generate the watermark before it sends the message

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


## PlanSwap

This command is used to exchange plans between phone numbers. You can use this to move your paid plan from one number to another.

!!! Warning "Important"
    * This command <b>has a fee of 1 day</b> for each usage. This means that when you move a <b>31 Days Pro Plan</b> from 27505517, you will get <b>30 Days of Pro Plan</b> on 32529517
    * The <b>source number</b> needs to be connected with your account for <b>planswap</b> to work.
    * The <b>destination number</b> needs to be in <b>Free Plan</b> for <b>planswap</b> to work.

!!! Example "Command"
    ```nohighlight
    /planswap SOURCE_PHONE_NUMBER DESTINATION_PHONE_NUMBER
    ```

!!! Example "Command Example"
    <p style="margin-bottom: -13px"><b>Exchange Plan from 27505517 to 32529517</b></p>
    ```nohighlight
    /planswap 27505517 32529517
    ```

## Delay

This command is used for setting up delays for your redirections. When delay is active, TeleFeed will schedule messages and send them later. This command can be run in two modes. Delay mode and spread mode. You can turn Spread Mode On via the instructions below.

* <b>Delay Mode</b> This mode is used by default. On this mode, TeleFeed will delay messages exactly the time they are received + delayed amount. This means that if the source sends 100 messages at once, with a 10 second delay set TeleFeed will send 100 messages after 10 seconds.
* <b>Spread Mode</b> In this mode, TeleFeed will spread messages evenly. This means that if the source sends 100 messages and you have a delay of 10 seconds set. TeleFeed will delay each message 10 second from the last one.

!!! Example "Turn On Spread Mode"
    You can turn on spread mode by going to ```/settings > Phone > Redirection > Delay Spread Mode On```

!!! Example "Command"
    /delay {{ amount }} {{ redirectionid }} on {{ phonenumber }}  
    /delay {{ amount }} on {{ phonenumber }}

!!! Example "Command Example"
    <p style="margin-bottom: -13px">Delay <b>group1</b> by <b>120 seconds</b> on <b>2759205517</b></p>
    ```nohighlight
    /delay 120 group1 on 2759205517
    ```

    <p style="margin-bottom: -13px">Delay all redirections by <b>120 seconds</b> on <b>2759205517</b></p>
    ```
    /delay 120 on 2759205517
    ```

    <p style="margin-bottom: -13px">Remove delay for <b>group1</b> on <b>2759205517</b></p>
    ```
    /delay 0 group1 on 2759205517
    ```

    <p style="margin-bottom: -13px">Remove global delay on <b>2759205517</b></p>
    ```
    /delay 0 on 2759205517
    ```

## Chats

This command is used to get a list of groups, bots, channels or users ID's for use [/redirection](/commands/#redirection) command.

!!! Example "Command"
    /chats {{ phonenumber }}

!!! Example "Command Example"
    <p style="margin-bottom: -13px;">Getting chats for <b>2759205517</b></p>
    ```nohighlight
    /chats 2759205517
    ```

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
