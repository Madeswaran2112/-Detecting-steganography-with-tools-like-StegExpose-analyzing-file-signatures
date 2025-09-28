# Detecting-steganography-with-tools-like-StegExpose-analyzing-file-signatures
## AIM:
To detect hidden data using steganography detection tools like StegExpose and analyze file signatures for authenticity and manipulation.
## Requirements:
- **Operating System:** Linux / Windows
- **Tools:**
    - StegExpose (Java-based tool)
    - Hex Editor (e.g., xxd, HxD)
    - File command (Linux) or TrID (Windows)
- **Sample files:**
    - Suspected stego files (.jpg, .png, .wav)
    - Clean reference files
## ARCHITECTURE DIAGRAM:
```mermaid
flowchart TD
    A[Input File: JPG/PNG/WAV] --> B[File Signature Analysis]
    B --> C{Signature Match?}
    C -- Yes --> D[Pass to StegExpose]
    C -- No --> E[File Tampered / Mismatch]
    D --> F[StegExpose Detection: Suspicious or Clean]
    F --> G[Report Findings]
```

## DESIGN STEPS:
### Step 1:
Install StegExpose or use the JAR version to detect steganography in image files.

### Step 2:
Run StegExpose on a directory of suspected image files using the command:

### Step 3:
Analyze file signatures using tools like file, binwalk, or xxd to check for inconsistencies or embedded content.

## PROGRAM:
**Check file type**
```bash
file suspect.jpg
```
or view magic bytes:
```
xxd suspect.jpg | head
```
**Run StegExpose**
```bash
java -jar StegExpose.jar suspect.jpg
```

## Analyze the Type of the file


<img width="723" height="333" alt="Screenshot 2025-09-28 194221" src="https://github.com/user-attachments/assets/a3e73153-8c29-45e5-a7e4-b1a6088ed269" />


## Install Steghide 

<img width="682" height="115" alt="Screenshot 2025-09-28 194247" src="https://github.com/user-attachments/assets/c567b810-084b-43e3-b5df-a161c7f37f24" />

## Using steghide embed the jpeg file

```bash
steghide embed -cf 12.jpeg -ef secret.txt
```


<img width="488" height="103" alt="Screenshot 2025-09-28 194256" src="https://github.com/user-attachments/assets/15e4d859-57ae-4caf-b6d8-af8f303ad1fd" />




## using steghide extract thr file in the jpeg file




<img width="596" height="105" alt="Screenshot 2025-09-28 194303" src="https://github.com/user-attachments/assets/21b288f6-b37a-42a2-88f1-7245be89c4cd" />




## OUTPUT:
List of Images with Steganography Detection Scores and File Signature Details

## RESULT:
Hidden data was successfully detected and file signatures were analyzed for irregularities.
