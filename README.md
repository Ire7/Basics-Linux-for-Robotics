# Basics-Linux-for-Robotics

## Step1: Understanding File Permissions in Linux
In Linux, every file and directory has a set of permissions that determine who can **read**, **write**, or **execute** it.
Permissions are assigned to three categories:

**Owner**  the user who owns the file  
**Group**  users who belong to the file’s group  
**Others** all other users

Each category can have three types of permissions:

| Symbol | Meaning  | Numeric Value |
|--------|----------|----------------|
| r      | Read     | 4              |
| w      | Write    | 2              |
| x      | Execute  | 1              |

To convert permissions into numeric form:
rwx = 4 + 2 + 1 = **7**
r-x = 4 + 0 + 1 = **5**

Example:  
rwxrwxr-x = Owner: rwx (7), Group: rwx (7), Others: r-x (5)  
**Numeric form = 775**

can view the permissions of files using the following command:
bash
ls -l

Example output:

rwxrwxr-x 1 user user 1234 Jul 22 14:35 myfile.py

## Step2: Flowchart Explanation

Here is the structure of how Linux divides file permissions:

File Permissions
       ↓
     Owner?
     /    \
  Group?  Others?
     \     /
  Permissions
  rwx   rwx   r-x

This shows that permissions are assigned to Owner, Group, and Others, each with a combination of read (r), write (w), and execute (x).

## Step3: Python Script to Change Permissions

i created a Python file that uses the `chmod` command via Python's `os` module to change a file’s permissions to `rwxrwxr-x` (numeric: 775).

## Python Code (chmod_script.py)

python
import os

file_path = "Q1"  # Replace with your target file

os.chmod(file_path, 0o775)

print(f"Permissions of {file_path} have been changed to 775 (rwxrwxr-x)")

## Steps to run the script:

1. Open the terminal
2. Create the script file:
bash
nano chmod_script.py

3. Paste the code above inside the file
4. Save using `Ctrl + O`, then press `Enter`, and exit with `Ctrl + X`
5. Run the script:
bash
python3 chmod_script.py

6. Confirm permissions have changed using:
bash
ls -l

## Expected Output:
Permissions of Q1 have been changed to 775 (rwxrwxr-x)

And file permission shown as:
rwxrwxr-x 1 user user 16088 Jul 22 14:35 Q1

## Final Result

| Step                            | Status |
|---------------------------------|--------|
| Understood file permissions     | Done     |
| Created flowchart               | Done     |
| Wrote and executed Python code  | Done     |
| Changed file permissions to 775 | Done     |
