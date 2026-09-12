
  sudo useradd nairobi   #add user
  177  sudo groupadd project-team   #add grp
  178  cat /etc/passwd   #check all user and grp
sudo usermod -aG project-team tokyo   #add user to grp 
sudo chown :project-team /opt/team-workspace   #change owner of directory
222  sudo chmod 2775 /opt/team-workspace   #give permission to dicrectory and file inside them



