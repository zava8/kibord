# kibord
## linuks keyboard layout mapping help (vindoz help in nekst section) 

```
/usr/share/X11/xkb $ ls
compat  geometry  keycodes  rules  symbols  types
/usr/share/X11/xkb $ ls -l symbols/zi
-rw-rw-r-- 1 viml viml 32327 Jul  7  2021 symbols/zi
/usr/share/X11/xkb $ cat symbols/zi
default  partial alphanumeric_keys modifier_keys
xkb_symbols "basic" {
    name[Group1]= "skovz";
    key  <KP4> {	[  A,	KP_4	]	};
    key  <KP5> {	[  D,	KP_5	]	};
    key  <KP6> {	[  H,	KP_6	]	};
    key  <KP7> {	[  T,	KP_7	]	};
    key  <KP9> {	[  N,	KP_9	]	};

    key  <KP1> {	[  KP_Home,	KP_1	]	};
    key  <KP3> {	[  KP_End,	KP_3	]	};

    key  <KP2> {	[  KP_Next,	KP_2	]	};
    key  <KP8> {	[  KP_Prior,	KP_8	]	};

    key  <KP0> {	[  underscore,	KP_0	]	};

};


/usr/share/X11/xkb $ vi rules/base.lst  # search for ! layout
# in this section add entry :
! layout
us              English (US)
zi              skovz
```
some important xkb points:[custom keyboard xkb guide][xkblink1]
to add a keyboard layout to /usr/share/X11/xkb/rules/evdev.xml

1. go to end of <layoutList> section (search for </layoutList>).
2. Add the folloving after the last </layout> tag

```
<layout>
   <configItem>
      <name>zi</name>
      <shortDescription>india_phonetical_zinglish</shortDescription>
      <description>india_phonetical_zinglish</description>
      <languageList>
         <iso639Id>inc</iso639Id>
      </languageList>
      <countryList>
         <iso3166Id>IN</iso3166Id>
      </countryList>
   </configItem>
   <variantList/>
</layout>
```
3. invoking niyu evdev, either by **sudo dpkg-reconfigure xkb-data**
3.  or by deleting the xkm files in /var/lib/xkb and either logging out and back in or just switching to a new layout and back
4. setxkbmap us # for us abc ; zi for skovz abc

<img src="nmped2.jpg"></img>
<hr/>
<img src="laptop_hin.jpg"></img>
<hr/>
<img src="zeb_kb_gurum.jpg"></img>

[xkblink1]: https://people.uleth.ca/~daniel.odonnell/blog/custom-keyboard-in-linuxx11
[nmpedimez]: nmped.jpg
