# CenterServer的Makefile文件
CPP = g++
CPPFLAGS = -I ../include -I ../include/ServerCommon -I ../include/curl -I ../include/DataBase -I ../include/libevent -I ../include/hiredis -I ../lua -I ../protobuf -I /usr/local/include -DLUA_COMPAT_5_1 -g -Wall -O3 -std=c++11 
CFLAGS = -I ../include -I ../include/ServerCommon -I ../include/curl -I ../include/DataBase -I ../include/libevent -I ../include/hiredis -I ../lua -I ../protobuf -I /usr/local/include -DLUA_COMPAT_5_1 -g -Wall -O3 -std=c11

LDFLAGS = -L ../bin
LIBS = -lpthread -lKernel -lCommon -levent -ljemalloc

BINDIR := ../bin/
BIN := CenterServer
OBJ := BaseCenterServer.o CenterServerManage.o CenterServerModule.o main.o jemalloc_cpp.o

$(BINDIR)$(BIN):$(OBJ)
	$(CPP) -o $@  $(LDFLAGS) $^ $(LIBS)

%.o:%.cpp
	$(CPP) -c $^ $(CPPFLAGS)

jemalloc_cpp.o:../jemalloc/jemalloc_cpp.cpp
	$(CPP) -c $^ $(CPPFLAGS)

#%.o:../protobuf/%.cc
#	$(CPP) -c $^ $(CPPFLAGS)

#%.o:../lua/%.c
#	$(CPP) -c -x c $^ $(CFLAGS)

install:
	@echo "CenterServer生成在../bin/目录中"

clean:
	rm -rf *.o
	
