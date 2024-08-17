Step 1: Create Users and Groups
Create Users

bash
Copy code
sudo useradd user1
sudo useradd user2
sudo useradd user3
sudo passwd user1
sudo passwd user2
sudo passwd user3
Create Groups

bash
Copy code
sudo groupadd devops
sudo groupadd aws
Change Primary Group of Users

bash
Copy code
sudo usermod -g devops user2
sudo usermod -g devops user3
Add Secondary Group to User

bash
Copy code
sudo usermod -aG aws user1
Step 2: Create Directory and File Structure
Create Directory Structure

bash
Copy code
sudo mkdir -p /dir1 /dir7/dir10 /opt/dir14/dir10
Create Files

bash
Copy code
sudo touch /dir1/f1 /dir7/dir10/f2
Change Group Ownership

bash
Copy code
sudo chgrp devops /dir1 /dir7/dir10 /dir7/dir10/f2
Change Ownership

bash
Copy code
sudo chown user1 /dir1 /dir7/dir10 /dir7/dir10/f2
Step 3: Tasks for User1
Switch to User1

bash
Copy code
su - user1
Create Users

bash
Copy code
sudo useradd user4
sudo useradd user5
sudo passwd user4
sudo passwd user5
Create Groups

bash
Copy code
sudo groupadd app
sudo groupadd database
User4: Create Directory and Files

bash
Copy code
su - user4
mkdir -p /dir6/dir4
touch /dir6/dir4/f3
mv /dir1/f1 /dir2/dir1/dir2
mv /dir7/dir10/f2 /dir7/dir10/f4
exit
User1: Create Directory and Files

bash
Copy code
mkdir -p /home/user2/dir1
cd /dir2/dir1/dir2/dir10
touch /opt/dir14/dir10/f1
mv /opt/dir14/dir10/f1 /home/user1/
rm -r /dir6/dir4
rm -rf /opt/dir14/*
echo "Linux assessment for an DevOps Engineer!! Learn with Fun!!" > /dir6/dir4/f3
Step 4: Tasks for User2
Switch to User2

bash
Copy code
su - user2
Create Files and Directories

bash
Copy code
touch /dir1/f2
rm -r /dir6
rm -r /dir8
sed -i 's/DevOps/devops/g' /dir6/dir4/f3
vi /dir6/dir4/f3
Copy and Paste Line in Vi

In vi editor, copy line 1 using yy and paste it 10 times using 10p.
Search and Replace in Vi

In vi, use the following command:
ruby
Copy code
:%s/Engineer/engineer/g
Delete File

bash
Copy code
rm /dir6/dir4/f3
Step 5: Tasks for Root
Switch to Root

bash
Copy code
sudo su
Search for Files and Show Count

bash
Copy code
find / -name f3
ls -lR / | grep -c '^-'  # Count the number of files
Print Last Line of a File

bash
Copy code
tail -n 1 /etc/passwd
Step 6: EBS Volume Tasks (On Local System)
If you’re working on a local system, you can simulate this by using a loopback device or simply skip these steps. For educational purposes:

Create File System and Mount
bash
Copy code
sudo mkfs.ext4 /dev/loop0
sudo mount /dev/loop0 /data
df -h | grep /data
touch /data/f1
Step 7: Cleanup
User5: Delete Directories and Files

bash
Copy code
su - user5
rm -r /dir1 /dir2 /dir3 /dir5 /dir7
rm /f1 /f4
rm -rf /opt/dir14
exit
Root: Cleanup

bash
Copy code
sudo userdel user1
sudo userdel user2
sudo userdel user3
sudo userdel user4
sudo userdel user5
sudo groupdel app
sudo groupdel aws
sudo groupdel database
sudo groupdel devops
rm -rf /home/user1 /home/user2 /home/user3 /home/user4 /home/user5
umount /data
rm -rf /data
Conclusion
Now you have completed all the tasks locally. If you have any issues or further questions, feel free to ask!






