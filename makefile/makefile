CC = gcc
OBJS = a.o b.o c.o

#  放在第一個的target會被當作成goal 執行make時會自動選取
#  所以可以命名為all來make所有檔案

all: test hello.out

hello.out:hello.o 2.o 3.o 
	@echo
	#At hello.out:hello.o 2.o 3.o 
	#需要3個.o檔，因此以下會在最後執行
	gcc -o hello.out hello.o 2.o 3.o
	@echo
	#也可以跑任何指令喔
	python3 test.py
	sudo echo 1
hello.o:hello.c a.h 
	@echo
	#At hello.o:hello.c a.h 
	#以下會先執行
	gcc -c hello.c

2.o:2.c b.h
	@echo
	#At 2.o:2.c b.h
	#也可以用make 2.o 只編譯2.c
	gcc -c 2.c

3.o:3.c a.h b.h c.h
	@echo
	#At 3.o:3.c a.h b.h c.h
	gcc -c 3.c

%.o: %.c
	@echo
	#At %.o: %.c
	#$ @ 列出 target 名稱 $@
	#$ < 列出 第一個src $<
	$(CC) -c -o $@ $<

test: $(OBJS)
	@echo
	#at test: $(OBJS)
	#$ ^列出所有的src $^

clean:
	@echo
	#at clean
	-rm 2.o 3.o hello.o hello.out
	-rm a.o b.o c.o	test

manual: 
	# 放在第一個的target會被當作成goal 執行make時會自動選取
	# 所以可以命名為all來make所有檔案
	# $$@ 工作目標檔名 e.g. hello.out
	# $$< 第一個必要條件的檔名 e.g. a.o
	# $$^ 所有必要條件的檔名，並以空格隔開這些檔名 (這份清單已移除重複的檔名) e.g. a.o b.o c.o
	# $$* 工作目標的主檔名
	# % 是萬用字元
	# 指令前加上- 失敗也不會停止
	# 指令前加上@ 不會顯示執行 搭配echo不錯

