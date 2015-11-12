#Scottish QGIS User Group Workshop

======

##By:
Heikki Vesanto
thinkWhere.com

======

## Instuctions:
Either "Download ZIP" on the right to download all the data as a zip and unzip it onto your own drive.

Or clone the repo if you are familiar with Git.

All steps will be covered on the day. And you only need the data and QGIS.

Version 2.8.3 is recommended the LTS release. But anything above 2.8 will also work.

======

###Steps that will be covered during the day:

Create Overview Preset

Create Composer

Add 2 Maps

Set presets to maps.

Create copyright statement.

Contains Ordnance Survey data © Crown copyright and database right 2015

Bottom map, 2 million scale.

Set bottom map as an overview. Invert overview, Center on overview.

Atlas generation.

Generate an atlas.
Coverage layer: Westmister Const Region - Main Map

Set top map to be controlled by Atlas.

Done.

Improvements:
Title
Change hid the areas outside of the atlas.

Add label.

[%'Constituency:
'  ||   "NAME" %]

Back to QGIS.

Westminster const symbology:

Red outline:
 $id  =  $atlasfeatureid
Grey area:
 $id <>  $atlasfeatureid

Set rendering order. Red to 1.

Return to composer. Unlock layer styles for top map.

Done! Again.

But we cant really tell much from our overview map.

Lets change this.

Back to QGIS:

UK admin
Lighter gray:
 "SUBUNIT"  = attribute( $atlasfeature, 'SubUnit')
Darker gery:
 "SUBUNIT"  <> attribute( $atlasfeature, 'SubUnit')
Lighter gray:
 "SUBUNIT"  = attribute( $atlasfeature, 'SubUnit')
 
Westminster const region Overview:
 $atlasfeatureid  =  $id

Create overview 2.

Final Done! But:

The labels are a bit busy. Hide the ones not in the atlas feature.

OS Strategi
settlement_seed
Labels - Rendering
Show label:
intersects(  $geometry , $atlasgeometry )

Finally print it out.

Named:
$feature  || '_const_' ||  "FILE_NAME" 