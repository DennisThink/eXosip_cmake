project(libosip2)
SET(CMAKE_ARCHIVE_OUTPUT_DIRECTORY_DEBUG ${THIRD_PARTY_LIB_TARGET_DIRECTORY})  
SET(LIBRARY_OUTPUT_PATH ${THIRD_PARTY_LIB_TARGET_DIRECTORY})

if(CMAKE_HOST_LINUX)
add_compile_options(-DHAVE_STRUCT_TIMEVAL)
add_compile_options(-DHAVE_PTHREAD)
add_compile_options(-DHAVE_SEMAPHORE_H)
add_compile_options(-DHAVE_SYS_UNISTD_H)
add_compile_options(-DHAVE_FCNTL_H)
else()
#add_compile_options(-DWIN32)
endif()

include_directories(${EXOSIP_SOURCE_DIR}/third_party/libosip2-5.3.1/include/)
SET(LIBOSIP2_SOURCE_FILE 
./src/osip2/fsm.h
./src/osip2/fsm_misc.c
./src/osip2/ict.c
./src/osip2/ict_fsm.c
./src/osip2/ist.c
./src/osip2/ist_fsm.c
./src/osip2/nict.c
./src/osip2/nict_fsm.c
./src/osip2/nist.c
./src/osip2/nist_fsm.c
./src/osip2/osip.c
./src/osip2/osip_dialog.c
./src/osip2/osip_event.c
./src/osip2/osip_time.c
./src/osip2/osip_transaction.c
./src/osip2/port_condv.c
./src/osip2/port_fifo.c
./src/osip2/port_sema.c
./src/osip2/port_thread.c
./src/osip2/xixt.h
)

SET(LIB_OSIP_PARSER2_SOURCE_FILE
./src/osipparser2/osip_accept.c
./src/osipparser2/osip_accept_encoding.c
./src/osipparser2/osip_accept_language.c
./src/osipparser2/osip_alert_info.c
./src/osipparser2/osip_allow.c
./src/osipparser2/osip_authentication_info.c
./src/osipparser2/osip_authorization.c
./src/osipparser2/osip_body.c
./src/osipparser2/osip_call_id.c
./src/osipparser2/osip_call_info.c
./src/osipparser2/osip_contact.c
./src/osipparser2/osip_content_disposition.c
./src/osipparser2/osip_content_encoding.c
./src/osipparser2/osip_content_length.c
./src/osipparser2/osip_content_type.c
./src/osipparser2/osip_cseq.c
./src/osipparser2/osip_error_info.c
./src/osipparser2/osip_from.c
./src/osipparser2/osip_header.c
./src/osipparser2/osip_list.c
./src/osipparser2/osip_md5c.c
./src/osipparser2/osip_message.c
./src/osipparser2/osip_message_parse.c
./src/osipparser2/osip_message_to_str.c
./src/osipparser2/osip_mime_version.c
./src/osipparser2/osip_parser_cfg.c
./src/osipparser2/osip_port.c
./src/osipparser2/osip_proxy_authenticate.c
./src/osipparser2/osip_proxy_authentication_info.c
./src/osipparser2/osip_proxy_authorization.c
./src/osipparser2/osip_record_route.c
./src/osipparser2/osip_route.c
./src/osipparser2/osip_to.c
./src/osipparser2/osip_uri.c
./src/osipparser2/osip_via.c
./src/osipparser2/osip_www_authenticate.c
./src/osipparser2/parser.h
./src/osipparser2/sdp_accessor.c
./src/osipparser2/sdp_message.c
)
add_library(osip2 ${LIBOSIP2_SOURCE_FILE} ${LIB_OSIP_PARSER2_SOURCE_FILE})