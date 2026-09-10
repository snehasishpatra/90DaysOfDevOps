
Environment basics (2): uname -a: display info about my system -a helps to et info in detail ,
lsb_release -a 
(or cat /etc/os-release)- it gives info about my os and its version
Filesystem sanity (2): create a throwaway folder and file, e.g., 
mkdir /tmp/runbook-demo it made dir name run book -demo
cp /etc/hosts /tmp/runbook-demo/hosts-copy && ls -l /tmp/runbook-demo: it copy content from souce to detination and just displays it
CPU / Memory (2): top/htop: it shows all running processes
/ps -o pid: shows all processes running
pcpu: 
pmem,
comm -p <pid>, 
free -h - it shows disk usage details in readable human format
Disk / IO (2): df -h: file sys disk space
du -sh /var/log : displays disk usage 
, iostat: input output network statistics
Network (2): ss -tulpn: socket statistics  list which program are listning on which port -t -tcp -u udp -l-listening -p process id -n -numeric
/netstat -tulpn:- same as before, 
curl -I <service-endpoint> : fetches only header data of the response 
ping : it sent a packet and check its echo and packets lost
Logs (2): journalctl -u <service> -n 50: shows log file , 
tail -n 50 /var/log/<file>.log: shows last 50 lines 
