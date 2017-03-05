FROM tensorflow/tensorflow:0.10.0
RUN apt-get update && apt-get install -y \
    build-essential \
    pkg-config \
    qt5-default \
    net-tools \
    iputils-ping \
    nano \
    python-dev \
    python-pip \
    python-pygame \
    python-pyaudio \
    git \
    && rm -rf /var/lib/apt/lists/*
    
WORKDIR /root
RUN git clone git://github.com/richardstechnotes/Manifold

WORKDIR /root/Manifold/ManifoldCore/ManifoldLib
RUN qmake
RUN make clean
RUN make -j8
RUN make install
RUN make clean

WORKDIR /root/Manifold/ManifoldCore/ManifoldPythonLib
RUN qmake
RUN make clean
RUN make -j8
RUN make install
RUN python setup.py build
RUN python setup.py install






