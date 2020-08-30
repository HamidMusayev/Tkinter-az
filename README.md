[<img src="https://github.com/hemidvsmusayev/Tkinter/blob/master/ww_images/logo.png?raw=true" align="center" width="750">](https://docs.python.org/3/library/tkinter.html)
# Haqqında -- STILL IN DEVELOP
<a href="https://docs.python.org/3/library/tkinter.html">Tkinter</a> Python üçün yaradılmış standart GUİ (Grafik İstifadəçi interfeysi) paketidir.


Əgər yaratdığım bu kontent sizə köməy etdisə və ya bəyəndinizsə📖, dəstək olmaq üçün bunlardan birini etməyiniz kifayətdir 👍| ⭐| 👏
# Mövzular
- [Standart parametrlər](#Standart-parametrlər)
- [Button](#Button)
- [Canvas](#Canvas)
- [Check button](#Check-button)
- [Frames](#Frames)
- [List box](#List-box)
- [Menu](#Menu)
- [Message box](#Message-box)
- [Paned window](#Paned-window)
- [Radio button](#Radio-button)
- [Scrolls](#Scrolls)
- [Text widgets](#Text-widgets)
- [Windows](#Windows)
- [Bonus-Kitablar](#Kitablar)

## Standart-parametrlər
Widgetlərə keçməzdən öncə gəlin onların ölçüləri, rəngləri, font tipləri kimi ümumi parametrləri ilə tanış olaq.

Hər widgetin öz görünüş və davranışlarını xarakterizə edən `fonts`, `colors`, `sizes`, `text`, `labels` və.s. kimi parametrləri mövcuddur.

You can specify options when calling the widget's constructor using keyword arguments such as `text='HQ!'` or `height=24`.

After you have created a widget, you can later change any option by using the widget's `.config()` method. You can retrieve the current setting of any option by using the widget's `.cget()` method. See Section 26, “Universal widget methods” for more on these methods.

- [Ölçülər](#Ölçülər)
- [Koordinasiya sistemi](#Koordinasiya-sistemi)
- [Rənglər](#Rənglər)
- [Font tipləri](#Font-tipləri)
- [Kənarlar](#Kənarlar)
- [Relief stilləri](#Relief-stilləri)
- [Bitmap](#Bitmap)
- [Cursorlar](#Cursorlar)
- [Şəkillər](#Şəkillər)
- [Geometrik stringlər](#Geometrik-stringlər)
- [Pəncərə adları](#Pəncərə-adları)
- [Boşluqlar və birləşmə stilləri](Boşluqlar-və-birləşmə-stilləri)
- [Dash patterns](#Dash-patterns)
- [Matching stipple patterns](#Matching-stipple-patterns)

### Ölçülər
Various lengths, widths, and other dimensions of widgets can be described in many different units.

If you set a dimension to an integer, it is assumed to be in pixels.

You can specify units by setting a dimension to a string containing a number followed by:

| Command | Description |
| --- | --- |
| `c` | Centimeters |
| `i` | Inches |
| `m` | Millimeters |
| `p` | Printer's points (about 1/72″) |


### Koordinasiya-sistemi
As in most contemporary display systems, the origin of each coordinate system is at its upper left corner, with the x coordinate increasing toward the right, and the y coordinate increasing toward the bottom.
The base unit is the pixel, with the top left pixel having coordinates (0,0). Coordinates that you specify as integers are always expressed in pixels, but any coordinate may be specified as a dimensioned quantity.

### Rənglər

[Color chooser example](https://github.com/hemidvs/Tkinter/blob/master/Color%20chooser/color_chooser.py)

There are two general ways to specify colors in Tkinter.

- You can use a string specifying the proportion of red, green, and blue in hexadecimal digits:

| Command | Description |
| --- | --- |
| `#rgb` | Four bits per color |
| `#rrggbb` | Eight bits per color |
| `#rrrgggbbb` | Twelve bits per color |

For example, '#fff' is white, '#000000' is black, '#000fff000' is pure green, and '#00ffff' is pure cyan (green plus blue).

- You can also use any locally defined standard color name. The colors 'white', 'black', 'red', 'green', 'blue', 'cyan', 'yellow', and 'magenta' will always be available. Other names may work, depending on your local installation.

### Font-tipləri

[Fonts Example](https://github.com/hemidvs/Tkinter/blob/master/Type%20fonts/type_fonts.py)

Depending on your platform, there may be up to three ways to specify type style.

- As a tuple whose first element is the font family, followed by a size (in points if positive, in pixels if negative), optionally followed by a string containing one or more of the style modifiers bold, italic, underline, and overstrike.

  Examples: ('Helvetica', '16') for a 16-point Helvetica regular; ('Times', '24', 'bold italic') for a 24-point Times bold italic. For a 20-pixel Times bold font, use ('Times', -20, 'bold').
  
- You can create a “font object” by importing the tkFont module and using its Font class constructor:
  
  `import tkFont`
  
  `font = tkFont.Font(option, ...)`
  
   where the options include:
  
| Command | Description |
| --- | --- |
| `family` | The font family name as a string. |
| `size` | The font height as an integer in points. To get a font n pixels high, use -n. |
| `weight` | 'bold' for boldface, 'normal' for regular weight. |
| `slant` | 'italic' for italic, 'roman' for unslanted. |
| `underline` | 1 for underlined text, 0 for normal. |
| `overstrike` | 1 for overstruck text, 0 for normal. |

   For example, to get a 36-point bold Helvetica italic face:
   
   `helv36 = tkFont.Font(family='Helvetica', size=36, weight='bold')`
    
To get a list of all the families of fonts available on your platform, call this function:
  
  `tkFont.families()`
  
The return value is a list of strings. Note: You must create your root window before calling this function.

These methods are defined on all `Font` objects:

`.actual(option=None)`

If you pass no arguments, you get back a dictionary of the font's actual attributes, which may differ from the ones you requested. To get back the value of an attribute, pass its name as an argument.

`.cget(option)`

Returns the value of the given option.

`.configure(option, ...)`

Use this method to change one or more options on a font. For example, if you have a Font object called titleFont, if you call titleFont.configure(family='times', size=18), that font will change to 18pt Times and any widgets that use that font will change too.

`.copy()`

Returns a copy of a Font object.

`.measure(text)`

Pass this method a string, and it will return the number of pixels of width that string will take in the font. Warning: some slanted characters may extend outside this area.

`.metrics(option)`

If you call this method with no arguments, it returns a dictionary of all the font metrics. You can retrieve the value of just one metric by passing its name as an argument. Metrics include:

| Command | Description |
| --- | --- |
| `ascent` | Number of pixels of height between the baseline and the top of the highest ascender. |
| `descent` | Number of pixels of height between the baseline and the bottom of the lowest ascender. |
| `fixed` | This value is 0 for a variable-width font and 1 for a monospaced font. |
| `linespace` | Number of pixels of height total. This is the leading of type set solid in the given font. |

### Kənarlar
The Tkinter module defines a number of anchor constants that you can use to control where items are positioned relative to their context. For example, anchors can specify where a widget is located inside a frame when the frame is bigger than the widget.

These constants are given as compass points, where north is up and west is to the left.

The anchor constants are shown in this diagram:

<img src="https://github.com/hemidvs/Tkinter/blob/master/ww_images/anchors.png" align="center" width="150">

For example, if you create a small widget inside a large frame and use the `anchor=tk.SE` option, the widget will be placed in the bottom right corner of the frame. If you used `anchor=tk.N` instead, the widget would be centered along the top edge.

Anchors are also used to define where text is positioned relative to a reference point. For example, if you use `tk.CENTER` as a text anchor, the text will be centered horizontally and vertically around the reference point. Anchor `tk.NW` will position the text so that the reference point coincides with the northwest (top left) corner of the box containing the text. Anchor `tk.W` will center the text vertically around the reference point, with the left edge of the text box passing through that point, and so on.
### Relief-stilləri

The relief style of a widget refers to certain simulated 3-D effects around the outside of the widget. Here is a screen shot of a row of buttons exhibiting all the possible relief styles:

<img src="https://github.com/hemidvs/Tkinter/blob/master/ww_images/relief.png?raw=true" align="center" width="400">
### Bitmaps
### Cursors
### Images
### Geometry-strings
### Window-names
### Cap-and-join-styles
### Dash-patterns
### Matching-stipplep-atterns

## Button

## Canvas

## Check-button

## Frames

## List-box

## Menu

## Message-box

## Paned-window

## Radio-button

## Scrolls

## Text-widgets

## Windows
root.resizable(False, False) 
## Bonus
### More references
- <a href="https://web.archive.org/web/20190524140835/https://infohost.nmt.edu/tcc/help/pubs/tkinter/web/index.html">Tkinter 8.5</a> reference
- <a href="https://coderslegacy.com/python/python-gui/">CodersLegacy</a> blogs Python GUI
