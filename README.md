# qubes-arch

An effort to make the [Qubes Core Stack](https://www.qubes-os.org/news/2017/10/03/core3/) available as a set of high quality packages for Arch Linux.

**This is extremely WIP and probably not ready for you to be reading this yet.**

## Goals

 * High quality Arch packages for all components of Qubes OS project.
 * Trivial path to converting an Arch install into a locked-down Qubes dom0.
 * Follow and participate in bleeding edge Qubes development.

## Packages

### xen-qubes

Adapted from the popular [xen package on AUR](https://aur.archlinux.org/packages/xen/), including the [Qubes patches](https://github.com/qubesos/qubes-vmm-xen).

TODO: currently unclear if the patches are entirely QoL / bugfixes, or if there's any feature enhancements here that Qubes components rely on.

### libvirt-qubes

This package conflicts with and replaces the Arch [community/libvirt](https://www.archlinux.org/packages/community/x86_64/libvirt/) package, adding additional patches from the [Qubes fork](https://github.com/qubesos/qubes-core-libvirt).

These patches add Qubes-specific additional fields to core libvirt structures. As such it's unclear how this fork could ever be pushed fully upstream.

### libvchan-xen

A wrapper around the [core Xen vchan library](https://www.cs.uic.edu/~xzhang/vchan/).

It's somewhat unclear why this even still needs to exist. Today, it appears to mostly just wrap around the upstream implementation that Xen adapted from the original implementation of this library. Perhaps it's intended to mostly be a shim until the other Qubes components have been updated to use the Xen vchan library?

### libvchan-socket

An alternative implementation to libvchan-xen that goes over sockets. Only seems to exist for test purposes.

