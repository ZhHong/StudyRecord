ORACLE_INCLUDES=-I$(ORACLE_HOME)/rdbms/public \
-I$(ORACLE_HOME)/plsql/public \
-I$(ORACLE_HOME)/network/public \
-I$(ORACLE_HOME)/precomp/public
ORACLE_LIBS=-L$(ORACLE_HOME)/lib -L$(ORACLE_HOME)/rdbms/lib
CC=g++
#CC_FLAG=-Wno-deprecated -fPIC -march=i486
CC_FLAG=-Wall
INC=$(ORACLE_INCLUDES)
LIB=$(ORACLE_LIBS) -lclntsh -locci -lxerces-c -lpthread
PRG=occi
SRC=occi.cpp
OBJ=occi.o
$(PRG): $(OBJ)
@echo "Link $(OBJ) to $(PRG) begin......"
$(CC) $(CC_FLAG) $(INC) $(LIB) -o $@ $<
@echo "Link $(OBJ) to $(PRG) end......"
$(OBJ): $(SRC)
@echo "Compile $(OBJ) begin......"
$(CC) $(CC_FLAG) $(INC) $(ORACLE_LIBS) -c $<
@echo "Compile $(OBJ) end......"
clean:
@echo "Removing linked and compiled files......"
rm -f $(OBJ) $(PRG)