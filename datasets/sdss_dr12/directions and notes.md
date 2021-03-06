## SDSS DR12

These are the notes and directions for populating the SDSS imaging data. This is comprised of a catalog and imaging. Here I have designed a new schema that improves upon that found in CAS.

### PhotoObj Catalog

##### File Organization

The root location of the DR12 data release is here:
<http://data.sdss3.org/sas/dr12/boss/photoObj/301/>

The data model for SDSS-III data is located here: <http://data.sdss3.org/datamodel/>

Each directory is a plate ID. Within each plate directory is a directory for each camcol (1-6), a [photoField](http://data.sdss3.org/datamodel/files/BOSS_PHOTOOBJ/RERUN/RUN/photoField.html) file, and a [photoRun file](http://data.sdss3.org/datamodel/files/BOSS_PHOTOOBJ/RERUN/RUN/photoRun.html). Within each camcol directory are the [photoObj](http://data.sdss3.org/datamodel/files/BOSS_PHOTOOBJ/RERUN/RUN/CAMCOL/photoObj.html) files.

##### Import Order

There are three scripts to populate the database. The execution order is very important as each successive script creates objects that expects to reference the fields created before it.

 1. `photoRun2db.py`
 2. `photoField2db.py`
 3. `photoObj2db.py`
 
### Imaging Data

The root location of the imaging data is here:
<http://data.sdss3.org/sas/dr12/boss/photoObj/frames/301/>

There is a directory for each plate (named by plate ID). Within each plate directory is a directory for each camcol (1-6), and a `frames-run*.html` page that provides thumbnails for the plate (plus a checksum file). Within each camcol directory are the [frame](http://data.sdss3.org/datamodel/files/BOSS_PHOTOOBJ/frames/RERUN/RUN/CAMCOL/frame.html) files (imaging products) over *ugriz*.
