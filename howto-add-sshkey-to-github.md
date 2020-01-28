# How To Add an SSH key to your GitHub

## Tips When Reading Instructions
- Never blindly follow instructions! Make sure you actually understand what is going on.
If you don't, spend some time on Google.
- Read the entire instructions before starting to actually work.
  - You may find that the instructions are for something completely different than what you are wanting.
  - Maybe the instructions start using weird third-party tools half-way through that you don't want.
    - Maybe you know a different way than using the third-party tools, in which case you can still use the
      instuctions. In computer science, there's always more than one way!
- Pay attention to results of commands. Sometimes errors happen which could be caused by many reasons:
  - Typed the command wrong.
  - APIs are different between versions.
    - Example: previous version you could call `make cat with hat`, but now you have to call `make a cat in a hat`. 
      Developers make many changes, this is why it is important to fully understand what the commands 
      are trying to accomplish!
  - The author of the instructions wrote down the wrong command or used the wrong formatting 
  \(more common than you may think!\).
    - Reading the entire instructions before starting can help with this problem. You might be able to
      figure out what the author was trying to do.
- If you're unsure how a command is supposed to be formatted, look up examples!

### Harsh Lesson

If you're only goal is to finish as quickly as possible, you're in the wrong major. You need to actually understand
what you are typing. Understanding sometimes means hours of researching, testing, and trial and error. Sometimes
certain things take years to even begin to actually understand \(e.x. JavaFX\).

# Instructions

Open a terminal. If on Windows, use [Git Bash](https://git-scm.com/downloads).

## Check For Existing SSH Keys

Run `ls -al ~/.ssh`

If `id_rsa` and `id_rsa.pub` exist, then skip to step "Adding an SSH Key to Your GitHub".

## Creating an RSA Key Pair

Using your email:

1. Run `ssh-keygen -t rsa -b 4096 -C "your_email@example.com"`
   - When prompted for input, just press `Enter` to accept the defaults.
   - Example: `ssh-keygen -t rsa -b 4096 -C "john.tuttle@blackburn.edu"`
1. Make sure the ssh-agent is running
   - Run `eval $(ssh-agent -s)`
     - This should print something like `Agent pid 52486`
1. Add your key to the ssh-agent
   - Run `ssh-add ~/.ssh/id_rsa`

## Adding an SSH key to your GitHub

1. run `cat ~/.ssh/id_rsa.pub`
1. Highlight the entire output and copy using `right-click` -> `copy`.
1. Go to https://github.com and sign in.
1. Go to https://github.com/settings/keys
1. Click "New SSH key"
   - Give the key a meaningful title (ex. "Rlab Computer Tarkin" or "Beru Account")
   - Paste the key. Make sure the key starts with "ssh_rsa" and ends with your email.
   Remove any leading and trailing whitespace if it exists.
   - The pasted key should look like this \(but much longer\):
   ```
   ssh_rsa
   gngakng24425v2k4b5v2b45245bvhb245bvb2kh4b5k24h5bvhk24h5b413kb54v1h3b541k6hb15h71b56h5b3v6bk56hjbvk1h6b1k3hbtbayfgoyaoiyrbaehgb3i5taehrgbi= john.tuttle@blackburn.edu
   ```
   Note: The key is in [Base64](https://en.wikipedia.org/wiki/Base64)
1. Click "Add SSH key"

Congrats! You have now added an SSH key to your GitHub account! You can repeat this process for any
trusted computer you want full access to your GitHub account.

## Configuring Git

Run the following commands:
- `git config --global user.email "<email>"` using your email inside of the quotes.
- `git config --global user.name "<name>"` using your name/alias inside of the quotes.

Example:
- `git config --global user.email "john.tuttle@blackburn.edu"`
- `git config --global user.name "John Tuttle"`

## Notes
- If using the Rlab/Plab machines on Ubuntu, you only need to do this once and the key will work
on any Rlab and Plab machine \(on the ubuntu side\). If you're curious as to why this works, you can ask. Otherwise accept
that your life has been made slightly easier.
