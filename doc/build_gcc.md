# steps in building GCC from its rpm source package:

+ download a rpm source package of GCC from web, such as:

  _http://vault.centos.org/centos/$releasever/os/Source/_

  where $releasever is the corresponding version of your CentOS,
  which can be found by using:

  `cat /etc/redhat_release`

  such as 7.5.1804

+ install the rpm source package, such as: 

  `rpm -i gcc-4.8.5-28.el7.src.rpm`

  this would create a rpmbuild directory under your home directory: 

  `~/rpmbuild`

  within the rpmbuild directory, there are several dirs, such as:

  `BUILD  BUILDROOT  RPMS  SOURCES  SPECS  SRPMS`

+ within "~/rpmbuild/SPECS", you can find "gcc.spec", 
  extract the source files by:

  `cd ~/rpmbuild/SPECS`
  `rpmbuild -bp --nodeps gcc.spec`

  that would put all extracted files under "~/rpmbuild/BUILD",
  such as "~/rpmbuild/BUILD/gcc-4.8.5-20150702"

+ we want to build GCC under other directory other than the source 
  tree to prevent any generated files polluting the source tree.
  so we make another directory, such as:

  `mkdir /data1/workspace/rpm_pkg_build/gcc-4.8.5-20150702/BUILD`

  we also want the built GCC to be within a personal directory to
  prevent it overlapping with the current GCC that used to do
  the build job. so we make another directory for the built GCC
  to install to, such as:

  `mkdir /data1/workspace/rpm_pkg_build/gcc-4.8.5-20150702/INSTALL`

+ intall the required package: GMP 4.2+
  GMP is Gnu mp, that is a package for arbitrary precision number
  calculation with high performance and tiny code size.


   
