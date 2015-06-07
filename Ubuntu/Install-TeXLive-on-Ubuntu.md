1. Mount the ISO image with Disk Image Mounter

2. Run installation script as root user

   Type ```i``` when asked during installation
   ```sh
   sudo -i
   cd /media/the_user/TeXLive2014
   ./install-tl
   ```

3. Installation may continues for minutes.

4. Post-installation

   - Set up paths (1)

     ```sh
     sudo gedit /etc/bash.bashrc
     ```

   - Append the following commands to it

     ```sh
     # Texlive 2014
     PATH=/usr/local/texlive/2014/bin/x86_64-linux:$PATH; export PATH
     MANPATH=/usr/local/texlive/2014/texmf/doc/man:$MANPATH; export MANPATH
     INFOPATH=/usr/local/texlive/2014/texmf/doc/info:$INFOPATH; export INFOPATH
     ```

   - Seupt paths (2)

     ```sh
     sudo gedit /etc/manpath.config
     ```

   - Append the following commands to it

     ```sh
     # Texlive 2014
     MANPATH_MAP /usr/local/texlive/2014/bin/x86_64-linux /usr/local/texlive/2014/texmf/doc/man
     ```

   You have to relaunch new terminals to run LaTeX commands.

5. Set the paper size to ```letter```

     ```sh
     sudo -i               # You must login as root user for paper setting
     tlmgr paper letter
     ```

6. Test your installation

     ```sh
     latex small2e
     ```

7. If you cannot import EPS files

     ```sh
     sudo apt-get install texlive-font-utils
     ```
