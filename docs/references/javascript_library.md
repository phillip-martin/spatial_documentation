# Javascript Library Reference
Our data can be loaded onto any Google map with just a few lines of code and our Javascript library. You can either use our GUI interface or create your own.

The Spatial Javascript Library can be downloaded from our [website](http://spatial.ai/pricing/)

## Methods

<dl>
    <dt>
        <h3 id="func-loadSpatialwControls">
            loadSpatialwControls(<b>apikey</b>, <b>map</b>, <b>vibes</b>, <b>colors</b>, <b>cssText</b>)
            <a class="headerlink" href="#func-loadSpatialwControls" title="Permalink to this definition">¶</a>
        </h3>
    </dt>
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
            <dd> dictionary of vibe categories and sub-categories; we can visualize any number of things on request; current options are: 
                <ul>
                    <li>events</li>
                    <li>now</li>
                    <li>
                        hip 
                        <ul>
                            <li>edgy_cool</li>
                             <li>up_and_coming</li>
                            <li>mainstream</li>
                        </ul>
                    </li>
                    <li>
                        foodie 
                        <ul>
                            <li>food_trucks</li>
                            <li>coffee_lovers</li>
                            <li>organic</li>
                            <li>fine_dining
                        </ul>
                    </li>
                    <li>
                        sights
                        <ul>
                            <li>attractions</li>
                            <li>monuments</li>
                            <li>photo_op
                        </ul>
                    </li>
                    <li>
                        the_arts 
                        <ul>
                            <li>theater</li>
                            <li>galleries</li>
                            <li>architecture
                        </ul>
                    </li>
                    <li>
                        nightlife
                        <ul>
                            <li>dance</li>
                            <li>sports_bars</li>
                            <li>live_music
                        </ul>
                    </li> 
                    <li>
                        healthy
                        <ul>
                            <li>active_living</li>
                            <li>healthy_eats</li>
                            <li>outdoors</li>
                            <li>yoga
                        </ul>
                    </li> 
                    <li>love
                        <ul>
                            <li>majestic_views</li>
                            <li>date_night
                        </ul>
                    </li> 
                    <li>
                        family 
                        <ul>
                            <li>sports</li>
                            <li>excursions</li>
                            <li>educational
                        </ul>
                    </li>
                    <li>
                        culture 
                        <ul>
                            <li>lgbt</li>
                            <li>latin_corridor</li>
                            <li>chinatown
                        </ul>
                    </li>
                    <li>
                        nature 
                        <ul>
                            <li>parks</li>
                            <li>water
                        </ul>
                    </li>
                </ul>
            </dd>
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
    <dt>
        <h3 id="func-loadSpatial">
            loadSpatial(<b>apikey</b>,<b>map</b>,<b>colors</b>)
            <a class="headerlink" href="#func-loadSpatial" title="Permalink to this definition">¶</a>
        </h3>
    </dt>
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
    <dt>
        <h3 id="func-setVibe">
            setVibe(<b>vibe</b>,<b>state</b>)
            <a class="headerlink" href="#func-setVibe" title="Permalink to this definition">¶</a>
        </h3>
    </dt>
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