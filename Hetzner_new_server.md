**Do not go with IPv6 - you need IPv4**

Reason: Putty cannot ssh to an IPv6 server. It simply does not support IPv6 connection. I tried using square brackets and tried using both port 22 and 222, but nothing worked. From then on, I could only use the terminal built into the Hetzner web-interface, which was terrible, as all the keys were mapped differently, than what I am used to. Also, the resolution was bad.

Filezilla is said to have inbuilt IPv6 support, but this can only be used for managing files. I could not get that to work though, and the Hetzner documention only mentions FTP/FTPS support for their "Storage Box" products.

**Normal workflow when connecting to a new server for the first time:**

```mermaid
  graph TD;
      1[Create your public key and private key using putty]
      1--->2[Give public key to server host]
      2--->3["Convert your private key to putty file (.pkk) format using puttygen"]
      3--->4["Load the .ppk file into putty (Category > Connection > SSH > Auth)"]
      4--->5["Connect using the IPv4 address on port 22"]
```
Now in order to update the list of ubuntu packages that you can install:

> sudo apt-get update

**Installing Jekyll**

> sudo apt-get install ruby-full build-essential zlib1g-dev

From the Jekyll website:

*Avoid installing RubyGems packages (called gems) as the root user. Instead, set up a gem installation directory for your user account. The following commands will add environment variables to your ~/.bashrc file to configure the gem installation path:*

> echo '# Install Ruby Gems to ~/gems' >> ~/.bashrc

> echo 'export GEM_HOME="$HOME/gems"' >> ~/.bashrc

> echo 'export PATH="$HOME/gems/bin:$PATH"' >> ~/.bashrc

> source ~/.bashrc

Now install Jekyll: 

> gem install jekyll bundler