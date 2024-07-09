FROM althack/ros2:humble-dev 


ENV DEBIAN_FRONTEND=noninteractive
RUN apt-get update \
        && apt-get install -y --no-install-recommends unzip ccache cppcheck \
        && wget https://github.com/clangd/clangd/releases/download/18.1.3/clangd-linux-18.1.3.zip \
        && unzip clangd-linux-18.1.3.zip \
        && mv clangd_18.1.3/bin/clangd /usr/bin/clangd \
        && mv clangd_18.1.3/lib/clang/* /usr/lib/clang \
        && ldconfig \
        && rm -rf clangd-linux-18.1.3.zip clangd_18.1.3 \
        && pip install cmakelang \
        && wget "https://github.com/aminya/setup-cpp/releases/download/v0.37.0/setup-cpp-x64-linux"\
        && chmod +x setup-cpp-x64-linux \
        && ./setup-cpp-x64-linux --clangtidy true --clangformat true \
        && rm setup-cpp-x64-linux \
        && apt-get autoremove -y \
        && apt-get clean -y \
        && rm -rf /var/lib/apt/lists/*
ENV DEBIAN_FRONTEND=dialog

# Set up auto-source of workspace for ros user
ARG WORKSPACE
RUN echo "if [ -f ${WORKSPACE}/install/setup.bash ]; then source ${WORKSPACE}/install/setup.bash; fi" >> /home/ros/.bashrc
