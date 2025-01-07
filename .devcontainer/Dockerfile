# Use a base image with Java installed
FROM mcr.microsoft.com/vscode/devcontainers/java:11

# Install Android SDK and other tools
RUN apt-get update && apt-get install -y \
    wget \
    unzip \
&& wget -q https://dl.google.com/android/repository/commandlinetools-linux-7583922_latest.zip -O cmdline-tools.zip \
&& mkdir -p /usr/local/android-sdk/cmdline-tools \
&& unzip -q cmdline-tools.zip -d /usr/local/android-sdk/cmdline-tools \
&& rm cmdline-tools.zip

# Set environment variables
ENV ANDROID_HOME=/usr/local/android-sdk
ENV PATH=$ANDROID_HOME/cmdline-tools/tools/bin:$PATH

# Accept licenses
RUN yes | sdkmanager --licenses

# Install essential packages
RUN sdkmanager "platform-tools" "platforms;android-30" "build-tools;30.0.3"
