## Task 1
# Site Plan Georeference and Digitization 

## Table of Contents
- [Site Plan Georeference and Digitization](#site-plan-georeference-and-digitization)
    - [Table of Contents](#table-of-contents)
    - [Task's Description](#tasks-description)
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
    - [Credit](#credit)

<!-- /code_chunk_output -->

## Task's Description

Each student choose one site plan file to be digitized (the chosen file's number must be matched with student's attendance number which can be seen in Integra). Do geo-reference of selected site plan map, so it can be displayed on the map according to its district. Digitize the existing road sections, then present the results in the good map composing.
 
### Requirements
1. Download QGIS Project software on the official site (https://qgis.org/id/site/forusers/download.html), then install it.
2. Download some materials needed:
    *  Site plan raster files (.TIFF) of some districts in Sidoarjo.
    *  Base map vector files (shape file) of some districts in Sidoarjo.
  
3. Screenshot of some specific areas on the google maps (http://maps.google.com).

## Documentation
### Step 1. Preparation
* Environment : **Linux Mint 18.3 Sylvia**.
* Software : **QGIS Project version 2.18.16**.
* Site plan raster file : **18. PUSKOPKAR - TAMAN GRAHA PENTA SIDOARJO - DS. BLURU KIDUL** (my attendance number is 18).
* Base map vector file : **Sidoarjo District** (the chosen site plan is located in Sidoarjo district).
* Some screenshots of specific area in the google maps, as much as needed.

### Step 2. Open the Base Map Vector Files
1. Open QGIS Project.
2. Make new project (Ctrl+N).
3. Open base map vector files of Sidoarjo district.
    * Click **Add Vector Layer** on the vector toolbar (marked by red rectangle).
  
      ![screenshot-1](https://github.com/mocatfrio/GIS-2018/blob/master/georeference-site-plan/img/1.png "Figure 1")

    * Click **browse**.
  
      ![screenshot-2](https://github.com/mocatfrio/GIS-2018/blob/master/georeference-site-plan/img/2.png "Figure 2")

    * Select all the **.shp** files, then click **open**.
  
      ![screenshot-3](https://github.com/mocatfrio/GIS-2018/blob/master/georeference-site-plan/img/3.png "Figure 3")

    * The Coordinate Reference System Selector dialogue will appear. Just leave it default **(WGS 84)**, then click **OK**.
  
      ![screenshot-4](https://github.com/mocatfrio/GIS-2018/blob/master/georeference-site-plan/img/4.png "Figure 4")
   
4. All the **.shp** files are loaded, then set and sort the files as needed. We can swap the position (just drag and drop), press the check mark to disable or enable, change the color, or remove them.
  
    ![screenshot-5](https://github.com/mocatfrio/GIS-2018/blob/master/georeference-site-plan/img/5.png "Figure 5")

    I just enable the **jalan_kec_sidoarjo** or the Sidoarjo street vector and **bts_kel_sidoarjo** or the Sidoarjo district borderline as the base map vector for now, but maybe I'll enable the others as needed.

    ![screenshot-6](https://github.com/mocatfrio/GIS-2018/blob/master/georeference-site-plan/img/6.png "Figure 6")


### Step 3. Georeference the Screenshot of Spesific Area from Google Maps

#### Step 3a. Take Some Screenshots from the Google Maps
1. Take a screenshot of **Bluru Kidul Village** area because the site plan is located on Bluru Kidul Village.

    ![screenshot-bluru-kidul](https://github.com/mocatfrio/GIS-2018/blob/master/georeference-site-plan/img/desa-bluru-kidul.png "Figure 7")

2. Take a screenshot again of **Puskopkar** area to make the maps more detail.
   
    ![screenshot-puskopkar](https://github.com/mocatfrio/GIS-2018/blob/master/georeference-site-plan/img/puskopkar.png "Figure 8")

#### Step 3b. Georeferencing Screenshot Part I

1. Install the **Georeferencer GDAL** plugin first. Click **Plugins** on the menu toolbar > **Manage and Install Plugins** > Search **Georeference GDAL** > Check the box to enable the plugin

    ![screenshot-7](https://github.com/mocatfrio/GIS-2018/blob/master/georeference-site-plan/img/7.png "Figure 9")

2. To do georeferencing, click **Raster** on the menu toolbar > Click **Georeferencer** > Click **Georeferencer**, then a georeferencer dialogue will appear. Click **Open Raster**.

    ![screenshot-8](https://github.com/mocatfrio/GIS-2018/blob/master/georeference-site-plan/img/8.png "Figure 10")

3. Choose the **Bluru Kidul Village Screenshot** and always use **WGS 84** as coordinate reference system.
4. Click **Add Point** to tag some georeference points on **Raster Image** and **Vector Image**. I add 5 points in this georeference (at least 3 points, more is better).
   
    ![screenshot-9](https://github.com/mocatfrio/GIS-2018/blob/master/georeference-site-plan/img/9.png "Figure 11")
   
5. After add some points, then click **Start Georeferencing**.
   
    ![screenshot-10](https://github.com/mocatfrio/GIS-2018/blob/master/georeference-site-plan/img/10.png "Figure 12")

    Follow the transformation settings below. 

    ![screenshot-11](https://github.com/mocatfrio/GIS-2018/blob/master/georeference-site-plan/img/11.png "Figure 13")

    I use **Polynomial 1** transformation type because its preserves collinearity and allows scaling, translation and rotation. The Polynomial algorithms 1-3 are among the most widely used algorithms introduced to match source and destination ground control points.

6. Georeference of Bluru Kidul Village screenshot done with mean error **0.291192** (figure 12).

    ![screenshot-12](https://github.com/mocatfrio/GIS-2018/blob/master/georeference-site-plan/img/12.png "Figure 14")

7. Don't forget to save the **GCP Points File**.

#### Step 3c. Georeferencing Screenshot Part II
Because the map is not detailed enough to georeferencing the site plan, so I do step 3b again using the **screenshot of Puskopkar** area to make the map to be more detail. The steps are exactly the same with step 3b.

1. Click **Raster** on the menu toolbar > Click **Georeferencer** > Click **Georeferencer**, then a georeferencer dialogue will appear. Click **Open Raster**.
2. Choose the **Puskopkar Screenshot** and always use **WGS 84** as coordinate reference system.
3. Click **Add Point** to tag some georeference points on **Raster Image** and **Vector Image**. I add 5 points in this georeference (at least 3 points, more is better).
   
   ![screenshot-13](https://github.com/mocatfrio/GIS-2018/blob/master/georeference-site-plan/img/13.png "Figure 15")

4. After add some points, then click **Start Georeferencing**. Use **Polynomial 1** transformation type.
5. Georeference of Puskopkar screenshot done with mean error **0.205479** (figure 15).

    ![screenshot-14](https://github.com/mocatfrio/GIS-2018/blob/master/georeference-site-plan/img/14.png "Figure 16")

6. Don't forget to save the **GCP Points File**.

### Step 4. Georeference the Site Plan File
1. Click **Raster** on the menu toolbar > Click **Georeferencer** > Click **Georeferencer**, then a georeferencer dialogue will appear. Click **Open Raster**.
2. Choose the **18. PUSKOPKAR -TAMAN GRAHA PENTA SIDOARJO - DS. BLURU KIDUL.tif** file. Always use **WGS 84** as coordinate reference system.
3. Click **Add Point** to tag some georeference points on **Raster Image** and **Vector Image**. I add 4 points in this georeference (at least 3 points, more is better).
   
   ![screenshot-15](https://github.com/mocatfrio/GIS-2018/blob/master/georeference-site-plan/img/15.png "Figure 17")

4. After add some points, then click **Start Georeferencing**. Use **Polynomial 1** transformation type.
5. Georeference of PUSKOPKAR -TAMAN GRAHA PENTA SIDOARJO - DS. BLURU KIDUL site plan done with mean error **0.544327** (figure 17).
   
    ![screenshot-16](https://github.com/mocatfrio/GIS-2018/blob/master/georeference-site-plan/img/16.png "Figure 18")

6. Don't forget to save the **GCP Points File**.

### Step 5. Site Plan Digitizing
1. Make new shapefile layer. Click **Layer** on the menu toolbar > Click **Create Layer** > Click **New Shapefile Layer** (Ctrl+Shift+N).
2. The New Shapefile Layer dialogue will appear. Select **Line** type and fill the new layer's name.

    ![screenshot-17](https://github.com/mocatfrio/GIS-2018/blob/master/georeference-site-plan/img/17.png "Figure 19")

    Then, a new layer will be created in the layers panel.

    ![screenshot-18](https://github.com/mocatfrio/GIS-2018/blob/master/georeference-site-plan/img/18.png "Figure 20")
    
3. Select the new shapefile layer. Click **Toggle Editing** on the plugin toolbar, then click **Add Feature**.

    ![screenshot-19](https://github.com/mocatfrio/GIS-2018/blob/master/georeference-site-plan/img/19.png "Figure 21")

4. Draw the line following the site plan which has been georeferenced. This process called Site Plan Digitization. If all is done, click **Save Layer Edits**.

    ![screenshot-20](https://github.com/mocatfrio/GIS-2018/blob/master/georeference-site-plan/img/20.png "Figure 22")

6. Finally, save the projects (Ctrl+S) and Site Plan Digitization is done!

    ![screenshot-21](https://github.com/mocatfrio/GIS-2018/blob/master/georeference-site-plan/img/21.png "Figure 23")

## Credit
* More documentation: https://github.com/mocatfrio/GIS-2018
* All the files can be downloaded at https://intip.in/filegis2018