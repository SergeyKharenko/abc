cmake_minimum_required(VERSION 3.26)
set(COMPONENT_NAME abci)

include_directories(../../)
aux_source_directory(. SRCS)
list(REMOVE_ITEM SRCS "./abcDarUnfold2.c")
list(REMOVE_ITEM SRCS "./abciUnfold2.c")
list(REMOVE_ITEM SRCS "./abcEspresso.c")
list(REMOVE_ITEM SRCS "./fahout_cut.c")
list(REMOVE_ITEM SRCS "./abcFpga.c")
list(REMOVE_ITEM SRCS "./abcPlace.c")
add_library(${COMPONENT_NAME} ${SRCS})
add_library(${PROJECT_NAME}::${SUBFOLDER_NAME}::${COMPONENT_NAME} ALIAS ${COMPONENT_NAME})
target_link_libraries(${COMPONENT_NAME}
        ${PROJECT_NAME}::aig::aig
        ${PROJECT_NAME}::aig::gia
        ${PROJECT_NAME}::aig::hop
        ${PROJECT_NAME}::aig::ioa
        ${PROJECT_NAME}::aig::ivy
        ${PROJECT_NAME}::aig::saig

        ${PROJECT_NAME}::bdd::bbr
        ${PROJECT_NAME}::bdd::cas
        ${PROJECT_NAME}::bdd::cudd
        ${PROJECT_NAME}::bdd::dsd
        ${PROJECT_NAME}::bdd::epd
        ${PROJECT_NAME}::bdd::extrab
        ${PROJECT_NAME}::bdd::llb
        ${PROJECT_NAME}::bdd::mtr
        ${PROJECT_NAME}::bdd::reo

        ${PROJECT_NAME}::base::abc
        ${PROJECT_NAME}::base::acb
        ${PROJECT_NAME}::base::exor

        ${PROJECT_NAME}::bool::bdc
        ${PROJECT_NAME}::bool::dec
        ${PROJECT_NAME}::bool::kit
        ${PROJECT_NAME}::bool::lucky
        ${PROJECT_NAME}::bool::rpo
        ${PROJECT_NAME}::bool::rsb

        ${PROJECT_NAME}::map::amap
        ${PROJECT_NAME}::map::cov
        ${PROJECT_NAME}::map::fpga
        ${PROJECT_NAME}::map::if
        ${PROJECT_NAME}::map::mapper
        ${PROJECT_NAME}::map::mio
        ${PROJECT_NAME}::map::mpm
        ${PROJECT_NAME}::map::scl
        ${PROJECT_NAME}::map::super

        ${PROJECT_NAME}::opt::cgt
        ${PROJECT_NAME}::opt::cut
        ${PROJECT_NAME}::opt::csw
        ${PROJECT_NAME}::opt::dar
        ${PROJECT_NAME}::opt::dau
        ${PROJECT_NAME}::opt::dsc
        ${PROJECT_NAME}::opt::fret
        ${PROJECT_NAME}::opt::fxu
        ${PROJECT_NAME}::opt::fxch
        ${PROJECT_NAME}::opt::lpk
        ${PROJECT_NAME}::opt::mfs
        ${PROJECT_NAME}::opt::nwk
        ${PROJECT_NAME}::opt::ret
        ${PROJECT_NAME}::opt::rwr
        ${PROJECT_NAME}::opt::sbd
        ${PROJECT_NAME}::opt::sim
        ${PROJECT_NAME}::opt::sfm

        ${PROJECT_NAME}::proof::abs
        ${PROJECT_NAME}::proof::acec
        ${PROJECT_NAME}::proof::dch
        ${PROJECT_NAME}::proof::fra
        ${PROJECT_NAME}::proof::fraig
        ${PROJECT_NAME}::proof::int
        ${PROJECT_NAME}::proof::pdr
        ${PROJECT_NAME}::proof::ssc
        ${PROJECT_NAME}::proof::ssw

        ${PROJECT_NAME}::sat::bmc
        ${PROJECT_NAME}::sat::bsat
        ${PROJECT_NAME}::sat::cnf
        ${PROJECT_NAME}::sat::xsat)
