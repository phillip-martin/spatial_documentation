# Endpoints

All operations are performed using http GET

<dl>
    <dt><h3>GET /api/pointsbyvibe</h3></dt>
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
            <dd>one of the following: [healthy_eats,active_living,photo_op,organic,culture,chinatown,edgy_cool,up_and_coming,mainstream,food_trucks,coffee_lovers,fine_dining,the_arts,theater,galleries,architecture,attractions,monuments,dance,sports_bars,live_music,outdoors,yoga,majestic_views,date_night,sports,excursions,educational,latin_corridor,nature,parks,water,mountains,healthy,family,sights,romantic,hip,nightlife,charming,foodie,lgbt]</dd>
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
            <dd>day of the week, one of:  [mon,tue,wed,thu,fri,sat,sun]</dd>
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
    <dt><h3>GET /api/pointdetail</h3></dt>
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
    <dt><h3>GET /api/getevents</h3></dt>
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
