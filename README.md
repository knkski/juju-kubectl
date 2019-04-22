juju-kubectl
============

[![Snap Status](https://build.snapcraft.io/badge/knkski/juju-kubectl.svg)](https://build.snapcraft.io/user/knkski/juju-kubectl)

This repository hosts a Juju plugin that makes it easy to run `kubectl` against
whatever Kubernetes models you have spun up.


Setup
-----

You can install this plugin with `snap`:

    sudo snap install juju-kubectl --classic --edge

Or if you want to run this plugin from source, clone this repo with

    https://github.com/knkski/juju-kubectl.git
    cd juju-kubectl

You will also need to install the Rust compiler. Instructions can be found at
https://rustup.rs/.


Usage
-----

You can run this plugin and just pass in the appropriate `kubectl`
arguments:

    # Installed via snap
    juju kubectl get nodes

    # Running from source
    cargo run --bin juju-kubectl get nodes

Note that both `cargo` and this plugin can take arguments, so to pass
options or parameters to `kubectl` itself, you will want to call it
like so:

    # Installed via snap
    juju kubectl -c controller-name -- get nodes

    # Running from source
    cargo run --bin juju-kubectl -- -c controller-name -- get nodes
