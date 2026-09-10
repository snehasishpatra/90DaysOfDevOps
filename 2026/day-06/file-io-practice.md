touch notes.txt made a empty notes.txt file
echo "Line 1" > notes.txt print 1 line 
echo "Line 2" >> notes.txt  print second line use this if you want to add a line not replace 

eg code:
<img width="1920" height="1080" alt="Screenshot (1)" src="https://github.com/user-attachments/assets/fa9133f2-80ea-4734-92a8-0ec6125c39ba" />31-16-194:~$ echo "second line" >> notes.txt
ubuntu@ip-172-31-16-194:~$ cat notes.txt
first line
second line
ubuntu@ip-172-31-16-194:~$ echo "3rd line" | tee -a notes.txt
3rd line
ubuntu@ip-172-31-16-194:~$ cat notes.txt
first line
second line
3rd line
ubuntu@ip-172-31-16-194:~$ cat head -n 1 notes.txt
     1  first line
     2  second line
     3  3rd line
cat: head: No such file or directory
cat: 1: No such file or directory
ubuntu@ip-172-31-16-194:~$ head -n 1 notes.txt
first line
ubuntu@ip-172-31-16-194:~$ tail -n 1 notes.txt
3rd line

echo "Line 3" | tee -a notes.txt tee used to add text also display 
cat notes.txt show text in it
head -n 2 notes.txt - dispay top n lines
tail -n 2 notes.txt- display last n lines
