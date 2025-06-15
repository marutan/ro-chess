#Make file for chess

LIB      = C:o.stubs C:risc_oslib.o.risc_oslib 
ILIB     = C:risc_oslib C:
OBJECTS  = o.chesslib  o.chesssave o.chess o.messages
IMAGE    = ^.!RunImage

chess : $(OBJECTS) 
        link $(OBJECTS) $(LIB) -o $(IMAGE) 

o.messages : c.messages
             cc messages -I $(ILIB)

o.chess : c.chess h.chesslib h.chesssave h.messages
         cc chess -I $(ILIB) 

o.chesssave : c.chesssave h.chess h.chesslib h.messages
              cc chesssave -I $(ILIB)

o.chesslib: c.chesslib h.chesslib
         cc chesslib -pcc


tidy: 
        wipe o.* ~C~V
        squeeze $(IMAGE)
