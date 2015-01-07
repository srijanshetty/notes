VM
--

## Hypervisor

- A hypervisor, also called a virtual-machine monitor, is the software that implements virtual machines.
- It is designed for the sole purpose of running de-privileged “guest” operating systems on top (except for the deceptive pseudo-virtualizers).
- As such it is (or contains) a kernel (defined as software running in the most privileged mode of the hardware).

## Microkernel

- A microkernel is a minimal base for building arbitrary systems (including virtual machines).
- It is characterised as containing the minimal amount of code that must run in the most privileged mode of the hardware in order to build arbitrary (yet secure) systems.

Virtual Filesystem
------------------

- They provide an abstraction between the concrete FS and the application.
- They specify an interface for the FS which can be used by applications without caring for the FS underneath.

## GVFS

- It is a VFS which supports OBEX, MTP and udev integration.
- OBEX is OBject EXchange protocol.
- MTP is Media Transfer procotol.

## Udev

- It looks after the loading and unloading of /dev and /dev related activities.

I/O
----

## Vectored I/O

- Also called scatter/gather.
- **Scatter:** Read from memory and divide it into multiple buffers atomically.
- **Gather:** Read from multiple buffers into memory atomically.

## Latency

- I/O takes a lot of time and this time is called latency.
- Owing to this asynchronous IO is preferred.
