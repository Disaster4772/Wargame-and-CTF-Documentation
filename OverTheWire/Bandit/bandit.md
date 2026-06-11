| Level | Command / Tool | Explanation |
| :--- | :--- | :--- |
| **0** | `ssh` | Connected to the remote OverTheWire server using specified credentials and port. |
| **0 -> 1** | `cat`, `ls` | Located and read the standard `readme` text file in the home directory to find the flag. |
| **1 -> 2** | `cat ./-` | Handled a dashed filename (`-`) by using relative pathing to stop terminal command interpretation. |
| **2 -> 3** | `cat ./"file name"` | Handled spaces in a filename using quotes. |
| **3 -> 4** | `ls -la` | Revealed hidden dotfiles (`.hidden`) by listing all files including hidden ones. |
| **4 -> 5** | `file ./*` | Interrogated file types in the directory to isolate the only human-readable ASCII text file. |
| **5 -> 6** | `find . -type f -size 1033c ! -executable` | Filtered directory to locate a file matching exact byte size, readability, and non-executable constraints. |
| **6 -> 7** | `find / -user bandit7 -group bandit6 -size 33c 2>/dev/null` | Searched system for specific file matching precise user/group owners and byte size, ignoring permission errors. |
| **7 -> 8** | `grep "millionth" data.txt` | Parsed a massive text file to locate the password string positioned next to the word 'millionth'. |
| **8 -> 9** | `sort data.txt \| uniq -u` | Chained utilities together to sort text lines and isolate the only string occurring exactly once. |
| **9 -> 10** | `strings data.txt \| grep "=="` | Extracted human-readable text from a binary file, filtering for the password preceded by '=' characters. |
| **10 -> 11** | `base64 -d data.txt` | Decoded a text block containing base64-encoded data to reveal the cleartext password. |
| **11 -> 12** | `tr 'A-Za-z' 'N-ZA-Mn-za-m'` | Decorrupted a text file by shifting alphabetic characters 13 positions using a ROT13 cipher bypass. |
