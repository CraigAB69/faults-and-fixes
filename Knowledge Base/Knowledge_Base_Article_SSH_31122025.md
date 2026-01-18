

If you haven't already:

ssh-keygen -t ed25519 -C "myusername@mypc"

This creates:

- `~/.ssh/id_ed25519` (private key)
    
- `~/.ssh/id_ed25519.pub` (public key)

ssh-copy-id myusername@remote-host

Test to see that you no longer need a password.

Linux:

Edit the ~/.ssh/config

Host remote-host
		Hostname 10.0.0.10
		User myusername
		IdentityFile ~/.ssh/id_ed25519


Ensure permission are correct:

On remote box:

chmod 700 ~/.ssh
chmod 600 ~/.ssh/authorized_keys


On the local linux box

chmod 700 ~/.ssh
chmod 600 ~/.ssh/id_ed25519

