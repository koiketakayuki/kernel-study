# Memory addressing

以下80x86プロセッサのお話

## メモリアドレスの種類

+ 論理アドレス (Logical Address)  
セグメントとオフセットのペア。  
https://en.wikipedia.org/wiki/Logical_address


+ リニアアドレス (Linear Address)  
https://wa3.i-3-i.info/word14344.html  
プログラムから見たメモリアドレス。  
0x00000000から0xffffffffまで

+ 物理アドレス (Physical Address)  
https://en.wikipedia.org/wiki/Physical_address  
ハードウェアのメモリアドレス。  
メモリチップのアドレスピンを指定する際に用いる  
unsigned 32 bit or 36 bit


論理アドレス、リニアアドレスは実際のメモリではないので Virtual Address である。  
使用時に物理アドレスにマッピングされる。



このマッピングはMemory Management Unit (MMU)によって行われる。  
https://en.wikipedia.org/wiki/X86_memory_segmentation  

まず論理アドレスがリニアアドレスに変換される。  
これはセグメンテーション回路という回路によって行われる。

その後、リニアアドレスが物理アドレスに変換される。  
この操作はページング回路という回路で行われる。

 