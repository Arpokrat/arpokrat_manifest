# ArpokratOS Core Manifest

This repository contains the root manifest for **ArpokratOS**, a Zero-Trust, privacy-hardened mobile operating system. It serves as the primary entry point for the Android `repo` tool.

## Architecture

ArpokratOS is built upon the robust security baseline of GrapheneOS and AOSP. Rather than maintaining a monolithic fork, this manifest utilizes an advanced **snippet override architecture**. 

It dynamically instructs the build system to:
1. Fetch the standard upstream baseline.
2. Sever specific default components (such as core frameworks, settings, and device kernels).
3. Seamlessly inject Arpokrat's proprietary, hardened implementations and vendor-specific hardware configurations (`vendor/arpokrat`).

## Getting Started

To initialize your local workspace and sync the complete ArpokratOS source tree, ensure you have the `repo` tool installed, then run the following commands:

```bash
# Initialize the workspace with the ArpokratOS manifest
repo init -u git@github.com:arpokrat/arpokrat_manifest.git -b main

# Sync the entire operating system source code (this may take a while)
repo sync -c -j8
