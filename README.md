# global food balance #
Many plants will have geographically restricted cultivation. An obvious case is olive and grape production around the Mediterranean sea, and similar latitudes globally. This contrasts with northern Europe, which often have food and drink based on wheat, barley, and milk products. Above a line that is roughly following the Alps, butter is the historical fat of choice (i.e. availability), below this line, it is olive oil.

This is, of course, a simplification, as cultural factors and movement of people are also at play. Of particular interest is France, which spans the Mediterranean climate and temperate north. This has some interesting cultural differences from those two greater regions, with [wine production throughout](https://en.wikipedia.org/wiki/French_wine) (not beer), accompanied with bread and butter/[cheese](https://en.wikipedia.org/wiki/List_of_French_cheeses) (not olives). There is, of course, olive production in France, but this is limited to a small region near the Mediterranean, and is small-scale compared to other countries in southern Europe.

Production of most of these foods can be observed at a global scale. Based on my [earlier version of fisheries only](https://github.com/wrf/misc-analyses/tree/master/fisheries), I made another [shinyapp](https://shiny.rstudio.com/) that can redraw the choropleth map based on imports, exports, and production of various food products around the world. The top 20 items are also displayed in a barplot below the map. It should run on another system by [downloading the original .csv file from the UN](http://www.fao.org/faostat/en/#data/FBS), placing it into the `./data` folder. This visualization is presumably what was intended to be displayed with the problematic [FAO FBS visualizations](https://www.fao.org/faostat/en/#data/FBS/visualize), which never worked any time I had visited their website.

The app v1.34 [is currently live here](https://wrfbiolum.shinyapps.io/foodbalance/).

The drop down menu will change whatever is displayed. There is a table at the bottom, and display options can be controlled as well. Lat-lon can be changed for the map view, but the rendering is likely to distort the map unless it is roughly 2:1 aspect ratio. The `Print PDF` button will print the map as a `.pdf` file of whatever food category is displayed on the screen. The plot titles and file name should adapt automatically.

![food_balance_app_v2_screenshot.png](https://github.com/wrf/foodbalance/blob/main/images/food_balance_app_v2_screenshot.png)

The data were downloaded in 2023 from the [UN FAO Food Balance Sheets](http://www.fao.org/faostat/en/#data/FBS), which included years 2010-2020. Descriptions and sub-category groupings were found [here](https://www.fao.org/faostat/en/#definitions).

Units are in 1000 tonnes, kilotonnes, or M kg, or properly in gigagrams - Gg. One tonne of water, 1000kg, would be a 1m cube. A shipping container (roughly 40x8x8.5 ft [1AAA type](https://en.wikipedia.org/wiki/ISO_668) or [2TEU size](https://en.wikipedia.org/wiki/Twenty-foot_equivalent_unit)) would be 68 cubic meters of internal space, rather less than 100 tonnes. So 1 Gg would be about 15 shipping containers.

For example, Switzerland imports 180 Gg of wine per year (plus producing 111Gg and exporting 1Gg). For ease of math, suppose that each 1kg is 1 bottle of 750mL of wine, whereby 1Gg would be 1M bottles (this actually would probably be about 1.25kg per bottle). Thus, the imports sum to roughly 7 shipping containers per day, for a population of about 8.5M. The final consumption is 290Gg/year, coming out to 794k bottles per day. On average, 1 in 10 people have wine for dinner. This makes more sense to imagine that 2/10 have wine with dinner, and that any given couple would be finishing a bottle once or twice a week.

# some food anecdotes from the data #
## wine ##
Grapevine growth tends to be restricted to around 35-45 degrees north or south, making a stripe across both hemispheres. This passes across known wine regions - [Chile](https://en.wikipedia.org/wiki/Chilean_wine), [Argentina](https://en.wikipedia.org/wiki/Argentine_wine), [South Africa](https://en.wikipedia.org/wiki/South_African_wine), [Australia](https://en.wikipedia.org/wiki/Australian_wine), and [New Zealand](https://en.wikipedia.org/wiki/New_Zealand_wine) in the southern hemisphere, and in the northern, [California](https://en.wikipedia.org/wiki/California_wine), the Mediterranean, and [Georgia](https://en.wikipedia.org/wiki/Georgian_wine). The missing piece was [China](https://en.wikipedia.org/wiki/Wine_in_China), which has the correct latitude and climate in the central part of the country. China is clearly rapidly increasing their wine production, as well as their imports. The 2019 data put China in 5th place for highest production (over 2Gg, appx. half of France), though under 1% of this is exported.

![map of Wine Production in 2020](https://github.com/wrf/foodbalance/blob/main/images/Wine_Production_Y2020.png)

Most of the new world wine production (rather, anywhere other than the old world) tends to plant typically French cultivars ([Cabernet](https://en.wikipedia.org/wiki/Cabernet_Sauvignon), [Pinot Noir](https://en.wikipedia.org/wiki/Pinot_noir), [Chardonnay](https://en.wikipedia.org/wiki/Chardonnay), [Sauvignon Blanc](https://en.wikipedia.org/wiki/Sauvignon_blanc), etc) which is possibly why French people get so fussy about new world wines.

## dairy production ##
The major exporter in the world is [New Zealand](https://www.dcanz.com/about-the-nz-dairy-industry/), followed by Germany, the Netherlands, and France. For a mountainous island country, it is unclear [where they put all of their cows](https://en.wikipedia.org/wiki/Dairy_farming_in_New_Zealand).

![map of Milk Export Quantity in 2020](https://github.com/wrf/foodbalance/blob/main/images/Milk_-_Excluding_Butter_Export_Quantity_Y2020.png)

## chocolate ##
We focus a lot about origins of coffee (e.g Ethiopia, Java, Costa Rica, etc), but somehow chocolate gets once removed, being attributed to [Belgium](https://en.wikipedia.org/wiki/Belgian_chocolate), [Switzerland](https://en.wikipedia.org/wiki/Swiss_chocolate), or Italy. Obviously, [cocoa](https://en.wikipedia.org/wiki/Theobroma_cacao) does not grow in any of those places.

![map of Cocoa Beans and products Production in 2019](https://github.com/wrf/foodbalance/blob/main/images/Cocoa_Beans_and_products_Production_Y2019.png)

Despite the actual origins from Ivory Coast, Ghana, Indonesia, and Nigeria, chocolate becomes famous within Europe for processing steps after the cultivation. The largest importer, it appears, is the Netherlands, potentially for the [Dutch process](https://en.wikipedia.org/wiki/Dutch_process_cocoa) for downstream resale to the rest of Europe. Direct exports account for about 1/3 of the imports. The argument for this is that downstream steps and materials contribute more in chocolate than in some other foods. Although, coffee is still subject to place of origin, differences in roasting, grinding, preparation, and possibly also addition of milk.

Why does the milk matter so much more than the [terroir](https://en.wikipedia.org/wiki/Terroir) of the cocoa? Apparently, this stems from a number of lawsuits in Europe (see [Cidell 2006](https://doi.org/10.1016/j.geoforum.2006.02.006) for discussion over the "Chocolate War").

## soybeans ##
Global [soybean](https://en.wikipedia.org/wiki/Soybean) production is dominated by the USA, Brazil, and Argentina. Most of this is exported, and used as animal feed (i.e. probably mostly pigs and cows). This is NOT mostly used to feed people in the form of tofu, so unfortunately there is no [international vegan conspiracy](https://en.wikipedia.org/wiki/Veganism#Philosophy). As these soybeans end up being transported across the planet to feed animals in Europe and China, this transport has been the subject of recent concern (see [Hong 2022](https://www.science.org/doi/10.1126/science.abj1572) - paywalled).

![map of Soyabeans Production in 2019](https://github.com/wrf/foodbalance/blob/main/images/Soyabeans_Production_Y2019.png)

China also imports [cassava](https://en.wikipedia.org/wiki/Cassava) at similar quantities (top importer globally), also used as animal feed.

## offal meats ##
Organ meats appear to have gone out of style in much of Europe, but are still imported by China. I suspect that mixed organ meats were a part of most cuisines for a long time out of necessity, including famous dishes like [haggis](https://en.wikipedia.org/wiki/Haggis), [Saumagen](https://en.wikipedia.org/wiki/Saumagen), [foie gras](https://en.wikipedia.org/wiki/Foie_gras), or various [tripe soups](https://en.wikipedia.org/wiki/Tripe_soup). Even blood had its place for [black pudding](https://en.wikipedia.org/wiki/Black_pudding), [boudin](https://en.wikipedia.org/wiki/Boudin), [Blutwurst](https://de.wikipedia.org/wiki/Blutwurst), [morcilla](https://es.wikipedia.org/wiki/Morcilla), among others. 

![map of Offal Export Quantity in 2020](https://github.com/wrf/foodbalance/blob/main/images/Offals_Export_Quantity_Y2020.png)
![map of Offal Import Quantity in 2020](https://github.com/wrf/foodbalance/blob/main/images/Offals_Import_Quantity_Y2020.png)

## pork and dates ##
These two have an inverse relationship, particularly evident in the North Africa / Middle East region, likely from reasons of [religion](https://en.wikipedia.org/wiki/Religious_restrictions_on_the_consumption_of_pork).

![map of Dates Production Quantity in 2020](https://github.com/wrf/foodbalance/blob/main/images/Dates_Production_Y2020.png)
![map of Pig Meat Production Quantity in 2020](https://github.com/wrf/foodbalance/blob/main/images/Pigmeat_Production_Y2020.png)

