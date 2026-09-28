## **Exp no :01 Date :** 

# **Evidence Acquisition Using Access Data FTK Imager** 

### **Description** 

Forensic Toolkit or FTK is a computer forensics software product made by AccessData. This is a Windows based commercial product. For forensic investigations, the same development team has created a free version of the commercial product with fewer functionalities. This FTK Imager tool is capable of both acquiring and analyzing computer forensic evidence. 

The evidence FTK Imager can acquire can be split into two main parts. They are: 

- Acquiring volatile memory 

- Acquiring non-volatile memory (Hard disk) 

There are two possible ways this tool can be used in forensics image acquisitions: 

- Using FTK Imager portable version in a USB pen drive or HDD and opening it directly from the evidence machine. This option is most frequently used in live data acquisition where the evidence PC/laptop is switched on. 

- Installing FTK Imager on the investigator’s laptop. 

In this case the source disk should be mounted into the investigator’s laptop via write blocker. The write blocker prevents data being modified in the evidence source disk while providing read-only access to the investigator’s laptop. This helps to maintain the integrity of the source disk. 

Acquiring volatile memory using FTK Imager 

The FTK Imager tool helps investigators to collect the complete volatile memory (RAM) of a computer. The following steps will show you how to do this. 

Open FTK Imager and navigate to the volatile memory icon (capture memory). 



<!-- Start of picture text -->
Memory Capture 4<br>Destination path:<br>C:\Drivers\FTK _MAGER Browse<br>Destination filename:<br>memdump.mem<br>@ Include pagefile<br>pagefile.sys<br>Create AD1 file<br>memcapture.adi<br>Capture Memory Cancel<br>Memory Progress<br>Destination: C:\Drivers\FTK __MAGER\memdump.mem<br>Status: Dumping RAM: 16GB/19GB [83%]<br>eee<br>Cancel<br><!-- End of picture text -->

**NOTE:** This tool provides options to include pagefile and AD1 files when acquiring the volatile memory. 

**Pagefile:** The pagefile (pagefile.sys) is used in Windows operating systems as volatile memory due to limitation of physical random-access memory (RAM). It is located under the “C” partition ready to use as volatile memory when the existing RAM capacity is exceeded. So this file can have quite a bit of valuable data when considering the volatile memory. Therefore, it is recommended to capture and collect this file in the acquisition. 

**AD1 file:** AD1 is the FTK imager image file. The investigator has the option to create an AD1 file for later use. 

Clicking the “capture memory” button will start acquiring the volatile memory. 



<!-- Start of picture text -->
Memory Progress<br>Destination: C:\Drivers\FTK _MAGER\memcapture.ad1<br>Status: Memory capture finished successfully<br>Close<br><!-- End of picture text -->

NOTE: Once the acquisition has completed, the destination folder will have the acquired memory with the file extension of “.mem”. 

Acquiring non-volatile memory (Disk Image) using FTK Imager 

As previously stated, this same tool can be used to collect a disk image as well. Open FTK 

Imager and navigate to “Create Disk Image”. 



<!-- Start of picture text -->
Select Source x<br>Please Select the Source Evidence Type<br>© Physical Drive<br>Logical Drive<br>) Image File<br>> Contents of a Folder<br>(logical file-level analysis only; excludes deleted. unallocated, etc)<br>Femico Device (multiple CD/DVD)<br>Next> Cancel Help<br><!-- End of picture text -->

NOTE: FTK Imager is capable of acquiring physical drives (physical hard drives), logical drives (partitions), image files, contents of a folder, or CDs/DVDs. Investigators can connect external HDDs into the collection computer 

via write blocker and use the “logical drive” option to select the mounted HDD as a partition. Collecting Physical Drives 

Select the “Physical Drive” option. 

Select the drive you need to acquire and click “Finish”. 



<!-- Start of picture text -->
Select File ,<br>Evidence Source Selection<br>Please enter the source path:<br>C:\Drivers\FTK __MAGER\memcapture.ad1<br>Browse_<br>< Back Finish Cancel Help<br><!-- End of picture text -->

Raw (dd): This is the image format most commonly used by modern analysis tools. These raw file formatted images do not contain headers, metadata, or magic values. The raw format typically includes padding for any memory ranges that were intentionally skipped (i.e., device memory) or that could not be read by the acquisition tool, which helps maintain spatial integrity (relative offsets among data). 

SMART: This file format is designed for Linux file systems. This format keeps the disk images as pure bitstreams with optional compression. The file consists of a standard 13-byte header followed by a series of sections. Each section includes its type string, a 64-bit offset to the next section, its 64-bit size, padding, and a CRC, in addition to actual data or comments, if applicable. 

E01: this format is a proprietary format developed by Guidance Software’s EnCase. This format compresses the image file. An image with this format starts with case information in the header and footer, which contains an MD5 hash of the entire bit stream. This case information contains the date and time of acquisition, examiner’s name, special notes and an optional password. 

AFF: Advance Forensic Format (AFF) was developed by Simson Garfinkel and Basis Technology. Its latest implementation is AFF4. The goal is to create a disk image format that does not lock the user into a proprietary format that may prevent them from being able to properly analyze it. 

Now enter the case details. 



<!-- Start of picture text -->
Evidence Item Information x<br>Case Number: 99240041354<br>Evidence Number: 1157<br>Unique Description: FTK Image Scanner<br>Examiner: DUDDU POTHAN<br>Notes:<br>< Back Next > Cancel Help<br><!-- End of picture text -->

Add an image destination (where the image file will be saved), image file name and fragment size. 



<!-- Start of picture text -->
Select Image Destinatior x<br>Image Destination Folder<br>C:\Drivers\FTK __MAGER Browse<br>Image Filename (Excluding Extension)<br>FTK_Imager_DUDDU POTHAN<br>Image Fragment Size (MB) 4500<br>For Raw, E01, and AFF formats: 0 = do not fragment<br>Compression (0=None, 1=Fastest, .... 9=Smallest) 6 ><br>Use AD Encryption {_}<br>Filter by File Owner{_}<br>< Back Finish Cancel Help<br><!-- End of picture text -->

Image Fragment Size (MB): this option will separate the image file into multiple images and save 

them in the same destination. If you need only one file instead of creating multiple fragmented images, you must set the image fragment size to “0”. 

Select the “verify images after they are created” option. This will verify the hash values once the image has created. In order to ensure integrity, it is recommended to use this option. However, this will increase the time taken to acquire your evidence, especially if you’re dealing with a large disk image size. 

Click “start” to start acquiring. 



<!-- Start of picture text -->
reate Imag<br>Image Source<br>€:\Drivers\FTK _MAGER\memeapture.adi<br>Image Destination(s)<br>€:\Drivers\FTK _MAGER\FTK_Imager_DUDDU POTHAN [Logical Image]<br>} |<br>Add... Edit Remove<br>Add Overflow Location<br>@ verify images after they are created {_]Precatculate Progress Statistics<br>(_) Create directory listings of all files in the image after they are created<br>| Start Cancel<br><!-- End of picture text -->

Once acquiring is complete, it will create a text file including all the information it has acquired. 



<!-- Start of picture text -->
Creating Image. x<br>Image Source: C:\Drivers\FTK _MAGER\memcapture.ad1<br>Destination: C:\Drivers\FTK _MAGER\FTK_Imager_DUDDU POTHAN<br>Status: Creating image...<br>Progress—— |<br>Elapsed time: 0:00:03<br>Estimated time left:<br>Cancel<br><!-- End of picture text -->



<!-- Start of picture text -->
Creating Image... x<br>Image Source: C:\Drivers\FTK _MAGER\memcapture.adi<br>Destination: C:\Drivers\FTK _MAGER\FTK_Imager_DUDDU POTHAN<br>Status: Image created successfully<br>ProgresscM<br>Elapsed time: 0:15:43<br>Estimated time left:<br>Image Summary... Close<br><!-- End of picture text -->



<!-- Start of picture text -->
5<br>= Properties<br>Name<br>| MDs Hash<br>Computed hash<br>Report Hash<br>Verify result<br>BsHat Hash<br>_ a<br>Computed hash<br>Report Hash<br>Close<br><!-- End of picture text -->

Hash values are matched. 



<!-- Start of picture text -->
ib Add Data Source x<br>Steps Sale Date Source Type<br>1. Select Host<br>2. Select Data Source Type " a<br>3. Select Data Source =) Disk Image or ve Fil<br>4. Configure ingest<br>5. Add Oata Source<br>is Local Disk<br>Ed ovat<br>‘= Unallocated Space Image File<br>+= Autopsy Logical tmager Results<br>t= ° _ XRY Text Export<br><Back | Next> | " Cancet ely<br>a a Sunt<br>Steps Select Data Source<br>1. Select Host Local files and folders<br>2. Select Date Source Type<br>3. Select Data Source (CA Usere\duddu\Desictop\New foider\DUDDU POTHAN Add<br>4. Configure ingest<br>S Add Data Source Delete<br>Clear<br>Logical File Set Display Nome: Default Change<br>Timestamps To Include<br>1B Modified Time - Often not changed whena file 's copied<br>BB Creation Time - Often changed when a file is copied<br>BB Access Time - Can be changed when the file is opened<br>NOTE: Tame stamps may have changed whan the files ware copied to the current location,<br><Back [ Net> | Fine Cancel Hote<br><!-- End of picture text -->



<!-- Start of picture text -->
MwA<br>Steps0 Comfigure ingest<br>1. Select Host<br>2. Select Data Source Type Run ingest modules on<br>3. SSA Z<br>Select Data Source selected module has no per-run settings<br>4.<br>AddaConfigure| All Files, Directories, and Unallocated Space<br>Sour Se<br>@ Hash Lookup<br>B File Type Identification<br>B_ Extension Mismatch Detector<br>B_ Embedded File Extractor<br>Bs Picture Analyzer<br>Keyword Search<br>B Email Parser<br>@ Encryption Detection<br>@ interesting Files Identifier<br>@ Contrat Repository<br>PhotoRec Carver<br>Virtual Machine Extractor Extracts recent user activity, such as Web browsing, rece<br>SelectAll Deselect All Hi nds<br>Next > i i Jot<br><!-- End of picture text -->



<!-- Start of picture text -->
dB Add Data Source x<br>1. Select Host<br>2. Select Data Source Type<br>3. Select Dete Source<br>4. Configure Ingest Data source has been added to the local database. Files are being analyzed.<br>5, Add Data Source<br>Niet >] Finish Cancet ‘<br><!-- End of picture text -->

**4. Initial Analysis and Overview** 

   - **Ingest Progress:** As Autopsy processes the data source, you'll see the progress in the lower-left corner. 

   - **Explore the Resulting Artifacts:** 

      - Autopsy automatically categorizes findings such as web artifacts, file system metadata, and communication records. 

   - **Use the Tree Viewer:** 

      - On the left pane, you’ll see a tree structure where you can explore different aspects like File System, Web History, Email, etc. 

**5. Detailed Analysis** 

   - **Keyword Search:** 

      - You can perform specific keyword searches using the Keyword Search module. 

      - Use pre-configured lists or enter custom keywords. 

   - **File Analysis:** 

      - Navigate through files and folders under the File Types or File System section. 

      - Open, view, or export files for further examination. 

   - **Timeline Analysis:** 

      - Use the Timeline module to visualize events based on timestamps. 

      - This can help track user activity over time. 

   - **Hash Analysis:** 

      - Compare file hashes with known databases to identify known good or bad files. 



<!-- Start of picture text -->
*<br>on<br><!-- End of picture text -->

### **6. Reporting** 

- **Generate a Report:** 

   - After analyzing the data, click on Generate Report from the toolbar. 

   - Choose the type of report (HTML, CSV, Excel, etc.). 

   - Select which parts of the analysis you want to include in the report. 

- **Export Findings:** 

   - Export individual files or artifacts that you need for your report or further analysis. 

- **Final Review:** 

   - Review the report to ensure it includes all relevant information. 

   - Save or print the report for use in your case. 



<!-- Start of picture text -->
7 ,<br>Select and Configure ReportModules<br>Report Modules:<br>O HIM Report A report about results and tagged items in HTML format,<br>Excel Report<br>Fes - Tent Header:<br>Data Source Summary Report Footer,<br>Save Tagged Hashes<br>Extract Unique Words<br>TSK Body File<br>Google Earth KML<br>(CASE-UCO<br>Portable Case<br>Nest > . Cancet te<br>dd Report Generation Progress... x<br>HTML Report > C\Users\duddu\. \Reports\OUDOU POTHAN HIML Report 08-31-2026-11-57-09\reparthtmi<br>Completd<br>Ir Close<br><!-- End of picture text -->



<!-- Start of picture text -->
isi ats Autopsy Forensic Report<br><!-- End of picture text -->

### **7. Case Closure** 

   - **Close the Case:** 

      - Once you have completed your investigation, close the case within Autopsy. 

   - **Archiving:** 

      - Ensure all data and reports are properly archived according to your organization's policies. 

**8. Advanced Features (Optional)** 

   - **Custom Ingest Modules:** 

      - Autopsy allows for custom modules to be added if you need specific analysis tools not included by default. 

   - **Collaboration:** 

      - Autopsy can be configured for multi-user cases if you’re working in a team environment. 

