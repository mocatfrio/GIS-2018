## Task 1
# Site Plan Geo-Reference and Digitization 
By: Hafara Firdausi (05111540000043) - Geographic Information System

## Table of Content
- [Site Plan Geo-Reference and Digitization](#site-plan-geo-reference-and-digitization)
  - [Table of Content](#table-of-content)
  - [Description](#description)
    - [Requirements](#requirements)
  - [Documentation](#documentation)
    - [Step 1. Preparation](#step-1-preparation)
    - [Step 2. Open the Base Map Vector Files](#step-2-open-the-base-map-vector-files)
    - [Step 3. Geo-Reference the Screenshot of Spesific Area from Google Maps](#step-3-geo-reference-the-screenshot-of-spesific-area-from-google-maps)
    - [Step 4. Geo-Reference the Site Plan File](#step-4-geo-reference-the-site-plan-file)
    - [Step 5. Site Plan Digitizing](#step-5-site-plan-digitizing)

<!-- /code_chunk_output -->

## Description

Each student choose one site plan file to be digitized (the chosen file's number must be matched with student's attendance number which can be seen in Integra). Do geo-reference of selected site plan map, so it can be displayed on the map according to its district. Digitize the existing road sections, then present the results in the good map composing.
 
### Requirements
1. Download QGIS Project software on the official site (https://qgis.org/id/site/forusers/download.html), then install it
2. Download some materials needed:
    *  Site plan raster files (.TIFF) of some districts in Sidoarjo
    *  Base map vector files (shape file) of some districts in Sidoarjo
  
3. Screenshot of some areas selected on the google map (http://maps.google.com)

## Documentation
### Step 1. Preparation
* Environment : **Linux Mint 18.3 Sylvia**
* Software : **QGIS Project version 2.18.16**
* Site plan raster file : **18. PUSKOPKAR - TAMAN GRAHA PENTA SIDOARJO - DS. BLURU KIDUL** (my attendance number is 18)
* Base map vector file : **Sidoarjo District** (the chosen site plan is located in Sidoarjo disctrict)
* Some screenshots of specific area in the google maps, as much as needed

> All the files can be downloaded at https://intip.in/filegis2018

### Step 2. Open the Base Map Vector Files
1. Open QGIS Project
2. Make new project (ctrl-N)
3. Open base map vector files of Sidoarjo district
    * Click **Add Vector Layer** (marked by red rectangle)
      ![screenshot-1](/georeference-site-plan/img/1.png)
    * Click **browse**
      ![screenshot-2](/georeference-site-plan/img/2.png)
    * Select all the **.shp** files, then click **open**
      ![screenshot-3](/georeference-site-plan/img/3.png)
    * The Coordinate Reference System Selector dialogue will come out. Just leave it default **(WGS 84)**, then click **OK**
      ![screenshot-4](/georeference-site-plan/img/4.png)
   
4. All the **.shp** files are loaded, then set and sort the files as needed. We can swap the position (just drag and drop), press the check mark to disable or enable, change the color, or remove them.
  ![screenshot-5](/georeference-site-plan/img/5.png)
  I just enable the **jalan_kec_sidoarjo** or the Sidoarjo street vector and **bts_kel_sidoarjo** or the Sidoarjo district borderline as the base map vector for now, but maybe I'll enable the others as needed.
  ![screenshot-6](/georeference-site-plan/img/6.png)


### Step 3. Geo-Reference the Screenshot of Spesific Area from Google Maps
### Step 4. Geo-Reference the Site Plan File
### Step 5. Site Plan Digitizing










<!-- > More documentation: https://github.com/mocatfrio/GIS-2018 -->