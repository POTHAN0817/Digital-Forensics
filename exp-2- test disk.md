**Experiment - 2**

**TestDisk: Open-Source Data Recovery Tool**

**recover a missing partition and repair a corrupted one using test
disk**

**Installation**

Linux : sudo apt-get install testdisk

macOS : brew install testdisk

Windows: Download the executable from the official website.

Link : <https://www.cgsecurity.org/wiki/TestDisk_Download>

**NOTE:-** if you using in windows please extract the .zip file first

**Procedure**

**1. Create a Log File**

-   Launch TestDisk from your terminal or command prompt using sudo
    testdisk (or testdisk_win.exe on Windows).

-   Select the \[Create\] option to generate a log file of the recovery
    session. This is helpful for future reference or troubleshooting.

    <img width="1118" height="667" alt="Screenshot (58)" src="https://github.com/user-attachments/assets/ba8ae440-1f5e-4836-8487-d52ab755d680" />


**2. Select the Drive to Analyze**

-   TestDisk will display a list of all detected storage devices.

-   Use the Up/Down arrow keys to highlight the drive that contains your
    lost data.

-   Select \[Proceed\] to move to the next step.

-   
<img width="1125" height="676" alt="Screenshot (59)" src="https://github.com/user-attachments/assets/b114d2fc-ee47-41fc-9f91-d3eb7404514e" />

**3. Choose the Partition Table Type**

-   TestDisk will automatically suggest the most likely partition table
    type (e.g., Intel/PC, EFI GPT).

-   The default value is usually correct. Confirm the selection by
    pressing Enter.

    
<img width="1128" height="658" alt="Screenshot (60)" src="https://github.com/user-attachments/assets/000a8aa1-ed93-444e-aff2-bb2a2619bd53" />



**4. Analyze Current Partition Structure**

-   From the main menu, choose \[Analyse\] and press Enter.

-   This will display the current partition table and check for errors
    or missing partitions.

    <img width="1128" height="658" alt="Screenshot (60)" src="https://github.com/user-attachments/assets/08d4c6ea-a707-4a93-b6ec-3ab5a3e19942" />


**5. Perform a Quick Search**

-   After the analysis, you will be prompted to perform a \[Quick
    Search\].

-   Select it and press Enter to scan the drive for lost partitions.

-   <img width="1118" height="659" alt="Screenshot (62)" src="https://github.com/user-attachments/assets/46248f01-b529-492a-bdd9-599ead9911b3" />



-   Once a partition is found, you can press p to list its files.
    Deleted files and folders often appear in red.

-   Press q to return to the search results.

**6. Perform a Deeper Search**

-   If the Quick Search fails to find your lost partitions, select
    \[Deeper Search\]

-   This process can take a long time, as it scans the entire drive,
    block by block, to find remnants of partition structures.

<img width="1115" height="662" alt="Screenshot (63)" src="https://github.com/user-attachments/assets/0d7e4b5c-4b30-4e64-ac73-599a40a8d594" />

-   Again, use p to preview files and confirm if a found partition is
    the one you are looking for.

**7. Modify Partition Status**

-   After finding the correct partitions, use the Left/Right arrow keys
    to set their status.

-   Use **Left/Right arrow keys** to change status:
<img width="1119" height="656" alt="Screenshot (64)" src="https://github.com/user-attachments/assets/379849a0-e1db-4f6e-b498-a825b1f1dc16" />

    -   **P**: Primary

    -   \***:** Bootable

    -   **L**: Logical

    -   **D**: Deleted

    -   **e**nsure that the partitions you want to recover are marked as
        Primary or Logical (and not deleted).

**8. Write the Partition Table**

-   Once you are confident the partition structure is correct, select
    \[Write\] from the menu.

-   Confirm the operation by pressing y (for yes). This will write the
    new partition table to your disk.
<img width="1119" height="656" alt="Screenshot (64)" src="https://github.com/user-attachments/assets/ebe76325-da72-412a-92a2-0d9d91907ee5" />
<img width="1119" height="671" alt="Screenshot (66)" src="https://github.com/user-attachments/assets/401033d9-3664-4224-bfb7-5b1ca8596940" />

**9. Recover Files**

-   If you just need to recover a few files without fixing the partition
    table, you can do so from the file list (after pressing p).

-   Navigate to the folder containing your desired files.

-   Use the colon : key to select the files you want to recover.

-   Press the uppercase C key to copy the selected file(s).

-   Navigate to a safe destination on a different storage device and
    press uppercase C again to paste.
<img width="1128" height="681" alt="Screenshot (67)" src="https://github.com/user-attachments/assets/3a874a7e-fc17-474d-827d-c1c031e292bc" />

**10. Exit and Restart**

-   Once your task is complete, select \[Quit\] to exit the program.

-   If you wrote a new partition table to the drive, it is recommended
    to restart your computer to allow the operating system to recognize
    the changes.
<img width="1138" height="674" alt="Screenshot (68)" src="https://github.com/user-attachments/assets/543a0508-f8cb-4f76-a2f3-33085254c00f" />

**References:**

<https://www.cgsecurity.org/wiki/TestDisk_Download>

<https://www.cgsecurity.org/testdisk_doc/>
