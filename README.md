#pisharp

##.NET Code running on a Raspberry Pi

Getting the new ASP.NET vNext running on a Raspberry Pi 2 is challenging but doable. These are the commands and scripts that I use in order to get everything installed and running properly.  This scripts are designed to work in conjunction with my upcoming presentations and a free ebook that I'm working on.  You can check out a early beta version of the ebook [here](https://raw.githubusercontent.com/lluppes/pisharp/master/RaspberryPiNetDeveloper_v1_Beta.pdf).

###Steps to get your Pi2 running Mono and ASP.NET vNext
1. Install Raspbian on your Pi2
2. Down load the getScripts file with the wget command
3. Mark it as executable with the chmod command
4. Run that file and follow the commands in the comments
5. Update your OS by running sh 2_update_os
6. Install Mono by running sh 3_install_mono
7. Install certs needed for kvm by running sh 4_install_certs
8. Install kvm by running sh 5_install_kvm
9. Install libuv by running sh 6_install_libuv

```
wget https://raw.githubusercontent.com/lluppes/pisharp/master/getScripts
chmod 755 getScripts
sh getScripts
sh 2_update_os
sh 3_install_mono
sh 4_install_certs
sh 5_install_kvm
sh 6_install_libuv
```

You should now be able to run your new ASP.NET programs!  There is still a bug somewhere that is creating a duplicate environment variable that needs to be removed so that command is in this list.

###To run a sample MVC6 Web Page
1. Change to the source directory
2. Remove that pesky RUNLEVEL variable
3. Go get the dependencies with kpm restore
3. Start the web server with k kestrel
4. Open your browser and navigate to http://localhost:5004
5. Voila!

```
cd /home/pi/aspnet5/home/samples/HelloMVC
unset RUNLEVEL
kpm restore
k kestrel
```

Let me know if you have problems with these scripts!

Lyle
