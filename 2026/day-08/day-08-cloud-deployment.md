  127  sudo tail -n 50 /var/log/nginx/acess.log
  128  sudo tail -n 50 /var/log/nginx/access.log
  129  sudo cp /var/log/nginx/access.log ~/nginx-logs.txt
  131  ls -l ~nginx-logs.txt
  133  scp -i "batch9key.pem" ubuntu@ec2-18-201-242-140.eu-west-1.compute.amazonaws.com>:~/nginx-logs.txt
  134  ls
  135  whoami
  136  sudo chown $ubuntu:$ubuntu ~/nginx-logs.txt
  137  scp -i "batch9key.pem" ubuntu@ec2-18-201-242-140.eu-west-1.compute.amazonaws.com>:~/nginx-logs.txt
  138  ls
  139  ls -a
  140  cat nginx-logs.txt
  141  pwd
  142  cd
  143  scp -i "batch9key.pem" ubuntu@ec2-18-201-242-140.eu-west-1.compute.amazonaws.com>:~/nginx-logs.txt
  144  ls
  145  cat nginx-logs.txt
was unable to install docker.io unable to locate nginx-logs.txt
was able to install file in local system
[nginx-logs.txt](https://github.com/user-attachments/files/32138776/nginx-logs.txt)
<img width="1722" height="582" alt="Screenshot 2026-09-12 103825" src="https://github.com/user-attachments/assets/654a6de3-f8b6-43e7-aa02-dba68740bec6" />
