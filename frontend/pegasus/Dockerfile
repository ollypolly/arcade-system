FROM ubuntu:22.04

# Set environment variable to avoid interactive prompts during build
ENV DEBIAN_FRONTEND=noninteractive

# Install dependencies for building Pegasus inside the container
RUN apt update && apt install -y \
    git cmake qt5-qmake qtbase5-dev qtchooser qt5-qmake-bin \
    libsdl2-dev libboost-all-dev libglib2.0-dev \
    xorg openbox libgl1-mesa-glx \
    && rm -rf /var/lib/apt/lists/*

# Set up working directory
WORKDIR /app

# Clone the Pegasus frontend repository
RUN git clone --recursive https://github.com/mmatyas/pegasus-frontend.git /app/pegasus

# Build Pegasus frontend
WORKDIR /app/pegasus
RUN cmake -DCMAKE_BUILD_TYPE=Release . && make -j$(nproc)

# Copy run script
COPY run.sh /app/run.sh
RUN chmod +x /app/run.sh

# Run Pegasus frontend on container start
CMD ["/app/run.sh"]
