SSH Host with Fail2ban, Google Authenticator
===
This docker container bundles up sshd, fail2ban and google-authenticator TOTP into a secure ssh gateway box. 'user' account is available.

Docker compose will mount your .google_authenticator and id_rsa.pub from within the data dir

