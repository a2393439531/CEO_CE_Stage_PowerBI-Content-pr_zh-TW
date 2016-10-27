<properties
   pageTitle="Use Shape Maps in Power BI Desktop (Preview)"
   description="Create relative comparisons to regions using shape maps in Power BI Desktop"
   services="powerbi"
   documentationCenter=""
   authors="davidiseminger"
   manager="mblythe"
   backup=""
   editor=""
   tags=""
   qualityFocus="no"
   qualityDate=""/>

<tags
   ms.service="powerbi"
   ms.devlang="NA"
   ms.topic="article"
   ms.tgt_pltfrm="NA"
   ms.workload="powerbi"
   ms.date="10/12/2016"
   ms.author="davidi"/>

# Shape Maps in Power BI Desktop (Preview)

In Power BI Desktop, you create a <bpt id="p1">**</bpt>Shape Map<ept id="p1">**</ept> visual to show relative comparisons of regions on a map by applying different colors to different regions. In contrast to the <bpt id="p1">**</bpt>Map<ept id="p1">**</ept> visual, <bpt id="p2">**</bpt>Shape Map<ept id="p2">**</ept> cannot show precise geographical locations of data points on a map; instead, its main purpose is to show relative comparisons of regions on a map by coloring them differently.

<bpt id="p1">**</bpt>Shape Map<ept id="p1">**</ept> visuals are based on ESRI/TopoJSON maps which have the compelling ability to use custom maps that you can create, such as geographical, seating arrangements, floor plans, and others. The ability to use custom maps is not available in this Preview release of <bpt id="p1">**</bpt>Shape Map<ept id="p1">**</ept>, but custom maps will be enabled when this features comes out of Preview, which is expected with the next Power BI Desktop monthly update.

## Creating Shape Maps

You can test the <bpt id="p1">**</bpt>Shape Map<ept id="p1">**</ept> control with the maps that are shipping with this Preview release, or you can use your own custom map as long as it meets the requirements outlined in the following section called <bpt id="p2">**</bpt>Use Custom Maps<ept id="p2">**</ept>.

The <bpt id="p1">**</bpt>Shape Map<ept id="p1">**</ept> visual is in Preview, and must be enabled in Power BI Desktop. To enabled <bpt id="p1">**</bpt>Shape Map<ept id="p1">**</ept>, select <bpt id="p2">**</bpt>File &gt; Options and Settings &gt; Options &gt; Preview Features<ept id="p2">**</ept>, then select the <bpt id="p3">**</bpt>Shape Map<ept id="p3">**</ept> checkbox. You'll need to restart Power BI Desktop after you make the selection.

![](media/powerbi-desktop-shape-map/shape-map_1a.png)

Once <bpt id="p1">**</bpt>Shape Map<ept id="p1">**</ept> is enabled, click the <bpt id="p2">**</bpt>Shape Map<ept id="p2">**</ept> control from the <bpt id="p3">**</bpt>Visualizations<ept id="p3">**</ept> pane.

![](media/powerbi-desktop-shape-map/shape-map_2.png)

Power BI Desktop creates an empty <bpt id="p1">**</bpt>Shape Map<ept id="p1">**</ept> visual design canvas.

![](media/powerbi-desktop-shape-map/shape-map_3.png)

Take the following steps to create a <bpt id="p1">**</bpt>Shape Map<ept id="p1">**</ept>:

1.  In the <bpt id="p1">**</bpt>Fields<ept id="p1">**</ept> pane, drag a data field that has the region names (or abbreviations) onto the <bpt id="p2">**</bpt>Location<ept id="p2">**</ept> bucket, and a data measure field into the <bpt id="p3">**</bpt>Values<ept id="p3">**</ept> bucket (you won't see a map yet).

    > <bpt id="p1">**</bpt>Note:<ept id="p1">**</ept> See the section titled <bpt id="p2">**</bpt>Getting Map Data<ept id="p2">**</ept>, below, for information on how to quickly get map data to test <bpt id="p3">**</bpt>Shape Map<ept id="p3">**</ept>.

    ![](media/powerbi-desktop-shape-map/shape-map_3a.png)

2.  In the <bpt id="p1">**</bpt>Format<ept id="p1">**</ept> settings pane, expand <bpt id="p2">**</bpt>Shape<ept id="p2">**</ept>, and select from the <bpt id="p3">**</bpt>Standard Maps<ept id="p3">**</ept> drop-down to show your data. At this point the rendering appears, as shown in the following image.

    ![](media/powerbi-desktop-shape-map/shape-map_3b.png)

    > <bpt id="p1">**</bpt>Note:<ept id="p1">**</ept> In the <bpt id="p2">**</bpt>Region Keys<ept id="p2">**</ept> section at the end of this article is a collection of tables that have map regions keys you can use to test the <bpt id="p3">**</bpt>Shape Map<ept id="p3">**</ept> visual.

3.  You can then modify the map projection and zooming settings, as well as the colors of data points, from the <bpt id="p1">**</bpt>Format<ept id="p1">**</ept> settings pane. You can also modify zoom settings. For example, you can change colors, set maximums and minimums, and so on.

    ![](media/powerbi-desktop-shape-map/shape-map_3d.png)

4.  You can also add a category data column to the <bpt id="p1">**</bpt>Legend<ept id="p1">**</ept> bucket, and classify the map regions based on categories.

## Use Custom Maps

You can use custom maps with <bpt id="p1">**</bpt>Shape Map<ept id="p1">**</ept> as long as they are in the <bpt id="p2">**</bpt>TopoJSON<ept id="p2">**</ept> format. If your map is in another format, you can use online tools such as <bpt id="p1">[</bpt><bpt id="p2">**</bpt>Map Shaper<ept id="p2">**</ept><ept id="p1">](http://mapshaper.org/)</ept> to convert your <bpt id="p3">*</bpt>shapefiles<ept id="p3">*</ept> or your <bpt id="p4">*</bpt>GeoJSON<ept id="p4">*</ept> maps into the <bpt id="p5">**</bpt>TopoJSON<ept id="p5">**</ept> format.

To use your <bpt id="p1">**</bpt>TopoJSON<ept id="p1">**</ept> map file, add a ShapeMap visual to your report and add some data to the <bpt id="p2">*</bpt>Location<ept id="p2">*</ept> and <bpt id="p3">*</bpt>Values<ept id="p3">*</ept> buckets. Then, in the <bpt id="p1">**</bpt>Visualizations<ept id="p1">**</ept> pane with the <bpt id="p2">**</bpt>Format<ept id="p2">**</ept> section selected (the paintbrush icon, shown as (1) in the following image), expand the <bpt id="p3">**</bpt>Shape<ept id="p3">**</ept> section and select <bpt id="p4">**</bpt>+ Add Map<ept id="p4">**</ept>.

![](media/powerbi-desktop-shape-map/shape-map_6.png)


## Getting Map Data

To quickly get data into a model so you can test <bpt id="p1">**</bpt>Shape Map<ept id="p1">**</ept>, you can copy one of the tables at the end of this article, then select <bpt id="p2">**</bpt>Enter Data<ept id="p2">**</ept> from the <bpt id="p3">**</bpt>Home<ept id="p3">**</ept> ribbon.

![](media/powerbi-desktop-shape-map/shape-map_4.png)

You can then paste the table into Power BI Desktop. The top row is automatically identified as a header.

![](media/powerbi-desktop-shape-map/shape-map_5.png)

You can enter a new column simply by typing a new column name (in the blank column to the right), then add values in each cell, just like you can do in Excel. When finished, select <bpt id="p1">**</bpt>Load<ept id="p1">**</ept> and the table is added to the data model for Power BI Desktop.


## Preview Behavior and Requirements

There are a few considerations and requirements for this Preview release of <bpt id="p1">**</bpt>Shape Map<ept id="p1">**</ept>:

-   The <bpt id="p1">**</bpt>Shape Map<ept id="p1">**</ept> visual is in Preview, and must be enabled in Power BI Desktop. To enabled <bpt id="p1">**</bpt>Shape Map<ept id="p1">**</ept>, select <bpt id="p2">**</bpt>File &gt; Options and Settings &gt; Options &gt; Preview Features<ept id="p2">**</ept>, then select the <bpt id="p3">**</bpt>Shape Map<ept id="p3">**</ept> checkbox.

-   Currently, you must also have the <bpt id="p1">**</bpt>Values<ept id="p1">**</ept> bucket set in order for the <bpt id="p2">**</bpt>Legend<ept id="p2">**</ept> classification to work properly. We anticipate improving this behavior in the final release of <bpt id="p1">**</bpt>Shape Map<ept id="p1">**</ept>.

-   The release version of <bpt id="p1">**</bpt>Shape Map<ept id="p1">**</ept> will have a user interface that shows the map keys of the currently selected map; in this Preview, you can reference the map region keys in the tables found in the following <bpt id="p2">**</bpt>Region Keys<ept id="p2">**</ept> section of this article.

## Region Keys

Use the following <bpt id="p1">**</bpt>Region Keys<ept id="p1">**</ept> in this Preview release to test <bpt id="p2">**</bpt>Shape Map<ept id="p2">**</ept>.

### Australia: States

|id|abbr|iso|名稱|postal|
|---|---|---|---|---|
|au-wa| WA| AU-WA|  Western Australia|  WA|
|au-vic|Vic|AU-VIC| Victoria|   VIC|
|au-tas |Tas|AU-TAS|    Tasmania    |TAS|
|au-sa  |SA |AU-SA  |South Australia|   SA|
|au-qld |Qld|AU-QLD |Queensland|    QLD|
|au-nt  |NT |AU-NT  |Northern Territory|    NT|
|au-nsw |NSW|AU-NSW |New South Wales|   NSW|
|au-act |ACT|AU-ACT |Australian Capital Territory|  ACT|


### Austria: States

|id|    iso|    名稱|   name-en|    postal|
|---|---|---|---|---|
|at-wi| AT-9|   Wien|   維也納| WI|
|at-vo| AT-8|   Vorarlberg| Vorarlberg| VO|
|at-tr| AT-7|   Tirol|  Tyrol|  TR|
|at-st| AT-6|   Steiermark| Styria| ST|
|at-sz| AT-5|   Salzburg|   Salzburg|   SZ|
|at-oo| AT-4|   Oberösterreich| Upper Austria|  OO|
|at-no| AT-3|   Niederösterreich|   Lower Austria|  否|
|at-ka| AT-2|   Kärnten|    Carinthia|  KA|
|at-bu| AT-1|   Burgenland| Burgenland| BU|

### Brazil: States

|id|
|---|
|Tocantins
|Pernambuco
|Goias
|Sergipe
|聖保羅
|Santa Catarina
|Roraima
|Rondonia
|Rio Grande do Sul
|Rio Grande do Norte
|Rio de Janeiro
|Piaui
|Parana
|Paraiba
|Para
|Minas Gerais
|Mato Grosso
|Maranhao
|Mato Grosso do Sul
|Distrito Federal
|Ceara
|Espirito Santo
|Bahia
|Amazonas
|Amapa
|Alagoas
|Acre
|Litigated Zone 1
|Litigated Zone 2
|Litigated Zone 3
|Litigated Zone 4

### Canada: Provinces

|id|    iso |名稱|  postal|
|---|---|---|---|
|ca-nu| CA-NU|  Nunavut|    NU|
|ca-nt| CA-NT|  Northwest Territories|  NT
|ca-yt| CA-YT|  Yukon|  YT
|ca-sk| CA-SK|  Saskatchewan|   SK
|ca-qc| CA-QC|  Quebec| QC
|ca-pe| CA-PE|  Prince Edward Island|   PE
|ca-on| CA-ON|  Ontario|    ON
|ca-ns| CA-NS|  Nova Scotia |NS
|ca-nl| CA-NL|  Newfoundland and Labrador|  NL
|ca-nb| CA-NB|  New Brunswick| NB
|ca-mb| CA-MB|  Manitoba|   MB
|ca-bc| CA-BC|  British Columbia    |BC
|ca-ab| CA-AB|  Alberta |AB


### France: Regions

|id |名稱|  name-en|
|---|---|---|
|Alsace |Alsace|    Alsace
|Rhone-Alpes|   Rhône-Alpes|    Rhone-Alpes
|Provence-Alpes-Cote d'Azur|    Provence-Alpes-Côte d'Azur| Provence-Alpes-Cote d'Azur
|Poitou-Charentes|  Poitou-Charentes|   Poitou-Charentes
|Picardie   |Picardie|  Picardy
|Pays de la Loire|  Pays de la Loire|   Pays de la Loire
|Nord-Pas-de-Calais|    Nord-Pas-de-Calais| Nord-Pas-de-Calais
|Midi-Pyrenees| Midi-Pyrénées|  Midi-Pyrenees
|Lorraine|  Lorraine|   Lorraine
|Limousin|  Limousin|   Limousin
|Languedoc-Roussillon|  Languedoc-Roussillon|   Languedoc-Roussillon
|Ile-del-France|    Île-de-France|  Ile-de-France
|Haute-Normandie|   Haute-Normandie|    Upper Normandy
|Franche-Comte| Franche-Comté|  Franche-Comte
|Corse| Corse|  Corsica
|Champagne-Ardenne| Champagne-Ardenne|  Champagne-Ardenne
|Centre-Val de Loire|   Centre-Val de Loire|    Centre-Val de Loire
|Bretagne|  Bretagne|   Brittany
|Bourgogne| Bourgogne|  Burgundy
|Basse-Normandie|   Basse-Normandie|    Lower Normandy
|Auvergne|  Auvergne|   Auvergne
|Aquitaine| Aquitaine|  Aquitaine

### Germany: States

|id|    iso|    名稱|   name-en|    postal
|---|---|---|---|---|
|de-be| DE-BE|  Berlin| Berlin| BE
|de-th| DE-TH|  Thüringen|  Thuringia|  TH
|de-st| DE-ST|  Sachsen-Anhalt| Saxony-Anhalt|  ST
|de-sn| DE-SN|  Sachsen |Saxony|    SN
|de-mv| DE-MV|  Mecklenburg-Vorpommern| Mecklenburg-Vorpommern| MV
|de-bb| DE-BB|  Brandenburg |Brandenburg|   BB
|de-sh| DE-SH|  Schleswig-Holstein| Schleswig-Holstein| SH
|de-sl| DE-SL|  Saarland|   Saarland|   SL
|de-rp| DE-RP|  Rheinland-Pfalz|    Rhineland-Palatinate|   RP
|de-nw| DE-NW|  Nordrhein-Westfalen|    North Rhine-Westphalia| NW
|de-ni| DE-NI|  Niedersachsen|  Lower Saxony|   NI
|de-he| DE-HE|  Hessen| Hesse|  HE
|de-hh| DE-HH|  Hamburg|    Hamburg|    HH
|de-hb| DE-HB|  Bremen| Bremen| HB
|de-by| DE-BY|  Bayern| Bavaria|    BY
|de-bw| DE-BW|  Baden-Württemberg|  Baden-Wurttemberg|  BW


### Ireland: Counties

|id|
|---|
|Wicklow
|Wexford
|Westmeath
|Waterford
|Sligo
|Tipperary
|Roscommon
|Offaly
|Monaghan
|Meath
|Mayo
|Louth
|Longford
|Limerick
|Leitrim
|Laoighis
|Kilkenny
|Kildare
|Kerry
|Galway
|Dublin
|Donegal
|Cork
|Clare
|Cavan
|Carlow


### Italy: Regions

|id|iso|名稱|name-en|postal|
|---|---|---|---|---|
|it-vn| IT-34|  Veneto| Veneto| VN
|it-vd| IT-23|  Valle d'Aosta|  Aosta Valley|   VD
|it-um| IT-55|  Umbria| Umbria| UM
|it-tt| IT-32|  Trentino-Alto Adige|    Trentino-South Tyrol|   TT
|it-tc| IT-52|  Toscana|    Tuscany|    TC
|it-sc| IT-82|  Sicilia|    Sicily| SC
|it-sd| IT-88|  Sardegna|   Sardinia|   SD
|it-pm| IT-21|  Piemonte|   Piedmont|   PM
|it-ml| IT-67|  Molise| Molise| ML
|it-mh| IT-57|  Marche| Marche| MH
|it-lm| IT-25|  Lombardia|  Lombardy|   LM
|it-lg| IT-42|  Liguria|    Liguria|    LG
|it-lz| IT-62|  Lazio|  Lazio|  LZ
|it-fv| IT-36|  Friuli-Venezia Giulia|  Friuli-Venezia Giulia|  FV
|it-er| IT-45|  Emilia-Romagna| Emilia-Romagna| ER
|it-cm| IT-72|  Campania|   Campania|   CM
|it-lb| IT-78|  Calabria|   Calabria|   LB
|it-bc| IT-77|  Basilicata| Basilicata| BC
|it-pu| IT-75|  Apulia| Puglia| PU
|it-ab| IT-65|  Abruzzo|    Abruzzo|    AB


### Mexico: States

|id|    abreviatura|    iso|    名稱|   name-en|    postal|
|---|---|---|---|---|---|
|mx-zac|    Zac.|   MX-ZAC| Zacatecas|  Zacatecas|  ZA
|mx-yuc|    Yuc.|   MX-YUC| Yucatán|    Yucatan|    YU
|mx-ver|    Ver.|   MX-VER| Veracruz|   Veracruz|   VE
|mx-tla|    Tlax.|  MX-TLA| Tlaxcala|   Tlaxcala|   TL
|mx-tam|    Tamps.| MX-TAM| Tamaulipas| Tamaulipas| TM
|mx-tab|    Tab.|   MX-TAB| Tabasco|    Tabasco|    TB
|mx-son|    Son.|   MX-SON| Sonora| Sonora| SO
|mx-sin|    Sin.|   MX-SIN| Sinaloa|    Sinaloa|    SI
|mx-slp|    S.L.P.| MX-SLP| San Luis Potosí|    San Luis Potosi|    SL
|mx-roo|    Q.R.|   MX-ROO| Quintana Roo|   Quintana Roo|   QR
|mx-que|    Qro.|   MX-QUE| Querétaro|  Queretaro|  QE
|mx-pue|    Pue.|   MX-PUE| Puebla| Puebla| PU
|mx-oax|    Oax.|   MX-OAX| Oaxaca| Oaxaca| OA
|mx-nle|    N.L.|   MX-NLE| Nuevo León| Nuevo Leon| NL
|mx-nay|    Nay.|   MX-NAY| Nayarit|    Nayarit|    NA
|mx-mor|    Mor.|   MX-MOR| Morelos|    Morelos|    MR
|mx-mic|    Mich.|  MX-MIC| Michoacán|  Michoacan|  MC
|mx-mex|    Méx.|   MX-MEX| Estado de México|   Mexico State|   MX
|mx-jal|    Jal.|   MX-JAL| Jalisco|    Jalisco|    JA
|mx-hid|    Hgo.|   MX-HID| Hidalgo|    Hidalgo|    HI
|mx-gro|    Gro.|   MX-GRO| Guerrero|   Guerrero|   GR
|mx-gua|    Gto.|   MX-GUA| Guanajuato| Guanajuato| GT
|mx-dur|    Dgo.|   MX-DUR| Durango|    Durango|    DU
|mx-dif|    Col.|   MX-DIF| Ciudad de México|   Mexico City|    DF
|mx-col|    Coah.|  MX-COL| Colima| Colima| CL
|mx-coa|    Chis.|  MX-COA| Coahuila|   Coahuila|   CA
|mx-chh|    Chih.|  MX-CHH| Chihuahua|  Chihuahua|  CH
|mx-chp|    CDMX.|  MX-CHP| Chiapas|    Chiapas|    CP
|mx-cam|    Camp.|  MX-CAM| Campeche|   Campeche|   CM
|mx-bcs|    B.C.S.| MX-BCS| Baja California Sur|    Baja California Sur|    BS
|mx-bcn|    B.C.|   MX-BCN| Baja California|    Baja California|    BN
|mx-agu|    Ags.|   MX-AGU| Aguascalientes| Aguascalientes| AG


### Netherlands: Provinces

|id|    iso|    名稱|   name-en|
|---|---|---|---|
|nl-zh| NL-ZH|  Zuid-Holland|   South Holland
|nl-ze| NL-ZE|  Zeeland|    Zeeland
|nl-ut| NL-UT|  Utrecht|    Utrecht
|nl-ov| NL-OV|  Overijssel| Overijssel
|nl-nh| NL-NH|  Noord-Holland|  North Holland
|nl-nb| NL-NB|  Noord-Brabant|  North Brabant
|nl-li| NL-LI|  Limburg|    Limburg
|nl-gr| NL-GR|  Groningen|  Groningen
|nl-ge| NL-GE|  Gelderland| Gelderland
|nl-fr| NL-FR|  Fryslân|    Friesland
|nl-fl| NL-FL|  Flevoland|  Flevoland
|nl-dr| NL-DR|  Drenthe|    Drenthe

### UK: Countries

|id|    iso|    名稱|
|---|---|---|
|gb-wls|    GB-WLS| Wales
|gb-sct|    GB-SCT| Scotland
|gb-nir|    GB-NIR| Northern Ireland
|gb-eng|    GB-ENG| England

### USA: States

|id|    名稱|   postal|
|---|---|---|
|us-mi| Michigan|   MI
|us-ak| Alaska| AK
|us-hi| Hawaii| HI
|us-fl| 佛羅里達州|    FL
|us-la| Louisiana|  LA
|us-ar| Arkansas|   AR
|us-sc| South Carolina| SC
|us-ga| Georgia|    GA
|us-ms| Mississippi|    MS
|us-al| Alabama|    AL
|us-nm| New Mexico| NM
|us-tx| Texas|  TX
|us-tn| Tennessee|  TN
|us-nc| North Carolina| NC
|us-ok| Oklahoma|   [確定]
|us-az| Arizona|    AZ
|us-mo| 密蘇里州|   MO
|us-va| 維吉尼亞州|   VA
|us-ks| Kansas| KS
|us-ky| 肯塔基州|   KY
|us-co| Colorado|   CO
|us-md| Maryland|   MD
|us-wv| West Virginia|  WV
|us-de| Delaware|   DE
|us-dc| District of Columbia|   DC
|us-il| Illinois|   IL
|us-oh| 俄亥俄州|   OH
|us-ca| California| CA
|us-ut| Utah|   UT
|us-nv| Nevada| NV
|us-in| Indiana|    IN
|us-nj| New Jersey| NJ
|us-ri| Rhode Island|   RI
|us-ct| Connecticut|    CT
|us-pa| Pennsylvania|   PA
|us-ny| New York|   NY
|us-ne| Nebraska|   NE
|us-ma| Massachusetts|  MA
|us-ia| Iowa|   IA
|us-nh| New Hampshire|  NH
|us-or| Oregon| 或
|us-mn| Minnesota|  MN
|us-vt| Vermont|    VT
|us-id| Idaho|  ID
|us-wi| Wisconsin|  WI
|us-wy| Wyoming|    WY
|us-sd| South Dakota|   SD
|us-nd| North Dakota|   ND
|us-me| Maine|  ME
|us-mt| Montana|    MT
|us-wa| 華盛頓| WA
