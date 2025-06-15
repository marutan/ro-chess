#Make file for chess

LIB      = <C$libroot>.o.stubs <C$libroot>.risc_oslib.o.risc_oslib 
ILIB     = <C$libroot>.risc_oslib
OBJECTS  = o.chesslib  o.chesssave o.chess o.messages
IMAGE    = !chess.!runimage

chess : $(OBJECTS) 
        link $(OBJECTS) $(LIB) -o $(IMAGE) 

o.messages : c.messages
             cc messages -c -I $(ILIB)

o.chess : c.chess h.chesslib h.chesssave h.messages
         cc chess -c -I $(ILIB) 

o.chesssave : c.chesssave h.chess h.chesslib h.messages
              cc chesssave -c -I $(ILIB)

o.chesslib: c.chesslib h.chesslib
         cc chesslib -pcc -c


tidy: 
        wipe o.* ~C~V
        squeeze $(IMAGE)
