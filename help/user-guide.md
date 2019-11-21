---
description: 'Last Updated: Nov. 2019'
---

# User Guide

## Technical concepts

WhatABot is an automatic conversational response service that integrates Chat technologies and Bots**.** Its goal is to support users that need to request  information, services, or products.  Bots are designed to return logical responses according to their purpose by following a set of set rules which are easily defined.

### Bot Model

These  rules are known as "Bot Models". Customers can build Bot Models, step by step, in the Portal's Bot Designer.

### Status

The Bot must know the exact point in which a conversation is taking place in order to generate responses that are coherent to the active conversation context. To do so, the Bot uses a status machine that evaluates and determines the context its given in order to respond in the correct fashion.

### Bot Variables

For the Bot to be more accurate and able to determine the context of the conversation, besides the status, a series of variables can be defined. During the conversation those variables are getting enriched. It is possible to define as many variables as needed depending on the rules and scope given to the Bot.

There is an initial status that a Bot needs to start new conversations, then as many statuses that are needed will be defined accordingly to the given parameters of the topics. The Bot then will be able to respond correctly and efficiently. Every time the Bot responds with a  “possible to do”, or "not possible to do” \(or yes or no\) response, it will transition to a different status in the conversation  as needed to complete the given task.  


### Conversation Variables

They are defined within an object called a **chat** that contains said variables, and as mentioned above, these variables are filled during the conversation.

The scope of these variables is defined by each conversation and the duration of the dialogue \(timeout\).

### Message variables

They are defined within an object called **msg** and represent the message sent by the end user to the Bot:

| variable | Description |
| :--- | :--- |
| `msg.body` | This variable shows the actual text of the message sent by the user. |
| `msg.type` | This variable shows the type of message sent by the user. |
|  | `chat` if the sent message is a text message. |
|  | `image`if the sent message is an image or a picture. |
|  | `document`If the sent message  is a PDF, Word, Excel or Powerpoint document. |
|  | `location`If the sent message is a GPS location. |
|  | `audio`If the sent message is an audio. |
|  | `video`If the sent message is a video. |
|  | In the case that the message type sent is different from chat, in the `msg.body` variable you can get the content of the multimedia element in DataUrl format. |
| `msg.id` | This variable displays the user identifier of the person that sent the message. |
|  | For WhatsApp, the identifier is the country code + the phone number + @c.us. |
| `msg.profile` | This variable displays the name of the user who sent the message. |
|  | In the case of WhatsApp, most of the time this field will appear blank because users when installing WhatsApp usually do not supply it. |
| `msg.email` | This variable shows the email address of the user that sent the message. |
|  | Not available on WhatsApp |
| `msg.line` | This variable displays the WhatsApp line identifier, or the Facebook page in which the Bot interacts with the end user who send the message. |
| `msg.platform` | This variable shows the type of messaging platform used by the Bot. Whats App - Facebook Messenger - or- Web Chat |

> The message variables are brief and have only scope while the Bot determines the response to be returned to the end user.

### Designer

The Bot model is defined in the designer by simple flow diagrams, which are composed of Steps and Connectors.

![Bot Flow Chart](../.gitbook/assets/image%20%282%29.png)

Each diagram starts with a ‘Status’ step \(represented in green\) and via Connector lines   linking to other Intermediate Steps until you reach a Final Step of ‘Message’ \(represented in red\).

As many diagrams as states will have the conversation are defined. The designer draws a line for each.

### Types of steps

**Status step**

This step represents the conversation status. Its  the initial step that the Bot must follow to generate the response for the end user depending on the state of the conversation.

### Designer Interface

![Initial Bot](../.gitbook/assets/image%20%285%29.png)

## **Condition step** 

Through this step the Bot evaluates a condition to determine which path to continue the flow of conversation. Yes, leading to one direction of conversation and no, leading in another.

![Condition](../.gitbook/assets/image%20%287%29.png)

## **Process Step**

Through this step the Bot can be connected to external systems              \(ERP, CRM, etc\) and obtain or send information by using webhooks.

![Process](../.gitbook/assets/image%20%281%29.png)

## **Expression Step**

Through this step the Bot can make simple calculations using mathematical, numerical, text and/or date-time formulas.

![Expression ](../.gitbook/assets/image%20%2813%29.png)

##  AI step

![AI step](../.gitbook/assets/ai%20%281%29.PNG)



The AI step can further the intelligence of your Bot by adding an extra level of thinking. 

By incorporating specific “Entities” to understand from “Phrases” entered by the user and creating an “Intent” list. The AI can understand the user’s intention and provide the proper outcome.

This gives you the ability to fine tune the AI to recognize specific Entity points, that the Bot uses to understand more difficult Intents. Using different variables to guide the system to understand the Intent from the Entities it finds in the given set of Phrases.

## **Trace log step**

Through this step the Bot can make a record of the conversation activity. It is useful for creating reports and statistics on the use of the Bot.

![Trace](../.gitbook/assets/image%20%283%29.png)

##  **Message Step**  

Through this step the Bot finishes the flow and gets the final answer to be returned to the end user. In this step it is possible to change the conversation status if necessary.

![Message](../.gitbook/assets/flowbot_wab-06.png)

![Message](../.gitbook/assets/flowbot_wab-06.png)

### Webhook

For the Bot to connect to external systems, its necessary from within the Process Step to specify a Webhook url which must be developed in the programming language of your choice and must meet the following specifications:

* The Web Service must be type RESTful with JSON format. 
* Methods allowed GET and POST. 
* The service must respond with a chat object that includes the variables defined in the Bot and Process Step:

![image](https://chat-bots.co/assets/img/docs/es/webhook-code-01.png)

![image](https://chat-bots.co/assets/img/docs/es/webhook-code-01.png)

* All Bot variables are type "text". 
* If the method is POST, you can send part of the `chat` objects and `msg` that are marked in the Process Step

![image](https://chat-bots.co/assets/img/docs/es/webhook-code-02.png)

![image](https://chat-bots.co/assets/img/docs/es/webhook-code-02.png)

## Bots

In this section you will find everything you need to create, edit and delete bots.

### Available Bots

To view the available bots, click the "Bots" button on the side menu, to be directed to the Bots section.

In this section, available bots appear on cards, grouped into drop down menus, separated by customer. Click on Bots to open the tab.

![Tab For Bots](../.gitbook/assets/image%20%284%29.png)

![Tab For Bots](../.gitbook/assets/image%20%284%29.png)

Each card shows the name, image, status and description of a bot

![content of Bot](../.gitbook/assets/image%20%288%29.png)

### Open bot

Identify the bot to open and position the cursor on it and click it

![Bot module ](../.gitbook/assets/image.png)

Two buttons appear on the card: "Open" \(in blue\), this opens the bot in the designer; and "Delete" \(in red\) this offers the option to remove the bot.

Click "Open" the bot will open in the designer to be viewed or edited.

![Designer](../.gitbook/assets/image%20%2815%29.png)

![Option to open bot](../.gitbook/assets/image%20%2811%29.png)

![Option to open bot](../.gitbook/assets/image%20%2811%29.png)

The designer interface is the space where you can create and edit the models. It is composed of 4 parts:

![Interface](../.gitbook/assets/image%20%286%29.png)

1. Bot logo Image \(with status\), name and client of the bot.

2. Toolbar of the bot. The toolbar offers the following options:

| Tool | Icon | Function |
| :--- | :--- | :--- |
| Zoom in |  | Increases the size of the model |
| Zoom out |  | Decreases the size of the model |
| Select/Hand |  | Select: selection mode./Hand: allows to move the work space. |
| Create status |  | Creates a new status in the model |
| Save bot |  | Saves changes made in the bot |
| Bot options |  | Opens the options menu for the bot |

3. Initial Status.

4. Work space

### **Creation of a bot**

In the "Bots" section at the bottom right, a circular button with the \(+\)icon appears. 

  If you'd like to see a video on the procedure click here.

The designer where you can start building the bot will be opened.

![Initial bot](../.gitbook/assets/initial_wab.png)

Click here for a video tutorial.

> click here [https://youtu.be/T6y3sTUjcVQ](https://youtu.be/T6y3sTUjcVQ)

### Create status step 

![Initial](../.gitbook/assets/initial.PNG)

Identified with green color and flag icon. Status step is used to create different states in a conversation.

To create a status step, go to the toolbar, then click the "Create Status" button, identified with the little flag icon.

![Create Status](../.gitbook/assets/status_wab.png)

The new status step, will appear at the bottom which divides the work space with a dark blue horizontal line or \(connector\) this connects the different steps.

The new status step, will appear at the bottom which divides the work space with a dark blue horizontal line or \(connector\) this connects the different steps.

![State 1](../.gitbook/assets/state_1_wab.png)

#### Properties of the  Status step.

To open the properties of a state step, click the "Options" button on it, a window like the following will appear: 

![options\_step](../.gitbook/assets/options_step.PNG)

A Status step has two properties: 

1. **Name:** Enter the name that will have the status step. 

2. **Next step:** next step in the flow of the model.

### Create Condition step 

![Condition](../.gitbook/assets/flowbot_cb-02.png)

Identified with the color yellow and the question mark icon \(? \). This step evaluates a condition, if true, the flow of the conversation will take the "Yes" path; otherwise, the flow of the conversation will take the "No" path. Position yourself on any intermediate step, click the "Next" button, "Yes"/"No" \(in condition\), an option menu will appear with the available steps. 

![Condition](../.gitbook/assets/condition_wab.png)

Click on "Condition", then the condition step will appear connected with the previous step.

#### Properties of Condition Step 

To open the properties of a condition step, click on the "Options" button, an option window will appear.

![options\_condition](../.gitbook/assets/options_condition.PNG)

A condition step has 4 properties: 

1. Name: enter the name for the step condition. 

2. Condition: condition to evaluate. You have the following options:

* The variable to evaluate \(`a`\). 
* Comparison operator, you can choose any of the following options:

| Operator | Kind | Description |
| :--- | :--- | :--- |
| **Equal to** | Text / Numeric | If the variable `a`is equal to the value `b`. |
| **Start with** | Text | If the content of the variable `a`starts with or is equal to the value `b`. |
| **Do not start with** | Text | If the content of the variable `a`does not start with the value `b`. |
| **Contain** | Text | If anywhere in the content of the variable `a`is the value of `b`. |
| **Do not have** | Text | If the value of `b`is not contained in any part of the variable `a`. |
| **Empty** | Text | If the variable `a`has no content. |
| **Not empty** | Text | If the variable `a`contains at least one character. |
| **Greater than** | Text / Numeric | If the value of the variable `a`is greater than the value of `b`. |
| **Greater than or equal** | Text / Numeric | If the value of the variable `a`is greater than or equal to the value of `b`. |
| **Less than** | Text / Numeric | If the value of the variable `a`is less than the value of `b`. |
| **Less than or equal to** | Text / Numeric | If the value of the variable `a`is less than or equal to the value of `b`. |
| **Regex** | Text | If the value of the variable `a`complies with the regular expression given in `b`. |

* The value \( `b`\) against which it will be compared `a`.
  1. **Yes** : next step in the flow of the model in case condition is fulfilled.
  2. **No** : next step in the flow of the model in case condition is **not** fulfilled.

     `watch video`

### Create Process step 

![Process](../.gitbook/assets/flowbot_cb-03.png)

Identified with the blue color and the gear like icon. The process step is used to connect to third party systems \(by using Webhooks\) and obtain or send information. Position your cursor on any intermediate step, click the "Next" button, "Yes"/"No" \(in condition\), an option menu will appear with the available steps. 

![Process](../.gitbook/assets/process_wab.png)

Click on "Process", then the process step connected with the previous step will appear.

#### Properties of a process step.

To open the properties of a process step, click on the options button of the process, an option window will appear as follows: 

![option\_process](../.gitbook/assets/options_process.PNG)

The Process step has 3 properties:

1. **Name** : Enter the name for the process step.
2. **Webhook** : method, url and  necessary variables for the webhook to operate correctly.

Method: you can choose between GET or POST to make the request.

Variables: you can send and receive variables as follows:

* Webhook variables: \(GET/POST\) define the variables that the Webhook will return from selected website URL 
* POST variables: \(POST\) select the variables you are sending to the website via the Webhook. 

![](../.gitbook/assets/options_process2.PNG)

3.**Next step:** "next step" field in menu window sets next stage of flow for the model.  

3.**Next step:** "next step" field in menu window sets next stage of flow for the model.  

### Create Expression step 

 

![Expression](../.gitbook/assets/flowbot_cb-04.png)

Identified with the brown color and the icon \(&lt;/&gt;\). This step allows you to evaluate an expression \(or formula\) and store the result in a variable \(new or existing\) from the conversation for later use. Position your cursor on any intermediate step, click the "Next" button, "Yes"/"No" \(in condition\), a popup menu will appear with the available steps. 

![Expression](../.gitbook/assets/expression_wab.png)

Click on "Expression", then the expression step connected to the previous step will appear.

Properties of step expression.

To open the properties of an expression step, click the "Options" button on the expression step, a menu window like the following will appear:

![Image\_step properties](../.gitbook/assets/options_expression.PNG)

![Image\_step properties](../.gitbook/assets/options_expression.PNG)

An expression step has four properties: 

1. **Name:** enter the name for the expression step.

2. **Variable bot:** the variable where the result of evaluating the expression will be saved, note that you can create it \(by writing the name\) or use an existing variable \(selecting it from the drop-down field\).

Remember that it is a conversation variable `chat.`as seen at the beginning of the field.

3. **Expression:**  In this field enter the expression you want to evaluate, note that literal values as text \(strings\) must be enclosed in quotes " "

`"Good morning"`,  values are entered without quotation marks: `12`if you use decimal point it should go to: `12.56`.

It can also include variables \(of conversation or message\) that must go between symbols "greater than" and "less than": `<msg.body>`, `<chat.myVariable>`. 

In the expression you can do arithmetic operations: `3 + 6`and use functions. An expression has the following menu options:

![Step properties](../.gitbook/assets/step-properties.png)

1. **Insert variable:** you can insert an existing variable. 

2. **Functions:** The available functions are:

| Kind | Function / Operator | Description |
| :--- | :--- | :--- |
| Arithmetic | **+** | **Add** : add 2 numeric values `3 + 8`returns 11 |
|  |  | **Concatenate** : concatenate text values `"Good" + " " + "morning"`return "Good morning" |
|  |  | **Add days** : add days to a date `Now + 1`return the date of tomorrow. |
|  | **-** | **Subtract** : subtracts 2 numeric values `8 - 4`returns 4. |
|  |  | **Subtract days** : subtracts days to a date `Now - 1`returns yesterday's date. |
|  |  | **Subtract dates** : subtract one date from another `Date("2018-04-25") - Date("2018-04-23")`returns 2. |
|  |   **\***   | **Multiply** : multiply 2 numeric values `3 * 8`returns 24. |
|  | **/** | **Divide** : divide 2 numeric values `27 / 9`returns 3. |
|  | **%** | **Module** : obtains the remainder of the division of 2 numerical values `14 % 3`returns 2. |
|  | **^** | **Power** : get the power of a number `3 ^ 3`returns 27. |
| Numerical | **Val \(txt\)** | Converts a text value to numeric `Val("54")`returns 54. |
|  | **IsNumeric \(txt\)** | Determines \(true / false\) if a value is numeric `IsNumeric(735)`returns "true". |
|  | **Abs \(num\)** | Returns the absolute value of the numeric value, `Abs(-3)`returns 3. |
|  | **Floor \(num\)** | Returns the resulting integer by rounding down the given numeric value,`Floor(7.85)`returns 7. |
|  | **Ceiling \(num\)** | Returns the resulting integer when rounding up the given numeric value,`Ceiling(7.25)`returns 8. |
|  | **Min \(num, num\)** | Returns the smallest value between the two given numbers, `Min(9, 4)`returns 4. |
|  | **Max \(num, num\)** | Returns the highest value between the two given numbers, `Max(7, 3)`returns 7. |
| Text | **Len \(txt\)** | Returns the length of the text string `Len("Texto")`returns 5. |
|  | **Str \(txt, \[format\]\)** | Returns the numeric value or date as a text string according to the [format](https://chat-bots.co/es/docs/bots#) \(optional\) |
|  | **LowerCase \(txt\)** | Returns text string converted to lowercase `LowerCase("TEXTO")`returns "text" |
|  | **UpperCase \(txt\)** | Returns text string converted to upper case `UpperCase("texto")`returns "TEXT". |
|  | **TrimLeft \(txt\)** | Returns the text string by removing the blank spaces on the left,`TrimLeft(" texto")`returning "text". |
|  | **TrimRight \(txt\)** | Returns the text string by removing the blanks on the right,`TrimRight("texto ")`returning "text". |
|  | **Left \(txt, num\)** | Returns the specified number of characters at the beginning of the text string `Left("Hello world", 4)`returns "Hello". |
|  | **Right \(txt, num\)** | Returns the specified number of characters at the end of the text string `Right("Hello world", 5)`returns "world". |
|  | **Mid \(txt, pos, lng\)** | Returns the characters from the center of the text string, according to position and length`Mid("Hello world", 3, 3)`returns "the". |
|  | **InStr \(txt, search\_txt\)** | Returns the position of the text to be searched within the given text string `InStr("Hello world", "the")`returns 3. |
|  | **Replace \(txt, search\_txt, new\_txt\)** | Returns the text string replacing the text to search for the new text `Replace("Hello world", "world", "planet")`returns "Hello planet." |
| Date | **Date \(txt\)** | Converts a text value to date / time `Date("1995/09/18 19:32:24")`returns \# 1995-09-18 \#. |
|  | **IsDate \(txt\)** | Determines whether a text value can be converted to date / time `IsDate("1995/09/18 19:32:24")`returns True. |
|  | **Day \(date\)** | Returns the day of the given date `Day("1995/09/18 19:32:24")`returns 18. |
|  | **Month \(date\)** | Returns the month of the given date `Month("1995/09/18 19:32:24")`returns 9. |
|  | **Year \(date\)** | Returns the year of the given date `Year("1995/09/18 19:32:24")`returns 1995. |
|  | **Hour \(date\)** | Returns the time \(0 - 23\) of the given date / time `Hour("1995/09/18 19:32:24")`returns 19. |
|  | **Minute \(date\)** | Returns the minute \(0 - 59\) of the given date / time `Minute("1995/09/18 19:32:24")`returns 32. |
|  | **Second \(date\)** | Returns the second \(0 - 59\) of the given date / time `Second("1995/09/18 19:32:24")`returns 24. |
| Logic | **And** | Given 2 values ​​of Boolean type, it returns True if both values ​​are evaluated as True, otherwise it returns False, `True And True`returns True. |
|  | **Or** | Given 2 values ​​of Boolean type, it returns True if any of the values ​​is evaluated as True.`True Or False`returns True. |
|  | **Xor** | Given 2 values ​​of Boolean type, it returns True if only one of the values ​​is evaluated as True.`True Xor True`returns False. |
|  | **Not** | Converts a value of Boolean type to its opposite `Not False`True- returns |
|  | **Iif** | Checks if a condition is met and return "yes value" if true or "no value" otherwise`iif(<chat.miVariable> = "hola", "valorSi", "ValorNo")` |
| Constants | **True** | True Counter \(true\) |
|  | **False** | Constant False \(false\) |
|  | **Now** | Current date and time of the system. |
| Operators | **=** | **equals**: checks if two values ​​of the same type are equal `3 = 3`returns True. |
|  | **&gt;** | **Greater than** : checks if the first of 2 values ​​of the same type is greater than the second one`3 < 3`returns False. |
|  | **&gt; =** | **Greater than or equal to** : checks if the first of 2 values ​​of the same type is greater than or equal to the second `3 >= 3`returns True. |
|  | **&lt;** | **Less than** : checks if the first of 2 values ​​of the same type is less than the second one `3 < 3`returns False. |
|  | **&lt;=** | **Less than or equal to** : checks if the first of 2 values ​​of the same type is less than or equal to the second `3 <= 3`returns True. |
|  | &lt;&gt; | **Different** : checks if 2 values ​​of the same type are different `3 <> 3`returns False. |

3. In the literal text values \(Strings\)  between quotes you can insert emojis.

![Image](../.gitbook/assets/emoticones.png)

![Image](../.gitbook/assets/emoticones.png)

4. **Next step:** next step in the flow of the model. 

4. **Next step:** next step in the flow of the model. 

## AI step

![AI](../.gitbook/assets/ai.PNG)

By incorporating specific “Entities” to understand from “Phrases” entered by the user and creating an “Intent” list. The AI can understand the user’s intention and provide the proper outcome.

This gives you the ability to fine tune the AI to recognize specific Entity points, that the Bot uses to understand more difficult Intents. Using different variables to guide the system to understand the Intent from the Entities it finds in the given set of Phrases. 

\*This section is further described in detail further below "Introduction to AI.

### Create Tracing step 

![Trace log](../.gitbook/assets/flowbot_cb-05.png)

Identified with the gray colored pencil  icon. This step allows you to generate a trace with up to 3 dimensions that is recorded in the system each time the conversation passes through it. It is useful for creating reports and statistics on the use of the Bot.

Position your cursor on any intermediate step, click the "Next button, "Yes"/"No" \(in condition\), a popup menu will appear with the available steps. 

![Image Trace log](../.gitbook/assets/trace-log_wab.png)

![Image Trace log](../.gitbook/assets/trace-log_wab.png)

Click on "Trace", then the trace step connected to the previous step will appear.

#### Properties of the tracing step.

To open the properties of a trace step, click on the "Options" button, a menu window like the following will appear:

![Properties window](../.gitbook/assets/trace-step.png)

![Properties window](../.gitbook/assets/trace-step.png)

A trace step has 4 properties: 

1. **Name:** enter the name for the trace step. **Remember that  this name connects to the trace ability reports that will be generated.** 

1. **Name:** enter the name for the trace step. **Remember that  this name connects to the trace ability reports that will be generated.** 

2.  **Dimensions:** You can save up to 3 different values. You can include variables.

> Remember that the trace includes 3 default dimensions that are date/time, line, and contact. 
>
> 3. **Annotation:** You can generate a note to your liking or need, this note can contain the amount of variables you need. 
>
> 4. **Next step:** Next step in the flow of the model.

> Remember that the trace includes 3 default dimensions that are date/time, line, and contact. 
>
> 3. **Annotation:** You can generate a note to your liking or need, this note can contain the amount of variables you need. 
>
> 4. **Next step:** Next step in the flow of the model.

### Create Message step 

![Message image](../.gitbook/assets/flowbot_wab-06.png)

![Message image](../.gitbook/assets/flowbot_wab-06.png)

Identified with the color red and the message bubble icon.

The message step is used to send a message to the user interacting with the bot, and capture the answer in a variable and jump to a status.

This step just as jump, is the last of a flow within a status, therefore, it does not allow descending steps.

Position your cursor on any intermediate step , click on the "Next" button, "Yes" / "No" \(in condition\), a popup menu with the available steps will appear.

![Message](../.gitbook/assets/message_wab.png)

Click on "Message", the message step connected to the previous step will appear.

#### Properties of the message step.

To open the properties of a message step, click on the "Options", a menu window like the following will appear:

![Message\_Step1](../.gitbook/assets/message_step.png)

![Message\_Step2](../.gitbook/assets/message_step2.png)

The message step has 3 properties: 

1.**Name:** enter the name for the message step. 

2. **Message**

* SENDING A MESSAGE
  * **Send message:**   in this field compose the message you want to send to the user, remember that this text can include variables, emojis and multimedia content; to insert them you can use the options \(buttons\) that are on the right side of the field.

    \*\*\*\*

  * **Quick answers:** Quick answers allow you to insert response buttons \(not applicable in WhastApp\) selectable by the user with a number of options to choose from. If you want the button to have a label \(text\) different from its value, separate the value of the label with a vertical bar \(or Sheffer Stroke\)  \( \| \); in this way `size S | a`, it would present a button with the label "Size S" but when selecting it the returned value would be "a". If you only use the label, that will be the value of the button when selected: it `size S`presents a button with the label "size S" and returns the value "size S" when selected.

> Separate each "quick response" with a comma \( , \) or press the key `ENTER`.
>
> * OPTIONS
>   * **Save user response in:** If the user responds to the message sent, you can save that answer in a new variable or an existing one. Remember that it is a `chat.` conversation variable,  as seen at the beginning of the field.
>   * **Download multimedia content of the response:** If the user's response is multimedia content \(audio, image, video, or document\), you can store said content in DAtaURI in the previously defined variable.
>   * **Mask user response:** Prevents the storage of the response in the Chat-Bots databases.
>
>   * \*Take into account that if you mask an answer, you will not have access to it later to generate reports or queries.

1. **Change bot to status:** You can switch the conversation to another state or continue in the current state. After you define the next state, you will notice a mark in the step that tells you which state will follow the flow of the conversation.

![Message\_Initial](../.gitbook/assets/message_initial_ok.png)

### Create jump step 

![Jump](../.gitbook/assets/flowbot_wab-07.png)

Identified with the orange color and right bending arrow icon. The jump step is used to pass the conversation to another bot. This step as well as message step, is the last of a flow within a state, therefore, does not allow descending steps. Position your cursor on any intermediate step, click the "Next" button, "Yes"/"No" \(in condition\), a popup menu will appear with the available steps. 

![Jump](../.gitbook/assets/jump_wab.png)

Click on "Jump", then the jump step connected to the previous step will appear.

#### Jump step properties

To open the properties of a jump step, click the "Options" button on it, a menu window like the following will appear:

![jump Step](../.gitbook/assets/options_jump.png)

The jump step has 2 properties: 

1. **Name:** type the name for the jump step. 

2. **Go to bot:** The Bot to which you are going to switch the conversation, this property is divided into 2 fields:

* **Customer:** select the client to where the bot you are going to use is located. 
* **Bot:** select the bot to which the conversation will switch to.

> A mark on the step will indicate which bot will continue the conversation.

![Jump\_new bot](../.gitbook/assets/jump_new-bot_ok.png)

> The conversation variables persist in the bot to which you made the jump.





### Save bot

To save a new bot, click on the image, name, status, and customer area, as shown in the image. 

![Save bot](../.gitbook/assets/save_bot_ok.png)

A window will appear as follows: 

![Modal](../.gitbook/assets/modal-save.png)

In this window you will find 4 options:

1. **Name of the bot:** Enter a name for the bot.

2. **Customer:** Select a customer for the bot.

3. **Description:** Type a description for the bot.

4. **Bot image:** \(optional\) You can assign an image to the bot.

* To do this, click the "Choose Image" button:

![Chosse image](../.gitbook/assets/bot-picture_not.png)

A file manager will appear \(varies depending on the operating system\), select the image you want to upload.

* The image will be loaded into the box \(as shown below\), you can move it with the cursor to place it in the desired position, you can also make it bigger \(to the right\) or smaller \(to the left\) by moving the slider located at the bottom.

![Picture bot](../.gitbook/assets/bot-picture.png)

* After entering all parameters correctly, click the "Save" button, a notification will appear at the bottom right indicating that the bot has been successfully saved.

![Bot save](../.gitbook/assets/bot-save-ok.png)

> If you need to modify any of the parameters described above, repeat the process.

To save later modifications to the structure or data of the bot, click the "Save" button. 

![Button save ](../.gitbook/assets/save_bot_botton.png)





### Delete bot

To delete a bot you must go to the "Bots" section and click on the bot that you are going to delete. 

![](../.gitbook/assets/delete_bot1.png)

Then a "Delete" button will appear, click it.

![Delete bot](../.gitbook/assets/delete_bot2.png)

A confirmation message will appear, click the "Delete" button to delete the bot or click "Cancel" to abandon the operation.

![ Delete Button](../.gitbook/assets/delete_bot3.png)

![ Delete Button](../.gitbook/assets/delete_bot3.png)

### Bot options

Each bot has a panel with multiple options, to access it you must go to the toolbar "Settings" button, then click on it. 

![](../.gitbook/assets/options_tool_key.png)

A panel with the available options will appear.

![](../.gitbook/assets/options_tool_key1.png)

To hide the options pane, move the cursor to the toolbar and click the "Close" button \(near the same as you used to open the panel, but in this case with the icon \( X \).

![](../.gitbook/assets/options_close_ok.png)

#### Tools

Below is the list of tools you have available when working with a bot.

**Validate bot**

This option allows to check if the current model is valid and will run smoothly. Among the validations are:

* Continuity between the steps.
* Orphaned steps.
* Configuration of the parameters of each step.

This option only validates the structure of the bot, not its overall performance. To validate a bot, click Options&gt;Validate. If you have a validation error, the program will indicate it with a notification at the bottom right \(2\); it will also mark the specific step where the error is \(1\). 

![Bot validation step showing error](../.gitbook/assets/option_error_ok.png)

When the bot has passed the validation successfully, a notification will appear at the bottom right indicating that the model was validated correctly. 

![](../.gitbook/assets/validate-bot.png)





**Select all**

This option allows you to select all the steps of a bot to move them at the same time. To select all steps, click Options&gt;Select all, you will notice that all steps are selected \(marked with a semi transparent border\), then you can position the cursor on any step and drag to new location. All steps will move at the same time. 

![](../.gitbook/assets/select-all.png)

To remove the selection, simply click on any empty part of the workspace. 

To remove the selection, simply click on any empty part of the workspace. 

**Dialogue Timeout**

All conversations in which a bot interacts have an expiration period, this is known as "dialogue timeout", and refers to the maximum time a user can restart a conversation. After the inactivity period, the conversation will return to the initial status and all the conversation variables will  reset.

To modify the default time \(20 minutes\), click on Options&gt;_timeout of the dialog_, a window with three time fields will appear: Days, Hours, Minutes.

![](../.gitbook/assets/dialogue-timeout.png)

> Minimum time is 5 minutes and maximum time is 365 days.
>
> **Show texts**
>
> When the structure of a model has increased, it may be useful to see all texts sent to the user by means of the message steps, instead of having to access the properties of each step to see them. To display all the texts of the message steps, click _Options&gt;View texts_. Next to each message will appear a blue box with its respective text. See picture below.

![](../.gitbook/assets/show-texts-ok.png)

To hide texts, click _Options&gt;View texts_,each time you show or hide the texts, an icon \(next to the option\) will indicate if they are active or inactive.

**Create copy**

When you need to work on a bot without altering its original structure or creating a new bot from an existing one, the platform offers you the option to create a copy of the bot, to do so follow these instructions: 

1. Go to the bots section.

2. Locate the bot you are going to copy.

3. Click "Open". \(see existing bots\).

4. Then click _Options&gt;Create copy._ 

5. A window with the information of the bot you are copying \(similar to the save bot\) will appear. 

![](../.gitbook/assets/create-copy.png)

6. Modify the data and image of the bot to your liking \(it is mandatory to change the name unless you choose to assign the bot to another customer\), when you have finished, click "Save" 

7. A notification will appear at the bottom right, indicating that the operation was successful.

> The bot you just copied will be automatically loaded into the designer. 
>
> **Exporting**
>
> You can export any bot to an external file \(.bot\) to later upload it to the platform. To do so, open the export bot \(if you don’t know how, see available bots\), click _Options&gt;Export._ The file will automatically be saved in the "Downloads" folder or it will ask for a path to be stored \(depending on your browser settings\).

> The bot you just copied will be automatically loaded into the designer. 
>
> **Exporting**
>
> You can export any bot to an external file \(.bot\) to later upload it to the platform. To do so, open the export bot \(if you don’t know how, see available bots\), click _Options&gt;Export._ The file will automatically be saved in the "Downloads" folder or it will ask for a path to be stored \(depending on your browser settings\).

![](../.gitbook/assets/exporting-ok.png)





**Importing**

In order to import a bot you must: 

1. Go to the bots section.

2. Click on the "Create bot" button, identified with the icon \( + \) or open a bot you want to overwrite.

3. In the "Designer" section, click _Options&gt;Import_.

4. A file manager will appear \(varies depending on the operating system\), to choose the file with the desired bot. Select it and click "Open".

5. The bot will be loaded into the designer keeping all the settings you had at the time of exporting.

6. Save the changes. 

6. Save the changes. 

**Web chat**

Chat-Bots allows you to create a bot that can be used to answer your customers' requests directly on your website. To generate a Web Chat click _Options&gt;Web chat._ A window like this will appear:

![](../.gitbook/assets/web-chat-ok.png)

1. Click the "Enable Web Chat for this Bot" box.

2. Enter a welcome text for your Web Chat.

3. Click the copy button to copy the code to the clipboard.

4. Click "OK". The code you copied to the clipboard must be sent to the website programmer for insertion before the tag `</body` closes on the website. Then, on the web page, on the bottom right the Web Chat window will appear, you can open or close it by clicking on the blue bar.

#### Test Bot

The WhatABot platform has a tool that allows you to test the bot you are developing, to use it go to _Options&gt; TEST BOT_ 

![](../.gitbook/assets/test-bot-ok.png)

Enter your messages in the "Message" field and click the "Send" button or press `enter` to send the message. At the top the messages and responses of the bot will show.

![imagen](https://chat-bots.co/assets/img/docs/es/img098.jpg) 

Notice also that this tool allows you to see the _status_ and current value of the variables as you try the bot; to do this, click the blue button with the electric icon.

![imagen](https://chat-bots.co/assets/img/docs/es/img099.jpg) 

A window with the current status , and the variables defined in the conversation along with the value they contain will appear.

![imagen](https://chat-bots.co/assets/img/docs/es/img100.jpg) 

![imagen](https://chat-bots.co/assets/img/docs/es/img100.jpg) 

#### Test with WhatsApp

To test your WhatsApp Bot, go to _Options&gt;TEST WHATSAPP._ If your bot has an assigned line, you can test directly on it, otherwise you can register up to 3 cell phone numbers to test through a line provided by Chat-Bots for this purpose. 

![](../.gitbook/assets/test-whatsapp1.png)

Choose a country from the drop down list, then enter the cell phone number you want to register and click the "Register" button. 

Choose a country from the drop down list, then enter the cell phone number you want to register and click the "Register" button. 

![](../.gitbook/assets/test-whatsapp2.png)

A table with the number of the line you can test, the cell number registered, the validity, and the option to delete the registered number will appear. If you want to register another number, repeat the previous step. 

![](../.gitbook/assets/test-whatsapp3.png)

When you have finished registering the cell phone numbers, click the "Go to WhatsApp" button. The WhatsApp application \(on the mobile\) or WhatsApp Web \(in the browser\) will open.

![](../.gitbook/assets/test-whatsapp4.png)

> Remember that you can only do tests with the cell numbers you registered for 24 hours
>
> ### Various
>
> Below you can find several concepts that will be useful when working with bots.
>
> #### Connectors
>
> Each step of the bot model is joined to another by means of a connector.
>
> The designer has 2 types of connectors: 
>
> 1. **Default connector \(YES, in condition\):** blue, with arrow in the center pointing in the direction of the flow.

![image](https://chat-bots.co/assets/img/docs/es/img055.jpg)

![image](https://chat-bots.co/assets/img/docs/es/img055.jpg)

2. **Exception connector \(NO in condition\)**: red, with arrow in the center pointing in the direction of the flow.

![image](https://chat-bots.co/assets/img/docs/es/img056.jpg)

![image](https://chat-bots.co/assets/img/docs/es/img056.jpg)

To delete a connector you have 2 options:

1. Take the cursor to the center of the connector, a button with the icon \( \) will appear, click it and the connector will disappear. 

![](../.gitbook/assets/connector-delete.png)

2. Place the cursor on the first of the 2 connected steps \(source step\), click the "Options" button, a window will appear \(varies depending on the type of step\). In the option "Next step:" \(status, process, expression, trace\), "Yes:"/"No:" \(condition\), the name of the step in which you are connected with will appear, click on the red button "Disconnect step" with the  delete,  icon then click on "OK".

![](../.gitbook/assets/connector-step.png)

To connect steps you have the following options:

1. Place the cursor on the first of the 2 steps \(source step\) you are going to connect, a button will appear with the text "Next", click and drag to the step you want to connect it with \(destination step\), release the mouse button and the two steps will be connected.  

![](../.gitbook/assets/connector-trace_message.png)

2. Place the cursor on the first of the 2 steps you want to connect \(source step\), click on "Options" button, a window will appear \(it varies depending on the type of step\). In the option "Next Step:" \(status, process, expression, trace\), "Yes:" and "No:" \(condition\), a list of steps with which you can join the current step will appear, select the step to connect and click "OK".

![](../.gitbook/assets/connetor-place.png)

#### Move a step

Moving any of the steps in the window is very easy. To do so, place the cursor on the step you want to move, the cursor will change its shape to a move icon indicating that the step allows itself to be moved. 

![](../.gitbook/assets/flowbot_cb-04.png)

Click and drag the step to the desired position, then release the mouse button and the step will be placed in the new position.

#### Move several steps

If you need to move several steps at a time, click on any empty part of the work space, drag the cursor until the semi transparent blue rectangle that appears covers all the steps you need to move.

If you need to move several steps at a time, click on any empty part of the work space, drag the cursor until the semi transparent blue rectangle that appears covers all the steps you need to move.

![](../.gitbook/assets/move_step1.png)

Release the mouse button and you will notice that the steps are selected \(with a semi transparent border\). Place the cursor over any of them, click and drag to the desired position, you will notice that the selected steps move at the same time.

> If you need to move steps that cannot be selected in the way described above, an alternative form of selection is to hold down the `CTRL` \(Control\) key and without dropping it, click on each step you are going to move. Then you can release the control key and move the selected steps as it was explained before.

![](../.gitbook/assets/move_step2.png)

#### Move rail

If you need to move a "rail" and all the steps it contains, bring the cursor closer to the blue dividing line, you will notice that the cursor changes its shape, indicating that you can move the rail up or down.

![](../.gitbook/assets/move_rail.png)

#### Insert Variables

In the properties of some steps, you will find fields in which you can insert variables, these fields have a blue button with the electric bolt icon. To make it easier to enter the variables, click on the button mentioned above, a popup menu will appear with the available variables. 

![](../.gitbook/assets/variables1.png)

Then click on the variable you want to insert.

#### Delete a step

To delete a step, place the cursor on the step you need to delete. A button with the delete icon  will appear, click on it.

![](../.gitbook/assets/variables2.png)

A confirmation window will appear, click on _delete_ to finish the process.

![](../.gitbook/assets/variables3.png)

## 



## **Introduction to AI**

Put simply, a Chatbot’s AI receives input as an Entity, it interprets the Entity, and translates it into an Intent output value. Upon receiving the appropriate Entity entities, it must analyze and contextualize to determine from the Phrase the user entered for the correct Intent response to the correct Intent prompt it has received.

By incorporating specific “Entities” to understand from “Phrases” entered by the user and creating an “Intent” list. The AI can understand the user’s intention and provide the proper outcome.

This gives you the ability to fine tune the AI to recognize specific Entity points, that the Bot uses to understand more difficult Intents. Using different variables to guide the system to understand the Intent from the Entities it finds in the given set of Phrases.

**Intents** 

 An Intent is an action or activity that a Bot can understand from what a user says in a Phrase. Therefore, it is important to provide enough samples of Phrases that specifically represent the Intent. With this information it is possible to train the Bot so that it understands the user’s intention. The more phrases you use \(up to 100\) The more Entities the AI in the Bot will have to act out the desired Intent. Click on Intent tab and a window will appear with the necessary fields to be completed accordingly for your AI.

Click the add Intent button, you can now enter your intention. The more parameters you need the more Intents you will need. Hovering the mouse over the  option field of the Intent you can see "Phrases" or "delete". Clicking on Phrases will open the Intent in the Phrases window to enter Sentences containing entities.

Intent video-pic

![](../.gitbook/assets/capture.PNG)

**Phrases**

Here you will provide sample phrases to represent the intent\(s\) purpose. Also, you can select possible entities to extract in each of them. Click on the Phrases tab to open option window. In the Intent field you can choose a given Intent to link with the phrases you are about to enter.  Click on the add Phrase button to add as many phrases you need according to your models’ job. Phrases containing Entities or new words in Phrases can be highlighted to represent the intent. Pick the new word and double click it. A window will appear to fill in the values and Entity and alias the new word will relate to.

![](file:///C:/Users/T/AppData/Local/Temp/msohtmlclip1/01/clip_image004.jpg)

![](../.gitbook/assets/phrases.PNG)

Assign Entity by double clicking on the word in the phrase. The following window will appear. \(for this I double clicked on **order** from the Phrase in the above photo\)

Click on entity and add the Entity you wish to connect with the word.

Click on alias and assign accordingly. 

Lastly assign the value.

![](../.gitbook/assets/selectword.PNG)

**Entities**

An Entity is a value extracted from phrases that a user says. You can define its different values with their possible synonyms for each Entity, or by using regular expressions. \(1\) Click on Entities tab to open option window to complete necessary fields before training the AI model.

![](../.gitbook/assets/add-entity%20%281%29.PNG)

\(2\) Click on the add Entities field, enter the Entity then click the add Entity button in the bottom right corner. Your Entity will appear on the list with the option to edit. Click on edit to name, and choose type, and Entity values.

![](../.gitbook/assets/entity-properties.PNG)

Entities video-pic

**Save and Train**

 Click on the  Save and Train tab, here train your model to make sure that it is responding accordingly to the given sequence of Intents, Entities, and Phrases or if you have to change or add more of the above values to correct its response.

![](../.gitbook/assets/sve-and-train.PNG)

When you hover the mouse over the given version the option along the right-hand side will appear to Pin, Test, or Delete. Click on test. This will take you directly to the Test window.

![](../.gitbook/assets/test.PNG)

**Test**

Here you can enter Phrases that contain the set parameters between Intents, and Entities. Enter the test Phrase and click the test button. Below your entry the result and value will appear showing your percentage and values.

![](../.gitbook/assets/test%20%281%29.PNG)

>

## Conversations

In this section you can filter the conversations by client, date, bot and, line to view in **real time** the incoming chats of each contact. To access the conversations section, click on the "Conversations" button on the left side menu.

![Conversation Filter Photo](../.gitbook/assets/conversations1.png)

### Filter

To filter the conversations you want to view, click _Filter_ \(1\); then click _Date_ field\(2\), a calendar will be displayed, select the deadline, then choose the customer by clicking on the _Customer_ field \(3\). Now mark the bots and the lines you want to filter \(4\). Click on the "View conversations" button.

![](../.gitbook/assets/conversations2.png)

The conversations that met the filter criteria will be displayed in the _Conversations_ tab \(1\), you can see the amount of chats for the chosen date\(2\) , if there are new messages in a chat you will be informed with an identifier \(3\), select any conversation by clicking on it\(4\) , date of conversation\(5\), chat messages \(6\), to return to the last messages of the selected chat click the _download_ button \(7\).

![image](https://chat-bots.co/assets/img/docs/es/img068.jpg)

### Filter search

\*\*\*\*

### Complement conversation

At any time an agent \( registered user on the platform\) can intervene in a conversation by taking \(provisionally\) the bots place and answer a user´s requests. To intervene in any conversation execute first the _filter process_, then write the answer message in the _send message_ field and click _send_ or press `Enter`key.

![image](https://chat-bots.co/assets/img/docs/es/img101.jpg)

![image](https://chat-bots.co/assets/img/docs/es/img101.jpg)

Notice that when intervening in a conversation, the platform automatically adds the name of the agent so the final user knows that someone is providing support.

![image](https://chat-bots.co/assets/img/docs/es/img102.jpg)

![image](https://chat-bots.co/assets/img/docs/es/img102.jpg)

> In order to intervene in a conversation, a user must have permission from the agent.

## Broadcast

In this section you can program messages which will be sent in bulk to your clients or prospects. In order to access the Broadcasting section, click _Broadcast_ on the left side menu.

![](../.gitbook/assets/broadcast1.png)

### Create broadcast

In this section you can program messages which will be sent in bulk to your customers or prospects. To create a broadcast click on _Create broadcast._

![](../.gitbook/assets/broadcast2.png)

To surf between the broadcast steps click on circular buttons \(1, 2 , 3 and 4\).

![](../.gitbook/assets/broadcast3.png)

You can also use _previous_ and _next_ buttons to move forward or go back between steps.

![](../.gitbook/assets/broadcast4.png)

#### 1: Name and line

Enter a name for broadcasting \(1\), select a customer from the dropdown list \(2\) and select a line for dissemination \(3\).

![](../.gitbook/assets/broadcast5.png)

Click on the "Next" button or on the circular button with number 2 at the top to go to the next step.

#### 2: Import recipients

Click the "Import Recipients" button \(1\) and select the file \(.txt or .xlsx\) that contains the recipients to load. The system will tell you how many numbers were loaded \(2\). You can also download the list of imported recipients by clicking the "Download" button \(3\). \(3\).

![](../.gitbook/assets/broadcast6.png)

> Only the numbers that have interacted with the selected line in step 1 will be filtered.
>
> If the chosen file is in excel \(.xlsx\) format, the recipients must appear in the first column \(A\) of the first spreadsheet of the file so that the system can read them.

Click the "Next" button or the circular button with number 3 at the top to move on to the next step.

#### 3: Write a message

Write the message you are going to send in the text box that appears_._

![](../.gitbook/assets/broadcast7.png)

You can divide your message into different bubbles by adding more text boxes_._

![](../.gitbook/assets/broadcast8.png)

Each text box has the following options: 

1. **Emojis and multimedia content:**

* Click emoji icon  to insert an emoji in the message.
* Click content icon  to insert a multimedia content \(audio, video, file\).

_2._ **Delete text box:**  Delete text box and its content.

Click the "Next" button or the circular button with number 4 at the top to move on to the next step.

#### 4: Send or schedule

To send the broadcast, click on \*Send now".

![](../.gitbook/assets/broadcast9.png)

You can also schedule the sending of the broadcast by checking the "Submit Later" box.

![](../.gitbook/assets/broadcast10.png)

Select date and time by using the calendar that appears and click on _program_ button \(2\).

![](../.gitbook/assets/broadcast11.png)

### See broadcasts

All created broadcasts in previous steps can be viewed, edited, and deleted from the "SEE BROADCASTS" section.

### Previously created broadcasts

To view previously created broadcasts click on the "SEE BROADCASTS" tab.

![](../.gitbook/assets/broadcast12.png)

A table with all the created broadcasts so far will appear .

![image](https://chat-bots.co/assets/img/docs/es/img130.jpg)

![image](https://chat-bots.co/assets/img/docs/es/img130.jpg)

In the table you will find the following options:

* **Name:** name given to the broadcast.
* **Line:** number of lines from which the broadcast is sent.
* **Recipients:** number of recipients + button to download the list in a plain text file \(.txt\).
* **Created:** date when the broadcast was created.
* **Created by:** name of the user who created the broadcast \(taken from the system\).
* **Scheduled:** date and time when sending the broadcast is scheduled
* **Sent:** date and time the broadcast is sent.
* **Status:** the broadcast can be in any of these 3 states:

  \(icon here\) - The broadcast has been scheduled and will be sent on the date and time as indicated.

  \(\)  -   The broadcast is currently being sent.

  \(\)  -   The broadcast has been sent to all recipients.

  \(\)  -   The broadcast has been canceled.

* **Actions:** edit or delete the broadcast.

  \*\*\*\*

## **Reports**

The reports section allows you to generate reports about the bot use. This section has 2 options: Traces and Indicators. To access the Reports section, click the "Reports" button on the main menu, as shown in the image.

![](../.gitbook/assets/reports1.png)

### Traces

Presents information from the traces defined in the bot logic. To generate a report with the traces of a bot, follow these instructions:

![](../.gitbook/assets/reports2.png)

1. Click on the "Traces" menu to access the section.

2. **Date range:** select the desired range of days in the calendar.

3. **Customer:** select a customer from the drop down list.

4. **Bot:** select the bot you want to view from the drop down list.

5. **Traceability:** select a traceability from the drop down list.

5. **Traceability:** select a traceability from the drop down list.

6. Click the "GENERATE REPORT" button. A table with the data of your report will appear.

![imagen](https://chat-bots.co/assets/img/docs/es/img085.jpg) 

If you want to modify the entered data , you can click the "RETURN TO PARAMETERS" button and adjust the options again \(1\). You can also export the report to a document in Excel format by clicking the "EXPORT TO EXCEL" button \(2\).

![image](https://chat-bots.co/assets/img/docs/es/img086.jpg)

![image](https://chat-bots.co/assets/img/docs/es/img086.jpg)

### Indicators

 Displays key indicators of use and user interaction for a bot. To generate a report from the indicators, follow these instructions:

![](../.gitbook/assets/reports3.png)

1. Click on the "Indicators" menu to access the section.

2. **Initial date:** select one month for the initial date.

3. **End date:** select a month for the final date.

4. **Customer:** select a customer for the report.

5. **Bot:** select a bot for the report.

6. **Universe:** Enter a Universe number.

7. Click the "GENERATE REPORT" button. Graphics with your data report will appear.

![imagen](https://chat-bots.co/assets/img/docs/es/img154.jpg) 

If you want to modify the entered data, you can click the "RETURN TO PARAMETERS" button and adjust the options again.

## Channels

In this section you will find everything you need to create, assign, and modify WhatsApp lines and Facebook pages, as well as create and edit customers.

### Lines

To access the Lines section, click the "Channels" button \(1\) on the main menu and then click the "Lines" option \(2\) as shown in the image.

![](../.gitbook/assets/channels_wa.png)

#### Edit line

Identify the line to edit and click the "Edit" option, as shown in the image

![imagen](https://chat-bots.co/assets/img/docs/es/img141.jpg) 

A window with the following fields will appear:

![imagen](https://chat-bots.co/assets/img/docs/es/img142.jpg) 

1. **Number:** \(not editable\) line number.

2. **Name of the line:** line name.

3. **Customer:** customer to which the line belongs.

4. **Bot:** bot to be used on the line.

5. **Active:** enable or disable the line. 

Edit the fields you need and click the "Save" button \(6\).

### Pages

To access the Pages section, click the "Resources" button \(1\) on the main menu and then click the "Pages" option \(2\) as shown in the image.

![](../.gitbook/assets/channels_wa01.png)

#### Subscribe page

To link to a facebook page in the Chat-Bots platform, click the "Subscribe Facebook Page" button.

![](../.gitbook/assets/channels_wa02.png)

A window with the following fields will appear:

![](../.gitbook/assets/channels_wa03.png)

1. **Name of the page:** name of the Facebook page, the list of names is automatically obtained when connecting to a Facebook account.

2. **"Get Pages" button:** click to open the Facebook manager, log in to your account and allow Chat-Bots to connect to your facebook account, The list of your pages will appear in the **Name of the page** field.

3. **Customer:** select the customer to which the page will be linked.

4. **Bot:** bot to be used on the page.

5. **Active:** enable or disable the page.

6. Click the "Save" button to keep your changes.

#### Edit-page

Identify the page you want to edit and click the "Edit" option, as shown in the image.

![](../.gitbook/assets/channels_wa04.png)

A modal with the following fields will appear:

![](../.gitbook/assets/channels_wa05.png)

1. **Name of the page:** \(no editable\) name of the chosen page.

2. **Customer:** customer to which the page belongs.

3. **Bot:** bot to be used on page.

4. **Active:** enable or disable the page.

Edit the fields you need and click "Save" \(5\).

### Customers

To access the Customers section, click the "Resources" button \(1\) on the main menu and then click the "Customers" option \(2\) as shown in the image.

![](../.gitbook/assets/customers1.png)

### Create/edit customer

To create a client, click on the "Create Customer" button, which is located at the bottom.

![](../.gitbook/assets/customers2.png)

Then a window with the following form will appear:

![](../.gitbook/assets/customers3.png)

1. **Name**: name of customer or company. 

2. **Contact**: name of a contact in the company. 

3. **E-mail**: customer contact email.

4. **Active**: button to enable or disable customer.

5. **Choose image**: click the button to assign an image to the client.

* A file manager will appear \(varies depending on the operating system\), select the image you want to upload.
  * The image will be loaded into the box \(as shown below\), you can move it by clicking and dragging to place it in the desired position.
  * With the slider located at the bottom you can also make it bigger \(slide right\) or smaller \(slide left\)  

```text
   ![imagen](https://chat-bots.co/assets/img/docs/es/img112.jpg)
```

1. Click on "Save" button to create a new customer. 

   \*\*\*\*

### **Edit a  customer**

To edit a customer, locate it in the customer table and click the "Edit" option.

![](../.gitbook/assets/customers4.png)

A window with a form that contains the customer information will appear:

![](../.gitbook/assets/customers5.png)

Edit the needed fields and click on "Save" button.

## Users

The functionalities of the Chat-Bots portal are enabled depending on the access given to each user, in this section they are managed. To access the Users section, click the "Users" button on the main menu, as shown in the image.

![](../.gitbook/assets/users1.png)

### Create/edit user

To create a user, click on the "Create User" button, which is located at the bottom.

![](../.gitbook/assets/users2.png)

Next, a window with the following form will appear:

![](../.gitbook/assets/users3.png)

1. **Login**: email used to access the application.

2. **Customer**: customer to which the user belongs.

3. **Names**: user names.

4. **Surname**: user surnames.

5. **Password**: password to be used.

6. **Confirm password**: confirm previously entered password.

7. **Active**: indicate whether or not the user can log in to the application.

8. Click the "Save" button to create the new user.

### Edit user

To edit a user, place it in the user table and click the "Edit" option.

![](../.gitbook/assets/users4.png)

A window with a form containing user information will appear:

![](../.gitbook/assets/users5.png)

Edit the needed fields and click on "Save" button.

### User permissions

Each user has a series of permissions that define what they can \(or cannot\) do on the platform.

#### Permissions

The permissions define which sections of the platform a user can access. To modify them, follow these instructions:

![](../.gitbook/assets/users6.png)

1. Click on the "PERMISSIONS" tab.

2. Check or uncheck the clients to whom the user will have permission.

3. Check or uncheck the sections to which the user will have access.

4. Click on the "Save" button to keep the changes.

#### Sections

In the SECTIONS tab you can define which of the main menu sections the user will have access to. To modify the sections follow these instructions:

![](../.gitbook/assets/users7.png)

1. Click on the "SECTIONS" tab.

2. Available sections.

3. Mark or uncheck the sections that the user can access.

4. Click the "Save" button to keep the changes.

## General

This section presents functionality concepts that you will find throughout the portal. It is important to be clear about the way they operate for its use.

### Tables

In various parts of the platform you will find tables that gather information easily and legibly for the user. These tables have a number of features that make it easier to interact with the data.

![](../.gitbook/assets/general1.png)

1. **Number of elements**: Number of rows \(rows\) per screen.

2. **Browser**: searches and filters the results in all columns \(containing text\) in the table.

3. **Sort by column**: Sort the rows in the table up or down based on the selected column.

4. **Element Actions**: Actions that can be applied to the selected element \(row\) : Delete, Edit, View... etc, varies depending on the data. To see the options of a row, pass the cursor over it.

5. **Current data**: shows the range and total of items being displayed.

6. **Paging**: Depending on the number of items chosen \(1\) and the total amount of items \(5\), the table will be divided into pages, use this item to browse between pages.

### Calendar

When inserting Date/Time data, the platform has a calendar that makes for easy information input.

To use it, place the cursor at any field that requires date/time data, click on it.

![](../.gitbook/assets/general2.png)

A calendar like this will appear:

![](../.gitbook/assets/general3.png)

1. **Month alternators**: left to go to the previous month, right to go to the next month.
2. **Year selector**: you can type or select the year with the drivers that appear when you approach the cursor.
3. **Current day**: current system date.
4. **Day selected**: date selected by the user.
5. **Time selector**: \(only in date/time fields\) you can type or select the time with the drivers that appear when you zoom in.
6. **Minute selector**: \(only in date/time fields\) you can type or select the minutes with the drivers that appear when you zoom in.
7. **AM/PM selector**: \(date/time fields only\) click to toggle between AM and PM.

#### Select range

Sometimes the system will ask you to enter a date range. To do this, click the form field, when the calendar appears, select the first date and then the second date.

![](../.gitbook/assets/general4.png)

### Multimedia Content

In the application, some text fields allow you to insert a rich text format or multimedia content. To do that, click on the button with the paperclip icon. A menu with the following options will be displayed:

![imagen](https://chat-bots.co/assets/img/docs/es/img128.jpg) 

Insert the code needed to send multimedia, the URL of the file will be requested. _\*\*hyperlink_ Insert the needed code to send a hyperlink, the link URL will be requested.

| Type | Function | Description |
| :--- | :--- | :--- |
| Enriched text | **Bold** | Apply bold to selected text. |
|  | **Italics** | Apply cursive style to selected text. |
|  | **Cross out** | Apply ~~crossed out~~ to the selected text. |
|  | **Mask** | Mask \(hide\) the selected text. |
| Multimedia | **New message** | Insert a new message \(bubble\) into the conversation. |
|  | **Multimedia** | Insert the required code  to send multimedia, the URL of the file will be requested. |
|  | **Document** | Insert the  required     code to send a document, the URL of the document and the name of the file will be requested when sent. |
|  | **Link** | Insert the required code to send a hyperlink, the link URL will be requested. |

### Edit Profile

WhatABot, stores basic information for each user \(e-mail, name, password, photo\), in this way you can identify who is interacting with the platform. To modify your data, click the "User" button \(top right\), then click "Edit profile".

![](../.gitbook/assets/profile1.png)

You will be directed to the "Edit profile" page.

![](../.gitbook/assets/profile2.png)

The editing options for a profile are:

* **Names**: User name.
* **Surname**: User last name.
* **Password**: Access password.
* **Confirm password**: Confirmation of the  entered  password  in the "Password" field.
* **Profile image**: Profile photo change.

To modify your profile photo you must:

1. Click "Choose image".

![](../.gitbook/assets/profile3.png)

2. A file manager will appear \(varies depending on the operating system\), select the image you want to upload.

3. The image will be loaded into the box \(as shown below\), you can move it with the cursor to place it in the desired position, using the slider at the bottom you can also make it bigger \(to the right\) or smaller \(to the left\)  

![](../.gitbook/assets/profile4.png)

4. After you have entered all the parameters correctly, click the "Save" button; if all goes well, a notification will appear at the bottom right indicating that the bot has been saved successfully.

![](../.gitbook/assets/profile5.png)

If you updated your profile image, you will notice that a thumbnail is now displayed on the top right.

![](../.gitbook/assets/profile6.png)

> The "**Password**" and "**\*Confirm password**" fields should not be changed unless you want to change your password, otherwise you can ignore them.

When you try to update your password, for security reasons, you will be asked for the current password in order to perform the process.

![](../.gitbook/assets/profile7.png)

## Submit a ticket

Please complete the form below to send a ticket to WhatABot and one of our consultants will contact you and provide you with the necessary support.







