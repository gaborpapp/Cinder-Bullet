Cinder-Bullet
-------------

####Static library build instructions on OSX

<pre>
tar zxvf bullet-2.81-rev2613.tgz
cd bullet-2.81-rev2613
patch < btConeShapeSerialization.diff
mkdir cmake
cd cmake
cmake -D"CMAKE_OSX_ARCHITECTURES=i386;x86_64" \
	-DBUILD_EXTRAS=ON \
	-DCMAKE_INSTALL_PREFIX=`pwd` \
	-DINCLUDE_INSTALL_DIR=install/include \
	-DPKGCONFIG_INSTALL_PREFIX=install/pkgconfig \
	-DLIB_DESTINATION=install/lib -DINSTALL_EXTRA_LIBS=ON ..
make
make install
</pre>

Copy the libs from build/lib to Cinder-Bullet/lib/macosx. Copy the contents of
build/install/include to Cinder-Bullet/include.

