# EN
Modification to U8glib V2 library for Arduino.

Original library from olikraus: https://github.com/olikraus/u8g2

1. Added feature: drawing dotted lines. 
The files \U8g2\src\clib\u8g2_hvline.c and \U8g2\src\clib\u8g2.h were modified and the drawDottedLines setting was added.

```c++
{
    display.getU8g2()->drawDottedLines = true;
    display.drawHLine(x, y, round(modeItemWidth));
    display.getU8g2()->drawDottedLines = false;
}
```


 2. Added new image output mode. 

The original has three modes of image output to the display:
*   the entire screen at a time (version F in the constructor) - screen buffer 1024B;
*   by parts (stripes) 8 times (version 1 in the constructor) - screen buffer 128B;
*   by parts (stripes) 4 times (version 2 in the constructor) - screen buffer 256B;

**Added**: by parts (stripes) 2 times (version 4 in the constructor) - screen buffer 512B;

In this case screen update occurs more often, than with versions 1 and 2. It is worth using if free RAM is not enough for version F, but more than 512B.


# RU
Модифицированная версия:
1. Может рисовать пунктирные линии/рамки;
2. Добавлен новый режим вывода изображения.

В оригинале есть три режима вывода изображения на экран:
*	весь экран за раз (версия F в конструкторе) - размер буфера экрана 1024Б;
*	по частям (полосками) за 8 проходов (версия 1 в конструкторе) - размер буфера экрана 128Б;
*	по частям (полосками) за 4 прохода (версия 2 в конструкторе) - размер буфера экрана 256Б;

**Добавлено**: по частям за 2 прохода (версия 4 в конструкторе) - размер буфера экрана 512Б.

В этом случае обновление экрана происходит чаще, чем в версиях 1 и 2. Использовать стоит, если свободной RAM недостаточно для версии F, но больше 512Б.
