SSH Host with Fail2ban, Google Authenticator
===
This docker container bundles up sshd, fail2ban and google-authenticator TOTP into a secure ssh gateway box. 'user' account is available.

## Start command
docker run -v data/.google_authenticator:/.google_authenticator -v data/id_rsa.pub:/home/user/.ssh/authorized_keys -p 2222:22 skinnys/docker-sshd-otp


## Docker Compose example ##
Docker compose will mount your .google_authenticator and id_rsa.pub from within the data dir
```
version: '2.0'
services:
  sshd:
    image: skinnys/docker-sshd-otp
    container_name: sshd
    volumes:
      -  data/.google_authenticator:/.google_authenticator
      -  data/id_rsa.pub:/home/user/.ssh/authorized_keys 
    ports:
      - "2222:22"
