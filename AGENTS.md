# Contributor Guide

This is the guide for the OpenAI Codex agent.

## General repository layout
- Source code: trunk/src/ contains the C++ code for the SRS server.
  - trunk/src/core and trunk/src/kernel contain the common definitions.
  - trunk/src/protocol contains the media streaming protocol implementations.
  - trunk/src/app contains the application-level implementations.
  - trunk/src/main contains the main entry points for the programs.
- Source code: proxy/ contains the proxy server in Go for RTMP/SRT/WebRTC proxying.
- Configuration:
  - trunk/conf/full.conf contains all supported configurations.
  - trunk/src/app/srs_app_config.cpp parses and checks the configuration file.
  - trunk/conf/*.conf contains other example configuration files.
- UTests: trunk/src/utest contains the unit tests using gtest.
- Third-party dependencies: trunk/3rdparty contains the dependency libraries. You may refer to these codes, but never attempt to change or update them.
  - trunk/3rdparty/st-srs is the coroutine library (state-threads).
  - trunk/3rdparty/srs-bench is the integration test tool for blackbox tests.
  - trunk/3rdparty/gtest-fit is the gtest framework used for unit tests.
  - trunk/3rdparty/ffmpeg-4-fit is the codec library for transcoding audio streams such as AAC with Opus.
  - trunk/3rdparty/openssl-1.1-fit is used for RTMP handshake and WebRTC DTLS handshake.
  - trunk/3rdparty/libsrtp-2-fit is used for SRTP in WebRTC.
  - trunk/3rdparty/srt-1-fit is the SRT implementation.
- Documentation:
  - README.md is a brief introduction to this project.
  - trunk/doc/CHANGELOG.md contains the changelog history.

## Testing Instructions
- Run CI tests defined in .github/workflows/test.yml file.
- Add or update tests for the code you change, even if nobody asked.
