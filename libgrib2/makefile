SHELL=/bin/sh

#  If you want to enable support for PNG or JPEG2000 encoding/decoding,
#  you must specify -DUSE_PNG and/or -DUSE_JPEG2000 in the DEFS variable
#  for the C pre-processor
#  -DUSE_PNG requires libpng.a and libz.a
#                     ( and png.h pngconf.h zconf.h zlib.h include files).
#  -DUSE_JPEG2000 requires libjasper.a
#                     ( and all the jasper/*.h include files).
#
#  In addition, INC must include all directories where the above
#  mentioned include files can be found.
DEFS=#-DUSE_PNG -DUSE_JPEG2000

#
# Please make sure to include all idirectories where include files  
#     can be found (jasper/*.h and png.h pngconf.h zconf.h zlib.h)
#

INC=-Iinclude
LIB=-Llib

#
#   This "C" source code contains many uses of the C++
#   comment style "//".  Please make sure you include the
#   appropriate compiler flag to allow the use of "//" comment indicators.
#

CFLAGS= -O3 $(INC) $(LIB) $(DEFS)

CC=gcc

OUT=libgrib2.a
ARFLAGS=

all: $(OUT)

clean:
	del $(OUT)

$(OUT)(gridtemplates.o): gridtemplates.h

$(OUT)(pdstemplates.o): pdstemplates.h

$(OUT)(drstemplates.o): drstemplates.h

$(OUT):	$(OUT)(gridtemplates.o) \
	$(OUT)(drstemplates.o) \
	$(OUT)(pdstemplates.o) \
	$(OUT)(gbits.o) \
	$(OUT)(g2_unpack1.o) \
	$(OUT)(g2_unpack2.o) \
	$(OUT)(g2_unpack3.o) \
	$(OUT)(g2_unpack4.o) \
	$(OUT)(g2_unpack5.o) \
	$(OUT)(g2_unpack6.o) \
	$(OUT)(g2_unpack7.o) \
	$(OUT)(g2_free.o) \
	$(OUT)(g2_info.o) \
	$(OUT)(g2_getfld.o) \
	$(OUT)(simunpack.o) \
	$(OUT)(comunpack.o) \
        $(OUT)(pack_gp.o) \
        $(OUT)(reduce.o) \
	$(OUT)(specpack.o) \
	$(OUT)(specunpack.o) \
	$(OUT)(rdieee.o) \
	$(OUT)(mkieee.o) \
	$(OUT)(int_power.o) \
	$(OUT)(simpack.o) \
	$(OUT)(compack.o) \
        $(OUT)(cmplxpack.o) \
	$(OUT)(misspack.o) \
	$(OUT)(jpcpack.o) \
	$(OUT)(jpcunpack.o) \
	$(OUT)(pngpack.o) \
	$(OUT)(pngunpack.o) \
	$(OUT)(dec_jpeg2000.o) \
	$(OUT)(enc_jpeg2000.o) \
	$(OUT)(dec_png.o) \
	$(OUT)(enc_png.o) \
	$(OUT)(g2_create.o) \
	$(OUT)(g2_addlocal.o) \
	$(OUT)(g2_addgrid.o) \
	$(OUT)(g2_addfield.o) \
	$(OUT)(g2_gribend.o) \
	$(OUT)(getdim.o) \
	$(OUT)(g2_miss.o) \
	$(OUT)(getpoly.o) \
	$(OUT)(seekgb.o)

.c.a:
	$(CC) -c $(CFLAGS) $<
	ar $(ARFLAGS) -ruv $@ $*.o
	del $*.o

