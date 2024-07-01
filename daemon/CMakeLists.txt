cmake_minimum_required(VERSION 3.26)

include_directories(../src)
aux_source_directory(. SRCS)
add_executable(abc_daemon ${SRCS})
set_source_files_properties(${SRCS} PROPERTIES LANGUAGE CXX)

add_dependencies(abc_daemon
        abc::misc::util
        abc::bool::dec
        abc::base::cmd
        abc::base::abc
#        abc::base::abci
        abc::base::bac
        abc::base::cba
#        abc::base::io
        abc::base::pla
        abc::base::test
#        abc::base::wlc
#        abc::base::wln
        abc::map::if
#        abc::map::mapper
#        abc::map::mio
#        abc::map::super
#        abc::map::scl
        abc::opt::rwt
#        abc::aig::aig
        abc::aig::gia
#        abc::sat::glucose
#        abc::sat::glucose2
)
target_link_libraries(abc_daemon
        PUBLIC
        abc::misc::util
        abc::bool::dec
        abc::base::cmd
        abc::base::abc
#        abc::base::abci
        abc::base::bac
        abc::base::cba
#        abc::base::io
        abc::base::pla
        abc::base::test
#        abc::base::wlc
#        abc::base::wln
        abc::map::if
#        abc::map::mapper
#        abc::map::mio
#        abc::map::super
#        abc::map::scl
        abc::opt::rwt
#        abc::aig::aig
        abc::aig::gia
#        abc::sat::glucose
#        abc::sat::glucose2
        readline
)
