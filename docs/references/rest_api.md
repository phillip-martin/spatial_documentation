# Endpoints

All operations are performed using http GET

<dl>
    <dt>
        <h3 id="get-apipointsbyvibe">
            GET /api/pointsbyvibe
            <a class="headerlink" href="#get-apipointsbyvibe" title="Permalink to this definition">¶</a>
        </h3>
    </dt>
    <dd>This endpoint is intended for mapping applications. It takes a bounding box and a vibe and returns a list of points.</dd>
    <dd><b>Operators:</b></dd>
    <dd>
        <dl>
            <dt>swlat</dt>
            <dd>southwest latitude of the bounding box</dd>
        </dl>
        <dl>
            <dt>swlng</dt>
            <dd>southwest longitude of the bounding box</dd>
        </dl>
        <dl>
            <dt>nelat</dt>
            <dd>northeast latitude of the bounding box</dd>
        </dl>
        <dl>
            <dt>nelng</dt>
            <dd>northeast longitude of the bounding box</dd>
        </dl>
        <dl>
            <dt>vibe</dt>
            <dd>one of the following vibe categories or sub-categories:
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
                            <li>fine_dining"
                        </ul>
                    </li>
                    <li>
                        sights
                        <ul>
                            <li>attractions</li>
                            <li>monuments</li>
                            <li>photo_op"
                        </ul>
                    </li>
                    <li>
                        the_arts 
                        <ul>
                            <li>theater</li>
                            <li>galleries</li>
                            <li>architecture"
                        </ul>
                    </li>
                    <li>
                        nightlife
                        <ul>
                            <li>dance</li>
                            <li>sports_bars</li>
                            <li>live_music"
                        </ul>
                    </li> 
                    <li>
                        healthy
                        <ul>
                            <li>active_living</li>
                            <li>healthy_eats</li>
                            <li>outdoors</li>
                            <li>yoga"
                        </ul>
                    </li> 
                    <li>love
                        <ul>
                            <li>majestic_views</li>
                            <li>date_night"
                        </ul>
                    </li> 
                    <li>
                        family 
                        <ul>
                            <li>sports</li>
                            <li>excursions</li>
                            <li>educational"
                        </ul>
                    </li>
                    <li>
                        culture 
                        <ul>
                            <li>lgbt</li>
                            <li>latin_corridor</li>
                            <li>chinatown"
                        </ul>
                    </li>
                    <li>
                        nature 
                        <ul>
                            <li>parks</li>
                            <li>water"
                        </ul>
                    </li>
                </ul>
            </dd>
        </dl>
        <dl>
            <dt>apikey</dt>
            <dd>provided key</dd>
        </dl>
        <dl>
            <dt>numgroups (optional)</dt>
            <dd>number of point clusters to return, default is 10</dd>
        </dl>
        <dl>
            <dt>d (optional)</dt>
            <dd>day of the week, one of:  
                <ul>
                    <li>mon</li>
                    <li>tue</li>
                    <li>wed</li>
                    <li>thu</li>
                    <li>fri</li>
                    <li>sat</li>
                    <li>sun</li>
                </ul>
            </dd>
        </dl>
        <dl>
            <dt>s (optional)</dt>
            <dd>time of day, in seconds after midnight; return items between s and an hour later</dd>
        </dl>
    </dd>
    <dd><b>Example Query:</b></dd>
    <dd>
        <pre><code>GET https://spatial.ai/api/pointsbyvibe?swlat=40.509559&swlng=-74.236877&nelat=40.883347&nelng=-73.697174&vibe=hip&apikey=YOURAPIKEY
        </code></pre>
    </dd>
    <dd><b>Example Response:</b></dd>
        <dd>
            <pre><code>
[  
    {  
        "lat":40.75900903,
        "lng":-73.98775802
    },
    {  
        "lat":40.7586,
        "lng":-73.98618
    },
    {  
        "lat":40.75900107,
        "lng":-73.98670793
    },
    {  
        "lat":40.75943,
        "lng":-73.98558
    },
    {  
        "lat":40.75897,
        "lng":-73.98489
    },
    <br/>
    ...
    <br/>
    {  
        "lat":40.7581136,
        "lng":-73.9874761
    },
    {  
        "lat":40.76111111,
        "lng":-73.98583333
    },
    {  
        "lat":40.7586107,
        "lng":-73.9874561
    },
    {  
        "lat":40.75932538,
        "lng":-73.98667837
    }
]
            </code></pre>
        </dd>
</dl>

<dl>
    <dt>
        <h3 id="get-apipointdetail">
            GET /api/pointdetail
            <a class="headerlink" href="#get-apipointdetail" title="Permalink to this definition">¶</a>
        </h3>
    </dt>
    <dd>This endpoint returns the vibe rating of a point.</dd>
    <dd><b>Operators:</b></dd>
    <dd>
        <dl>
            <dt>lat</dt>
            <dd>latitude</dd>
        </dl>
        <dl>
            <dt>lng</dt>
            <dd>longitude</dd>
        </dl>
        <dl>
            <dt>apikey</dt>
            <dd>provided key</dd>
        </dl>
    <dd><b>Example Query:</b></dd>
    <dd>
        <pre><code>https://spatial.ai/api/pointdetail?lat=40.76111111&lng=-73.98583333&apikey=YOURAPIKEY
        </code></pre>
    </dd>
    <dd><b>Example Response:</b></dd>
        <dd>
            <pre><code>
{  
    "foodie":"9.0/10",
    "hot":"9.8/10",
    "active":"9.8/10",
    "culture":"9.4/10",
    "food-trucks":"5.0/10",
    "sights":"7.0/10",
    "romantic":"10.0/10",
    "hip":"9.4/10",
    "lgbt":"4.9/10",
    "now":"10.0/10",
    "dance":"9.6/10",
    "healthy":"9.4/10",
    "family":"9.0/10",
    "nightlife":"10.0/10",
    "healthy-eats":"8.2/10",
    "active-living":"9.6/10",
    "photo-op":"0.5/10",
    "organic":"7.8/10",
    "chinatown":"4.4/10",
    "edgy-cool":"3.9/10",
    "up-and-coming":"7.0/10",
    "mainstream":"10.0/10",
    "coffee-lovers":"9.8/10",
    "fine-dining":"7.6/10",
    "the-arts":"10.0/10",
    "theater":"10.0/10",
    "galleries":"8.8/10",
    "architecture":"5.0/10",
    "attractions":"9.0/10",
    "monuments":"10.0/10",
    "sports-bars":"10.0/10",
    "live-music":"10.0/10",
    "outdoors":"10.0/10",
    "yoga":"9.0/10",
    "majestic-views":"10.0/10",
    "date-night":"10.0/10",
    "sports":"7.0/10",
    "excursions":"2.9/10",
    "educational":"10.0/10",
    "nature":"4.8/10",
    "parks":"4.0/10",
    "water":"2.9/10",
    "lat":40.76111111,
    "lng":-73.98583333,
    "top_behaviors":[  
        "entertainment",
        "eating",
        "drinking"
    ],
    "media_volume":"high",
    "top_hashtags":[  
        "nyc",
        "timessquare",
        "newyork",
        "broadway",
        "newyorkcity",
        "manhattan"
    ]
}
            </pre></code>
        </dd>
    </dd>
</dl>

<dl>
    <dt>
        <h3 id="get-apigetevents">
            GET /api/getevents
            <a class="headerlink" href="#get-apigetevents" title="Permalink to this definition">¶</a>
        </h3>
    </dt>
    <dd>This endpoint returns event listings.</dd>
    <dd><b>Operators:</b></dd>
    <dd>
        <dl>
            <dt>swlat</dt>
            <dd>southwest latitude of the bounding box</dd>
        </dl>
        <dl>
            <dt>swlng</dt>
            <dd>southwest longitude of the bounding box</dd>
        </dl>
        <dl>
            <dt>nelat</dt>
            <dd>northeast latitude of the bounding box</dd>
        </dl>
        <dl>
            <dt>nelng</dt>
            <dd>northeast longitude of the bounding box</dd>
        </dl>
        <dl>
            <dt>starts_before (optional)</dt>
            <dd>events starting before this time (in epoch seconds)</dd>
        </dl>
        <dl>
            <dt>starts_after (optional)</dt>
            <dd>events starting after this time (in epoch seconds)</dd>
        </dl>
        <dl>
            <dt>ends_before (optional) </dt>
            <dd>events ending before this time (in epoch seconds)</dd>
        </dl>
        <dl>
            <dt>ends_after (optional)</dt>
            <dd>events ending after this time (in epoch seconds)</dd>
        </dl>
        <dl>
            <dt>filter (optional)</dt>
            <dd>filter event name by this</dd>
        </dl>
    </dd>
    <dd><b>Example Query:</b></dd>
    <dd>
        <pre><code>https://spatial.ai/api/getevents?swlat=39.961299&swlng=-105.298001&nelat=40.095373&nelng=-105.187108&starts_before=1463708397&starts_after=1463679597&apikey=YOURAPIKEY
        </code></pre>
    </dd>
    <dd><b>Example Response:</b></dd>
        <dd>
            <pre><code>
[  
    {  
        "lat":39.9844668,
        "lng":-105.2491333,
        "name":"Open Mic Night",
        "start_time":1463702400,
        "end_time":1463713200
    },
    {  
        "lat":40.01778810831,
        "lng":-105.28111666109,
        "location":"Boulder Book Store",
        "name":"Ren & Helen Davis - \"Landscapes for the People\"",
        "start_time":1463707800,
        "end_time":1463711400,
        "category":""
    },
    {  
        "lat":40.020120333631,
        "lng":-105.27544222577,
        "location":"Etown",
        "name":"Glue Talk with Dr. Stan Tatkin and Bruce Tift",
        "start_time":1463707800,
        "end_time":1463711400,
        "category":""
    },
    {  
        "lat":40.0155716,
        "lng":-105.2616425,
        "location":"The mama'hood Boulder",
        "name":"The Wisdom of Birth",
        "start_time":1463702400,
        "end_time":1463713200,
        "category":""
    },
    {  
        "lat":40.0155716,
        "lng":-105.2616425,
        "location":"The mama'hood Boulder",
        "name":"Kids Yoga",
        "start_time":1463696100,
        "end_time":1463699700,
        "category":""
    },
    {  
        "lat":40.022613,
        "lng":-105.247622,
        "location":"Sanitas Brewing",
        "name":"Pullin' The Nails on the Barrels Beer Tasting",
        "start_time":1463702400,
        "end_time":1463713200,
        "category":""
    },
    {  
        "lat":40.01822,
        "lng":-105.22924,
        "location":"Vapor Distillery",
        "name":"C-Bob's Gin Joint Jam at Vapor's Speakeasy",
        "start_time":1463702400,
        "end_time":1463716800,
        "category":""
    },
    {  
        "lat":40.0269814,
        "lng":-105.2823868,
        "location":"The Integral Center",
        "name":"Game Night ~ Permission with Maria Bailey and Jason Digges",
        "start_time":1463706000,
        "end_time":1463713200,
        "category":""
    },
    {  
        "lat":40.0347701,
        "lng":-105.2764318,
        "location":"Growing Gardens",
        "name":"After School Gardening Club",
        "start_time":1463694300,
        "end_time":1463699700,
        "category":""
    },
    {  
        "lat":40.0081062,
        "lng":-105.2648163,
        "location":"Roadhouse Boulder Depot",
        "name":"Going Away Party for Marni",
        "start_time":1463700600,
        "end_time":1463704200,
        "category":""
    },
    {  
        "lat":40.02642,
        "lng":-105.24419,
        "location":"Green Guru",
        "name":"Fundraiser Happy Hour",
        "start_time":1463698800,
        "end_time":1463713200,
        "category":""
    },
    {  
        "lat":40.019420085765,
        "lng":-105.26099695362,
        "location":"Dairy Arts Center",
        "name":"International OCEAN FILM TOUR Volume 3 | Boulder",
        "start_time":1463707800,
        "end_time":1463711400,
        "category":""
    }
]
            </code></pre>
        </dd>
    </dd>
</dl>


<dl>
    <dt>
        <h3 id="get-query">
            GET /api/query
            <a class="headerlink" href="#get-query" title="Permalink to this definition">¶</a>
        </h3>
    </dt>
    <dd>This endpoint processes a query string, such as 'show me hip bars in pittsburgh' or 'events in detroit monday'</dd>
    <dd><b>Operators:</b></dd>
    <dd>
        <dl>
            <dt>q</dt>
            <dd>query string
        </dl>
        <dl>
            <dt>apikey</dt>
            <dd>provided key</dd>
        </dl>
        <dl>
            <dt>swlat</dt>
            <dd>southwest latitude of the bounding box</dd>
        </dl>
        <dl>
            <dt>swlng</dt>
            <dd>southwest longitude of the bounding box</dd>
        </dl>
        <dl>
            <dt>nelat</dt>
            <dd>northeast latitude of the bounding box</dd>
        </dl>
        <dl>
            <dt>nelng</dt>
            <dd>northeast longitude of the bounding box</dd>
        </dl>
    </dd>
    <dd><b>Response</b>
    </dd>
    <dd>Returns a dictionary with the following
        <dl>
            <dt>poi</dt>
            <dd>array of points of interest; events or venues</dd>
        </dl>
        <dl>
            <dt>hex</dt>
            <dd>array of regions matching combined vibes in the query</dd>
        </dl>
        <dl>
            <dt>vibes</dt>
            <dd>list of vibes processed from query string</dd>
        </dl>
        <dl>
            <dt>recenter</dt>
            <dd>coordinates to recenter the map</dd>
        </dl>
    </dd>
    <dd><b>Example Query:</b></dd>
    <dd>
        <pre><code>GET https://spatial.ai/api/query?q=show%20me%20hip%20bars%20in%20pittsburgh&apikey=YOUR_API_KEY
        </code></pre>
    </dd>
    <dd><b>Example Response:</b></dd>
        <dd>
            <pre><code>
{  
    "poi":[  
        {  
            "name":"Cattivo",
            "lat":40.472509,
            "lng":-79.961687,
            "rating":4,
            "tags":[  
                "bars",
                "music venues"
            ],
            "type":"venue"
        },
        {  
            "name":"New Amsterdam",
            "lat":40.472148,
            "lng":-79.959533,
            "rating":4,
            "tags":[  
                "dance clubs",
                "pubs"
            ],
            "type":"venue"
        },
        {  
            "name":"Mister Grooming & Goods",
            "lat":40.472132,
            "lng":-79.958813,
            "rating":4.5,
            "tags":[  
                "barbers"
            ],
            "type":"venue"
        },
        
        ...
        
        {  
            "name":"Industry Public House",
            "lat":40.4707662016153,
            "lng":-79.9603226780891,
            "rating":3.5,
            "tags":[  
                "american (new)",
                "cocktail bars"
            ],
            "type":"venue"
        },
        {  
            "name":"Tender Bar & Kitchen",
            "lat":40.470578,
            "lng":-79.960043,
            "rating":3.5,
            "tags":[  
                "american (new)",
                "cocktail bars"
            ],
            "type":"venue"
        },
        {  
            "name":"Hambone's Pub",
            "lat":40.470474,
            "lng":-79.960431,
            "rating":3.5,
            "tags":[  
                "pubs",
                "american (new)"
            ],
            "type":"venue"
        }
    ],
    "hex":[  
        {  
            "swlat":40.42798792337201,
            "swlng":-79.9681528346991,
            "nelat":40.43161115225921,
            "nelng":-79.96340835811442
        },
        {  
            "swlat":40.42798792337201,
            "swlng":-79.97764178786844,
            "nelat":40.43161115225921,
            "nelng":-79.97289731128376
        },
        
        ...
        
        {  
            "swlat":40.42798792337201,
            "swlng":-79.97289731128376,
            "nelat":40.43161115225921,
            "nelng":-79.9681528346991
        },
        {  
            "swlat":40.42436469448481,
            "swlng":-79.98238626445311,
            "nelat":40.42798792337201,
            "nelng":-79.97764178786844
        }
    ],
    "vibes":[  
        "hip"
    ],
    "recenter":{  
        "lat":40.436945,
        "lng":-79.9755245
    }
}
            </code></pre>
        </dd>
</dl>