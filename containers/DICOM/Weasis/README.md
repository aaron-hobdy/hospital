# WEASIS MEDICAL VIEWER
Weasis is a multipurpose standalone and web-based DICOM viewer. 
It is a very popular clinical viewer used in hospitals and health networks.

# NOTES
1. Build:
   - ```sudo docker build -t weasis .```

1. Weasis is a Java based GUI application and requires a display.
   - Run ```xhost+``` on the docker host.

1. Run:
   - ```sudo docker run -v /tmp/.X11-unix:/tmp/.X11-unix -e DISPLAY=$DISPLAY -h $HOSTNAME -v $HOME/.Xauthority:/home/simspace/.Xauthority weasis```

1. Click accept on the popup and import images from /images.


