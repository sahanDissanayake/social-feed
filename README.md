Social-feed
===========
<a href="http://pavelk2.github.io/social-feed/" target="_blank"><img src="http://habrastorage.org/files/7f6/0f6/e3f/7f60f6e3fab24b0d8c2e4b9b15ccbfc0.png"/></a>
The jQuery plugin which shows a user feed from the most popular social networks.<br/> 
Currently are supported: <a href="http://facebook.com">Facebook</a>, <a href="http://instagram.com">Instagram</a>, <a href="http://vk.com">VK</a>, <a href="http://plus.google.com">Google+</a>, (<a href="http://twitter.com">Twitter</a> is currently not supported)
<hr>
If you use this plugin, please <a href="mailto:pavel@kucherbaev.com">write me a short message</a> with a link to the project where you embed the plugin, and some features you want to have implemented here. It will help me to stay focused on the important issues and see the global picture!
<br/><strong>It is not mandatory, but I really appreciate it!</strong>
<p>
<strong>Attention:</strong> After Twitter has prohibided an anonymous fetching of tweets - this function is currently not supported. Wait an update with a fix.
</p>
<h6>Check out my other projects: <a href="http://kucherbaev.com" target="_blank"> http://kucherbaev.com</a><h6>

<h4>Getting started</h4>
Connect css:

        <!-- Social-feed css -->
        <link href="css/jquery.socialfeed.css" rel="stylesheet" type="text/css">
        <!-- font-awesome for social network icons -->
        <link href="//netdna.bootstrapcdn.com/font-awesome/4.0.3/css/font-awesome.css" rel="stylesheet">

Create a container for your feed:

        <div class="social-feed-container"></div>

Connect js:

        <!-- jQuery -->
        <script src="http://code.jquery.com/jquery-latest.min.js"></script>
    
        <!-- doT.js for rendering templates and moment.js for showing time ago -->
        <script src="dependencies/doT.min.js"></script>
        <script src="dependencies/moment.min.js"></script>
    
        <!-- Social-feed js -->
        <script src="js/jquery.socialfeed.js"></script>

Initialize the social-feed plugin:

    <script>
    $(document).ready(function(){
        $('.social-feed-container').socialfeed({
                    // FACEBOOK
                    facebook:{
                        accounts:['@teslamotors','#teslamotors'],
                        limit:2,
                        access_token:'YOUR_FACEBOOK_ACCESS_TOKEN' // APP_ID|APP_SECRET
                    },
                    // VK
                    vk:{
                        accounts:['@125936523','#teslamotors'], 
                        limit:2,
                        source:'all'
                    },
                    // GOOGLEPLUS
                    google:{
                         access_token: 'YOUR_GOOGLE_PLUS_ACCESS_TOKEN', 
                         accounts: ['#teslamotors'],
                         limit: 2
                     },
                    // INSTAGRAM
                    instagram:{
                        accounts:['@teslamotors','#teslamotors'],
                        client_id:'YOUR_INSTAGRAM_CLIENT_ID',
                        limit:2
                    },
                    // BLOGSPOT
                    /*blogspot:{
                        accounts:['@iman-khaghanifar']
                    },*/
                    // GENERAL SETTINGS
                    length:400,
                    show_media:true,
                    // Moderation function - if returns false, template will have class hidden
                    moderation: function(content){
                        return  (content.text) ? content.text.indexOf('fuck') == -1 : true;
                    },
                    //update_period: 5000,
                    // When all the posts are collected and displayed - this function is evoked
                    callback: function(){
                        console.log('all posts are collected');
                    }
                });
        });
        </script>

When you run the plugin, make sure that you have your <strong>webserver running</strong>

If you want to change the layout of the feed, you can do it in the <em>template.html</em> file.
<br/>
Also you can simply create template as a string and pass it as template_html parameter.
If you don't need to show the feed from all the supported social networks, put the credentials only for those you need.

<h4>Dependencies:</h4>
-  http://fontawesome.io/ - for displaying icons of social networks
-  http://momentjs.com/ - for displaying time ago
-  http://olado.github.io/doT/ - for rendering templates

<h4>License:</h4>
MIT

