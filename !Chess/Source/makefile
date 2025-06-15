#Make file for chess

LIB      = C:o.stubs C:risc_oslib.o.risc_oslib 
ILIB     = -I C:risc_oslib -I C:
OBJECTS  = o.chesslib  o.chesssave o.chess o.messages
IMAGE    = ^.!RunImage

chess : $(OBJECTS) 
        link $(OBJECTS) $(LIB) -o $(IMAGE) 

o.messages : c.messages
             cc -c messages $(ILIB)

o.chess : c.chess h.chesslib h.chesssave h.messages
         cc -c chess $(ILIB) 

o.chesssave : c.chesssave h.chess h.chesslib h.messages
              cc -c chesssave $(ILIB)

o.chesslib: c.chesslib h.chesslib
         cc -c chesslib -pcc


tidy: 
        wipe o.* ~C~V
        squeeze $(IMAGE)
