FROM ubuntu

ENV CURRET_EMSDK_VERSION=1.38.25
ENV EMSDK=/opt/emsdk
ENV EM_CONFIG=/root/.emscripten
ENV LLVM_ROOT=/opt/emsdk/clang/e${CURRET_EMSDK_VERSION}_64bit
ENV EMSCRIPTEN_NATIVE_OPTIMIZER=/opt/emsdk/clang/e${CURRET_EMSDK_VERSION}_64bit/optimizer
ENV BINARYEN_ROOT=/opt/emsdk/clang/e${CURRET_EMSDK_VERSION}_64bit/binaryen
ENV EMSDK_NODE=/opt/emsdk/node/8.9.1_64bit/bin/node
ENV EMSCRIPTEN=/opt/emsdk/emscripten/$CURRET_EMSDK_VERSION
ENV JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64
ENV PATH=/opt/emsdk:/opt/emsdk/clang/e${CURRET_EMSDK_VERSION}_64bit:/opt/emsdk/node/8.9.1_64bit/bin:/opt/emsdk/emscripten/$CURRET_EMSDK_VERSION:$JAVA_HOME/bin:$PATH

RUN apt-get update
RUN apt-get install -y git
RUN apt-get install -y openjdk-8-jdk
RUN git clone https://github.com/emscripten-core/emsdk.git /opt/emsdk
RUN apt-get install -y python
WORKDIR /opt/emsdk
RUN ./emsdk install sdk-${CURRET_EMSDK_VERSION}-64bit
RUN ./emsdk activate sdk-${CURRET_EMSDK_VERSION}-64bit

RUN mkdir /opt/examples
COPY helloworld.cpp /opt/examples
WORKDIR /opt/examples
RUN emcc ./helloworld.cpp
RUN node a.out.js
