# Use GitHub via SSH

1. In local terminal
   ```bash
   # 1. Generate new key pair
   ssh-keygen

   # 2. Display the key in terminal
   cat ~/.ssh/id_rsa.pub
   ```
2. Copy the key from terminal.
3. Paste the key in GitHub's settings. Settings -> SSH and GPG keys.
4. Done. Should be able to use GitHub via SSH.