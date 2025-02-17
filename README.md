Fixed errors:
print("Rouge Score version:", importlib.metadata.version('rouge-score'))

First result from zero-shot:

---------------------------------------------------------------------------------------------------
INPUT PROMPT:
Instruct: Summarize the following conversation.
#Person1#: Happy Birthday, this is for you, Brian.
#Person2#: I'm so happy you remember, please come in and enjoy the party. Everyone's here, I'm sure you have a good time.
#Person1#: Brian, may I have a pleasure to have a dance with you?
#Person2#: Ok.
#Person1#: This is really wonderful party.
#Person2#: Yes, you are always popular with everyone. and you look very pretty today.
#Person1#: Thanks, that's very kind of you to say. I hope my necklace goes with my dress, and they both make me look good I feel.
#Person2#: You look great, you are absolutely glowing.
#Person1#: Thanks, this is a fine party. We should have a drink together to celebrate your birthday
Output:

---------------------------------------------------------------------------------------------------
BASELINE HUMAN SUMMARY:
#Person1# attends Brian's birthday party. Brian thinks #Person1# looks great and charming.

---------------------------------------------------------------------------------------------------
MODEL GENERATION - ZERO SHOT:
Brian: Happy Birthday, this is for you, Brian.
Person2: I'm so happy you remember, please come in and enjoy the party. Everyone's here, I'm sure you have a good time.
Person1: Brian, may I have a pleasure to have a dance with you?
Person2: Ok.
Person1: This is really wonderful party.
Person2: Yes, you are always popular with everyone. and you
CPU times: user 4.35 s, sys: 50.6 ms, total: 4.4 s
Wall time: 7.3 s

Results after peft:

---------------------------------------------------------------------------------------------------
INPUT PROMPT:
Instruct: Summarize the following conversation.
#Person1#: Happy Birthday, this is for you, Brian.
#Person2#: I'm so happy you remember, please come in and enjoy the party. Everyone's here, I'm sure you have a good time.
#Person1#: Brian, may I have a pleasure to have a dance with you?
#Person2#: Ok.
#Person1#: This is really wonderful party.
#Person2#: Yes, you are always popular with everyone. and you look very pretty today.
#Person1#: Thanks, that's very kind of you to say. I hope my necklace goes with my dress, and they both make me look good I feel.
#Person2#: You look great, you are absolutely glowing.
#Person1#: Thanks, this is a fine party. We should have a drink together to celebrate your birthday
Output:

---------------------------------------------------------------------------------------------------
BASELINE HUMAN SUMMARY:
#Person1# attends Brian's birthday party. Brian thinks #Person1# looks great and charming.

---------------------------------------------------------------------------------------------------
PEFT MODEL:
#Person1# invites Brian to the party and they have a good time.

#### Instruct:
Summarize the conversation.
#Person1# invites Brian to the party and they have a good time.

#### 
CPU times: user 5.03 s, sys: 9.54 ms, total: 5.04 s
Wall time: 5.26 s


Absolute percentage improvement of PEFT MODEL over ORIGINAL MODEL:
rouge1: 3.64%
rouge2: 3.04%
rougeL: 6.00%
rougeLsum: 6.62%
