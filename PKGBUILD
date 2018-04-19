# Script generated with Bloom
pkgdesc="ROS - Messages relating to the ROS Computation Graph. These are generally considered to be low-level messages that end users do not interact with."
url='http://ros.org/wiki/rosgraph_msgs'

pkgname='ros-lunar-rosgraph-msgs'
pkgver='1.11.2_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('ros-lunar-catkin'
'ros-lunar-message-generation'
'ros-lunar-std-msgs'
)

depends=('ros-lunar-message-runtime'
'ros-lunar-std-msgs'
)

conflicts=()
replaces=()

_dir=rosgraph_msgs
source=()
md5sums=()

prepare() {
    cp -R $startdir/rosgraph_msgs $srcdir/rosgraph_msgs
}

build() {
  # Use ROS environment variables
  source /usr/share/ros-build-tools/clear-ros-env.sh
  [ -f /opt/ros/lunar/setup.bash ] && source /opt/ros/lunar/setup.bash

  # Create build directory
  [ -d ${srcdir}/build ] || mkdir ${srcdir}/build
  cd ${srcdir}/build

  # Fix Python2/Python3 conflicts
  /usr/share/ros-build-tools/fix-python-scripts.sh -v 2 ${srcdir}/${_dir}

  # Build project
  cmake ${srcdir}/${_dir} \
        -DCMAKE_BUILD_TYPE=Release \
        -DCATKIN_BUILD_BINARY_PACKAGE=ON \
        -DCMAKE_INSTALL_PREFIX=/opt/ros/lunar \
        -DPYTHON_EXECUTABLE=/usr/bin/python2 \
        -DPYTHON_INCLUDE_DIR=/usr/include/python2.7 \
        -DPYTHON_LIBRARY=/usr/lib/libpython2.7.so \
        -DPYTHON_BASENAME=-python2.7 \
        -DSETUPTOOLS_DEB_LAYOUT=OFF
  make
}

package() {
  cd "${srcdir}/build"
  make DESTDIR="${pkgdir}/" install
}

