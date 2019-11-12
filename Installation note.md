-OS : Ubutu 18.03

# Using darcs command line
## Installation
- sudo apt-get install darcs flex make
- darcs get --lazy http://basilisk.fr/basilisk
- cd basilisk
- darcs pull

## Compliation
- cd basilisk/src
- **export BASILISK=$PWD**
- **export PATH=$PATH:$PWD**
- ln -s config.gcc config
- make -k
- make
### Config settting 
> To avoid having to re-type the two export commands above everytime you login, 
you should also add them to your $HOME/.bashrc file. You can either edit $HOME/.bashrc manually or do

- cd basilisk/src
- echo "export BASILISK=$PWD" >> ~/.bashrc
- echo "export PATH=\$PATH:$BASILISK" >> ~/.bashrc

# Visualisation Packages config
- sudo apt-get install gnuplot imagemagick **ffmpeg** (but not libav-tools) smpeg-plaympeg graphviz valgrind gifsicle pstoedit
- **sudo apt-get install libglu1-mesa-dev libosmesa6-dev**
- cd $BASILISK/gl
- **make libglutils.a libfb_osmesa.a** 
> The command line in **Blod** should be compatible with the setting in src/config, the following setting should be verified 
in config: 
> - **OPENGLIBS = -lfb_osmesa -lGLU -lOSMesa**
> - **#OPENGLIBS = -lfb_glx -lGLU -lGLEW -lGL -lX11**
- make
- cd ..
- make bview-servers
