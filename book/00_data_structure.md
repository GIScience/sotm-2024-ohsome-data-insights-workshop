# Data Structure

## General OSM Attributes

| attribute name | data type             | description                                                      |
|----------------|-----------------------|------------------------------------------------------------------|
| user_id        | INTEGER               |                                                                  |
| valid_from     | TIMESTAMP             |                                                                  |
| valid_to       | TIMESTAMP             |                                                                  |
| osm_type       | VARCHAR               |                                                                  |
| osm_id         | VARCHAR               |                                                                  |
| osm_version    | INTEGER               |                                                                  |
| contrib_type   | VARCHAR               |                                                                  |
| status         | VARCHAR               | Potential values are: `latest`, `history`, `deleted`, `invalid`. |
| tags           | MAP(VARCHAR, VARCHAR) |                                                                  |
| tags_before    | MAP(VARCHAR, VARCHAR) |                                                                  |

## OSM Changeset Attributes

| attribute name      | data type             | description |
|---------------------|-----------------------|-------------|
| changeset           | STRUCT                |             |
| changeset.id        | BIGINT                |             | 
| changeset.timestamp | TIMESTAMP             |             | 
| changeset.tags | MAP(VARCHAR, VARCHAR) |             |
| changeset.hashtags | VARCHAR[]             |             |
| changeset.editor | VARCHAR               |             |

## Geographic Attributes

| attribute name | data type | description                                                                                                                                                                                                                                                                                                                               |
|----------------|-----------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| area           | BIGINT    | The area of the OSM element in m². Will always be `0` for the following geometry types: `Point`, `LineString`, `GeometryCollection`.                                                                                                                                                                                                      |
| area_delta     | BIGINT    |                                                                                                                                                                                                                                                                                                                                           |
| length         | BIGINT    | The length of the OSM element in m. Will always be `0` for the following geometry types: `Point`, `Polygon`, `MultiPolygon`, `GeometryCollection`.                                                                                                                                                                                                                                                                                                                                              |
| length_delta   | BIGINT    |                                                                                                                                                                                                                                                                                                                                           |
| xzcode         | STRUCT    |                                                                                                                                                                                                                                                                                                                                           |
| xzcode.level   | INTEGER   |                                                                                                                                                                                                                                                                                                                                           |
| xzcode.code    | BIGINT    |                                                                                                                                                                                                                                                                                                                                           |
| country_iso_a3 | VARCHAR[] |                                                                                                                                                                                                                                                                                                                                           |
| bbox           | STRUCT    |                                                                                                                                                                                                                                                                                                                                           |
| bbox.xmin      | DOUBLE    |                                                                                                                                                                                                                                                                                                                                           |
| bbox.ymin      | DOUBLE    |                                                                                                                                                                                                                                                                                                                                           |
| bbox.xmax      | DOUBLE    |                                                                                                                                                                                                                                                                                                                                           |
| bbox.ymax      | DOUBLE    |                                                                                                                                                                                                                                                                                                                                           |
| xmin           | DOUBLE    |                                                                                                                                                                                                                                                                                                                                           |
| xmax           | DOUBLE    |                                                                                                                                                                                                                                                                                                                                           |
| ymin           | DOUBLE    |                                                                                                                                                                                                                                                                                                                                           |
| ymax           | DOUBLE    |                                                                                                                                                                                                                                                                                                                                           |
| centroid       | STRUCT    |                                                                                                                                                                                                                                                                                                                                           |
| centroid.x     | DOUBLE    |                                                                                                                                                                                                                                                                                                                                           |
| centroid.y     | DOUBLE    |                                                                                                                                                                                                                                                                                                                                           |
| quadkey_z10    | VARCHAR   | Quadkey hierarchical geospatial index at zoom level 10. We have used the OSM element centroid location to determine the Quadkey ID. There are around 1 Million Quadkeys at this level globally. Check [Bing Maps Tile System](https://learn.microsoft.com/en-us/azure/azure-maps/zoom-levels-and-tile-grid?tabs=csharp) for more details. |
| h3_r5          | UBIGINT   | Cell ID in H3 hierarchical geospatial index at resolution level 5. We have used the OSM element centroid location to determine the H3 cell ID. There are about 2 Million cells at this level globally. The cell size varies between 150 - 300 km². Check [H3 docs](https://h3geo.org/docs/) for more details.                             |
| geometry_type  | VARCHAR   | Potential values are: `Point`, `LineString`, `Polygon`, `MultiPolygon`, `GeometryCollection`, `InvalidGeometry`.                                                                                                                                                                                                                          |
| geometry_valid | BOOLEAN   |                                                                                                                                                                                                                                                                                                                                           |
| geometry       | VARCHAR   | The geometry of the OSM element in [WKT format](https://en.wikipedia.org/wiki/Well-known_text_representation_of_geometry).                                                                                                                                                                                                                |


## Special Attributes for OSM Map Features

| attribute name                | data type  | description |
|-------------------------------|------------|-------------|
| map_features                  | STRUCT     |             |
| map_features.aerialway        | BOOLEAN    |             |
| map_features.aeroway          | BOOLEAN    |             |
| map_features.amenity          | BOOLEAN    |             |
| map_features.barrier          | BOOLEAN    |             |
| map_features.boundary         | BOOLEAN    |             |
| map_features.building         | BOOLEAN    |             |
| map_features.craft            | BOOLEAN    |             |
| map_features.emergency        | BOOLEAN    |             |
| map_features.geological       | BOOLEAN    |             |
| map_features.healthcare       | BOOLEAN    |             |
| map_features.highway          | BOOLEAN    |             |
| map_features.historic         | BOOLEAN    |             |
| map_features.landuse          | BOOLEAN    |             |
| map_features.leisure          | BOOLEAN    |             |
| map_features.man_made         | BOOLEAN    |             |
| map_features.military         | BOOLEAN    |             |
| map_features.natural          | BOOLEAN    |             |
| map_features.office           | BOOLEAN    |             |
| map_features.place            | BOOLEAN    |             |
| map_features.power            | BOOLEAN    |             |
| map_features.public_transport | BOOLEAN    |             |
| map_features.railway          | BOOLEAN    |             |
| map_features.route            | BOOLEAN    |             |
| map_features.shop             | BOOLEAN    |             |
| map_features.sport            | BOOLEAN    |             |
| map_features.telecom          | BOOLEAN    |             |
| map_features.water            | BOOLEAN    |             |
| map_features.waterway         | BOOLEAN    |             |


## Special Attributes for OSM Relations

| attribute name   | data type | description |
|------------------|-----------|-------------|
| members          | STRUCT    |             |
| members.type     | VARCHAR   |             |
| members.id       | BIGINT    |             |
| members.role     | VARCHAR   |             |
| members.geometry | BLOB      |             |