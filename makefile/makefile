
hello.out:hello.o 2.o 3.o 
	#需要3個.o檔，因此以下會在最後執行
	gcc -o hello.out hello.o 2.o 3.o
	#也可以跑任何指令喔
	python3 test.py
hello.o:hello.c a.h 
	#以下會先執行
	gcc -c hello.c
2.o:2.c b.h
	#也可以用make 2.o 只編譯2.c
	gcc -c 2.c
3.o:3.c a.h b.h c.h
	gcc -c 3.c

clean:
	rm 2.o 3.o hello.o hello.out
