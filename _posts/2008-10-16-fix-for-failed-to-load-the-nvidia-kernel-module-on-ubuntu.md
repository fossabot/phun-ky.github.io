--- 
layout: posttitle: "Fix for "Failed to load the NVIDIA kernel module" on Ubuntu"description: ""category: "undefined" tags: [] --- I struggled with my NVIDIA drivers after a kernel update, and no matter what I tried; I edited my xorg.conf, reinstalled drivers from source or with apt-get, nothing worked, until I found a great solution to this error (you can maybe fix this with similar errors):<br /><br/><br /><br/><pre class="brush: bash">"(EE) NVIDIA(0): Failed to load the NVIDIA kernel module!"</pre><br /><br/>So, the fix:<br /><br/><br /><br/>First, go here: <a href="http://www.nvidia.com/Download/index.aspx?lang=en-us">http://www.nvidia.com/Download/index.aspx?lang=en-us</a> to get the latest NVIDIA drivers. Install them as root after you've reset x (ctrl+alt+backspace). Then reboot.<br /><br/><br /><br/>Then remove the xorg.conf that the NVIDIA install created and start X with default options.<br /><br/><br /><br/>Edit /etc/modprobe.d/lrm-video with a text editor and put a # in front of the line containing something like<br /><br/><pre class="brush: bash">install nvidia /sbin/lrm-video nvidia $CMDLINE_OPTS</pre><br /><br/>There might be one or more lines like that, so it could look like this:<br /><br/><pre class="brush: bash">
# Make nvidia/nvidia_legacy and fglrx use /sbin/lrm-video to load<br/>install fglrx /sbin/lrm-video fglrx $CMDLINE_OPTS<br/>#install nvidia /sbin/lrm-video nvidia $CMDLINE_OPTS<br/>#install nvidia_legacy /sbin/lrm-video nvidia_legacy $CMDLINE_OPTS<br/>#install nvidia_new /sbin/lrm-video nvidia_new $CMDLINE_OPTS'
</pre><br/>Add the line:<br /><br/><pre class="brush: bash">nvidia</pre><br /><br/>to /etc/modules file. This file contains the list of kernel modules that should be always loaded when your machine boots. After you've done this, run:<br /><br/><pre class="brush: bash">sudo nvidia-xconfig</pre><br /><br/>to make a new xorg.conf and restart X. Good luck!