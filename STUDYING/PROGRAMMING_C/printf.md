#printf()の正体
##参考リンク
  - [可変個引数](https://programming-place.net/ppp/contents/c/052.html)
  - [printf関数](https://programming-place.net/ppp/contents/c/appendix/reference/printf.html)
  - [vprintf関数](https://programming-place.net/ppp/contents/c/appendix/reference/vprintf.html)
  - [va_list型](https://programming-place.net/ppp/contents/c/appendix/reference/va_list.html)
  - [media @IT:printf()のソースコードで、ソースコードリーディングのコツを身に付ける：main()関数の前には何があるのか](https://atmarkit.itmedia.co.jp/ait/articles/1703/01/news170.html)
  - [Function that accepts different data types](https://forum.arduino.cc/t/function-that-accepts-different-data-types/454584/26)
  - [templet](https://cplusplus.com/doc/oldtutorial/templates/)
 ### 可変個引数とは、
 ### vprintf関数とは、
 ### va_list型とは、
### TEMplete template
```C
<class T> void dataprint(T param){
  Serial.print(param);
  Serial.print(",");
}
```
上記コードでは、整数型でしか表示されない、(表示する変数の型が整数型だっただけかも)だから、Serial.print(param,2);としたら、2進数が表示されたのかも。
以下のコードを見つけた
```
template<class T>
inline print &operator <<(print &obj, T arg)
{
  obj.print(arg);
  return obj;
}
```
最終的に、このgithubを見つけた。
- [Arduino Streaming Library](https://gist.github.com/fitzterra/3ac5a09f83e3b116d1c0bf53e2a357bd)
