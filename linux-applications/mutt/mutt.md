<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [About](#about)
- [Main inbox status markers](#main-inbox-status-markers)
  - [Message status flags](#message-status-flags)
  - [Message recipent flags](#message-recipent-flags)
- [Reference docs](#reference-docs)
  - [Key binding](#key-binding)
  - [Visual interactive chart](#visual-interactive-chart)
  - [Mutt Quick Reference Chart](#mutt-quick-reference-chart)
- [Attachments](#attachments)
- [Searching](#searching)
  - [Hints](#hints)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

# About

Usage notes for mutt. Mutt is a mail-reading CLI program for Linux

# Main inbox status markers

## Message status flags

Flag	|Description
------|-----------------
D|	message is deleted (is marked for deletion)
d	|message has attachments marked for deletion
K	|contains a PGP public key
N	|message is new
O	|message is old
P	|message is PGP encrypted
r	|message has been replied to
S	|message is signed, and the signature is successfully verified
s	|message is signed
!	|message is flagged
\*	|message is tagged
n	|thread contains new messages (only if collapsed)
o	|thread contains old messages (only if collapsed)

## Message recipent flags

Flag|	Description
----|---------------
+|	message is to you and you only
T|	message is to you, but also to or CC'ed to others
C|	message is CC'ed to you
F|	message is from you
L|	message is sent to a subscribed mailing list

See: [Message status flags](https://dev.mutt.org/doc/manual.html#tab-msg-status-flags)

# Reference docs

* [Manual](https://dev.mutt.org/doc/manual.html)

## Key binding

https://dev.mutt.org/trac/wiki/MuttFaq/Action

## Visual interactive chart

http://sheet.shiar.nl/mutt

## Mutt Quick Reference Chart

[Source](https://www.ucolick.org/~lharden/muttchart.html "Permalink to Mutt Quick Reference Chart")

Note: some commands may appear more than once if their effects differ depending on context. Converted using [fyeamarkdown](http://fuckyeahmarkdown.com/).

Mutt Command      | Context                                                        | Effect                                                                                                                  | Tutorial Section                                         | [Relevant .muttrc settings][1]                                                         |  
| --------------- | ---------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------|----------------------------------------------------------------------------------------|
| a               | Sending Message                                                | Attaches a file to the message you have created                                                                         | [Sending Messages][2]                                    | none                                                                                   |  
| b               | Sending Message                                                | Lets you edit the list of blind carbon copy recipients for the message you have created                                 | [Sending Messages][2]                                    | none                                                                                   |   
| c               | Sending Message                                                | Lets you edit the list of carbon copy recipients for the message you have created                                       | [Sending Messages][2]                                    | none                                                                                   |  
| d               | Main Menu, Reading Message                                     | Marks the current message for deletion                                                                                  | [Deleting Messages][3]                                   | none                                                                                   |  
| f               | Main Menu, Reading Message                                     | Forwards the message to another address                                                                                 | [Forwarding Messages][4]                                 | askbcc, askcc, edit_headers, editor                                                    |  
| i               | Reading Message                                                | Returns from reading a message to the Main Menu                                                                         | [Reading Messages][5]                                    | none                                                                                   |  
| j               | Main Menu                                                      | Changes the selected message to the next message                                                                        | [Getting Around in the Menu][6]                          | color                                                                                  |  
| k               | Main Menu                                                      | Changes the selected message to the previous message                                                                    | [Getting Around in the Menu][6]                          | color                                                                                  |  
| m               | Main Menu, Reading Message                                     | Creates a new message to send                                                                                           | [Sending Messages][2]                                    | abort_nosubject, abort_unmodified, askbcc, askcc, edit_headers, editor, recall         |  
| mutt            | Command line                                                   | Starts mutt                                                                                                             | [Getting Into and Out of the Mutt Menu][7]               | beep-new, color, mark_old, move, sort                                                  |  
| p               | Main Menu, Reading Message                                     | Prints the currently selected message                                                                                   | [Printing Messages][8]                                   | print, print_command                                                                   |  
| q               | Main Menu                                                      | Quits mutt                                                                                                              | [Getting Into and Out of the Mutt Menu][7]               | delete, mark_old, mbox, move                                                           |  
| q               | Sending Message                                                | Aborts or postpones the message you have created                                                                        | [Sending Messages][2] or [Postponing Messages][9]        | postpone, postponed                                                                    |  
| r               | Main Menu, Reading Message                                     | Creates a reply to the current message                                                                                  | [Replying to Messages][10]                               | abort_nosubject, abort_unmodified, askbcc, askcc, edit_headers, editor, include, metoo |  
| s               | Main Menu, Reading Message                                     | Saves the current message to a file                                                                                     | [Saving Messages][11]                                    | folder                                                                                 |  
| s               | Sending Message                                                | Lets you change the subject for the message you have created                                                            | [Sending Messages][2]                                    | none                                                                                   |  
| t               | Sending Message                                                | Lets you edit the list of recipients for the message you have created                                                   | [Sending Messages][2]                                    | none                                                                                   |  
| u               | Main Menu, Reading Message (messages marked for deletion only) | Removes the deletion mark from the current message                                                                      | [Deleting Messages][3]                                   | none                                                                                   |  
| x               | Help Menu                                                      | Returns from the help menu to the Main Menu                                                                             | [Getting Around in the Menu][6]                          | none                                                                                   |  
| y               | Sending Message                                                | Sends the message you have created                                                                                      | [Sending Messages][2]                                    | abort_unmodified, copy, record                                                         |  
| ?               | Main Menu                                                      | Goes from the Main Menu to the Help Menu                                                                                | [Getting Around in the Menu][6]                          | color                                                                                  |  
| -               | Reading Message                                                | Moves to the previous page in the message you are reading                                                               | [Reading Messages][5]                                    | none                                                                                   |  
| /               | Main Menu                                                      | Prompts for a pattern to search for in the headers of your messages                                                     | [Getting Around in the Menu][6]                          | none                                                                                   |  
| =               | Main Menu                                                      | Selects the first message                                                                                               | [Getting Around in the Menu][6]                          | color, sort                                                                            |  
| $               | Main Menu                                                      | Deletes all messages selected for deletion, and checks for new messages                                                 | [Deleting Messages][3]                                   | beep_new, delete, mark_old, mbox, move                                                 |  
| *               | Main Menu                                                      | Selects the last message                                                                                                | [Getting Around in the Menu][6]                          | color, sort                                                                            |  
| < number >  | Main Menu                                                      | Selects message < number >                                                                                          | [Getting Around in the Menu][6]                          | color                                                                                  |  
| < Enter >   | Main Menu                                                      | Brings the currently selected message up on the screen                                                                  | [Reading Messages][5]                                    | color                                                                                  |  
| < Space >   | Reading Message                                                | Moves to the next page in the message you are reading, or to the first page of the next message not marked for deletion | [Reading Messages][5]                                    | none                                                                                   |  
| < Tab >     | Main Menu                                                      | Selects the next new message                                                                                            | [Getting Around in the Menu][6]                          | color                                                                                  |  
| < Esc > /   | Main Menu                                                      | Prompts for a pattern to search for in the bodies of your messages                                                      | [Getting Around in the Menu][6]                          | none                                                                                   |  
| up/down arrow   | Main Menu                                                      | Changes the selected message to the previous/next message                                                               | [Getting Around in the Menu][6]                          | color                                                                                  |  
| PageUp/PageDown | Main Menu, Reading Message                                     | Moves up/down one page in the Main Menu or the message you are reading                                                  | [Getting Around in the Menu][6] or [Reading Messages][5] | none                                                                                   |  

[1]: https://www.ucolick.org/learnmutt.html#Muttrc
[2]: https://www.ucolick.org/learnmutt.html#Send
[3]: https://www.ucolick.org/learnmutt.html#Delete
[4]: https://www.ucolick.org/learnmutt.html#Forward
[5]: https://www.ucolick.org/learnmutt.html#Read
[6]: https://www.ucolick.org/learnmutt.html#Menu
[7]: https://www.ucolick.org/learnmutt.html#Start
[8]: https://www.ucolick.org/learnmutt.html#Print
[9]: https://www.ucolick.org/learnmutt.html#Postpone
[10]: https://www.ucolick.org/learnmutt.html#Reply
[11]: https://www.ucolick.org/learnmutt.html#Save

# Attachments

Viewing attachments is perhaps the least intuitive part of Mutt. It requires creating a ~/.mailcap file that specifies which applications should be used to open which kinds of attachments. I basically adopted this system wholesale, especially the view_attachment.sh script.

For example, these lines in my .mailcap file tell Mutt to open Microsoft Word documents in TextEdit, while allowing it to open *.docx files in Microsoft Word. Rich Text files are opened using Bean. HTML attachments and messages are piped through pandoc and converted to markdown for easy reading.

http://wcm1.web.rice.edu/mutt-tips.html

# Searching

## Hints

* Use `/` (search) to search for an instance
* Use `//` after searching to clear the query

http://www.rosipov.com/blog/effective-search-with-mutt/
