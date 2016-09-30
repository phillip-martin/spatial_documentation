# Map Integration From Scratch

Starting from scratch, you can easily add a google map and integrate Spatial visualizations in just a few minutes.

## step 1 - Create Base HTML File

Create a file called `index.html`with the following code:

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


## step 2 - Add a Google Map

First, add the google maps library in the head of your `index.html` file. Make sure to replace "YOUR_GOOGLE_MAPS_API_KEY" in the source to your own google map api key.

```html
<script type="text/javascript" src="http://maps.googleapis.com/maps/api/js?key=YOUR_GOOGLE_MAPS_API_KEY&v=3&libraries=visualization"></script>
```

<dl>
    <dt>NOTE: As of June 22, 2016. Google requires an api key for embedding a google map. Look <a href="https://developers.google.com/maps/pricing-and-plans/standard-plan-2016-update">here</a> for more info.</dt>
</dl>

Next, add a div in the body of your `index.html` file. This is where the map will go.

```html
<div id="map" style="width:80%; height:400px; background-color: gray"></div>
```

Create an initialization script for the Google map and place it in the head of your `index.html` file.

```html
<script>
    initialize = function() {
        var mapDiv = document.getElementById('map');
        var map = new google.maps.Map(mapDiv, {
            center: {lat: 42.339674, lng: -83.046438},
            zoom: 11
        });
    }
</script>
```

Modify the opening body tag to call `initialize()` when it loads

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
    <script type="text/javascript" src="http://maps.googleapis.com/maps/api/js?key=YOUR_GOOGLE_MAPS_API_KEY&v=3&libraries=visualization"></script>

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

Open your `index.html` file in your browser. If you see "Oops! Something went wrong.", remember to replace "YOUR_GOOGLE_MAPS_API_KEY" in the google map library source to your own google map api key.

## step 3 - Integrate Spatial Visualizations

Add the Spatial Javascript Library in the head of your `index.html`. Make sure it is placed after the google maps script.

```html
<script type="text/javascript" src="https://cdn.spatial.ai/spatial-1.1.2.js" ></script>
```

In the `initialize` function, call [`loadSpatialwControls`](/references/javascript_library/). Make sure to replace "YOUR_SPATIAL_API_KEY" in the new function with your own spatial api key.

```html
<script>
    initialize = function() {
        var mapDiv = document.getElementById('map');
        var map = new google.maps.Map(mapDiv, {
            center: {lat: 42.339674, lng: -83.046438},
            zoom: 11
        });

        loadSpatialwControls(
            'YOUR_SPATIAL_API_KEY',
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
    <script type="text/javascript" src="http://maps.googleapis.com/maps/api/js?key=YOUR_GOOGLE_MAPS_API_KEY&v=3&libraries=visualization"></script>

    <!-- Spatial Library -->
    <script type="text/javascript" src="https://cdn.spatial.ai/spatial-1.1.2.js" ></script>

    <!-- embedded script -->
    <script>
        initialize = function() {
            var mapDiv = document.getElementById('map');
            var map = new google.maps.Map(mapDiv, {
                center: {lat: 42.339674, lng: -83.046438},
                zoom: 11
            });

            loadSpatialwControls(
                'YOUR_SPATIAL_API_KEY',
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

If the Spatial menu pops up on the map but clicking on the buttons doesn't do anything, make sure that you replaced "YOUR_SPATIAL_API_KEY" above with your own spatial api key.
