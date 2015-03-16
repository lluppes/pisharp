#pisharp

##.NET Code running on a Raspberry Pi

Getting the new ASP.NET vNext running on a Raspberry Pi 2 is challenging but doable. These are the commands and scripts that I use in order to get everything installed and running properly.  This scripts are designed to work in conjunction with my upcoming presentation and ebook.

###Steps to get your Pi2 running Mono and ASP.NET vNext
1. Install Raspbian on your Pi2
2. Down load the getScripts file: **wget https://raw.githubusercontent.com/lluppes/pisharp/master/getScripts**
3. Mark it as executable with the command:  **chmod 755 getScripts**
4. Run that file and follow the commands in the comments:  **sh getScripts**
5. Update your OS by running:  **sh 1_update_os**
6. Install Mono by running:  **sh 2_install_mono**
7. Install certs needed for kvm by running: **sh 4_install_certs**
8. Install kvm by running: **sh 5_install_kvm**
9. Install libuv by running: **sh 6_install_libuv**

You should now be able to run your new ASP.NET programs!  There is still a bug somewhere that is creating a duplicate environment variable that needs to be removed so that command is in this list.

###To run a sample MVC6 Web Page
1. Change to the source:  **cd /home/pi/aspnet5/home/samples/HelloMVC**
2. Remove that pesky variable:  **unset RUNLEVEL**
3. Go get the dependencies:  **kpm restore**
3. Start the web server:  **k kestrel**
4. Open your browser and navigate to http://localhost:5004
5. Voila!
