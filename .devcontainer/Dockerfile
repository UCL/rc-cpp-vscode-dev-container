FROM mcr.microsoft.com/devcontainers/cpp:0-ubuntu-20.04

# ARG REINSTALL_CMAKE_VERSION_FROM_SOURCE="3.25.1"
#
# COPY ./reinstall-cmake.sh /tmp/

# RUN if [ "${REINSTALL_CMAKE_VERSION_FROM_SOURCE}" != "none" ]; then \
#         chmod +x /tmp/reinstall-cmake.sh && /tmp/reinstall-cmake.sh ${REINSTALL_CMAKE_VERSION_FROM_SOURCE}; \
#         fi \
#         && rm -f /tmp/reinstall-cmake.sh

RUN apt-get update \
        && export DEBIAN_FRONTEND=noninteractive \
        && apt-get -y install --no-install-recommends clang-format openmpi-bin libopenmpi-dev \
        && apt-get autoremove -y \
        && apt-get clean -y \
        && rm -rf /var/lib/apt/lists/*
