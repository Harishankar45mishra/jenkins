1. Update System
apt update && apt upgrade -y
3. Install Java
apt install openjdk-17-jdk -y

Verify:

java -version
3. Add Jenkins Repository
curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key | tee \
/usr/share/keyrings/jenkins-keyring.asc > /dev/null
echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
https://pkg.jenkins.io/debian-stable binary/ | tee \
/etc/apt/sources.list.d/jenkins.list > /dev/null
4. Install Jenkins
apt update
apt install jenkins -y
5. Start Jenkins
systemctl start jenkins
systemctl enable jenkins

Check status:

systemctl status jenkins
6. Access Jenkins

Open in browser:

http://YOUR_SERVER_IP:8080
7. Get Initial Password
cat /var/lib/jenkins/secrets/initialAdminPassword
8. Open Port (if needed)
ufw allow 8080
