objs := init.o

all: $(objs)
	arm-none-eabi-ld -Ttext 0x0000000 -o init.elf $^
	arm-none-eabi-objcopy -O binary -S init.elf init.bin
	arm-none-eabi-objdump -D -m arm init.elf > init.dis
	
%.o:%.c
	arm-none-eabi-gcc -Wall -g -c -o $@ $<

%.o:%.S
	arm-none-eabi-gcc -Wall -g -c -o $@ $<

clean:
	rm -f init.bin init.elf init.dis *.o		
	
