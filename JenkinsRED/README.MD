1  sudo yum update
    2  $ sudo yum update –y
    3   sudo yum update –y
    4  sudo wget -O /etc/yum.repos.d/jenkins.repo     https://pkg.jenkins.io/redhat-stable/jenkins.repo
    5  sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io-2023.key
    6  sudo yum upgrade
    7  sudo dnf install java-17-amazon-corretto -y
    8  sudo yum install jenkins -y
    9  sudo systemctl enable jenkins
   10  sudo systemctl start jenkins
   11  sudo systemctl status jenkins
   12  /var/lib/jenkins/secrets/initialAdminPassword
   13  sudo cat /var/lib/jenkins/secrets/initialAdminPassword
