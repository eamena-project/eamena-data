# Calculate the number of Heritage Places by Grid Squares

1. **R**. Calculate the number of Heritage Places by Grid Squares and export as a GeoJSON (folder `year_2024`) with the [ref_hps()](https://github.com/eamena-project/eamenaR?tab=readme-ov-file#grids) function (eamenaR package)

```R
d <- hash::hash()
d <- ref_hps(db.con = db.con,
             d = d,
             stat = "grid",
             stat.name = "eamena_hps_by_grids",
             date.before = NA)
geoj <- merge(d$grid_geom, d$grid_nb, by = 'gs', all.x = TRUE)
geoj <- geoj[!is.na(geoj$nb_hp), ]
sf::st_write(geoj, "C:/Rprojects/eamena-data/working_data/hp_by_gs_nb/year_2024/nb_hp_by_grids.geojson", driver = "GeoJSON")
```

2. **Python**. Retrieve surveyed grid squares having 0 Heritage places (i.e, the file `gs_with_0_hp.csv`) using the function [gs_with_0_hp()](https://github.com/eamena-project/eamena-functions/blob/c4069cf8063c9aa406becfd58cfb535745c3d8a9/business_data.py#L232)

```py
gs_0_hp = gs_with_0_hp()
```
For local changes in the Json file
```
gs_0_hp = gs_with_0_hp(gkey="/Users/salahebrahimipour/Desktop/EAMENA/eamena-arches-dev/credentials/gsheet-407918-65ebbb9cb656.json")
```
```
gs_0_hp.to_csv('C:/Rprojects/eamena-data/working_data/hp_by_gs_nb/year_2024/gs_with_0_hp.csv', index=False)
```

3. **Python**. Merge the two dataset (i.e, GS with HP and GS without HP)

```py
updated_geo_df = hp_by_gs_nb(nb_hp_gs='C:/Rprojects/eamena-data/working_data/hp_by_gs_nb/year_2024/nb_hp_by_grids.geojson', gs_with_0_hp='C:/Rprojects/eamena-data/working_data/hp_by_gs_nb/year_2024/gs_with_0_hp.csv',  verbose=True)
updated_geo_df.to_file('C:/Rprojects/eamena-data/working_data/hp_by_gs_nb/year_2024/nb_hp_by_grids_including_0_hp.geojson', driver='GeoJSON')
```

4. **QGIS**. Layout the GeoJSON file `nb_hp_by_grids_including_0_hp.geojson` in QGIS (project: [grids_nb_hp.qgz](https://github.com/eamena-project/eamena-data/blob/main/working_data/hp_by_gs_nb/grids_nb_hp.qgz))
