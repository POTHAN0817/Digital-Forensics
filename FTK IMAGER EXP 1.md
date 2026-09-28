# Evidence Acquisition Using Access Data FTK Imager

**Exp no :01**                                                                                   **Date :**

## Description

Forensic Toolkit or FTK is a computer forensics software product made by AccessData. This is a Windows based commercial product. For forensic investigations, the same development team has created a free version of the commercial product with fewer functionalities. This FTK Imager tool is capable of both acquiring and analyzing computer forensic evidence.

The evidence FTK Imager can acquire can be split into two main parts. They are:

- Acquiring volatile memory
- Acquiring non-volatile memory (Hard disk)

There are two possible ways this tool can be used in forensics image acquisitions:

- Using FTK Imager portable version in a USB pen drive or HDD and opening it directly from the evidence machine. This option is most frequently used in live data acquisition where the evidence PC/laptop is switched on.
- Installing FTK Imager on the investigator’s laptop.

In this case the source disk should be mounted into the investigator’s laptop via write blocker. The write blocker prevents data being modified in the evidence source disk while providing read-only access to the investigator’s laptop. This helps to maintain the integrity of the source disk.

## Acquiring volatile memory using FTK Imager

The FTK Imager tool helps investigators to collect the complete volatile memory (RAM) of a computer. The following steps will show you how to do this.

Open FTK Imager and navigate to the volatile memory icon (capture memory).

<!-- Page 2 -->

![Screenshot](images/page-02-screenshot-01.png)

![Screenshot](images/page-02-screenshot-02.jpeg)

<!-- Page 3 -->

**NOTE:** This tool provides options to include pagefile and AD1 files when acquiring the volatile memory.

**Pagefile:** The pagefile (pagefile.sys) is used in Windows operating systems as volatile memory due to limitation of physical random-access memory (RAM). It is located under the “C” partition ready to use as volatile memory when the existing RAM capacity is exceeded. So this file can have quite a bit of valuable data when considering the volatile memory. Therefore, it is recommended to capture and collect this file in the acquisition.

**AD1 file:** AD1 is the FTK imager image file. The investigator has the option to create an AD1 file for later use.

Clicking the “capture memory” button will start acquiring the volatile memory.

![Screenshot](images/page-03-screenshot-01.png)

**NOTE:** Once the acquisition has completed, the destination folder will have the acquired memory with the file extension of “.mem”.

## Acquiring non-volatile memory (Disk Image) using FTK Imager

As previously stated, this same tool can be used to collect a disk image as well. Open FTK Imager and navigate to “Create Disk Image”.

<!-- Page 4 -->

![Screenshot](images/page-04-screenshot-01.jpeg)

**NOTE:** FTK Imager is capable of acquiring physical drives (physical hard drives), logical drives (partitions), image files, contents of a folder, or CDs/DVDs. Investigators can connect external HDDs into the collection computer via write blocker and use the “logical drive” option to select the mounted HDD as a partition.

### Collecting Physical Drives

Select the “Physical Drive” option.

Select the drive you need to acquire and click “Finish”.

![Screenshot](images/page-04-screenshot-02.png)

<!-- Page 5 -->

Raw (dd): This is the image format most commonly used by modern analysis tools. These raw file formatted images do not contain headers, metadata, or magic values. The raw format typically includes padding for any memory ranges that were intentionally skipped (i.e., device memory) or that could not be read by the acquisition tool, which helps maintain spatial integrity (relative offsets among data).

SMART: This file format is designed for Linux file systems. This format keeps the disk images as pure bitstreams with optional compression. The file consists of a standard 13-byte header followed by a series of sections. Each section includes its type string, a 64-bit offset to the next section, its 64-bit size, padding, and a CRC, in addition to actual data or comments, if applicable.

E01: this format is a proprietary format developed by Guidance Software’s EnCase. This format compresses the image file. An image with this format starts with case information in the header and footer, which contains an MD5 hash of the entire bit stream. This case information contains the date and time of acquisition, examiner’s name, special notes and an optional password.

AFF: Advance Forensic Format (AFF) was developed by Simson Garfinkel and Basis Technology. Its latest implementation is AFF4. The goal is to create a disk image format that does not lock the user into a proprietary format that may prevent them from being able to properly analyze it.

Now enter the case details.

![Screenshot](images/page-05-screenshot-01.png)

<!-- Page 6 -->

Add an image destination (where the image file will be saved), image file name and fragment size.

![Screenshot](images/page-06-screenshot-01.png)

Image Fragment Size (MB): this option will separate the image file into multiple images and save them in the same destination. If you need only one file instead of creating multiple fragmented images, you must set the image fragment size to “0”.

Select the “verify images after they are created” option. This will verify the hash values once the image has created. In order to ensure integrity, it is recommended to use this option. However, this will increase the time taken to acquire your evidence, especially if you’re dealing with a large disk image size.

Click “start” to start acquiring.

![Screenshot](images/page-06-screenshot-02.jpeg)

<!-- Page 7 -->

Once acquiring is complete, it will create a text file including all the information it has acquired.

![Screenshot](images/page-07-screenshot-01.png)

![Screenshot](images/page-07-screenshot-02.png)

<!-- Page 8 -->

![Screenshot](images/page-08-screenshot-01.jpeg)

Hash values are matched.

<!-- Page 9 -->

![Screenshot](images/page-09-screenshot-01.jpeg)

![Screenshot](images/page-09-screenshot-02.jpeg)

<!-- Page 10 -->

![Screenshot](images/page-10-screenshot-01.jpeg)

![Screenshot](images/page-10-screenshot-02.jpeg)

## 4. Initial Analysis and Overview

- **Ingest Progress:** As Autopsy processes the data source, you'll see the progress in the lower-left corner.

<!-- Page 11 -->

- **Explore the Resulting Artifacts:**
  - Autopsy automatically categorizes findings such as web artifacts, file system metadata, and communication records.
- **Use the Tree Viewer:**
  - On the left pane, you’ll see a tree structure where you can explore different aspects like File System, Web History, Email, etc.

## 5. Detailed Analysis

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

<!-- Page 12 -->

![Screenshot](images/page-12-screenshot-01.jpeg)

## 6. Reporting

- **Generate a Report:**
  - After analyzing the data, click on Generate Report from the toolbar.
  - Choose the type of report (HTML, CSV, Excel, etc.).
  - Select which parts of the analysis you want to include in the report.
- **Export Findings:**
  - Export individual files or artifacts that you need for your report or further analysis.
- **Final Review:**
  - Review the report to ensure it includes all relevant information.
  - Save or print the report for use in your case.

<!-- Page 13 -->

![Screenshot](images/page-13-screenshot-01.jpeg)

![Screenshot](images/page-13-screenshot-02.jpeg)

<!-- Page 14 -->

![Screenshot](images/page-14-screenshot-01.jpeg)

## 7. Case Closure

- **Close the Case:**
  - Once you have completed your investigation, close the case within Autopsy.
- **Archiving:**
  - Ensure all data and reports are properly archived according to your organization's policies.

## 8. Advanced Features (Optional)

- **Custom Ingest Modules:**
  - Autopsy allows for custom modules to be added if you need specific analysis tools not included by default.
- **Collaboration:**
  - Autopsy can be configured for multi-user cases if you’re working in a team environment.
