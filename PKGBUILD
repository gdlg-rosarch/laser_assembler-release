# Script generated with Bloom
pkgdesc="ROS - Provides nodes to assemble point clouds from either LaserScan or PointCloud messages"
url='http://ros.org/wiki/laser_assembler'

pkgname='ros-lunar-laser-assembler'
pkgver='1.7.4_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('ros-lunar-catkin>=0.5.68'
'ros-lunar-filters'
'ros-lunar-laser-geometry'
'ros-lunar-message-filters'
'ros-lunar-message-generation'
'ros-lunar-pluginlib'
'ros-lunar-roscpp'
'ros-lunar-rostest'
'ros-lunar-sensor-msgs'
'ros-lunar-tf'
)

depends=('ros-lunar-filters'
'ros-lunar-laser-geometry'
'ros-lunar-message-filters'
'ros-lunar-message-runtime'
'ros-lunar-pluginlib'
'ros-lunar-roscpp'
'ros-lunar-sensor-msgs'
'ros-lunar-tf'
)

conflicts=()
replaces=()

_dir=laser_assembler
source=()
md5sums=()

prepare() {
    cp -R $startdir/laser_assembler $srcdir/laser_assembler
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

