## Task 1
# Site Plan Georeference and Digitization 

## Table of Content
- [Site Plan Georeference and Digitization](#site-plan-georeference-and-digitization)
  - [Table of Content](#table-of-content)
  - [Description](#description)
    - [Requirements](#requirements)
  - [Documentation](#documentation)
    - [Step 1. Preparation](#step-1-preparation)
    - [Step 2. Open the Base Map Vector Files](#step-2-open-the-base-map-vector-files)
    - [Step 3. Georeference the Screenshot of Spesific Area from Google Maps](#step-3-georeference-the-screenshot-of-spesific-area-from-google-maps)
      - [Step 3a. Take Some Screenshots from the Google Maps](#step-3a-take-some-screenshots-from-the-google-maps)
      - [Step 3b. Georeferencing Screenshot Part I](#step-3b-georeferencing-screenshot-part-i)
      - [Step 3c. Georeferencing Screenshot Part II](#step-3c-georeferencing-screenshot-part-ii)
    - [Step 4. Georeference the Site Plan File](#step-4-georeference-the-site-plan-file)
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
1. Open QGIS Project.
2. Make new project (ctrl-N).
3. Open base map vector files of Sidoarjo district.
    * Click **Add Vector Layer** (marked by red rectangle).
  
      ![screenshot-1](/georeference-site-plan/img/1.png "Figure 1")

    * Click **browse**.
  
      ![screenshot-2](/georeference-site-plan/img/2.png "Figure 2")

    * Select all the **.shp** files, then click **open**.
  
      ![screenshot-3](/georeference-site-plan/img/3.png "Figure 3")

    * The Coordinate Reference System Selector dialogue will come out. Just leave it default **(WGS 84)**, then click **OK**.
  
      ![screenshot-4](/georeference-site-plan/img/4.png "Figure 4")
   
4. All the **.shp** files are loaded, then set and sort the files as needed. We can swap the position (just drag and drop), press the check mark to disable or enable, change the color, or remove them.
  
    ![screenshot-5](/georeference-site-plan/img/5.png "Figure 5")

    I just enable the **jalan_kec_sidoarjo** or the Sidoarjo street vector and **bts_kel_sidoarjo** or the Sidoarjo district borderline as the base map vector for now, but maybe I'll enable the others as needed.

    ![screenshot-6](/georeference-site-plan/img/6.png "Figure 6")


### Step 3. Georeference the Screenshot of Spesific Area from Google Maps

#### Step 3a. Take Some Screenshots from the Google Maps
1. Take a screenshot of **Bluru Kidul Village** area because the site plan is located on Bluru Kidul Village.

    ![screenshot-bluru-kidul](/georeference-site-plan/img/desa-bluru-kidul.png "Figure 7")

2. Take a screenshot again of **Puskopkar** area to make the maps more detail.
   
    ![screenshot-puskopkar](/georeference-site-plan/img/puskopkar.png "Figure 8")

#### Step 3b. Georeferencing Screenshot Part I

1. Install the **Georeferencer GDAL** plugin first. Click **Plugins** menu > **Manage and Install Plugins** > Search **Georeference GDAL** > Check the box to enable the plugin

    ![screenshot-7](/georeference-site-plan/img/7.png "Figure 9")

2. To do georeferencing, click the **Raster** menu > Select **Georeferencer** > Click **Georeferencer**, then a georeferencer dialogue will come out. Click **Open Raster**.

    ![screenshot-8](/georeference-site-plan/img/8.png "Figure 10")

3. Choose the **Bluru Kidul Village Screenshot** and always use **WGS 84** as coordinate reference system.
4. Click **Add Point** to tag some georeference points on **Raster Image** and **Vector Image** (at least 3 points, more is better).
   
    ![screenshot-9](/georeference-site-plan/img/9.png "Figure 11")
   
5. After add some points, then click **Start Georeferencing**.
   
    ![screenshot-10](/georeference-site-plan/img/10.png "Figure 12")

    Follow the transformation settings below. I use **Polynomial 1** transformation type. The Polynomial algorithms 1-3 are among the most widely used algorithms introduced to match source and destination ground control points. Polynomial 1 preserves collinearity and allows scaling, translation and rotation only.

    ![screenshot-11](/georeference-site-plan/img/11.png "Figure 13")

    Georeferencing the screenshot of Bluru Kidul Village from google maps done with mean error **0.291192** (can be seen in figure 12).

    ![screenshot-12](/georeference-site-plan/img/12.png "Figure 14")

#### Step 3c. Georeferencing Screenshot Part II

### Step 4. Georeference the Site Plan File
### Step 5. Site Plan Digitizing










<!-- > More documentation: https://github.com/mocatfrio/GIS-2018 -->