# Partitioning and Sorting

## Geo-sorted ohsome contributions

### 1st level partition

| attribute name | value   | description |
|----------------|---------|-------------|
| status         | latest  |             |
| status         | history |             |
| status         | deleted |             |
| status         | invalid |             |


```
  222.3 GiB [#########################] /status=latest                                                                                                                          
  195.7 GiB [######################   ] /status=history                                                                                                                         
   27.2 GiB [###                      ] /status=deleted                                                                                                                         
  540.0 KiB [                         ] /status=invalid   
```

### 2nd level partition

| attribute name | value              | description |
|----------------|--------------------|-------------|
| geometry_type  | Point              |             |
| geometry_type  | LineString         |             |
| geometry_type  | Polygon            |             |
| geometry_type  | MultiPolygon       |             |
| geometry_type  | GeometryCollection |             |
| geometry_type  | InvalidGeometry    |             |


```
--- /data/processing/ohsome-parquet/contributions/contributions/status=latest --------------------------------------------------------------------------------------------------
                                        /..                                                                                                                                     
  115.0 GiB [#########################] /geometry_type=Polygon                                                                                                                  
   63.4 GiB [#############            ] /geometry_type=LineString                                                                                                               
   36.6 GiB [#######                  ] /geometry_type=Point                                                                                                                    
    5.0 GiB [#                        ] /geometry_type=GeometryCollection                                                                                                       
    2.1 GiB [                         ] /geometry_type=MultiPolygon                                                                                                             
  243.2 MiB [                         ] /geometry_type=InvalidGeometry      
```

```
--- /data/processing/ohsome-parquet/contributions/contributions/status=history -------------------------------------------------------------------------------------------------
                                        /..                                                                                                                                     
   90.6 GiB [#########################] /geometry_type=LineString                                                                                                               
   59.9 GiB [################         ] /geometry_type=Polygon                                                                                                                  
   44.7 GiB [############             ] /geometry_type=Point                                                                                                                    
  488.4 MiB [                         ] /geometry_type=InvalidGeometry      
```

```
    9.8 GiB [#########################] /geometry_type=Polygon                                                                                                                  
    9.0 GiB [######################   ] /geometry_type=Point                                                                                                                    
    8.3 GiB [####################     ] /geometry_type=LineString                                                                                                               
   59.9 MiB [                         ] /geometry_type=InvalidGeometry   
```

```
  396.0 KiB [#########################] /geometry_type=Point                                                                                                                    
   96.0 KiB [######                   ] /geometry_type=LineString                                                                                                               
   44.0 KiB [##                       ] /geometry_type=InvalidGeometry    
```


### Sorting

| attribute name | value | description |
|----------------|-------|-------------|
| xzcode.code    | -     |             |



## Time-sorted ohsome contributions

### Partitions


### Sorting