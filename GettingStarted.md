## Request Account
Request a cluster account by filling out the following form: Cluster account request form [Cluster account request form](https://research.computing.yale.edu/support/hpc/account-request)

## Cluster Selection
* Milgram: for sensitive data and/or data with PHI, in compliance with HIPAA
* McCleary: for insensitive data or public data
* Grace: Similar to McCleary, but mainly for the CS & EE department (ask if your PI has the right to access it)

## Log into Cluster

Before logging into the the cluster, you must ensure your device is under the Yale network or is connected with Yale VPN.

An email will be sent to you after account request is approved. For SSH connection, you will need to upload the SSH Key for your devices. 
First, check if your device already has an SSH key pair: 
```
ls ~/.ssh/id_*
```
If an SSH key exists, you should see a file name like `id_rsa.pub` or `id_ed25519.pub`. 
If keys already exist, you’ll see files such as `id_rsa` and `id_rsa.pub` or `id_ed25519` and `id_ed25519.pu`b. The private key (e.g., id_rsa) should be kept secure, while the public key (e.g., id_rsa.pub) can be shared with cluster.
If SSH key pair does not exist, you can generate your public and private ssh keys:
```
ssh-keygen
```
Your terminal should respond:
```
Generating public/private rsa key pair.
Enter file in which to save the key (/home/yourusername/.ssh/id_rsa):
```
Press Enter to accept the default value. Your terminal should respond:
```
Enter passphrase (empty for no passphrase):
```
Choose a secure passphrase. Your passphrase will prevent access to your account in the event your private key is stolen. You will not see any characters appear on the screen as you type. The response will be:
```
Enter same passphrase again:
```
Enter the passphrase again. The key pair is generated and written to a directory called `.ssh` in your home directory. The public key is stored in `~/.ssh/id_rsa.pub`. If you forget your passphrase, it cannot be recovered. Instead, you will need to generate and upload a new SSH key pair.

Next, upload your public SSH key on the cluster. Run the following command in a terminal:
```
cat ~/.ssh/id_rsa.pub
```
Copy and paste the output to the [SSH key uploader](https://sshkeys.ycrc.yale.edu/cgi-bin/sshkeys.py). Note: It can take a few minutes for newly uploaded keys to sync out to the clusters so your login may not work immediately.

Once the public key is uploaded successfully, log onto the cluster using
```
ssh netid@clustername.ycrc.yale.edu.
```
