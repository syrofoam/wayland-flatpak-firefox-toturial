## Enable hardware decoding in wayland flatpak firefox

- [Prequsites](#Prequsites)
- [flatseal](#flatseal)
- [Libva](#libva)
- [vainfo](#vainfo)
- [firefox](#firefox)
- [add firefox addon h264fy](#h264fy)
- [warning](#warning)
- [monitoring](#monitoring)


## Prequsites

Flatpak installed to you favorite distrobution.

- Flatpak [flatpak]([https://flatpak.org/)

- Flatseal [Flatseal](https://flathub.org/apps/com.github.tchx84.Flatseal)

- libva package from you favorite linux. va-utils nixos and arch.

- programs to monitor cpu/gpu/apu.
## flatseal

![flatseal setting](/test.png)
Remove X11 as the default api so wayland is first and fallback is still X11.

## Libva
Can be added to your distro with:

*nix-shell -p va-uitils*

*pacman -S va-utils*.

## vainfo

stian@phobos ~ $`vainfo`

```text
ibva info: VA-API version 1.20.0
libva info: Trying to open /run/opengl-driver/lib/dri/radeonsi_drv_video.so
libva info: Found init function __vaDriverInit_1_20
libva info: va_openDriver() returns 0
vainfo: VA-API version: 1.20 (libva 2.20.0)
vainfo: Driver version: Mesa Gallium driver 23.1.9 for AMD Radeon Graphics (renoir, LLVM 16.0.6, DRM 3.54, 6.6.13-xanmod1)
vainfo: Supported profile and entrypoints
      VAProfileMPEG2Simple            : VAEntrypointVLD
      VAProfileMPEG2Main              : VAEntrypointVLD
      VAProfileVC1Simple              : VAEntrypointVLD
      VAProfileVC1Main                : VAEntrypointVLD
      VAProfileVC1Advanced            : VAEntrypointVLD
      VAProfileH264ConstrainedBaseline: VAEntrypointVLD
      VAProfileH264ConstrainedBaseline: VAEntrypointEncSlice
      VAProfileH264Main               : VAEntrypointVLD
      VAProfileH264Main               : VAEntrypointEncSlice
      VAProfileH264High               : VAEntrypointVLD
      VAProfileH264High               : VAEntrypointEncSlice
      VAProfileHEVCMain               : VAEntrypointVLD
      VAProfileHEVCMain               : VAEntrypointEncSlice
      VAProfileHEVCMain10             : VAEntrypointVLD
      VAProfileHEVCMain10             : VAEntrypointEncSlice
      VAProfileJPEGBaseline           : VAEntrypointVLD
      VAProfileVP9Profile0            : VAEntrypointVLD
      VAProfileVP9Profile2            : VAEntrypointVLD
      VAProfileNone                   : VAEntrypointVideoProc
```

What we get information about is the differenct supported hardware codecs in the apu.

## firefox

Go into the adressbar and type about:configurion
Then you want to set ***media.ffmpeg.vaapi.enabled** bolean to *True*

## h265fy
The firefox addon h265fy turns AV1 video on youtube into h265, new chip should support it tho.

## warning

**Doing this COULD crash your web browser**

*But could also result in lower tempratures and better perf*

## monitoring
to check gpu I used ***amdgpu_top***
and for cpu I used ***btop***
![amdgpu_top](/amdgpu_top.png)

Enjoy :metal: