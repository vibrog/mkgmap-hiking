
# mkgmap style for OSM hiking maps

[Style rules][1] and [TYP definitions][2] for making a
hiking map from [OpenStreetMap](http://www.openstreetmap.org/) data
for a [Garmin GPS][3] using [mkgmap][4].
The cartography is adopted from hiking maps by
[Asker Skiklubb](http://asker-skiklubb.no/)
and a [symbol standard][5] from the
[Norwegian Mapping Authority](http://www.kartverket.no/).

Build the TYP file from `hiking_typdef.txt` with [cGPSmapper][6].
Then build the map file using mkgmap:

    sty=$mkgmap_style_folder/hiking
    mkgmap="java -Xmx1536M -jar $java_home/mkgmap.jar"
    $mkgmap -c $sty/arguments --style-file=$sty $osm_data_folder/*.osm{,.gz}
    $mkgmap -c $sty/arguments --gmapsupp $sty/ID984.TYP [0-9]*.img

For large areas you'll need to use a splitter.

An example map file covering [Oslomarka][8] is available at
<http://www.vidargundersen.com/hikingtrails.img>
To install, simply copy it to the `Garmin` folder on the GPS memory card.
Rename to `gmapsupp.img` on 60CSx.

Created by Vidar Bronken Gundersen.
[CC BY][9]

[1]: http://wiki.openstreetmap.org/wiki/Mkgmap/help/style_rules
[2]: http://wiki.openstreetmap.org/wiki/Mkgmap/help/TYP_files
[3]: http://www.garmin.com/us/products/onthetrail
[4]: http://www.mkgmap.org.uk/
[5]: http://www.kartverket.no/globalassets/standard/bransjestandarder-utover-sosi/symbol.pdf
  "Symbolfonter for friluftsliv og sport (1997). Statens kartverk Landkartdivisjonen, ISBN 82-90408-52-8"
[6]: http://www.cgpsmapper.com/
[8]: http://no.wikipedia.org/wiki/Marka_(Oslo)
[9]: http://creativecommons.org/licenses/by/4.0/
