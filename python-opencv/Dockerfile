FROM python-scikit-learn

RUN apt-get update && apt-get install -y  libjpeg62-turbo-dev libtiff5-dev libjasper-dev \
                        libpng12-dev libavcodec-dev libavformat-dev \
                        libswscale-dev libv4l-dev libgtk2.0-dev 
                        
RUN apt-get update && apt-get install -y cmake wget \
    && wget -O opencv-3.1.0.tar.gz https://codeload.github.com/Itseez/opencv/tar.gz/3.1.0 \
    && wget -O opencv_contrib-3.1.0.tar.gz https://codeload.github.com/Itseez/opencv_contrib/tar.gz/3.1.0 \
    && tar -xzf opencv-3.1.0.tar.gz \
    && tar -xzf opencv_contrib-3.1.0.tar.gz \
    && cd opencv-3.1.0 && mkdir build && cd build \
    && cmake -D CMAKE_BUILD_TYPE=RELEASE \
        -D CMAKE_INSTALL_PREFIX=/usr/local \
        -D INSTALL_C_EXAMPLES=OFF \
        -D INSTALL_C_EXAMPLES=OFF \
        -D INSTALL_PYTHON_EXAMPLES=ON \
        -D WITH_IPP=OFF \
        -D OPENCV_EXTRA_MODULES_PATH=/opencv_contrib-3.1.0/modules \
        -D BUILD_EXAMPLES=ON .. \
    && make && make install && ldconfig \
    && rm -Rf /opencv-3.1.0 && rm -Rf /opencv-3.1.0.tar.gz && rm -Rf /opencv_contrib-3.1.0 && rm -Rf /opencv_contrib-3.1.0.tar.gz \
    && apt-get remove --purge  -y cmake \
    && apt-get autoremove -y \
    && apt-get clean && rm -rf /var/lib/apt/lists/*

