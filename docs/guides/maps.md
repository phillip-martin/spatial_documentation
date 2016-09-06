# Three Minute Google Maps Integration

Starting from scratch, you can easily add a google map and integrate Spatial visualizations in just a few minutes.

Through this tutorial, we assume that you are starting out with an empty directory, which we will denote as the root directory of your project.

<iframe width="560" height="315" src="https://www.youtube.com/embed/FYvUwB40IUw" frameborder="0" allowfullscreen></iframe>
<br/>

## step 1 - Create Base HTML File

Create a base HTML file called `index.html` in the root directory of your project with the following code:

**index.html:**
```
<!DOCTYPE html>
<html lang="en">
<meta charset="UTF-8">
<head>

</head>
<body>

</body>
</html>
```

**resulting project structure:**

```
project
+--index.html
```


## step 2 - Add A Google Map

Add a div in the body of your `index.html` file. This is where the map will go.

```html
<div id="map" style="width:80%; height:400px; background-color: gray"></div>
```

Add the google maps library in the head of your `index.html` file.

```html
<script type="text/javascript" src="http://maps.googleapis.com/maps/api/js?key=YOUR_GOOGLE_MAPS_API_KEYv=3&libraries=visualization"></script>
```

<dl>
    <dt>NOTE: As of June 22, 2016. Google requires an api key for embedding a google map. Look <a href="https://developers.google.com/maps/pricing-and-plans/standard-plan-2016-update">here</a> for more info.</dt>
</dl>

Create an initialization script for the Google map and place it in the head of your `index.html` file.

```html
<script>
    initialize = function() {
        var mapDiv = document.getElementById('map');
        var map = new google.maps.Map(mapDiv, {
            center: {lat: 42.339674, lng: -83.046438},
            zoom: 11
    });
</script>
```

Modify the opening body tag to call `initialize` when it loads

```html
<body onload="initialize()">
```

**resulting index.html:**:

```html
<!DOCTYPE html>
<html lang="en">
<meta charset="UTF-8">
<head>

    <!-- google maps library -->
    <script type="text/javascript" src="http://maps.googleapis.com/maps/api/js?key=YOUR_GOOGLE_MAPS_API_KEYv=3&libraries=visualization"></script>

    <!-- embedded script -->
    <script>
        initialize = function() {
            var mapDiv = document.getElementById('map');
            var map = new google.maps.Map(mapDiv, {
                center: {lat: 42.339674, lng: -83.046438},
                zoom: 11
            });
        }
    </script>

</head>
<body onload="initialize()">

    <div id="map" style="width:80%; height:400px; background-color: gray"></div>

</body>
</html>
```

## step 3 - Add Spatial Javascript Library to Project

Create a directory called `js/`.
<br/>
If you haven't already, download the Spatial Javascript Library from [here](http://spatial.ai/pricing/). 
<br/>
Place `spatialGoogleMaps.js` in the `js/` directory.

**resulting project structure:**

```
project
+--index.html
+--js
   +--spatialGoogleMaps.js
```

## step 4 - Integrate Spatial Visualizations

Add the Spatial Javascript Library in the head of your `index.html`. Make sure it is placed after the google maps script.

```html
<script type="text/javascript" src="js/spatialGoogleMaps.js" ></script>
```

In the `initialize` function, call [`loadSpatialwControls`](/references/javascript_library/).
```html
<script>
    initialize = function() {
        var mapDiv = document.getElementById('map');
        var map = new google.maps.Map(mapDiv, {
            center: {lat: 42.339674, lng: -83.046438},
            zoom: 11
        });

        loadSpatialwControls(
            '3twDDLNaJ3szwvsf3ca5OXFQGbutYdzW',
            map,
            'google',
            {
                'Hip': 'red',
                'Nightlife': '#FF8A95'
            },
            {
                'Hip': 'Up_and_coming',
                'Nightlife': 'Dance,Live_music'
            }
        );
    }
    </script>
```

**resulting index.html**
```html
<!DOCTYPE html>
<html lang="en">
<meta charset="UTF-8">
<head>

    <!-- google maps library -->
    <script type="text/javascript" src="http://maps.googleapis.com/maps/api/js?key=AIzaSyBEI_r_Kc9UeQAiFtJN_H5EvMWPgYtw2Mo&v=3&libraries=visualization"></script>

    <!-- Spatial Library -->
    <script type="text/javascript" src="js/spatialGoogleMaps.js" ></script>

    <!-- embedded script -->
    <script>
        initialize = function() {
            var mapDiv = document.getElementById('map');
            var map = new google.maps.Map(mapDiv, {
                center: {lat: 42.339674, lng: -83.046438},
                zoom: 11
            });

            loadSpatialwControls(
                '3twDDLNaJ3szwvsf3ca5OXFQGbutYdzW',
                map,
                'google',
                {
                    'Hip': 'red',
                    'Nightlife': '#FF8A95'
                },
                {
                    'Hip': 'Up_and_coming',
                    'Nightlife': 'Dance,Live_music'
                }
            );
        }
    </script>

</head>

<!-- first load the map, then load the Spatial layer -->
<body onload="initialize()">

    <div id="map" style="width:80%; height:400px; background-color: gray"></div>

</body>
</html>
```

Now, open `index.html` in your favorite browser.