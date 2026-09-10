touch notes.txt made a empty notes.txt file
echo "Line 1" > notes.txt print 1 line 
echo "Line 2" >> notes.txt  print second line use this if you want to add a line not replace 

eg code:
<img width="1920" height="1080" alt="Screenshot (1)" src="https://github.com/user-attachments/assets/fa9133f2-80ea-4734-92a8-0ec6125c39ba" />31-16-194:~$ 


echo "Line 3" | tee -a notes.txt tee used to add text also display 
cat notes.txt show text in it
head -n 2 notes.txt - dispay top n lines
tail -n 2 notes.txt- display last n lines
