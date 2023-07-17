# Linux-CLS
Linux CLS
Project description
To ensure the proper level of authorization and maintain system security, my organization's research team was responsible for updating file permissions for specific files and directories within the projects directory. The existing permissions did not align with the required level of access. To accomplish this, I undertook the following steps:
Check file and directory details
The following code demonstrates how I used Linux commands to determine the existing permissions set for a specific directory in the file system.

![image](https://github.com/JeffBeck12/Linux-CLS/assets/138726687/b40805e2-e6c1-4610-b200-664ea3e280dc)

In the provided screenshot, my entered command is displayed in the first line, while the subsequent lines show the corresponding output. By using the "ls" command with the "-la" option, I retrieved a comprehensive listing of the contents within the projects directory. This included hidden files as well. The output reveals the presence of one directory called "drafts," one hidden file named ".project_x.txt," and five other project files. Each file or directory is accompanied by a 10-character string in the first column, representing the set permissions.
Describe the permissions string

# Describe the permissions string

The 10-character string can be deconstructed to determine who is authorized to access the file and their specific permissions. The characters and what they represent are as follows:
1st character: This character is either a d or hyphen (-) and indicates the file type. If it’s a d, it’s a directory. If it’s a hyphen (-), it’s a regular file.


2nd-4th characters: These characters indicate the read (r), write (w), and execute (x) permissions for the user. When one of these characters is a hyphen (-) instead, it indicates that this permission is not granted to the user.

5th-7th characters: These characters indicate the read (r), write (w), and execute (x) permissions for the group. When one of these characters is a hyphen (-) instead, it indicates that this permission is not granted for the group.

8th-10th characters: These characters indicate the read (r), write (w), and execute (x) permissions for other. This owner type consists of all other users on the system apart from the user and the group. When one of these characters is a hyphen (-) instead, that indicates that this permission is not granted for other.

Taking the example of the file "project_t.txt," the displayed file permissions are "-rw-rw-r--". The first character "-" signifies that it is a file rather than a directory. The second, fifth, and eighth characters "r" indicate that the user, group, and others have read permissions for the file. The third and sixth characters "w" signify that only the user and group have write permissions. Lastly, no one has execute permissions for "project_t.txt."
Change file permissions
The organization determined that other shouldn't have write access to any of their files. To comply with this, I referred to the file permissions that I previously returned. I determined project_k.txt must have the write access removed for other.

The following code demonstrates how I used Linux commands to do this:

![image](https://github.com/JeffBeck12/Linux-CLS/assets/138726687/f06fe4b7-7999-4406-8caf-84f48a648b47)

In the provided screenshot, the first two lines demonstrate the commands you entered, while the subsequent lines exhibit the output of the second command. The "chmod" command is utilized to modify permissions for files and directories. The first argument denotes the desired permission changes, and the second argument specifies the target file or directory. In this specific example, you removed write permissions for others from the file "project_k.txt." 

Following this modification, you employed the "ls -la" command to review the updates made to the permissions.

# Change file permissions on a hidden file

The research team at my organization recently archived project_x.txt. They do not want anyone to have write access to this project, but the user and group should have read access. 

The following code demonstrates how I used Linux commands to change the permissions:

![image](https://github.com/JeffBeck12/Linux-CLS/assets/138726687/7b5793ec-e8bf-4630-9ec9-bd54344cd8b7)


In the provided screenshot, the first two lines depict the commands you entered, while the subsequent lines showcase the output of the second command. Based on the information given, the file ".project_x.txt" is recognized as a hidden file since it starts with a period (.).

In this particular example, you made the following modifications to the file's permissions:

1. Removed write permissions from the user and group: Using "u-w" (user-write) and "g-w" (group-write), you removed write permissions for both the user and group.

2. Added read permissions to the group: Employing "g+r" (group-read), you added read permissions specifically for the group.

These adjustments to the permissions resulted in the desired changes for the file ".project_x.txt".

# Change directory permissions

My organization only wants the researcher2 user to have access to the drafts directory and its contents. This means that no one other than researcher2 should have execute permissions.

The following code demonstrates how I used Linux commands to change the permissions:

![image](https://github.com/JeffBeck12/Linux-CLS/assets/138726687/2c00da34-ba14-46a4-9b27-25f8b4227237)

In the provided screenshot, the first two lines demonstrate the commands you entered, while the subsequent lines exhibit the output of the second command. Based on your previous findings, it was established that the group had execute permissions for the file or directory in question.

To remove the execute permissions specifically for the group, you utilized the "chmod" command. As the researcher2 user already possessed execute permissions, there was no need to add them again.

The modifications made through the "chmod" command resulted in the removal of execute permissions for the group, aligning with your desired changes.

# Summary
You modified permissions for files and directories in the projects directory to match your organization's desired level of authorization. First, you checked the existing permissions using "ls -la" to inform your decisions. Then, you used the "chmod" command multiple times to make the necessary permission changes.
By following these steps, you successfully aligned the permissions with your organization's requirements.






