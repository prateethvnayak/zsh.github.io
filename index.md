# ZSH Shell [with OH-MY-ZSH config]

### Installation [without root]

Obtain the `sourceforge` tar file of the `zsh` shell files

```bash
wget -O zsh.tar.xz https://sourceforge.net/projects/zsh/files/latest/download
```
Create a new dir to store the installation files. 

```bash
mkdir .zsh
```

untar the files, you get a local dir named `zsh-5.7.1`

```bash
tar -xf zsh.tar.xz 
```

Now, we need to configure the installation to the created dir. Here, the dir `.zsh` created in `$HOME`. You can check the home env using `echo $HOME`

```bash
cd zsh-5.7.1
./configure --prefix=$HOME/.zsh/
```

Once, the configuration is finished without any errors, we can install the zsh-shell using the following commands
```bash
make -j & make install
```

### Making the ZSH default shell

Before installation of `zsh`, if the system was using the `bash` then write the path of the zsh-shell installed into the system path & and execute the zsh on entry
```bash 
echo "export PATH=$HOME/.zsh/bin:$PATH" >> ~/.bashrc
echo "exec zsh" >> ~/.bashrc
```

**CAUTION** : If you are on a remote machine, then first navigate into the `zsh` executable and run it once before adding the path to bashrc, as a mistake in bashrc will automatically logout your session and login would fail with bashrc run fail thereafter.

Now, source the bashrc file, and you will be welcomed with a `zsh-firsttime-installer` as shown below
```bash 
source ~/.bashrc
```
![](images/welcome.png =100x20)

