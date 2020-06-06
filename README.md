# exolynx
exomizer unpacker example for lynx

Allows for stream depacking from ROM

Pack files with the following command

./exomizer level -P0 -f -o chunk_39.exo chunk_39.dat

Unpack from cartridge file:

ReadAndUnpack::
; Load File A to DestPtr
;     lda filenumber
;     jsr OpenFile
    MOVEI DESTINATIONADDRESS, zp_dest_lo
    jsr decrunch
    rts

get_crunched_byte:
    php
    phx
    phy
    jsr ReadByte
    ply
    plx
    plp
    rts



