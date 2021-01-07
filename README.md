# WRF-CORINE
WRF source codes for using CORINE land use with NOAH-MP  - geogrid data is found at pangaea.de

CORINE 2012 Land Cover data (v2020 - [https://land.copernicus.eu/pan-european/corine-land-cover/clc-2012]) is added to the USGS adataset as a secondary layer. Where there is no CORINE data the database will be the USGS set. The default dataset in the GEOGRID.TBL can be choosen freely, but it must be an USGS variant. Curently the landuse_with_lakes_30s version is set as default. Because the only way to add is to expand a dataset, the CORINE categories has a higher code number, instead of 1 to 44, 41 to 88 is used, while the original USGS categories are left unchanged. Two categories, the Broad-leaved forests (3.1.1 - \[23\]), and Coniferous forests (3.1.2 - \[24\]) are recategorised into: Broad-leaved evergreen forest \[45\],	Broad-leaved deciduous forest \[46\],	Coniferous evergreen forest \[47\],	Coniferous deciduous forest \[48\] categories using the ESA CCI Land cover data ([http://www.esa-landcover-cci.org/], version: ESACCI-LC-L4-LCCS-Map-300m-P1Y-2012-v2.0.7b), where the CORINE land cover was equal to the ESA land cover (e.g. where there are broad-leaved forests in CORINE and either BL evergreen or deciduous the gridpoint was assigned a new category). 

Application:
1) link the GEOGRID.TBL.ARW_noahmp to GEOGRID.TBL and modify the default LANDUSE dataset to your preferred one.
2) overwrite the source codes found in the WRF-4.2/phys folder with the supplied ones. 
3) in the namelist.input set num_land_cat to 88
4) link the supplied \*.TBL files to their default ones
5) CURRENTLY ONLY WORKS WITH URBAN_PHYS=0, AND NOAH-MP (urban inclusion is on its way)

Source code modification places: look for !CORINE in the .F files. 




