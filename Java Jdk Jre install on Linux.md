***RUN COMMAND WITH ROOT PERMISSION [SUDO, ROOT]***
1. If you have no local tar.gz java binary file, download from internet
`wget [download url]`
2. Make dir
`mkdir /opt/[<jdk> or <jre>]`
3. Uncompress
`tar -zxf [path to binary file]`
`tar -C [dir in step 2] -zxf [path to binary file]`
4. Set enviroment path (!!!! NOTE, jre has no javac in .../bin)
`update-alternatives --install /usr/bin/[<java> or <javac>] [<java> or <javac>] [path to java binary in step 2]/bin/java 100`
5. Check 
`update-alternatives --display [<java> or <javac>]`
6. Check version
`[<java> or <javac>] -version`
