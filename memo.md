## わからんかったとこ

```C
#include <stdio.h>
#include <stdlib.h>

int main(int argc, char **argv) {
  if (argc != 2) {
    fprintf(stderr, "引数の個数が正しくありません\n");
    return 1;
  }

  printf(".intel_syntax noprefix\n");
  printf(".globl main\n");
  printf("main:\n");
  printf("  mov rax, %d\n", atoi(argv[1]));
  printf("  ret\n");
  return 0;
}
```
atoi(argv[1])じゃなくてatoi(argv[0])じゃないの？<br>
→コマンドライン引数的に入力される数字は2つ目<br>
参考:http://www.ritsumei.ac.jp/~mmr14135/johoWeb/cmnds.html
```C
argv[0] = ./9cc
argv[1] = 123
```


## トークナイザ実装
構造体とかいっぱい出てきてわけわかめ
```C
Token *tokenize(char *p){
{
```
関数にポインタついてる！？  
Token *　型ってだけだと思うけども
構造体を型宣言で使う時はポインタ必要なの？<br>

### 可変引数
```C
void error(char *fmt, ...){
   
{
```
...を用いることで、引数の数が固定でないことを表す。
可変個の引数にアクセスするにはstdarg.hをincludeする必要がある。
参考:http://wisdom.sakura.ne.jp/programming/c/c62.html

### calloc
void *calloc(size_t n, size_t size);<br>
ヒープメモリからサイズ分のブロックをn個割り当てる。<br>
あらかじめ配列を作ってメモリを確保する必要はなくなる。<br>
使い終わったらfreeで開放する必要があるっぽい。

### isspace
文字が空白だったら0以外、空白でなかったら0を返す<br>


### isdigit
文字が数字だったらTrueを返す<br>

### 
