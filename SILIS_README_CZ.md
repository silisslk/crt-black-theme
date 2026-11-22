# SILIS Black – zjednodušená verze 0.6

- CRT šum a šedé vlny se plynule a nepravidelně hýbou samostatně, bez synchronizace na zvuk.
- Zvuk potoka zůstává jako standardní `sound/bgm.mp3` přehrávaný běžným audio systémem Open MainUI.
- Původní mechanismus vypnutí hudby při uspání a ukončení při odchodu z MainUI zůstává beze změn.
- Velké ikony hlavního menu a vodorovný výběr her z V0.5 zůstávají zachovány.
- Nastavení napájení OnionOS není změněno.

## Ověření
Úprava odstraňuje závislost CRT rendereru na zvukové obálce. Kontrolní překlad lze udělat s SDL 1.2 development headers. Pro Miyoo je nutný odpovídající ARM toolchain a SDK (viz docs/BUILDING.md).

**Nejde o instalační ARM sestavení.** Na konzoli zatím nepřepisujte `.tmp_update/bin/MainUI`.
