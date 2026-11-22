---
name: rm-files-and-dirs
description: to delete a file or directory use 'kioclient move 'file:///absolute/path/with spaces.mp3' trash:/'
---

## WHAT
File deletions and destructive commands like 'rm *' are destructive and run a high risk of permanenlty removing files that you may not mean to remove, worse off its permanent. This skill gives you a practical way to delete files on this desktop while still keeping a path to restore them open should the user want to or should you need to in the case of an accidental deletion.


## WHEN
Any time you would us 'rm' or 'mv  <toTrash>' use this skill Instead to preserve a reliable way for restoration should something go wrong.


## HOW
'kioclient move 'file:///absolute/path/with spaces.mp3' trash:/' 

OR A FALLBACK

'gio trash'


## WHY
This should replaces any notion of moving to any other 'Trash' directory. 'gio trash' also works but 'kioclient' is the KDE-native choice. Rationale: files land in the per-volume Trash so they appear in Dolphin's Trash view and restore through the GUI; on a separate mount the trash is that volume's .Trash-1000, not ~/.local/share/Trash. Standing rule: never 'rm -rf' on user data. Always move to trash so it is reversible.


## RULES AND EXCEPTIONS
- Standing rule: never rm -rf on user data; always move to trash so it is reversible.

- DO NOT use 'ktrash6' or 'ktrash5' (ktrash6/5 only empties/restores, it does not move files in)

- Note: to move files to the trash, do not use ktrash, but "kioclient move 'file:///absolute/path/with spaces.txt' trash:/"


### ANYTHING EXTRA
> NEVER USE rm commands never run any destructive delete commands unless explicitly stated by the user and even in those cases send them files to a TRASH directory to avoid permanent data loss. Permanent deletion should always be a user action and never an agent decision.


### 2 GOTCHAS
1. Three slashes. trash://Music parses Music as the URL host, which is why every variant you tried said malformed. The item lives in the path: trash:///....
2. The KDE trash slave renames items on the way in with a collision prefix (0-Music, 0-probe2.txt), and the restore URL must use that internal name, not the display name. List the real names with kioclient ls 'trash:/', confirm with kioclient stat 'trash:///0-NAME', then feed that exact URL to kioclient move 'trash:///0-NAME' 'file:///dest' or ktrash6 --restore for the recorded original location.