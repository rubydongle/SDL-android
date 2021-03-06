set( LIB_NAME libfceux)

add_definitions( -Wall  -Wno-write-strings  -Wno-sign-compare  -Wno-parentheses  -Wno-unused-local-typedefs  -fPIC )
set( SYS_LIBS  -lrt  -lpthread )

include_directories( ${CMAKE_SOURCE_DIR}/src )
include_directories( ${CMAKE_SOURCE_DIR}/src/drivers )

add_definitions( -DPSS_STYLE=1 )

set(SRC_CORE
	${CMAKE_CURRENT_SOURCE_DIR}/asm.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/cart.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/cheat.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/conddebug.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/config.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/debug.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/drawing.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/fceu.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/fds.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/file.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/emufile.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/filter.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/ines.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/input.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/movie.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/netplay.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/nsf.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/oldmovie.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/palette.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/ppu.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/sound.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/state.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/unif.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/video.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/vsuni.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/wave.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/x6502.cpp
#	${LUA_ENGINE_SOURCE}
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/01-222.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/09-034a.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/103.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/106.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/108.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/112.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/116.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/117.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/120.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/121.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/12in1.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/151.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/156.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/158B.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/15.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/164.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/168.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/170.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/175.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/176.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/177.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/178.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/183.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/185.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/186.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/187.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/189.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/18.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/190.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/193.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/199.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/206.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/208.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/222.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/225.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/228.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/230.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/232.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/234.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/235.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/244.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/246.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/252.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/253.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/28.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/32.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/33.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/34.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/36.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/3d-block.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/40.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/411120-c.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/41.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/42.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/43.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/46.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/50.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/51.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/57.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/603-5052.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/62.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/65.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/67.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/68.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/69.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/71.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/72.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/77.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/79.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/80013-B.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/80.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/8157.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/8237.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/82.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/830118C.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/88.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/8in1.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/90.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/91.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/96.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/99.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/a9746.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/ac-08.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/addrlatch.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/ax5705.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/bandai.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/bb.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/bmc13in1jy110.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/bmc42in1r.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/bmc64in1nr.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/bmc70in1.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/BMW8544.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/bonza.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/bs-5.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/cheapocabra.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/cityfighter.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/coolboy.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/dance2000.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/datalatch.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/dream.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/__dummy_mapper.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/edu2000.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/eh8813a.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/emu2413.c
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/et-100.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/et-4320.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/F-15.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/famicombox.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/ffe.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/fk23c.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/fns.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/ghostbusters63in1.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/gs-2004.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/gs-2013.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/h2288.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/hp10xx_hp20xx.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/hp898f.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/inlnsf.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/karaoke.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/kof97.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/ks7010.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/ks7012.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/ks7013.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/ks7016.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/ks7017.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/ks7030.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/ks7031.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/ks7032.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/ks7037.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/ks7057.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/le05.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/lh32.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/lh53.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/malee.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/mihunche.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/mmc1.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/mmc2and4.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/mmc3.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/mmc5.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/n106.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/n625092.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/novel.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/onebus.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/pec-586.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/rt-01.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/sa-9602b.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/sachen.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/sb-2000.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/sc-127.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/sheroes.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/sl1632.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/subor.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/super24.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/supervision.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/t-227-1.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/t-262.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/tengen.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/tf-1201.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/transformer.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/unrom512.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/vrc1.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/vrc2and4.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/vrc3.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/vrc5.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/vrc6.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/vrc7.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/vrc7p.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/boards/yoko.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/input/arkanoid.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/input/bworld.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/input/cursor.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/input/fkb.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/input/fns.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/input/ftrainer.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/input/hypershot.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/input/mahjong.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/input/mouse.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/input/oekakids.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/input/pec586kb.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/input/powerpad.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/input/quiz.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/input/shadow.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/input/snesmouse.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/input/suborkb.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/input/toprider.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/input/virtualboy.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/input/zapper.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/utils/backward.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/utils/ConvertUTF.c
  	${CMAKE_CURRENT_SOURCE_DIR}/utils/xstring.cpp
  	${CMAKE_CURRENT_SOURCE_DIR}/utils/crc32.cpp     
  	${CMAKE_CURRENT_SOURCE_DIR}/utils/endian.cpp  
  	${CMAKE_CURRENT_SOURCE_DIR}/utils/general.cpp  
  	${CMAKE_CURRENT_SOURCE_DIR}/utils/guid.cpp    
  	${CMAKE_CURRENT_SOURCE_DIR}/utils/md5.cpp  
  	${CMAKE_CURRENT_SOURCE_DIR}/utils/memory.cpp
)

add_library( ${LIB_NAME} SHARED ${SRC_CORE})

set(SRC_DRIVERS_COMMON
  ${CMAKE_CURRENT_SOURCE_DIR}/drivers/common/args.cpp
  ${CMAKE_CURRENT_SOURCE_DIR}/drivers/common/cheat.cpp
  ${CMAKE_CURRENT_SOURCE_DIR}/drivers/common/config.cpp
  ${CMAKE_CURRENT_SOURCE_DIR}/drivers/common/configSys.cpp
  ${CMAKE_CURRENT_SOURCE_DIR}/drivers/common/hq2x.cpp
  ${CMAKE_CURRENT_SOURCE_DIR}/drivers/common/hq3x.cpp
  ${CMAKE_CURRENT_SOURCE_DIR}/drivers/common/scale2x.cpp
  ${CMAKE_CURRENT_SOURCE_DIR}/drivers/common/scale3x.cpp
  ${CMAKE_CURRENT_SOURCE_DIR}/drivers/common/scalebit.cpp
  ${CMAKE_CURRENT_SOURCE_DIR}/drivers/common/vidblit.cpp
  ${CMAKE_CURRENT_SOURCE_DIR}/drivers/common/os_utils.cpp
  ${CMAKE_CURRENT_SOURCE_DIR}/drivers/common/nes_ntsc.c
  ${CMAKE_CURRENT_SOURCE_DIR}/drivers/videolog/nesvideos-piece.cpp
  ${CMAKE_CURRENT_SOURCE_DIR}/drivers/videolog/rgbtorgb.cpp
)

#set(SRC_DRIVERS_SDL
#  ${CMAKE_CURRENT_SOURCE_DIR}/drivers/sdl/cheat.cpp
#  ${CMAKE_CURRENT_SOURCE_DIR}/drivers/sdl/config.cpp
#  ${CMAKE_CURRENT_SOURCE_DIR}/drivers/sdl/debugger.cpp
#  ${CMAKE_CURRENT_SOURCE_DIR}/drivers/sdl/glxwin.cpp
#  ${CMAKE_CURRENT_SOURCE_DIR}/drivers/sdl/gui.cpp
#  ${CMAKE_CURRENT_SOURCE_DIR}/drivers/sdl/GamePadConf.cpp
#  ${CMAKE_CURRENT_SOURCE_DIR}/drivers/sdl/input.cpp
#  ${CMAKE_CURRENT_SOURCE_DIR}/drivers/sdl/memview.cpp
#  ${CMAKE_CURRENT_SOURCE_DIR}/drivers/sdl/ramwatch.cpp
#  ${CMAKE_CURRENT_SOURCE_DIR}/drivers/sdl/sdl.cpp
#  ${CMAKE_CURRENT_SOURCE_DIR}/drivers/sdl/sdl-joystick.cpp
#  ${CMAKE_CURRENT_SOURCE_DIR}/drivers/sdl/sdl-sound.cpp
#  ${CMAKE_CURRENT_SOURCE_DIR}/drivers/sdl/sdl-throttle.cpp
#  ${CMAKE_CURRENT_SOURCE_DIR}/drivers/sdl/sdl-video.cpp
#  ${CMAKE_CURRENT_SOURCE_DIR}/drivers/sdl/unix-netplay.cpp
#)
