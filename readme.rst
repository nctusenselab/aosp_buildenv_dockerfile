Usage
-----
::

    # download
    git clone https://github.com/u1240976/aosp_buildenv_dockerfile
    cd aosp_buildenv_dockerfile/

    # create build environment, wait for installation.
    docker build -t="android-x86-kitkat-test1" . # -t="<IMAGE_NAME>"

    # start docker container of build env, mount the host's current directory(pwd) into container's /root/android/ (Docker Volume)
    # note: At the time we need to build AOSP, use android source directory instead of current directory(pwd), 
    # then docker container can build android source on the docker host (outside container).
    docker run -ti -v=`pwd`:/root/android/ android-x86-kitkat-test1 bash
