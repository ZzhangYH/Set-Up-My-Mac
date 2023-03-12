# Setup SSH Key
With SSH keys, you can connect to GitHub or GitLab without supplying your username and personal access token at each visit. You can also use an SSH key to sign commits.
- [Generate a new SSH key](#generate-a-new-ssh-key)
- [Add your SSH key to the ssh-agent](#add-your-ssh-key-to-the-ssh-agent)
- [Add your SSH Key to your account](#add-your-ssh-key-to-your-account)
- [Test your SSH connection](#test-your-ssh-connection)


## Generate a new SSH key
Open Terminal and run the line below, substituting your email address as a label.
```
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```

Follow the prompts and by default just `[Press Enter]` on every step:
```
> Generating public/private ALGORITHM key pair.
> Enter a file in which to save the key (/Users/YOU/.ssh/id_ALGORITHM): [Press enter]
> Enter passphrase (empty for no passphrase): [Press Enter]
> Enter same passphrase again: [Press Enter]
```


## Add your SSH key to the ssh-agent
Start the ssh-agent in the background.
```
eval "$(ssh-agent -s)"
```

Add your SSH key to the ssh-agent.
```shell
ssh-add ~/.ssh/id_rsa
```


## Add your SSH Key to your account
Copy your SSH key to clipboard.
```shell
pbcopy < ~/.ssh/id_rsa.pub
```

Then you can **_paste_** your SSH Key to your GitHub or GitLab account to enable authentication for Git operations over SSH.


## Test your SSH connection
Open Terminal and run the following line.
```shell
ssh -T git@github.com
```
👉 __Note:__ Use the GitHub or GitLab **_instance URL_** you are trying to connect to. The instance URL can be found within the option __Clone with SSH__. For example, in `git@github.com:username/repository-space-name`, the prefix `git@github.com` is the instance URL.

Follow the instructions and type `yes`:
```
> The authenticity of host 'github.com (IP ADDRESS)' can't be established.
> RSA key fingerprint is SHA256:nThbg6kXUpJWGl7E1IGOCspRomTxdCARLviKw6E5SY8.
> Are you sure you want to continue connecting (yes/no)? [yes]
```

Receiving a welcome with `Hi username!` or `@username!` means you are all done!