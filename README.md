Modification to U8glib V2 library for Arduino.

Original library from olikraus: https://github.com/olikraus/u8g2

Added feature: drawing dotted lines. 
The files \U8g2\src\clib\u8g2_hvline.c and \U8g2\src\clib\u8g2.h were modified and the drawDottedLines setting was added.

```c++
{
    display.getU8g2()->drawDottedLines = true;
    display.drawHLine(x, y, round(modeItemWidth));
    display.getU8g2()->drawDottedLines = false;
}
```


