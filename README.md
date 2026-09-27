# Tongue Emulation for VRChat
![Release version](https://img.shields.io/github/v/release/Purpzie/tongue-emulation)
![No AI](https://img.shields.io/badge/No_AI-green.svg?logo=data:image/svg%2bxml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyNzYiIGhlaWdodD0iMjc2Ij48Y2lyY2xlIGN4PSIxMzgiIGN5PSIxMzgiIHI9IjEyMCIgZmlsbD0iIzAwMCIvPjxjaXJjbGUgY3g9IjEzOCIgY3k9IjEzOCIgcj0iMTI0IiBzdHJva2U9IiNCMzAwMDAiIHN0cm9rZS13aWR0aD0iMjgiIGZpbGw9Im5vbmUiLz48cmVjdCB4PSI4MCIgeT0iMTQiIHdpZHRoPSIzMiIgaGVpZ2h0PSIyNDIiIGZpbGw9IiNGRkYiIHRyYW5zZm9ybT0ic2tld1goLTkpIi8+PHJlY3QgeD0iOTIiIHk9IjE0IiB3aWR0aD0iMzIiIGhlaWdodD0iMjQyIiBmaWxsPSIjRkZGIiB0cmFuc2Zvcm09InNrZXdYKDkpIi8+PHJlY3QgeD0iNzgiIHk9IjE3MyIgd2lkdGg9IjUwIiBoZWlnaHQ9IjMyIiBmaWxsPSIjRkZGIi8+PHJlY3QgeD0iMTgwIiB5PSIxNSIgd2lkdGg9IjM2IiBoZWlnaHQ9IjIzMCIgZmlsbD0iI0ZGRiIvPjxjaXJjbGUgY3g9IjEzOCIgY3k9IjEzOCIgcj0iMTI0IiBzdHJva2U9IiNCMzAwMDAiIHN0cm9rZS13aWR0aD0iMjgiIGZpbGw9Im5vbmUiIHN0cm9rZS1kYXNoYXJyYXk9IjM5MCIvPjxsaW5lIHgxPSI0NSIgeTE9IjQ1IiB4Mj0iMjMxIiB5Mj0iMjMxIiBzdHJva2U9IiNCMzAwMDAiIHN0cm9rZS13aWR0aD0iMjIiLz48L3N2Zz4=)

Notably, the Quest Pro lacks directional tongue tracking.
This tiny program listens to VRChat's OSC and moves your tongue around using other parts of your face.

Left and right are controlled by your jaw.
Up is controlled by lip pucker, and down is controlled by jaw open.

## Avatar support
Currently, this only works for avatars with these parameters (such as [Jerry's Template](https://github.com/Adjerry91/VRCFaceTracking-Templates)):
- `FT/v2/TongueX` (float)
- `FT/v2/TongueX1` (bool)
- `FT/v2/TongueX2` (bool)
- `FT/v2/TongueX4` (bool)
- `FT/v2/TongueXNegative` (bool)
- `FT/v2/TongueY` (float)
- `FT/v2/TongueY1` (bool)
- `FT/v2/TongueY2` (bool)
- `FT/v2/TongueY4` (bool)
- `FT/v2/TongueYNegative` (bool)

The latest version of [Pawlygon's Template](https://github.com/PawlygonStudio/VRC-Facetracking) works, but you'll need to [edit the avatar's OSC config](https://docs.vrchat.com/docs/osc-avatar-parameters#avatar-parameters--config-files) to remap parameters to the names above.

## Optional Puppet
Avatars can override emulation with a two axis puppet.
- Parameter: `TongueEmulation/PuppetActive` (bool)
- Horizontal: `TongueEmulation/PuppetX` (float)
- Vertical: `TongueEmulation/PuppetY` (float)

Don't mark them as synced!

## Configuration
VRChat's OSC sockets are used by default.
You can change them by passing these arguments:

```
tongue-emulation.exe [listening socket] [sending socket]
```
Example with defaults:
```
tongue-emulation.exe 127.0.0.1:9001 127.0.0.1:9000
```
