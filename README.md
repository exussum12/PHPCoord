PHPCoord
========

Conversion/modernisation of phpcoord for PHP5.3/PSR-0. Conversion was based on v2.3

[![Build Status](https://travis-ci.org/Pre-schoolLearningAlliance/PHPCoord.png)](https://travis-ci.org/Pre-schoolLearningAlliance/PHPCoord)

The original code by Jonathan Stott can be found at http://www.jstott.me.uk/phpcoord/

PHPCoord is a set of PHP functions for handling various
co-ordinate systems and converting between them. Currently, OSGB (Ordnance
Survey of Great Britain) grid references, UTM (Universal Transverse
Mercator) references and latitude/longitude are supported. A function is 
also provided to find the surface distance between two points of latitude
and longitude.

When using the OSGB conversions, the majority of applications use the
WGS84 datum rather than the OSGB36 datum. Conversions should be accurate to
within 5m or so. If accuracy is not important (i.e. to within 200m or so),
then it isn't necessary to perform the conversions.

Usage
-----
```php
$OSRef = new OSRef(500000, 200000); //Easting, Northing
$LatLng = $OSRef->toLatLng();
$LatLng->OSGB36ToWGS84(); //optional, see note above

$lat =  $LatLng->lat;
$long = $LatLng->long;


$LatLng = new LatLng(50.12345, 1.23456); //Latitude, Long
$OSRef = $LatLng->toOSRef(); 

$easting = $OSRef->easting;
$northing = $OSRef->northing;

```

Requirements
------------
* PHP 5.3 or higher

License
-------
The original PHPcoord is GPL-licensed, and this version inherits that. Terms can be found at http://www.gnu.org/licenses/gpl.html 