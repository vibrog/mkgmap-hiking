
# mkgmap style for OSM hiking maps

[Style rules][10] and [TYP definitions][1] for
making a hiking map (suitable for [Oslomarka][2])
from [OpenStreetMap](http://www.openstreetmap.org/) data
for a [Garmin GPS][3] using [mkgmap][4].
The cartography is adopted from hiking maps by
[Asker Skiklubb](http://asker-skiklubb.no/) and
open [symbol][5] and [color][6] standards from the
[Norwegian Mapping Authority](http://www.statkart.no/).

Use [cGPSmapper][7] or mkgmap to build the TYP file from `hiking_typdef.txt`.
The [online TYP editor at ATI land][8] is also a neat tool.
Then build the map file using mkgmap:

    sty=$mkgmap_style_folder/hiking
    mkgmap="java -Xmx1536M -jar $java_home/mkgmap.jar"
    $mkgmap -c $sty/arguments --style-file=$sty $osm_data_folder/*.osm{,.gz}
    $mkgmap -c $sty/arguments --gmapsupp $sty/ID984.TYP [0-9]*.img

For large areas you'll need to use a splitter.

Created by Vidar Bronken Gundersen.
[CC BY][9]

[10: http://wiki.openstreetmap.org/wiki/Mkgmap/help/style_rules
[1]: http://wiki.openstreetmap.org/wiki/Mkgmap/help/TYP_files
[2]: http://no.wikipedia.org/wiki/Marka_(Oslo)
[3]: http://www.garmin.com/us/products/onthetrail
[4]: http://www.mkgmap.org.uk/
[5]: http://www.statkart.no/filestore/Standardisering/docs/symbol.pdf
  "Symbolfonter for friluftsliv og sport (1997). Statens kartverk Landkartdivisjonen, ISBN 82-90408-52-8"
[6]: http://www.statkart.no/Skjermkartografi.d25-SwJjM0n.ips
  "Spesifikasjon for skjermkartografi"
[7]: http://www.cgpsmapper.com/
[8]: http://ati.land.cz/gps/typdecomp/editor.cgi
[9]: http://creativecommons.org/licenses/by/3.0/
