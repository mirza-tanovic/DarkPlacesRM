filegroup(
    name = "vecxis-sdl2-sources",
    srcs = [
        "builddate.c",
        "sys_sdl.c",
        "vid_sdl.c",
        "thread_sdl.c",
        "snd_main.c",
        "snd_mem.c",
        "snd_mix.c",
        "snd_ogg.c",
        "snd_wav.c",
        "snd_modplug.c",
        "snd_sdl.c",
        "cd_sdl.c",
        "cd_shared.c",
        "cl_input.c",
        "cl_main.c",
        "gl_backend.c",
        "gl_rmain.c",
        "gl_textures.c",
        "crypto.c",
        "cgf_read.c",
        "host.c",
        "irc.c",
        "mathlib.c",
        "r_shadow.c",
        "sbar.c",
        "image.c",
        "sv_main.c",
        "vid_shared.c",
        "world.c",
        "keys.c",
        "bih.c",
        "cap_avi.c",
        "cap_ogg.c",
        "cl_collision.c",
        "cl_demo.c",
        "cl_dyntexture.c",
        "cl_parse.c",
        "cl_particles.c",
        "cl_screen.c",
        "cl_video.c",
        "clvm_cmds.c",
        "cmd.c",
        "collision.c",
        "common.c",
        "console.c",
        "csprogs.c",
        "curves.c",
        "cvar.c",
        "dpsoftrast.c",
        "dpvsimpledecode.c",
        "filematch.c",
        "fractalnoise.c",
        "fs.c",
        "ft2.c",
        "utf8lib.c",
        "gl_draw.c",
        "gl_rsurf.c",
        "hmac.c",
        "host_cmd.c",
        "image_png.c",
        "jpeg.c",
        "lhnet.c",
        "libcurl.c",
        "matrixlib.c",
        "mdfour.c",
        "menu.c",
        "meshqueue.c",
        "mod_skeletal_animatevertices_sse.c",
        "mod_skeletal_animatevertices_generic.c",
        "model_alias.c",
        "model_brush.c",
        "model_shared.c",
        "model_sprite.c",
        "mvm_cmds.c",
        "netconn.c",
        "palette.c",
        "polygon.c",
        "portals.c",
        "protocol.c",
        "prvm_cmds.c",
        "prvm_edict.c",
        "prvm_exec.c",
        "random.c",
        "r_explosion.c",
        "r_lerpanim.c",
        "r_lightning.c",
        "r_modules.c",
        "r_sky.c",
        "r_sprites.c",
        "sha256.c",
        "siphash.c",
        "stats.c",
        "sv_demo.c",
        "sv_move.c",
        "sv_phys.c",
        "sv_user.c",
        "svbsp.c",
        "svvm_cmds.c",
        "sys_shared.c",
        "timedemo.c",
        "view.c",
        "wad.c",
        "zone.c",
    ],
)

#let's build the sdl2 client
#IMPORTANT: this is not a fully reproducible build as we're linking against
#           distro-specific versions of libraries such as SDL2.
cc_binary(
    name="vecxis-sdl2",
    deps=["@sqlite//:sqlite"],
    srcs=[":vecxis-sdl2-sources"],
    copts=["-I/usr/include/", "-I/usr/include/SDL2/", "-DSVREVISION=v0.4.2-36-g4867018", "-UCRYPTO_STATIC",
    "-UCRYPTO_RIJNDAEL_STATIC"],
    linkopts=["-lm", "-lSDL2", "-pthread", "-lrt", "-ldl", "-lX11", "-lmodplug"],
    linkstatic=1,
    includes=["."],
    defines=["VECXIS_RELEASE", "USERDIRMODE_PREFERED=USERDIRMODE_SAVEDGAMES", "BUILDTYPE=release",
    "JPEG_LIB_VERSION=62", "SDL_INPUT_LINUXEV", "SND_MODPLUG_STATIC"],
    hdrs_check="warn",
    stamp=1,
)
