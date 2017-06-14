# nyc_council_zips
Crosswalk of NYC city council districts and zip codes



Loaded the council district and zip code shapefiles into a PostgreSQL instance with PostGIS, converted to WGS-84 projection.

SQL:

SELECT coun_dist, zips.zipcode
FROM nycdist, zips
WHERE  (SELECT ST_Intersects(nycdist.geom, zips.geom)) 
