# CryptoHack Docker Container

A Jupyter notebook environment built for attacking crypto CTF challenges, with custom theming matching [CryptoHack](https://cryptohack.org).

![screenshot](screenshot.png)

It comes with the following installed and integrated:
 - Sage 9 (based on Python3)
 - Pwntools
 - PyCryptodome
 - z3 Prover

## Installation

### Build

```bash
cd cryptohack-docker
docker build . -t cryptohack
```

### Run
```bash
docker run -p 8888:8888 -v /home/vishwa/ctf-challenges:/home/sage/ctf-challenges -it cryptohack
```

### Run with VirtualBox Shared Folder
```bash
docker run -p 8888:8888 -v /media/sf_D_DRIVE:/home/sage/ctf-challenges --group-add 144 -it cryptohack
```

The `144` here is the gid of the `vboxsf` group on the host machine.

Then open 127.0.0.1:8888 in your browser.

## Notes

We map to 127.0.0.1 on the host rather than the default 0.0.0.0 as Jupyter token authentication was disabled for the sake of convenience.
