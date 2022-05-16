# Dvorus keyboard layout (English, Russian)

Dvorus is a keyboard layout for touch-typing. It can be very useful for programmers, especially for Vim users who tend to use special character extensively, and Emacs users who'd better have Ctrl and Alt keys "at hand".
It utilizes a similar principle as the Dvorak layout,
but adds also a pair of its own features; it can be summarized as follows:
- split sounds to vowels (on the left) and consonants (on the right) — roughly like in Dvorak
- all alphabetic keys positions should be "squeezed" together to avoid accidental misses when moving fingers
- minimize hands movement: Ctrl and Alt keys should be always easily available for thumbs
- major row shifted up one row — follows from 2 points above (though may be inconvenient e.g. for short fingers)
- extensive usage of levels for special symbols so they can be "at hand", e.g. accessible with minimal hand movement. Hence AltGr Latch is placed under the right ring finger
- Shift is also easily accessible as a latch key — under left pinkey
- Positions of other modifiers are changed: BackSpace is near left pinkey, Esc either
- (optional) Aligned English/Russian letters positions which make it simple to memoize the layout (hence the name: DVOrak-RUS)

## English layout
```
 ┌─────┐
 │Caps │
 │Lock │
 └─────┘
 ┌─────┬─────┬─────┬─────┬─────┬─────┬─────┬─────┬─────┬─────┬─────┬─────┬─────┬──────────┐  
 │AltGr│ Q   │ K @ │ Y # │ U $ │ | & │     │     │ D ≤ │ L ≥ │ M { │ B } │ Z ` │          │
 │latch│ q   │ k @ │ y # │ u $ │ ' & │  ←  │  →  │ d < │ l > │ m { │ b } │ z ` │   Tab ↹  │  
 ├─────┴──┲━━┷━━┳━━┷━━┳━━┷━━┳━━┷━━┱──┴──┬──┴──┬──┴──┲━━┷━━┳━━┷━━┳━━┷━━┳━━┷━━┱──┴──┬───────┤
 │<- Back ┃Shift┃ S [ ┃ O ] ┃ E _ ┃ A \ │     │ R   ┃ N " ┃ W — ┃AltGr┃ V % ┃ J   │ Enter │
 │   space┃Latch┃ s [ ┃ o ] ┃ e _ ┃ a \ │  ↑  │ r ; ┃ n " ┃ w : ┃latch┃ v % ┃ j ~ │   ⏎   │  
 ├────────┺┯━━━━┻┯━━━━┻┯━━━━┻┯━━━━┹┬────┴┬────┴┬────┺┯━━━━┻┯━━━━┻┯━━━━┻┯━━━━┹┬────┴┐      │  
 │         │ ! . │ ? , │ P ( │ I ^ │ X ) │     │ C ± │ T ‑ │ H ≠ │ G ÷ │ F × │ | | │      │
 │ Escape  │ . . │ , , │ p ( │ i ^ │ x ) │  ↓  │ c + │ t - │ h = │ g / │ f * │ \ \ │      │
 ├─────────┴─┬───┴─┬───┴─┬───┴─┬───┴─┬───┴─┬───┴─┬───┴─┬───┴─┬───┴─┬───┴─┬───┴─────┴──────┤  
 │           │     │     │     │     │     │     │     │     │     │     │                │  
 │  Grp1=En  │  0  │  1  │  2  │  3  │  4  │  5  │  6  │  7  │  8  │  9  │    Grp2=Ru     │  
 ├────────┬──┴────┬┴─────┴┬────┴─────┴─────┴─────┴─────┴─────┴┬────┴──┬──┴────┬───────┬───┘
 │        │       │       │                                   │       │       │       │
 │  Alt   │Windows│ Ctrl  │                Space              │  Alt  │ Menu  │ Ctrl  │
 └────────┴───────┴───────┴───────────────────────────────────┴───────┴───────┴───────┘
```

## Installation & Configuration
### Linux X11, with key code remapping (the reccomended way)
```
xkbcomp "dvorus_us_evdev_remap.xkb" $DISPLAY
```

#### Linux console & X11 DM login screen
Append contents of `us_dvorus` to `/usr/share/X11/xkb/symbols/us`.
Use ckbcomp to convert from xkb to kmap files. In Debian-based distributions this is done automatically by `dpkg-reconfigure keyboard-configuration` or, equivalently by manually editing `/etc/default/keyboard`:
```
XKBLAYOUT="us"
XKBVARIANT="dvorus"
```
In Ubuntu one needs to edit `/etc/default/keyboard`, then run `dpkg-reconfigure`
confirming that he wants to keep the layout, after which layout seems to be
compiled into kernel/initramfs.

Xkb symbols can be loaded manually by those commands (NOT recommended):
```
setxkbmap -layout us -variant dvorus
```

### Windows

It's done in 3 steps:
- Install shared libraries (which were biult by Microsoft MSKLC), select "dvorus" variants in Language Configuration
- Load supplied dvorus.skl in SharpKeys (version ≥ 3.7)
- Make modifiers sticky (configuration dialog can be raised by pressing e.g. Shift key a few times)

## Russian layout — Русская раскладка
```
 ┌─────┐
 │Caps │
 │Lock │
 └─────┘
 ┌─────┬─────┬─────┬─────┬─────┬─────┬─────┬─────┬─────┬─────┬─────┬─────┬─────┬──────────┐  
 │AltGr│ Ю   │ Ы @ │ Я № │ У ₽ │ Ь Ъ │     │     │ Д ≤ │ Л ≥ │ М „ │ Б “ │ З   │          │
 │latch│ ю " │ ы @ │ я № │ у ₽ │ ь ъ │  ←  │  →  │ д < │ л > │ м « │ б » │ з   │   Tab ↹  │  
 ├─────┴──┲━━┷━━┳━━┷━━┳━━┷━━┳━━┷━━┱──┴──┬──┴──┬──┴──┲━━┷━━┳━━┷━━┳━━┷━━┳━━┷━━┱──┴──┬───────┤
 │<- Back ┃Shift┃ С Ш ┃ О Ё ┃ Е Э ┃ А \ │     │ Р   ┃ Н Щ ┃ В — ┃AltGr┃ Ч % ┃ Й   │ Enter │
 │   space┃Latch┃ с ш ┃ о ё ┃ е э ┃ а \ │  ↑  │ р ; ┃ н щ ┃ в : ┃latch┃ ч % ┃ й ~ │   ⏎   │  
 ├────────┺┯━━━━┻┯━━━━┻┯━━━━┻┯━━━━┹┬────┴┬────┴┬────┺┯━━━━┻┯━━━━┻┯━━━━┻┯━━━━┹┬────┴┐      │  
 │         │ ! . │ ? , │ П ( │ И Ц │ Ж ) │     │ К ± │ Т ‑ │ Х ≠ │ Г ÷ │ Ф × │ | | │      │
 │ Escape  │ . . │ , , │ п ( │ и ц │ ж ) │  ↓  │ к + │ т - │ х = │ г / │ ф * │ \ \ │      │
 ├─────────┴─┬───┴─┬───┴─┬───┴─┬───┴─┬───┴─┬───┴─┬───┴─┬───┴─┬───┴─┬───┴─┬───┴─────┴──────┤  
 │           │     │     │     │     │     │     │     │     │     │     │                │  
 │  Grp1=En  │  0  │  1  │  2  │  3  │  4  │  5  │  6  │  7  │  8  │  9  │    Grp2=Ru     │  
 ├────────┬──┴────┬┴─────┴┬────┴─────┴─────┴─────┴─────┴─────┴┬────┴──┬──┴────┬───────┬───┘
 │        │       │       │                                   │       │       │       │
 │  Alt   │Windows│ Ctrl  │                Space              │  Alt  │ Menu  │ Ctrl  │
 └────────┴───────┴───────┴───────────────────────────────────┴───────┴───────┴───────┘
```

## Установка и конфигурирование
### Linux X11 с переназначением клавиш (рекомендуемый способ)
Наберите команду (с полным путём файла):
```
xkbcomp "dvorus_us_ru_evdev_remap.xkb" $DISPLAY
```

#### Консоль Linux & менеджер входа X11 DM
Добавьте содержимое us_dvorus в конец /usr/share/X11/xkb/symbols/us, аналогично и для "ru".
Используйте ckbcomp чтобы сконвертировать из xkb в kmap. В дистрибутивах на основе Debian это делается автоматически либо с помощью `dpkg-reconfigure keyboard-configuration`, либо редактированием файла `/etc/default/keyboard`:
```
XKBLAYOUT="us,ru"
XKBVARIANT="dvorus,dvorus"
```
Символьную часть Xkb можно загрузить и в ручную (НЕ рекомендуется):
```
setxkbmap -layout us,ru -variant dvorus,dvorus
```

### Windows

Это делается в 3—4 шага:
- Установите .dll-библиотеки (собранные программой Microsoft MSKLC), выберите вариант DvorusEn и DvorusRu в настройках языка
- Загрузите файл dvorus.skl в SharpKeys (версии ≥ 3.7)
- Сделайте модификаторы залипающими (соответствующий диалог можно вызвать, нажав клавишу Shift несколько раз подряд)
- (опционально, рекомендуется) Назначьте переключение раскладок по (бывшей) клавише ```/~/Ё``.

