
#Using wayland and flatpak version of firefox.

***vainfo is part of va-utils.

stian@phobos ~ $`vainfo`

'''Trying display: wayland
>libva info: VA-API version 1.20.0
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

Gpu in question: AMD Ryzen 9 5900HX with Radeon Graphics
There is also a 6800 in the same pc.

There is H264 codec, hvec, vpn9, etc. Fairly new cpu your milage will wary.

So for utube they use AV1 and only the newest kind of gpu might have acceleration, use addon for firefox.

Before cpu was hot watching video, now not that moutch. Also usage in amd_gputop, after selecting the apu not dedicated gpu.

Use flatseal (a permission program for 'flapaks') to make firefox default to wayland protocol by //deselecting the X11 and just having it as 'fallback' when if wayland crashes.

Use about:config in firefox and tell firefox to use 'media.ffmpeg.vaapi.enabled'
restart browser and then good to go.
