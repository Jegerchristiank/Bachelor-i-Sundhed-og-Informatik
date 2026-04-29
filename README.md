En LaTeX skabelon til specialer, Ph.D.-afhandlinger og rapporter. Skabelonen består af et logo, en billedefil, en KUstyle.sty fil og en main.tex fil.

VIGTIGT! For at dokumentet kan compile, skal man benytte XeLaTeX eller LuaLaTeX som compiler. Dette kan gøres i Overleaf ved at gå til Menu -> Settings -> Compiler -> Vælg XeLaTeX/LuaLaTeX

For at ændre detaljerne på forsiden, skal man ændre på flg. kommandoers værdi inden document-miløet:

'title' angiver titlen på projektet.
'subtitle' angiver undertitlen på projektet.
'name' angiver navnet.
'ptype' angiver titlen over navnet. I dette eksempel angiver det hvilken projekttype, der er at tale om.
'date' angiver datoen.
'advisor' angiver vejlederen.
'fpimage' angiver billedefilen på forsiden. Her indsættes adressen til billedet. Hvis intet billede ønskes, fjernes denne kommando.
'kuheaderone' og 'kuheadertwo' styrer KU-teksten øverst på forsiden.
'kucoverbackground' angiver forsidebaggrunden. Brug fx `assets/ku-cover-background-blue.png` for blå KU-grafik.
'kuheadercolor' styrer farven på KU-teksten øverst på forsiden.
