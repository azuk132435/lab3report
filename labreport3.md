** Lab Reoprt 3 **

Failure:
```
public void testReverseInPlace() {
    int[] input1 = { 5, 4, 3};
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 3, 4, 5 }, input1);
	}
```
Success:
```
public void testReverseInPlace() {
    int[] input1 = { 3 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 3 }, input1);
	}
```
Terminal:
![Image](Lab 2 - part 1.JPG)
<br>
before:
```
static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }
```
after:
```
static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length / 2; i += 1) {
      int temp = arr[i];
      arr[i] = arr[arr.length - i - 1];
      arr[arr.length - i - 1] = temp;
    }
  }
```
```
$ less -N 911report/chapter-13.5.txt

      1 
      2
      3
      4             1. Muhammad Mani Ahmad al Kahtani. Currently in custody, he is the last known Saudi
      5                 muscle candidate to be sent to the United States, in early August 2001, to round out
      6                 the number of hijackers. As discussed later in this chapter, he was refused entry.
      7                 Secretary of Defense interview with David Frost (BBC), June 27, 2004, available at
      8                 www.defenselink.mil. CIA analytic report, "Threat Threads: Recent Advances in
      9                 Understanding 11 September,"CTC 2002-30086CH, Sept. 16, 2002, p. 4; Intelligence
     10                 report, interrogation of KSM, July 3, 2003; Intelligence report, interrogation of

$ less -N 911report
911report is a directory
```
So what this command (less -N) is doing is printing out numbers for each line of the text file, and simply returning that 
the directory is a directory. I believe this could be very useful when proofreading for example if someone wanted you to 
review their text file you can say I found an error on x line, and it will be very easily found visually when viewing the file through the terminal.
```
$ less -p report 911report/chapter-13.5.txt

                www.defenselink.mil. CIA analytic report, "Threat Threads: Recent Advances in
                Understanding 11 September,"CTC 2002-30086CH, Sept. 16, 2002, p. 4; Intelligence
                report, interrogation of KSM, July 3, 2003; Intelligence report, interrogation of
                detainee, Apr. 3, 2003.
            2. Khalid Saeed Ahmad al Zahrani. He traveled to Afghanistan illegally after being
                prohibited by Saudi authorities from leaving Saudi Arabia. After being assigned to a
                mission in the U.S., he secretly reentered the Kingdom but failed in an attempt to
                have his name removed from the list of prohibited travelers so that he could obtain
                a U.S. visa. See Intelligence reports, interrogations of detainee, Apr. 20, 2002;
                Oct. 4, 2002; Apr. 3, 2003.
            3. Ali Abd al Rahman al Faqasi al Ghamdi. (aka Abu Bakr al Azdi) He reportedly was to
                have been part of the planes operation but was held in reserve by Bin Ladin for a
                later, even larger operation. Like other muscle hijackers, he reportedly set out for
                Chechnya but diverted to Afghanistan. See Intelligence reports, interrogations of
                Abu Bakr al Azdi, July 23, 2003; Sept. 25, 2003; Intelligence report, interrogation
                of Khallad, Nov. 6, 2003.

$ less -p 911 911report
911report is a directory
```
![Image](Lab 2 - Highlight.JPG)
<br>
So what this command (less -p pattern) does is for a directory it just returns that the directory is a directory, but for
files it is able to go through and highlight throughout the text ever time whatever you write as "pattern" ( here I did
report). I think this is useful just for example if in a class you needed to highlight key terms it could easily 
go through a file and highlight all ol them for you. (I will include a screenshot cause the highlight can't be shown in a code block).

```
$ less +F 911report/chapter-2.txt

            By August 1, members of the cells not directly involved in the attacks had mostly
                departed from East Africa. The remaining operatives prepared and assembled the
                bombs, and acquired the delivery vehicles. On August 4, they made one last casing
                run at the embassy in Nairobi. By the evening of August 6, all but the delivery
                teams and one or two persons assigned to remove the evidence trail had left East
                Africa. Back in Afghanistan, Bin Ladin and the al Qaeda leadership had left Kandahar
                for the countryside, expecting U.S. retaliation. Declarations taking credit for the
                attacks had already been faxed to the joint al Qaeda-Egyptian Islamic Jihad office
                in Baku, with instructions to stand by for orders to "instantly" transmit them to Al
                Quds al Arabi. One proclaimed "the formation of the Islamic Army for the Liberation
                of the Holy Places," and two others-one for each embassy-announced that the attack
                had been carried out by a "company" of a "battalion" of this "Islamic Army."

            On the morning of August 7, the bomb-laden trucks drove into the embassies roughly
                five minutes apart-about 10:35 A.M. in Nairobi and 10:39 A.M. in Dar es Salaam.
                Shortly afterward, a phone call was placed from Baku to London. The previously
                prepared messages were then faxed to London.

            The attack on the U.S. embassy in Nairobi destroyed the embassy and killed 12
                Americans and 201 others, almost all Kenyans. About 5,000 people were injured. The
                attack on the U.S. embassy in Dar es Salaam killed 11 more people, none of them
                Americans. Interviewed later about the deaths of the Africans, Bin Ladin answered
                that "when it becomes apparent that it would be impossible to repel these Americans
                without assaulting them, even if this involved the killing of Muslims, this is
                permissible under Islam." Asked if he had indeed masterminded these bombings, Bin
                Ladin said that the World Islamic Front for jihad against "Jews and Crusaders" had
                issued a "crystal clear" fatwa. If the instigation for jihad against the Jews and
                the Americans to liberate the holy places "is considered a crime,"he said,"let
                history be a witness that I am a criminal."

$ less +F 911report
911report is a directory
```
![Image](Lab 2 - end.JPG)
So what this command (less +F) does is goes to the end of the file and displays it, once again it just returns that the 
directory is a directory. One way this could be useful is if you have a ton of files and you need to study from them in a terminal if they have summaries at the end you can quickly just use this over and over for all the files and just read the summaries of all the information you need (I am providing a screenshot to prove this is actually the end of the file.

```
$ less +30 911report/chapter-1.txt
    In passing through these checkpoints, each of the hijackers would have been screened by a walk-through metal detector calibrated to detect items with at least the metal content of a .22-caliber handgun. Anyone who might have set off that detector would have been screened with a hand wand-a procedure requiring the screener to identify the metal item or items that caused the alarm. In addition, an X-ray machine would have screened the hijackers' carry-on belongings. The screening was in place to identify and confiscate weapons and other items prohibited from being carried onto a commercial flight.

    None of the checkpoint supervisors recalled the hijackers or reported anything suspicious regarding their screening.

    While Atta had been selected by CAPPS in Portland, three members of his hijacking team-Suqami, Wail al Shehri, and Waleed al Shehri-were selected in Boston. Their selection affected only the handling of their checked bags, not their screening at the checkpoint. All five men cleared the checkpoint and made their way to the gate for American 11. Atta, Omari, and Suqami took their seats in business class (seats 8D, 8G, and 10B, respectively). The Shehri brothers had adjacent seats in row 2 (Wail in 2A, Waleed in 2B), in the firstclass cabin. They boarded American 11 between 7:31 and 7:40. The aircraft pushed back from the gate at 7:40.

    Shehhi and his team, none of whom had been selected by CAPPS, boarded United 175 between 7:23 and 7:28 (Banihammad in 2A, Shehri in 2B, Shehhi in 6C, Hamza al Ghamdi in 9C, and Ahmed al Ghamdi in 9D). Their aircraft 
pushed back from the gate just before 8:00.

$ less +30 911report
911report is a directory
```
![Image](Lab 2 - jump.JPG)
This command (less +linenumber) allows you to jump to the line that you want the display in the terminal to start at and once against just return is a directory for directories. This can be useful when combined with the earlier line tool where if someone says there's an error in line x you can now instantly jump to line x and see what is wrong. (I am adding a screenshot to prove it jumps to the right part correctly.

Sources: ChatGPT
find command-line options for less in a terminal
<br>
Sure thing! If you want to explore the command-line options for the `less` command, you can open the terminal and type:

```bash
man less
```

This will display the manual page for `less`, including all the available command-line options and their descriptions. You can navigate through the manual using the arrow keys, and press 'q' to exit when you're done.
<br>
can you give me some examples <br>
Absolutely! Here are a few examples of using the `less` command with different options:

1. **Basic usage:**
   ```
   less filename
   ```
   Replace "filename" with the name of the file you want to view.

2. **View a file and line numbers:**
   ```
   less -N filename
   ```
   This will display line numbers on the left side.

3. **Search for a pattern:**
   ```
   less -p pattern filename
   ```
   Replace "pattern" with the text you want to search for.

4. **Display line numbers and search for a pattern:**
   ```
   less -N +/pattern filename
   ```
   Combining line numbers and search.

5. **View multiple files:**
   ```
   less file1 file2
   ```
   You can view multiple files in sequence.

6. **Quit immediately after displaying file:**
   ```
   less +F filename
   ```
   Start with the file open and go to the end immediately.

7. **View binary files:**
   ```
   less -b filename
   ```
   View binary files, useful for examining non-text files.

Remember, you can always check the manual (`man less`) for a comprehensive list of options and details on how to use them.
<br>
can you name some more <br>
Certainly! Here are a few more `less` command examples:

8. **Jump to a specific line number:**
   ```bash
   less +linenumber filename
   ```
   Replace "linenumber" with the specific line number you want to jump to.

9. **Display line numbers in a visually distinct form:**
   ```bash
   less -N -M filename
   ```
   This will display line numbers and visually mark the ends of lines.

10. **Highlight search matches:**
    ```bash
    less -p pattern -i filename
    ```
    This will ignore case when searching, making it case-insensitive.

11. **Display help (command summary):**
    ```bash
    less --help
    ```
    Shows a summary of command-line options.

12. **View and follow the output of a continuously growing file (like `tail -f`):**
    ```bash
    less +F filename
    ```
    Similar to `tail -f`, this will display new content as it's added to the file.

13. **Display control characters as '^X' notation:**
    ```bash
    less -Q filename
    ```
    Useful for viewing files with control characters.

14. **Quit immediately if the entire file fits on one screen:**
    ```bash
    less -F filename
    ```
    If the file is short enough to fit on one screen, it will quit immediately.

15. **Display file modification time:**
    ```bash
    less --time filename
    ```
    Show the last modification time of the file.

Feel free to explore these options based on your specific needs!

