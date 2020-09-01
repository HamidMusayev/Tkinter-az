[<img src="https://github.com/hemidvsmusayev/Tkinter/blob/master/ww_images/logo.png?raw=true" align="center" width="750">](https://docs.python.org/3/library/tkinter.html)
# Haqqında -- TEZLİKLƏ
<a href="https://docs.python.org/3/library/tkinter.html">Tkinter</a> Python üçün yaradılmış standart GUİ (Grafik İstifadəçi interfeysi) paketidir.


Əgər bu kontent işinizə yaradısa və ya bəyəndinizsə 📖, dəstək olmaq üçün bunlardan birini etməyiniz kifayətdir 👍| ⭐| 👏

# Mövzular
- [Standart parametrlər](#Standart-parametrlər)
- [ttk modulu haqqında](#tkk-modulu-haqqında)
- [Paketlərin import edilməsi](#Paketlərin-import-edilməsi)
- [Widget stilləri](#Widget-stilləri)
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
- [Bonus-Kitablar](#Bonus-Kitablar)

## Standart-parametrlər
Widgetlərə keçməzdən öncə gəlin onların ölçüləri, rəngləri, font tipləri kimi ümumi parametrləri ilə tanış olaq.

Hər widgetin öz görünüş və davranışlarını xarakterizə edən `font`, `color`, `size`, `text`, `label` və.s. kimi parametrləri mövcuddur.

Parametrləri təyin etmək üçün widgetin constructorunda onu cağırmaq və dəyərini vermək lazımdır. Məsələn: `Button(window, text='Ok', fg='Blue')`.

Widget yaradıldıqdan sonra onun hər hansı parametrini daha sonra dəyişmək lazım gələrsə `.config()` metodundan istifadə edilir.
 
Həmçinin yaradılmış widgetin hər hansı parametrinin dəyərini göstərmək üçün `.cget()` metdonundan istifadə edilir.

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
Widgetlərin uzunluq, en və başqa ölçü dəyərləri müxtəlif vahidlərlə göstərilə bilər.

Əgər ölçünü integer kimi qeyd etsəniz bu proqram tərəfinfən pixel olaraq qəbul edilir.

Ölçü dəyərləri aşağıdakı cədvələ uyğun rəqəmli stringlər şəkilində verilir:

| Yazılışı | İzahı |
| --- | --- |
| `c` | Santimetr |
| `i` | İnc |
| `m` | Millimetr |
| `p` | point(1/72 inc) |

### Koordinasiya-sistemi
Müasir koordinasiya sistemlərində olduğu kimi, hər bir koordinat sisdeminin başlanğıcı sol üst küncdədir. X koordinatı sağa, Y koordinatı isə sola getdikcə artır.

Əsas ölçü vahidi pikseldir. Ən yuxarı soldakı pikselin koordinatları (0,0). İnteger kimi verilən koordinatlar piksellər ilə işlənir, lakin bütün koordinatlar ölçü vahidləri ilə verilə bilər.

<img src="https://github.com/hemidvs/Tkinter-en/blob/master/ww_images/coordinate.PNG?raw=true">

### Rənglər
[Color chooser nümunəsi](https://github.com/hemidvs/Tkinter/blob/master/Color%20chooser/color_chooser.py)

Tkinter də rəngləri təyin etmək üçün iki seçim mövcuddur.

- Standart rənglərin adları ilə verilməsi: `'white'`, `'black'`, `'red'`, `'green'`, `'blue'`, `'cyan'`, `'yellow'` və `'magenta'`

- Rənglərin qırmızı, yaşıl və mavi hexadecimal formatına uyğun string şəkilində verilməsi:

| Yazılışı | İzahı |
| --- | --- |
| `#rgb` | 4 bitlik |
| `#rrggbb` | 8 bitlik |
| `#rrrgggbbb` | 16 bitlik |

Məsələn, '#fff' ağ, '#000000' qara, '#000fff000' is açıq yaşıl, and '#00ffff' cyan (yaşıl ilə göy qarışığı).

Rəngləri [buradan](https://www.google.com/search?q=color+picker) və ya Google-nin Material design rəngləri [buradan](https://material.io/resources/color/#!/?view.left=0&view.right=0) incələyə bilərik.

### Font-tipləri
[Nümunə](https://github.com/hemidvs/Tkinter/blob/master/Type%20fonts/type_fonts.py)

İstfadə etdiyiniz platformadan asılı olaraq yazı stilini təyin etmək üçün 3 üsul var.

- Tuple şəkilində. Burada birinci element font ailəsi(font family), ikinci ölçüsü(əgər müsbət işarəli olarsa point olaraq işlənir, mənfi işarəlidirsə piksellərlə), ehtiyac yarandıqa isə üçüncü element kimi yazının digər stilini `'bold'`, `'italic'`, `'underline'` və `'overstrike'` verə bilərik.
  
  Məsələn: `('Helvetica', '16')` 16-point Helvetica regular; `('Times', '24', 'bold italic')` 24-point Times bold italic. 20-piksel Times bold font üçün isə `('Times', -20, 'bold')`.

- tkFont modulunu import edərək Font sinifinə aid yeni bir "font obyekti" təyin etməklə:
  
  `import tkFont`
  
  `font = tkFont.Font(option, ...)`
  
   parametrlərə bunlar daxildir:
  
| Yazılışı | İzahı |
| --- | --- |
| `family` | String formatında verilmiş font ailəsi adı. |
| `size` | Font ölçüsü (integer formatında - points kimi). n piksel ölçüsündə yazmaq üçün -n. |
| `weight` | 'bold' - qalın , 'normal' - normal. |
| `slant` | 'italic' - italic, 'roman' - cursiv. |
| `underline` | 1 - altı xəttli yazı, 0 - normal. |
| `overstrike` | 1 - orta xəttli yazı, 0 - normal. |

Məsələn: 36 point bold Helvetica italic tipli yazı üçün:
  
`helv36 = tkFont.Font(family='Helvetica', size=36, weight='bold')`

Patformanızda mövcud olan bütün fontları görmək üçün:
  
  `tkFont.families()`
  
Geri Dönən dəyər string list şəkilində olacaq. Qeyd: Bu funksiyanı çağırmazdan öncə ana pəncərənizi(Window) yaratmalıyıq.

Bu metodlar bütün `Font` obyektlərində istidə olunur:

`.actual(option=None)`

Əgər bu metodu çağırıb heçbir arqument verməsək, hazırki fontların mümkün bütün atributlarını döndürər
////// If you pass no arguments, you get back a dictionary of the font's actual attributes, which may differ from the ones you requested. To get back the value of an attribute, pass its name as an argument.

`.cget(option)`

Verilmiş parametrin(option) hazırki dəyərini döndürür.

`.configure(option, ...)`

Bu metodu istifadə etməklə fontun bir və ya bir neçə parametrinin dəyərini dəyişmək mümkündür. Məsələn: Əgər sizin `titleFont` adlı Font obyektiniz varsa `titleFont.configure(family='times', size=18)` yazılışı ilə fontun ölçüsü 18pt, Times stilinə keçir və bu obyekti istifadə edən bütün widgetlər ona uyğun olaraq dəyişir.

`.copy()`

Font obyektini köçürür və döndürür.

`.measure(text)`

Bu metod içərisinə yazılmış string mətnin həmin font ilə yazılışı zamanı uzunluğun tutduğu piksellərin sayını döndürür. Qeyd: bəzi kursiv yazılarda dəqiq olmaya bilər.

`.metrics(option)`

Əgər bu metodu arqumentsiz çağırsaq, bütün fontlar lüğətini döndürər. 
\\\\\\\If you call this method with no arguments, it returns a dictionary of all the font metrics. You can retrieve the value of just one metric by passing its name as an argument. Metrics include:

| Yazılışı | İzahı |
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




## tkk-modulu-haqqında

## Paketlərin-import-edilməsi

## Widget-stilləri

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

## Bonus-Kitablar
- <a href="https://web.archive.org/web/20190524140835/https://infohost.nmt.edu/tcc/help/pubs/tkinter/web/index.html">Tkinter 8.5</a> reference
- <a href="https://coderslegacy.com/python/python-gui/">CodersLegacy</a> blogs Python GUI
