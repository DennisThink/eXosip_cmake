project(eXosip)
SET(CMAKE_ARCHIVE_OUTPUT_DIRECTORY_DEBUG ${THIRD_PARTY_LIB_TARGET_DIRECTORY})  
SET(LIBRARY_OUTPUT_PATH ${THIRD_PARTY_LIB_TARGET_DIRECTORY}) 


if(CMAKE_HOST_LINUX)
add_compile_options(-DHAVE_SYS_SOCKET_H)
add_compile_options(-DHAVE_NETINET_IN_H)
add_compile_options(-DHAVE_ARPA_INET_H)
add_compile_options(-DHAVE_NETDB_H)
add_compile_options(-DHAVE_SYS_EPOLL_H)
add_compile_options(-DHAVE_FCNTL_H)
add_compile_options(-DINET6_ADDRSTRLEN=128)
add_compile_options(-DHAVE_LIMITS_H)
endif()
include_directories(${EXOSIP_SOURCE_DIR}/third_party/libosip2-5.3.1/include/)
include_directories(${EXOSIP_SOURCE_DIR}/include/)

SET(EXOSIP_SOURCE_FILE ./eXcall_api.c
./eXconf.c
./eXinsubscription_api.c
./eXmessage_api.c
./eXoptions_api.c
./eXosip.c
./eXosip2.h
./eXpublish_api.c
./eXregister_api.c
./eXsubscription_api.c
./eXtl_dtls.c
./eXtl_tcp.c
./eXtl_tls.c
./eXtl_udp.c
./eXtransport.c
./eXtransport.h
./eXutils.c
./inet_ntop.c
./inet_ntop.h
./jauth.c
./jcall.c
./jcallback.c
./jdialog.c
./jevents.c
./jnotify.c
./jpipe.c
./jpipe.h
./jpublish.c
./jreg.c
./jrequest.c
./jresponse.c
./jsubscribe.c
./milenage.c
./milenage.h
./misc.c
./rijndael.c
./rijndael.h
./sdp_offans.c
./udp.c
)

add_library(exosip ${EXOSIP_SOURCE_FILE})