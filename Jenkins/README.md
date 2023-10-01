sudo apt update
curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key | sudo tee   /usr/share/keyrings/jenkins-keyring.asc > /dev/null
    echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc]   https://pkg.jenkins.io/debian-stable binary/ | sudo tee   /etc/apt/sources.list.d/jenkins.list > /dev/null
sudo apt-get update
sudo apt-get install jenkins
sudo apt install openjdk-11-jdk
java --version
sudo systemctl restart jenkins
sudo systemctl status jenkins
# We need to add 8080 port in the security group
# To check password of Jenkins
sudo cat /var/lib/jenkins/secrets/initialAdminPassword
