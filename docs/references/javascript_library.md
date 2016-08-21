# Javascript Library Reference
Our data can be loaded onto any Google map with just a few lines of code and our Javascript library. You can either use our GUI interface or create your own.

The Spatial Javascript Library can be downloaded from our [website](http://spatial.ai/pricing/)

## Methods

<dl>
    <dt><h3>loadSpatialwControls(<b>apikey</b>, <b>map</b>, <b>vibes</b>, <b>colors</b>, <b>cssText</b>)</h3></dt>
    <dd>This loads the Spatial GUI and hex layer.</dd>
    <dd>
        <dl>
            <dt>apikey</dt>
            <dd>obtained through the <a href="http://spatial.ai/pricing/">Spatial website</a></dd>
        </dl>
        <dl>
            <dt> map </dt>
            <dd> google.maps.Map object </dd>
        </dl>
        <dl>
            <dt> vibes </dt>
            <dd> dictionary of vibe categories and sub categories; we can visual any number of things on request; current options are: [healthy_eats,active_living,photo_op,organic,culture,chinatown,edgy_cool,up_and_coming,mainstream,food_trucks,coffee_lovers,fine_dining,the_arts,theater,galleries,architecture,attractions,monuments,dance,sports_bars,live_music,outdoors,yoga,majestic_views,date_night,sports,excursions,educational,latin_corridor,nature,parks,water,mountains,healthy,family,sights,romantic,hip,nightlife,charming,foodie,lgbt]</dd>
        </dl>
        <dl>
            <dt> colors (optional) </dt>
            <dd> dictionary of colors to use for each vibe (if you want to override the default colors) </dd>
        </dl>
        <dl>
            <dt> cssText (optional)  </dt>
            <dd> css string for the Spatial container (if you want to relocate it from the default, top right corner) </dd>
        </dl>
</dl>

<dl>
    <dt><h3>loadSpatial(<b>apikey</b>,<b>map</b>,<b>colors</b>)</h3></dt>
    <dd>This only loads the hex layer, for use with your own controls.</dd>
    <dd>
        <dl>
            <dt>apikey</dt>
            <dd>obtained through the <a href="http://spatial.ai/pricing/">Spatial website</a></dd>
        </dl>
        <dl>
            <dt> map </dt>
            <dd> google.maps.Map object </dd>
        </dl>
        <dl>
            <dt> colors (optional) </dt>
            <dd> dictionary of colors to use for each vibe (if you want to override the default colors) </dd>
        </dl>
    </dd>
</dl>
<dl>
    <dt><h3>setVibe(<b>vibe</b>,<b>state</b>)</h3></dt>
    <dd>If you are using your own GUI controls, call this method to turn a vibe on or off.</dd>
    <dd>
        <dl>
            <dt>vibe</dt>
            <dd>vibe layer to be changed</dd>
        </dl>
        <dl>
            <dt> state </dt>
            <dd> new state (0 for off, 1 for on) </dd>
        </dl>
    </dd>
</dl>
