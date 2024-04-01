# bluhende_Baume

Map visulaization of trees with pretty flowers in Berlin based on open data

# Work log, how to repeat this project

## 1. Discover the dataset. Get all available features.
https://fbinter.stadt-berlin.de/fb/wfs/data/senstadt/s_wfs_baumbestand?SERVICE=WFS&REQUEST=GetCapabilities

```
<ows:Value>application/json</ows:Value>
<ows:Value>application/geo+json</ows:Value>
```

```
<ows:WGS84BoundingBox>
    <ows:LowerCorner>13.079 52.3284</ows:LowerCorner>
    <ows:UpperCorner>13.7701 52.6877</ows:UpperCorner>
</ows:WGS84BoundingBox>
```

```
<wfs:FeatureTypeList>
<wfs:FeatureType>
<wfs:Name>fis:s_wfs_baumbestand</wfs:Name>
<wfs:Title>Baumbestand Berlin - Straßenbäume - Sachdaten zur Karte</wfs:Title>
<wfs:Abstract>Sachdaten zu Straßenbäumen mit Angaben zur Baumart, Adresse, Pflanzjahr, Höhe etc.</wfs:Abstract>
<wfs:DefaultCRS>urn:ogc:def:crs:EPSG:6.9:25833</wfs:DefaultCRS>
<wfs:OutputFormats>
<wfs:Format>text/xml; subtype=gml/2.1.2</wfs:Format>
<wfs:Format>text/xml; subtype=gml/3.1.1</wfs:Format>
<wfs:Format>text/xml; subtype=gml/3.2.1</wfs:Format>
</wfs:OutputFormats>
<ows:WGS84BoundingBox>
<ows:LowerCorner>13.079 52.3284</ows:LowerCorner>
<ows:UpperCorner>13.7701 52.6877</ows:UpperCorner>
</ows:WGS84BoundingBox>
<wfs:MetadataURL xlink:href="https://fbinter.stadt-berlin.de/fb/csw?REQUEST=GetRecordById&VERSION=2.0.2&SERVICE=CSW&Id=3368004a-d596-336a-8fdf-c4391f3313dd&ELEMENTSETNAME=FULL"/>
</wfs:FeatureType>
</wfs:FeatureTypeList>
```

https://fbinter.stadt-berlin.de/fb/wfs/data/senstadt/s_wfs_baumbestand?SERVICE=WFS&version=2.0.0&REQUEST=DescribeFeatureType

https://fbinter.stadt-berlin.de/fb/wfs/data/senstadt/s_wfs_baumbestand?service=wfs&request=GetFeature&version=1.1.0&typeName=fis:s_wfs_baumbestand&FORMAT=application/json


curl -H  "Content-Type: application/geo+json" "https://fbinter.stadt-berlin.de/fb/wfs/data/senstadt/s_wfs_baumbestand?service=wfs&request=GetFeature&version=1.1.0&typeName=fis:s_wfs_baumbestand&outputFormat=application/json" -o ./trees.geojson
