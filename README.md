# COLLECTION-mouserat-activity

[![GitHub release](https://img.shields.io/github/release/mcci-catena/COLLECTION-mouserat-activity.svg)](https://github.com/mcci-catena/COLLECTION-mouserat-activity/releases/latest) [![GitHub commits](https://img.shields.io/github/commits-since/mcci-catena/COLLECTION-mouserat-activity/latest.svg)](https://github.com/mcci-catena/COLLECTION-mouserat-activity/compare/v0.5.2...master)

Collection of repos as build environment for Catena 4430 for WUSTL / Lex Kravitz' RAD2 (Rodent Activity Detector, V2).

This corresponds to MCCI document 234001363.

[![Picture of Model 4430 Complete!](assets/catena4430-black-case.jpg)](https://store.mcci.com/products/mcci-catena-4430-activity-sensor-wing)

This repo is intended to be built on Linux (Ubuntu 18 or later). The build script might work with Ubuntu for Windows, but has not been tested.

To build:

1. Clone this repository:

    ```bash
    git clone --recursive COLLECTION-mouserat-activity
    ```

2. If building with a project secure key, get a copy of that key and put it someplace handy; please make sure it's password protected, at least.

3. Build with the following commands:

    - to build with the test-signing key:

      ```bash
      ./build-with-cli --test
      ```

    - to build with a project-specific key:

      ```bash
      ./build-with-cli --key={path-to-file}.pem
      ```

    - to build for 2 MHz clock and hardware serial, for Europe, with the test-signing key:

      ```bash
      ./build-with-cli.sh --clock=2 --serial=hw --region=eu868 --test
      ```

    - to build for multiple regions and multiple networks:

      ```bash
      ./build-with-cli.sh --test --verbose && ./build-with-cli.sh --test --verbose --region=au915 --network=ttn && ./build-with-cli.sh --test --verbose --region=eu868 --network=ttn
      ```

   The output shows up in `build/ide`.
