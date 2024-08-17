Sure! You can follow the steps on your local Linux machine instead of using an Amazon EC2 instance. Here’s how you can perform the tasks specified in the problem statement:

### Step 1: Create Users and Groups

1. **Create Users**  
   ```bash
   sudo useradd user1
   sudo useradd user2
   sudo useradd user3
   sudo passwd user1
   sudo passwd user2
   sudo passwd user3
   ```

2. **Create Groups**  
   ```bash
   sudo groupadd devops
   sudo groupadd aws
   ```

3. **Change Primary Group of Users**  
   ```bash
   sudo usermod -g devops user2
   sudo usermod -g devops user3
   ```

4. **Add Secondary Group to User**  
   ```bash
   sudo usermod -aG aws user1
   ```

### Step 2: Create Directory and File Structure

1. **Create Directory Structure**  
   ```bash
   sudo mkdir -p /dir1 /dir7/dir10 /opt/dir14/dir10
   ```

2. **Create Files**  
   ```bash
   sudo touch /dir1/f1 /dir7/dir10/f2
   ```

3. **Change Group Ownership**  
   ```bash
   sudo chgrp devops /dir1 /dir7/dir10 /dir7/dir10/f2
   ```

4. **Change Ownership**  
   ```bash
   sudo chown user1 /dir1 /dir7/dir10 /dir7/dir10/f2
   ```

### Step 3: Tasks for User1

1. **Switch to User1**  
   ```bash
   su - user1
   ```

2. **Create Users**  
   ```bash
   sudo useradd user4
   sudo useradd user5
   sudo passwd user4
   sudo passwd user5
   ```

3. **Create Groups**  
   ```bash
   sudo groupadd app
   sudo groupadd database
   ```

4. **User4: Create Directory and Files**  
   ```bash
   su - user4
   mkdir -p /dir6/dir4
   touch /dir6/dir4/f3
   mv /dir1/f1 /dir2/dir1/dir2
   mv /dir7/dir10/f2 /dir7/dir10/f4
   exit
   ```

5. **User1: Create Directory and Files**  
   ```bash
   mkdir -p /home/user2/dir1
   cd /dir2/dir1/dir2/dir10
   touch /opt/dir14/dir10/f1
   mv /opt/dir14/dir10/f1 /home/user1/
   rm -r /dir6/dir4
   rm -rf /opt/dir14/*
   echo "Linux assessment for an DevOps Engineer!! Learn with Fun!!" > /dir6/dir4/f3
   ```

### Step 4: Tasks for User2

1. **Switch to User2**  
   ```bash
   su - user2
   ```

2. **Create Files and Directories**  
   ```bash
   touch /dir1/f2
   rm -r /dir6
   rm -r /dir8
   sed -i 's/DevOps/devops/g' /dir6/dir4/f3
   vi /dir6/dir4/f3
   ```

3. **Copy and Paste Line in Vi**  
   - In `vi` editor, copy line 1 using `yy` and paste it 10 times using `10p`.

4. **Search and Replace in Vi**  
   - In `vi`, use the following command:
     ```
     :%s/Engineer/engineer/g
     ```
   
5. **Delete File**  
   ```bash
   rm /dir6/dir4/f3
   ```

### Step 5: Tasks for Root

1. **Switch to Root**  
   ```bash
   sudo su
   ```

2. **Search for Files and Show Count**  
   ```bash
   find / -name f3
   ls -lR / | grep -c '^-'  # Count the number of files
   ```

3. **Print Last Line of a File**  
   ```bash
   tail -n 1 /etc/passwd
   ```

### Step 6: EBS Volume Tasks (On Local System)

If you’re working on a local system, you can simulate this by using a loopback device or simply skip these steps. For educational purposes:

1. **Create File System and Mount**  
   ```bash
   sudo mkfs.ext4 /dev/loop0
   sudo mount /dev/loop0 /data
   df -h | grep /data
   touch /data/f1
   ```

### Step 7: Cleanup

1. **User5: Delete Directories and Files**  
   ```bash
   su - user5
   rm -r /dir1 /dir2 /dir3 /dir5 /dir7
   rm /f1 /f4
   rm -rf /opt/dir14
   exit
   ```

2. **Root: Cleanup**  
   ```bash
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
   ```

### Conclusion

Now you have completed all the tasks locally. If you have any issues or further questions, feel free to ask!
