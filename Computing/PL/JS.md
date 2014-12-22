<!DOCTYPE html>
<!--[if IE 8]>
<html id="ie8" lang="en">
<![endif]-->
<!--[if !(IE 8)]><!-->
<html lang="en">
<!--<![endif]-->
<!--
	generated in 0.488 seconds
	87983 bytes batcached for 300 seconds
-->
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<!-- Always force latest IE rendering engine (even in intranet) & Chrome Frame -->
<meta http-equiv="X-UA-Compatible" content="IE=edge,chrome=1">
<title>The Secret Life of JavaScript Primitives | JavaScript, JavaScript...</title>
<link rel="profile" href="http://gmpg.org/xfn/11" />
<link rel="pingback" href="http://javascriptweblog.wordpress.com/xmlrpc.php" />
<!--[if lt IE 9]>
<script src="http://s1.wp.com/wp-content/themes/pub/ari/js/html5.js?m=1331670375g" type="text/javascript"></script>
<![endif]-->

<meta name="google-site-verification" content="GFQL_ZeMCS7ugiWO25zGQZE5pxnaJJC3mLBScV0d20U" />
<link rel="alternate" type="application/rss+xml" title="JavaScript, JavaScript... &raquo; Feed" href="http://javascriptweblog.wordpress.com/feed/" />
<link rel="alternate" type="application/rss+xml" title="JavaScript, JavaScript... &raquo; Comments Feed" href="http://javascriptweblog.wordpress.com/comments/feed/" />
<link rel="alternate" type="application/rss+xml" title="JavaScript, JavaScript... &raquo; The Secret Life of JavaScript Primitives Comments Feed" href="http://javascriptweblog.wordpress.com/2010/09/27/the-secret-life-of-javascript-primitives/feed/" />
<script type="text/javascript">
/* <![CDATA[ */
function addLoadEvent(func){var oldonload=window.onload;if(typeof window.onload!='function'){window.onload=func;}else{window.onload=function(){oldonload();func();}}}
/* ]]> */
</script>
<link rel='stylesheet' id='all-css-0' href='http://s0.wp.com/_static/??-eJx9j9EOgjAMRX/IWYlKeDF+y9jqGHR0YV0If+8wMUYxvPU25/SmMEdleBQcBUJWkbLzY4IUPOESJ+7RyHc6mpQO8F8jP2CCHiVqM6hX2uAtsfsI7BxazqIeTMQzzN463O2YkLSgVZGT/KQ9zfCEZR+ilpUIaL1GwlCwPS3E+m2tY1f+2tZIV+4kiLkFPXlIshCu0D3cqsupOp/rprn2T9GmiBc=' type='text/css' media='all' />
<link rel='stylesheet' id='ari-droid-sans-css'  href='http://fonts.googleapis.com/css?family=Droid+Sans%3A400%2C700&#038;ver=4.0-alpha' type='text/css' media='all' />
<link rel='stylesheet' id='ari-droid-serif-css'  href='http://fonts.googleapis.com/css?family=Droid+Serif%3A400%2C700%2C400italic%2C700italic&#038;ver=4.0-alpha' type='text/css' media='all' />
<link rel='stylesheet' id='all-css-4' href='http://s1.wp.com/_static/??-eJx9j8EKwjAQRH/IuNSK0oP4LWmyblc22ZJs6e839CCK0Ns8mDcwwJDVOGiun3AOtZ5gnV0Dw2yQFjfLQtw6hOpEgzfW/APuJZ7LkVpwFKUWCVrrC/8kmzBhhekKJDp6OVpdORJa3SdJNRb0cX/wTI+uH4a+7y7323sDz0lVwQ==' type='text/css' media='all' />
<link rel='stylesheet' id='print-css-4' href='http://s0.wp.com/wp-content/mu-plugins/global-print/global-print.css?m=1387483371g' type='text/css' media='print' />
<script type='text/javascript'>
/* <![CDATA[ */
var LoggedOutFollow = {"invalid_email":"Your subscription did not succeed, please try again with a valid email address."};
/* ]]> */
</script>
<script type='text/javascript' src='http://s1.wp.com/_static/??-eJyFj90OwiAMhV9IZFs08cb4LNvoSBEoUpDo08sSNTpNdtW/7/S0sgQxkk/gkzQsHQ1oQWSG2OvaE+gn2hreyMqhH21WwDNoLhni7RlWAeFQxz7B1qF/wR+ugTg5YK6Wf6bfVuivCGUVM5BCP55FBMb7z9bBkhbBZo2eZc01KMpJTGQtFVlQaUhLjctvRQRbn1FivntRVdXJHdtd0+wPbdd05gFmiIRF'></script>
<link rel='stylesheet' id='all-css-0' href='http://s2.wp.com/wp-content/mu-plugins/highlander-comments/style.css?m=1377793621g' type='text/css' media='all' />
<!--[if lt IE 8]>
<link rel='stylesheet' id='highlander-comments-ie7-css'  href='http://s2.wp.com/wp-content/mu-plugins/highlander-comments/style-ie7.css?m=1351637563g&#038;ver=20110606' type='text/css' media='all' />
<![endif]-->
<link rel="EditURI" type="application/rsd+xml" title="RSD" href="http://javascriptweblog.wordpress.com/xmlrpc.php?rsd" />
<link rel="wlwmanifest" type="application/wlwmanifest+xml" href="http://javascriptweblog.wordpress.com/wp-includes/wlwmanifest.xml" /> 
<link rel='prev' title='Auto-generating JavaScript Unit&nbsp;Tests' href='http://javascriptweblog.wordpress.com/2010/09/20/auto-generating-javascript-unit-tests/' />
<link rel='next' title='Rethinking JavaScript for-loops' href='http://javascriptweblog.wordpress.com/2010/10/11/rethinking-javascript-for-loops/' />
<meta name="generator" content="WordPress.com" />
<link rel='canonical' href='http://javascriptweblog.wordpress.com/2010/09/27/the-secret-life-of-javascript-primitives/' />
<link rel='shortlink' href='http://wp.me/pQpop-mS' />
<link rel="alternate" type="application/json+oembed" href="https://public-api.wordpress.com/oembed/1.0/?format=json&amp;url=http%3A%2F%2Fjavascriptweblog.wordpress.com%2F2010%2F09%2F27%2Fthe-secret-life-of-javascript-primitives%2F&amp;for=wpcom-auto-discovery" /><link rel="alternate" type="application/xml+oembed" href="https://public-api.wordpress.com/oembed/1.0/?format=xml&amp;url=http%3A%2F%2Fjavascriptweblog.wordpress.com%2F2010%2F09%2F27%2Fthe-secret-life-of-javascript-primitives%2F&amp;for=wpcom-auto-discovery" />
<!-- Jetpack Open Graph Tags -->
<meta property="og:type" content="article" />
<meta property="og:title" content="The Secret Life of JavaScript Primitives" />
<meta property="og:url" content="http://javascriptweblog.wordpress.com/2010/09/27/the-secret-life-of-javascript-primitives/" />
<meta property="og:description" content="You may not know it but, in JavaScript, whenever you interact with string, number or boolean primitives you enter a hidden world of object shadows and coercion. So dust off your Sherlock Holmes out..." />
<meta property="article:published_time" content="2010-09-27T07:01:52+00:00" />
<meta property="article:modified_time" content="2012-02-28T05:39:00+00:00" />
<meta property="article:author" content="http://javascriptweblog.wordpress.com/author/angusjs/" />
<meta property="og:site_name" content="JavaScript, JavaScript..." />
<meta property="og:image" content="http://wordpress.com/i/blank.jpg?m=1383295312g" />
<meta name="twitter:site" content="@wordpressdotcom" />
<meta name="twitter:card" content="summary" />
<meta property="fb:app_id" content="249643311490" />
<meta property="article:publisher" content="https://www.facebook.com/WordPresscom" />
<link rel="shortcut icon" type="image/x-icon" href="http://s2.wp.com/i/favicon.ico?m=1311975824g" sizes="16x16 24x24 32x32 48x48" />
<link rel="icon" type="image/x-icon" href="http://s2.wp.com/i/favicon.ico?m=1311975824g" sizes="16x16 24x24 32x32 48x48" />
<link rel="apple-touch-icon-precomposed" href="http://s0.wp.com/i/webclip.png?m=1391188133g" />
<link rel='openid.server' href='http://javascriptweblog.wordpress.com/?openidserver=1' />
<link rel='openid.delegate' href='http://javascriptweblog.wordpress.com/' />
<link rel="search" type="application/opensearchdescription+xml" href="http://javascriptweblog.wordpress.com/osd.xml" title="JavaScript, JavaScript..." />
<link rel="search" type="application/opensearchdescription+xml" href="http://wordpress.com/opensearch.xml" title="WordPress.com" />
	<style>
		/* First link color */
		a,
		.comment-meta a:hover,
		.entry-meta a:hover,
		.entry-title a:hover,
		.logged-in-as a:hover,
		.main-navigation a:hover,
		.main-navigation li.current_page_item > a,
		.main-navigation li.current_page_ancestor > a,
		.main-navigation li.current-menu-item > a,
		.main-navigation li.current-menu_ancestor > a,
		.post-edit-link:hover,
		.site-footer a:hover,
		.widget a:hover,
		.widget_flickr #flickr_badge_uber_wrapper a:hover {
			color: #2c52f5;
		}
		.bypostauthor .avatar,
		button:hover,
		html input[type="button"]:hover,
		input[type="reset"]:hover,
		input[type="submit"]:hover,
		.widget_calendar #wp-calendar tbody td a {
			background: #2c52f5;
		}
	</style>
<meta name="application-name" content="JavaScript, JavaScript..." /><meta name="msapplication-window" content="width=device-width;height=device-height" /><meta name="msapplication-tooltip" content="by Angus Croll" /><meta name="msapplication-task" content="name=Subscribe;action-uri=http://javascriptweblog.wordpress.com/feed/;icon-uri=http://s2.wp.com/i/favicon.ico" /><meta name="msapplication-task" content="name=Sign up for a free blog;action-uri=http://wordpress.com/signup/;icon-uri=http://s2.wp.com/i/favicon.ico" /><meta name="msapplication-task" content="name=WordPress.com Support;action-uri=http://support.wordpress.com/;icon-uri=http://s2.wp.com/i/favicon.ico" /><meta name="msapplication-task" content="name=WordPress.com Forums;action-uri=http://forums.wordpress.com/;icon-uri=http://s2.wp.com/i/favicon.ico" /><meta name="title" content="The Secret Life of JavaScript Primitives | JavaScript, JavaScript... on WordPress.com" />
<meta name="description" content="You may not know it but, in JavaScript, whenever you interact with string, number or boolean primitives you enter a hidden world of object shadows and coercion. So dust off your Sherlock Holmes outfit and read on... The basics Objects are aggregations of properties. A property can reference an object or a primitive. Primitives are&hellip;" />
	<style type="text/css">
			.site-title a {
			color: #0d1298;
		}
		</style>
	
<script type='text/javascript' src='//partner.googleadservices.com/gampad/google_service.js'>
</script>
<script type='text/javascript'>
if ( typeof GS_googleAddAdSenseService == 'function' ) { GS_googleAddAdSenseService("ca-pub-3443918307802676"); }
if ( typeof GS_googleEnableAllServices == 'function' ) { GS_googleEnableAllServices() };
</script>
<script type="text/javascript" src="//c.amazon-adsystem.com/aax2/amzn_ads.js"></script>
<script type="text/javascript">
try { amznads.getAds("3033","300x250"); } catch(e) { /* ignore */ }
</script>
<script type="text/javascript">
var amznKeys = amznads.getKeys();
if (typeof amznKeys != "undefined" && amznKeys != "") { for (var i =0; i < amznKeys.length; i++) { var key = amznKeys[i]; GA_googleAddAttr("amzn", key);} }
document.close();
</script>
<script type='text/javascript'>
if ( typeof GA_googleAddSlot == 'function' ) { GA_googleAddSlot("ca-pub-3443918307802676", "wpcom_below_post_adsafe"); }
</script>
<script type='text/javascript'>
if ( typeof GA_googleFetchAds == 'function' ) { GA_googleFetchAds(); }
</script>

<script type="text/javascript">
var wpcom_ads = { bid: 12490669, pt: 'permalink', wa: 0, as: 1, domain: 'javascriptweblog.wordpress.com', url: 'http://javascriptweblog.wordpress.com/2010/09/27/the-secret-life-of-javascript-primitives/', gid: '', };
</script>
<style type="text/css" id="syntaxhighlighteranchor"></style>
<script type="text/javascript">
	window.google_analytics_uacct = "UA-52447-2";
</script>

<script type="text/javascript">
	var _gaq = _gaq || [];
	_gaq.push(['_setAccount', 'UA-52447-2']);
	_gaq.push(['_setDomainName', 'wordpress.com']);
	_gaq.push(['_initData']);
	_gaq.push(['_trackPageview']);

	(function() {
		var ga = document.createElement('script'); ga.type = 'text/javascript'; ga.async = true;
		ga.src = ('https:' == document.location.protocol ? 'https://ssl' : 'http://www') + '.google-analytics.com/ga.js';
		(document.getElementsByTagName('head')[0] || document.getElementsByTagName('body')[0]).appendChild(ga);
	})();
</script>
</head>

<body class="single single-post postid-1418 single-format-standard mp6 color-light sidebar-content highlander-enabled highlander-light">
<div id="page" class="hfeed site clear-fix">
	
	<div id="subsidiary">
		<header id="masthead" class="site-header" role="banner">
			<hgroup>
				<h1 class="site-title"><a href="http://javascriptweblog.wordpress.com/" title="JavaScript, JavaScript&#8230;" rel="home">JavaScript, JavaScript&#8230;</a></h1>
				<h2 class="site-description">by Angus Croll</h2>
			</hgroup>
					</header><!-- #masthead .site-header -->
		

	<div id="secondary" class="widget-area" role="complementary">
				<aside id="text-3" class="widget widget_text">			<div class="textwidget"><a href="http://feeds.feedburner.com/JavascriptJavascript" style="border:none;" title="Subscribe to my feed" rel="alternate"><img src="https://encrypted-tbn2.gstatic.com/images?q=tbn:ANd9GcSUXbOkM_1i2DSPcJ2giZYfcwIVoi3Pvui6VvHN4JOGi0tQKGQD4g" style="vertical-align:text-middle;height:44px;width:36x;" alt=""></a>&nbsp;&nbsp;<a href="https://www.twitter.com/angusTweets" style="border:none;"><img src="https://twitter.com/images/resources/twitter-bird-blue-on-white.png" style="vertical-align:text-middle;height:44px;width:44px;" alt="Follow angusTweets on Twitter" /></a><a href="https://github.com/angus-c" title="Follow me on GitHub"><img style="vertical-align:text-middle;height:44px;width:44px;" src="https://github.com/github/media/raw/master/octocats/octocat.png" alt="Follow me on GitHub"></a></div>
		</aside><aside id="text-12" class="widget widget_text">			<div class="textwidget"><span style="font-family:'droid sans', arial, sans-serif;font-size:14px;font-style:normal;font-weight:normal;color:#000000;">I also blog here...</span><br><a style="font-family:'droid sans', arial, sans-serif;font-size:16px;font-style:normal;font-weight:bold;color:#0000FF;" href="http://blog.anguscroll.com/">Angus on Svbtle</a>
<br><br>
<span style="font-family:'droid sans', arial, sans-serif;font-size:14px;font-style:normal;font-weight:normal;color:#000000;">...and I wrote these...</span><br><a style="font-family:'droid sans', arial, sans-serif;font-size:16px;font-style:normal;font-weight:bold;color:#0000FF;" href="http://byfat.xxx/if-hemingway-wrote-javascript">If Hemingway wrote JavaScript</a><br>
<a style="font-family:'droid sans', arial, sans-serif;font-size:16px;font-style:normal;font-weight:bold;color:#0000FF;" href="http://blog.anguscroll.com/if-kerouac-wrote-javascript">If Kerouac wrote JavaScript</a><br>
<a style="font-family:'droid sans', arial, sans-serif;font-size:16px;font-style:normal;font-weight:bold;color:#0000FF;" href="http://blog.anguscroll.com/tupac-does-javascript">If Nabokov wrote JavaScript</a><br>
<a style="font-family:'droid sans', arial, sans-serif;font-size:16px;font-style:normal;font-weight:bold;color:#0000FF;" href="http://blog.anguscroll.com/macbeths-lost-callback">Macbeth's lost callback</a>
<br><br>
<span style="font-family:'droid sans', arial, sans-serif;font-size:14px;font-style:normal;font-weight:normal;color:#000000;">..and I gave these talks...</span>
<br><a style="font-family:'droid sans', arial, sans-serif;font-size:16px;font-style:normal;font-weight:bold;color:#0000FF;" href="https://speakerdeck.com/anguscroll/parlez-vous-javascript">Parlez-vous JavaScript</a>
<br><a style="font-family:'droid sans', arial, sans-serif;font-size:16px;font-style:normal;font-weight:bold;color:#0000FF;" href="https://speakerdeck.com/anguscroll/break-all-the-rulez">Break all the Rulez</a>
<br><a style="font-family:'droid sans', arial, sans-serif;font-size:16px;font-style:normal;font-weight:bold;color:#0000FF;" href="https://speakerdeck.com/anguscroll/the-politics-of-javascript">The Politics of JavaScript</a>
<br><br><br><br><br><br><br><br><br><br><br></div>
		</aside><aside id="text-7" class="widget widget_text">			<div class="textwidget"><a href="http://feedjit.com/ir1/36a838868ab6245b84eef90cd00c1327/"><img src="http://feedjit.com/b/36a838868ab6245b84eef90cd00c1327.png" alt="" border="0" style="width:0;height:0;" /></a></div>
		</aside>	</div><!-- #secondary .widget-area -->
	</div>

	<div id="main" class="clear-fix">
		<div id="primary" class="site-content">
			<div id="content" role="main">

			
				
<article id="post-1418" class="post-1418 post type-post status-publish format-standard hentry category-javascript tag-boolean tag-coercion tag-number tag-objects tag-primitives tag-string clear-fix">
	
	<header class="entry-header">
					<h1 class="entry-title">The Secret Life of JavaScript Primitives</h1>
			</header><!-- .entry-header -->

		<div class="entry-content">
		<p>You may not know it but, in JavaScript, whenever you interact with string, number or boolean primitives you enter a hidden world of object shadows and coercion. So dust off your Sherlock Holmes outfit and read on&#8230;</p>
<p><strong><span id="more-1418"></span></strong></p>
<h4 style="color:black;">The basics</h4>
<p>Objects are aggregations of properties. A property can reference an object or a primitive. Primitives are values, they have no properties.</p>
<p>In JavaScript there are 5 primitive types: <code>undefined</code>, <code>null</code>, <code>boolean</code>, <code>string</code> and <code>number</code>. Everything else is an object. The primitive types boolean, string and number can be wrapped by their object counterparts. These objects are instances of the <code>Boolean</code>, <code>String</code> and <code>Number</code> constructors respectively. </p>
<pre class="brush: jscript; title: ; wrap-lines: false; notranslate" title="">typeof true; //&quot;boolean&quot;
typeof Boolean(true); //&quot;boolean&quot;
typeof new Boolean(true); //&quot;object&quot;
typeof (new Boolean(true)).valueOf(); //&quot;boolean&quot;

typeof &quot;abc&quot;; //&quot;string&quot;
typeof String(&quot;abc&quot;); //&quot;string&quot;
typeof new String(&quot;abc&quot;); //&quot;object&quot;
typeof (new String(&quot;abc&quot;)).valueOf(); //&quot;string&quot;

typeof 123; //&quot;number&quot;
typeof Number(123); //&quot;number&quot;
typeof new Number(123); //&quot;object&quot;
typeof (new Number(123)).valueOf(); //&quot;number&quot;
</pre>
<p>. </p>
<h4 style="color:black;">If primitives have no properties, why does <code>"abc".length</code> return a value?</h4>
<p>Because JavaScript will readily coerce between primitives and objects. In this case the string value is coerced to a string object in order to access the property length. The string object is only used for a  fraction of second after which it is sacrificed to the Gods of garbage collection &#8211; but in the spirit of the TV discovery shows, we will trap the elusive creature and preserve it for further analysis&#8230;</p>
<pre class="brush: jscript; title: ; wrap-lines: false; notranslate" title="">
String.prototype.returnMe= function() {
    return this;
}

var a = &quot;abc&quot;;
var b = a.returnMe();  

a; //&quot;abc&quot; 
typeof a; //&quot;string&quot; (still a primitive)
b; //&quot;abc&quot;
typeof b; //&quot;object&quot;</pre>
<p>&#8230;and as with many well meaning scientific investigations we have now interfered with the natural progression of things and prevented the object from being garbage collected so long as <code>b</code> is around. Heisenberg is alive and well <span class='wp-smiley emoji emoji-wink' title=';-)'>;-)</span>   </p>
<p>(Note that in strict mode, the elusive creature gets away &#8211; thanks @DmitrySoshnikov)</p>
<p>Here&#8217;s a more environmentally responsible example that verifies the object type without interfering with garbage collection:  </p>
<pre class="brush: jscript; title: ; wrap-lines: false; notranslate" title="">Number.prototype.toString = function() {
    return typeof this;
}

(123).toString(); //&quot;object&quot;</pre>
<p>.<br />
By this means primitives have access to all the properties (including methods) defined by their respective object constructors.</p>
<h4 style="color:black;">And these objects can also be coerced to values?</h4>
<p>Yes. Mostly. Objects of this type are merely wrappers, their value is the primitive they wrap and they will generally coerce down to this value as required. For full details see <a href="http://javascriptweblog.wordpress.com/2010/05/03/the-value-of-valueof/" target="_blank">this article</a>.  </p>
<pre class="brush: jscript; title: ; wrap-lines: false; notranslate" title="">
//object coerced to primitive 
var Twelve = new Number(12); 
var fifteen = Twelve + 3; 
fifteen; //15
typeof fifteen; //&quot;number&quot; (primitive)
typeof Twelve; //&quot;object&quot;; (still object)

//another object coerced to primitive
new String(&quot;hippo&quot;) + &quot;potamus&quot;; //&quot;hippopotamus&quot; 

//object not coerced (because 'typeof' operator can work with objects)
typeof new String(&quot;hippo&quot;) + &quot;potamus&quot;; //&quot;objectpotamus&quot;
</pre>
<p>Sadly boolean objects do not coerce so easily. And, to add insult to injury, a boolean object evaluates to true unless its value is null or undefined. Try this:</p>
<pre class="brush: jscript; title: ; wrap-lines: false; notranslate" title="">
if (new Boolean(false)) {
    alert(&quot;true???&quot;); 
}
</pre>
<p>Usually you have to explicitly ask boolean objects for their value. The following might be useful for determining whether the value is &#8220;truthy&#8221; of &#8220;falsey&#8221;&#8230;.</p>
<pre class="brush: jscript; title: ; wrap-lines: false; notranslate" title="">
var a = &quot;&quot;;
new Boolean(a).valueOf(); //false
</pre>
<p>&#8230;but in practice its easier to do this&#8230;</p>
<pre class="brush: jscript; title: ; wrap-lines: false; notranslate" title="">
var a = Boolean(&quot;&quot;);
a; //false
</pre>
<p>..or even this&#8230;</p>
<pre class="brush: jscript; title: ; wrap-lines: false; notranslate" title="">
var a = &quot;&quot;;
!!a; //false
</pre>
<p>.</p>
<h4 style="color:black;">Does coercion allow me to assign values to primitives?</h4>
<p>No. </p>
<pre class="brush: jscript; title: ; wrap-lines: false; notranslate" title="">
var primitive = &quot;september&quot;;
primitive.vowels = 3;

primitive.vowels; //undefined; </pre>
<p>If JavaScript detects an attempt to assign a property to a primitive it will indeed coerce the primitive to an object. But, as with the previous examples, this new object has no references and will immediately become fodder for garbage collection.</p>
<p>Here&#8217;s  a pseudo-code representation of the same example to illustrate what really happens</p>
<pre class="brush: jscript; title: ; wrap-lines: false; notranslate" title="">
var primitive = &quot;september&quot;;
primitive.vowels = 3;
//new object created to set property 
(new String(&quot;september&quot;)).vowels = 3;

primitive.vowels;
//another new object created to retrieve property 
(new String(&quot;september&quot;)).vowels; //undefined
</pre>
<p>So as you can see, its not only useless but pretty wasteful. </p>
<h4 style="color:black;">Wrap up</h4>
<p>It turns out that the ability to assign properties is just about the only advantage of objects over their primitive counterparts, but in practice even this is a dubious quality. Strings, booleans and numbers have specific and well defined purposes and redefining them as state holders is likely just going to confuse people. Moreover, since primitives are immutable you cannot modify them by tweaking the properties of the object wrapper: </p>
<pre class="brush: jscript; title: ; wrap-lines: false; notranslate" title="">var me = new String(&quot;Angus&quot;);
me.length = 2; //(error in strict mode)
me.length; //5 (not 2 - thanks @joseanpg)
me.valueOf(); &quot;Angus&quot;</pre>
<p>&nbsp;<br />
Nevertheless, I do think that a good understanding of primitives and what happens under the covers when you interact with them is an important step towards a deeper knowledge of the language. I hope this helped. </p>

<div class="wpa" style="position: relative; width:300px; text-align: center; padding: 0; margin: 10px auto; overflow: hidden; clear: both;">
<a style="position: absolute; text-align: left; display: block; font: 9px/1 sans-serif; text-decoration: underline;" href="http://en.wordpress.com/about-these-ads/" rel="nofollow">About these ads</a>
<script type="text/javascript">
		var wpcom_adclk_hovering = false;
		var wpcom_adclk_recorded = false;
		var wpcom_adclk_theme = "Ari";
		var wpcom_adclk_slot = "wpcom_below_post_adsafe";
		var wpcom_adclk_network = ( typeof wpcom_adclk_network === "undefined" ) ? "" : wpcom_adclk_network ;

		jQuery(document).ready( function() {
			function wpcom_adclk_hover_yes() { wpcom_adclk_hovering = true; }
			function wpcom_adclk_hover_no() { wpcom_adclk_hovering = false; }
			jQuery(".wpa").click(wpcom_adclk_click);
			jQuery(".wpa iframe").hover( wpcom_adclk_hover_yes, wpcom_adclk_hover_no );
			jQuery(".wpa object").hover( wpcom_adclk_hover_yes, wpcom_adclk_hover_no );

			jQuery(window).blur( function() {
				if ( wpcom_adclk_hovering ) { wpcom_adclk_click(); }
			});
		});

		function wpcom_adclk_impression() {
			var stat_gif = document.location.protocol + "//stats.wordpress.com/g.gif?v=wpcom-no-pv";
			stat_gif += "&x_ads_imp_theme=" + wpcom_adclk_theme;
			stat_gif += "&x_ads_imp_placement="+wpcom_adclk_slot;
			stat_gif += "&x_ads_imp_network=" + wpcom_adclk_network;
			stat_gif += "&x_ads_imp_theme_network="+wpcom_adclk_theme+"_"+wpcom_adclk_network;
			new Image().src = stat_gif + "&baba=" + Math.random();
			return true;
		}

		function wpcom_adclk_click() {
			if (wpcom_adclk_recorded) { return true; } // no double counting
			var stat_gif = document.location.protocol + "//stats.wordpress.com/g.gif?v=wpcom-no-pv";
			stat_gif += "&x_ads_click_theme=" + wpcom_adclk_theme;
			stat_gif += "&x_ads_click_placement="+wpcom_adclk_slot;
			stat_gif += "&x_ads_click_network=" + wpcom_adclk_network;
			stat_gif += "&x_ads_click_theme_network="+wpcom_adclk_theme+"_"+wpcom_adclk_network;

			new Image().src = stat_gif + "&baba=" + Math.random();
			wpcom_adclk_recorded = true;
			var now=new Date(); var end=now.getTime()+250;
			while(true){now=new Date();if(now.getTime()>end){break;}}
			return true;
		}
	
if ( typeof GA_googleAddAttr == 'function' ) {
GA_googleAddAttr("AdOpt", "1");
GA_googleAddAttr("Origin", "other");
GA_googleAddAttr("LangId", "1");
GA_googleAddAttr("Domain", "javascriptweblog.wordpress.com");
GA_googleAddAttr("BlogId", "12490669");
GA_googleAddAttr("PageURL", "http://javascriptweblog.wordpress.com/2010/09/27/the-secret-life-of-javascript-primitives/");
GA_googleAddAttr("AdSafe", "1");
GA_googleAddAttr("Autotag", "science");
GA_googleAddAttr("Autotag", "technology");
GA_googleAddAttr("Tag", "javascript");
GA_googleAddAttr("Tag", "boolean");
GA_googleAddAttr("Tag", "coercion");
GA_googleAddAttr("Tag", "number");
GA_googleAddAttr("Tag", "objects");
GA_googleAddAttr("Tag", "primitives");
GA_googleAddAttr("Tag", "string");
GA_googleAddAttr("Partner", "AOL");
GA_googleAddAttr("theme_bg", "ffffff");
GA_googleAddAttr("theme_border", "4c4c4c");
GA_googleAddAttr("theme_text", "4c4c4c");
GA_googleAddAttr("theme_link", "2c52f5");
GA_googleAddAttr("theme_url", "2c52f5");
GA_googleAddAdSensePageAttr("google_page_url", "http://javascriptweblog.wordpress.com/2010/09/27/the-secret-life-of-javascript-primitives/");
GA_googleFillSlot("wpcom_below_post_adsafe");
}
</script>
</div>
<style type="text/css">
div.wpa>div { margin-top: 1em; } #google_ads_div_wpcom_below_post_adsafe_ad_container { display: block !important; }
</style>
<script type="text/javascript">
jQuery( window ).load( function() {
    if ( jQuery(".wpa script[src*='virool.com']").length > 0 || jQuery(".wpa script[src*='shareth.ru']").length > 0 || jQuery(".wpa iframe[src*='boomvideo.tv']").length > 0 || jQuery(".wpa iframe[src*='viewablemedia.net']").length > 0 || jQuery(".wpa .sharethrough-placement").length > 0 ) {
        jQuery( '.wpa' ).css( 'width', '400px' );
    }
setTimeout(function(){if(typeof GS_googleAddAdSenseService !== 'function'){new Image().src=document.location.protocol+"//stats.wordpress.com/g.gif?v=wpcom-no-pv&x_noads=adblock&baba="+Math.random()}},100);
} );
</script>
<div id="jp-post-flair" class="sharedaddy sd-like-enabled"><div class='sharedaddy sd-block sd-like jetpack-likes-widget-wrapper jetpack-likes-widget-unloaded' id='like-post-wrapper-12490669-1418-53881026eb251' data-src='//widgets.wp.com/likes/#blog_id=12490669&amp;post_id=1418&amp;origin=javascriptweblog.wordpress.com&amp;obj_id=12490669-1418-53881026eb251' data-name='like-post-frame-12490669-1418-53881026eb251'><h3 class='sd-title'>Like this:</h3><div class='likes-widget-placeholder post-likes-widget-placeholder' style='height:55px'><span class='button'><span>Like</span></span> <span class="loading">Loading...</span></div><span class='sd-text-color'></span><a class='sd-link-color'></a></div>
<div id='jp-relatedposts' class='jp-relatedposts' >
	<h3 class="jp-relatedposts-headline"><em>Related</em></h3>
</div></div>			</div><!-- .entry-content -->
	
	<footer class="entry-meta">
					<span class="posted-on">
				<span class="post-date"><a href="http://javascriptweblog.wordpress.com/2010/09/27/the-secret-life-of-javascript-primitives/" title="00:01" rel="bookmark"><time class="entry-date" datetime="2010-09-27T00:01:52+00:00" pubdate>September 27, 2010</time></a></span><span class="byline"> by <span class="author vcard"><a class="url fn n" href="http://javascriptweblog.wordpress.com/author/angusjs/" title="View all posts by Angus Croll" rel="author">Angus Croll</a></span></span>			</span>
			
						<span class="sep"> | </span>
			<span class="tag-links">
				Tags: <a href="http://javascriptweblog.wordpress.com/tag/boolean/" rel="tag">boolean</a>, <a href="http://javascriptweblog.wordpress.com/tag/coercion/" rel="tag">coercion</a>, <a href="http://javascriptweblog.wordpress.com/tag/number/" rel="tag">number</a>, <a href="http://javascriptweblog.wordpress.com/tag/objects/" rel="tag">Objects</a>, <a href="http://javascriptweblog.wordpress.com/tag/primitives/" rel="tag">primitives</a>, <a href="http://javascriptweblog.wordpress.com/tag/string/" rel="tag">string</a>			</span>
					
				<span class="sep"> | </span>
		<span class="comments-link"><a href="http://javascriptweblog.wordpress.com/2010/09/27/the-secret-life-of-javascript-primitives/#comments" title="Comment on The Secret Life of JavaScript Primitives">23 Comments</a></span>
		
		
			</footer><!-- #entry-meta -->
</article><!-- #post-1418 -->

					<nav role="navigation" id="nav-below" class="site-navigation post-navigation">
		<h1 class="assistive-text">Post navigation</h1>

	
		<div class="nav-previous"><a href="http://javascriptweblog.wordpress.com/2010/09/20/auto-generating-javascript-unit-tests/" rel="prev"><span class="meta-nav">&larr;</span> Auto-generating JavaScript Unit&nbsp;Tests</a></div>		<div class="nav-next"><a href="http://javascriptweblog.wordpress.com/2010/10/11/rethinking-javascript-for-loops/" rel="next">Rethinking JavaScript for-loops <span class="meta-nav">&rarr;</span></a></div>
	
	</nav><!-- #nav-below -->
	
					<div id="comments" class="comments-area">
	
	
			<h2 class="comments-title">
			23 thoughts on &ldquo;<span>The Secret Life of JavaScript Primitives</span>&rdquo;		</h2>

		<ol class="commentlist">
				<li class="comment even thread-even depth-1 highlander-comment" id="li-comment-702">
		<article id="comment-702" class="comment">
			<footer>
				<div class="comment-author vcard">
					<img alt='' src='http://2.gravatar.com/avatar/efb2415f773b0a945ff2b15f48401c0b?s=50&#038;d=monsterid&#038;r=G' class='avatar avatar-50' height='50' width='50' />				</div><!-- .comment-author .vcard -->
			</footer>

			<div class="comment-content">
								<div class="comment-meta commentmetadata">
					<cite class="fn">joseanpg</cite> <span class="says">says:</span>					<a href="http://javascriptweblog.wordpress.com/2010/09/27/the-secret-life-of-javascript-primitives/#comment-702"><time pubdate datetime="2010-09-27T10:27:54+00:00">
					September 27, 2010 at 10:27					</time></a>
									</div><!-- .comment-meta .commentmetadata -->
				<p>Very good article! Your blog is a nice source of JavaScript wisdom and funny style (<i>&#8220;&#8230; the Gods of garbage collection – but in the spirit of the TV discovery shows, we will trap the elusive creature and preserve it for further analysis&#8221;</i> :^D)</p>
<p>I would like to make a small contribution: <code>stringObjectInstance.length</code><code>  have  DontEnum,<br />
DontDelete, ReadOnly  attributes in ES3  ( [[Writable]]: false, [[Enumerable]]: false, [[Configurable]]: false in ES5), therefore in the snippet<br />
</code><code><br />
var me = new String("Angus");<br />
me.length = 2;<br />
me.length; //2<br />
me.valueOf(); "Angus"<br />
</code><br />
the second statement will do nothing in ES3 or non-strict ES5,  and throws a TypeError in strict ES5.  In the third stament that 2 must be a 5.  The source of the confusion may lie in the fact that an assignment returns the rvalue, and this value is usually displayed by the console.</p>
				<div class="reply">
					<a class='comment-reply-link' href='/2010/09/27/the-secret-life-of-javascript-primitives/?replytocom=702#respond' onclick='return addComment.moveForm("comment-702", "702", "respond", "1418")'>Reply</a>				</div><!-- .reply -->
			</div>
		</article><!-- #comment-## -->

	<ul class="children">
	<li class="comment byuser comment-author-angusjs bypostauthor odd alt depth-2 highlander-comment" id="li-comment-703">
		<article id="comment-703" class="comment">
			<footer>
				<div class="comment-author vcard">
					<img alt='' src='http://2.gravatar.com/avatar/52c6174ba60557536f93809b4e95d97c?s=50&#038;d=monsterid&#038;r=G' class='avatar avatar-50' height='50' width='50' />				</div><!-- .comment-author .vcard -->
			</footer>

			<div class="comment-content">
								<div class="comment-meta commentmetadata">
					<cite class="fn"><a href='http://javascriptweblog.wordpress.com' rel='external nofollow' class='url'>Angus Croll</a></cite> <span class="says">says:</span>					<a href="http://javascriptweblog.wordpress.com/2010/09/27/the-secret-life-of-javascript-primitives/#comment-703"><time pubdate datetime="2010-09-27T10:32:35+00:00">
					September 27, 2010 at 10:32					</time></a>
									</div><!-- .comment-meta .commentmetadata -->
				<p>Thanks Jose this is a good insight &#8211; I will update. (glad you like the article!)</p>
				<div class="reply">
					<a class='comment-reply-link' href='/2010/09/27/the-secret-life-of-javascript-primitives/?replytocom=703#respond' onclick='return addComment.moveForm("comment-703", "703", "respond", "1418")'>Reply</a>				</div><!-- .reply -->
			</div>
		</article><!-- #comment-## -->

	</li><!-- #comment-## -->
</ul><!-- .children -->
</li><!-- #comment-## -->
	<li class="comment even thread-odd thread-alt depth-1 highlander-comment" id="li-comment-705">
		<article id="comment-705" class="comment">
			<footer>
				<div class="comment-author vcard">
					<img alt='' src='http://2.gravatar.com/avatar/882f228c4993ccf0a86e96394636415c?s=50&#038;d=monsterid&#038;r=G' class='avatar avatar-50' height='50' width='50' />				</div><!-- .comment-author .vcard -->
			</footer>

			<div class="comment-content">
								<div class="comment-meta commentmetadata">
					<cite class="fn"><a href='http://dmitrysoshnikov.com' rel='external nofollow' class='url'>Dmitry A. Soshnikov</a></cite> <span class="says">says:</span>					<a href="http://javascriptweblog.wordpress.com/2010/09/27/the-secret-life-of-javascript-primitives/#comment-705"><time pubdate datetime="2010-09-27T10:51:41+00:00">
					September 27, 2010 at 10:51					</time></a>
									</div><!-- .comment-meta .commentmetadata -->
				<p>Notice, that in strict mode of ES5, a <em>this value</em> isn&#8217;t coerced to an object. I.e. in your <code>var b = a.returnMe(); </code>, &#8220;b&#8221; is still a string in this case, but not the object.</p>
<p>Good write up.</p>
<p>Dmitry.</p>
				<div class="reply">
					<a class='comment-reply-link' href='/2010/09/27/the-secret-life-of-javascript-primitives/?replytocom=705#respond' onclick='return addComment.moveForm("comment-705", "705", "respond", "1418")'>Reply</a>				</div><!-- .reply -->
			</div>
		</article><!-- #comment-## -->

	<ul class="children">
	<li class="comment byuser comment-author-angusjs bypostauthor odd alt depth-2 highlander-comment" id="li-comment-711">
		<article id="comment-711" class="comment">
			<footer>
				<div class="comment-author vcard">
					<img alt='' src='http://2.gravatar.com/avatar/52c6174ba60557536f93809b4e95d97c?s=50&#038;d=monsterid&#038;r=G' class='avatar avatar-50' height='50' width='50' />				</div><!-- .comment-author .vcard -->
			</footer>

			<div class="comment-content">
								<div class="comment-meta commentmetadata">
					<cite class="fn"><a href='http://javascriptweblog.wordpress.com' rel='external nofollow' class='url'>Angus Croll</a></cite> <span class="says">says:</span>					<a href="http://javascriptweblog.wordpress.com/2010/09/27/the-secret-life-of-javascript-primitives/#comment-711"><time pubdate datetime="2010-09-27T11:17:40+00:00">
					September 27, 2010 at 11:17					</time></a>
									</div><!-- .comment-meta .commentmetadata -->
				<p>Thanks Dmitry &#8211; here is why I thought even in strict mode <em>this</em> will be an object </p>
<p>See ECMA 8.7.1<br />
<em>The following [[Get]] internal method is used by GetValue when V is a property reference with a primitive base value<br />
1.  Let O be ToObject(base).<br />
2   Let desc be the result of calling the [[GetProperty]] internal method of O with property name P<br />
etc. </em><br />
There is no mention of strict mode exception</p>
<p>All this happens before 10.4.3 (where <em>this</em> is only converted to object in non strict mode). So I thought strict mode does not matter in this case since <em>this</em> is already an object</p>
<p>Is this right?</p>
				<div class="reply">
					<a class='comment-reply-link' href='/2010/09/27/the-secret-life-of-javascript-primitives/?replytocom=711#respond' onclick='return addComment.moveForm("comment-711", "711", "respond", "1418")'>Reply</a>				</div><!-- .reply -->
			</div>
		</article><!-- #comment-## -->

	</li><!-- #comment-## -->
</ul><!-- .children -->
</li><!-- #comment-## -->
	<li class="comment even thread-even depth-1 highlander-comment" id="li-comment-708">
		<article id="comment-708" class="comment">
			<footer>
				<div class="comment-author vcard">
					<img alt='' src='http://2.gravatar.com/avatar/efb2415f773b0a945ff2b15f48401c0b?s=50&#038;d=monsterid&#038;r=G' class='avatar avatar-50' height='50' width='50' />				</div><!-- .comment-author .vcard -->
			</footer>

			<div class="comment-content">
								<div class="comment-meta commentmetadata">
					<cite class="fn">joseanpg</cite> <span class="says">says:</span>					<a href="http://javascriptweblog.wordpress.com/2010/09/27/the-secret-life-of-javascript-primitives/#comment-708"><time pubdate datetime="2010-09-27T11:10:08+00:00">
					September 27, 2010 at 11:10					</time></a>
									</div><!-- .comment-meta .commentmetadata -->
				<p>Dmitry, Angus is right. In 11.2.3 you can see:<br />
<em>The production CallExpression : MemberExpression Arguments is evaluated as follows:<br />
-Let ref be the result of evaluating MemberExpression.<br />
 -Let func be GetValue(ref).<br />
</em><br />
And in 8.7.1:<br />
<em><br />
4. If IsPropertyReference(V), then<br />
          a. If HasPrimitiveBase(V) is false, then let get be the [[Get]] internal<br />
               method of base, otherwise let get be the special <b> [[Get]] internal<br />
              method defined below</b>.<br />
</em><br />
Below:<br />
<em>1. Let O be <b>ToObject(base)</b>.</em></p>
<p>Therefore, the this value received by [[Call]] is an String Object</p>
				<div class="reply">
					<a class='comment-reply-link' href='/2010/09/27/the-secret-life-of-javascript-primitives/?replytocom=708#respond' onclick='return addComment.moveForm("comment-708", "708", "respond", "1418")'>Reply</a>				</div><!-- .reply -->
			</div>
		</article><!-- #comment-## -->

	<ul class="children">
	<li class="comment odd alt depth-2 highlander-comment" id="li-comment-714">
		<article id="comment-714" class="comment">
			<footer>
				<div class="comment-author vcard">
					<img alt='' src='http://2.gravatar.com/avatar/882f228c4993ccf0a86e96394636415c?s=50&#038;d=monsterid&#038;r=G' class='avatar avatar-50' height='50' width='50' />				</div><!-- .comment-author .vcard -->
			</footer>

			<div class="comment-content">
								<div class="comment-meta commentmetadata">
					<cite class="fn"><a href='http://dmitrysoshnikov.com' rel='external nofollow' class='url'>Dmitry A. Soshnikov</a></cite> <span class="says">says:</span>					<a href="http://javascriptweblog.wordpress.com/2010/09/27/the-secret-life-of-javascript-primitives/#comment-714"><time pubdate datetime="2010-09-27T12:10:16+00:00">
					September 27, 2010 at 12:10					</time></a>
									</div><!-- .comment-meta .commentmetadata -->
				<p>Yes, but <em>O</em> is used only to get the method. Then (at step 7):</p>
<blockquote><p>providing <b>base</b> as the this value</p></blockquote>
<p>And <em>base</em> is a primitive value.</p>
<p>Dmitry.</p>
				<div class="reply">
					<a class='comment-reply-link' href='/2010/09/27/the-secret-life-of-javascript-primitives/?replytocom=714#respond' onclick='return addComment.moveForm("comment-714", "714", "respond", "1418")'>Reply</a>				</div><!-- .reply -->
			</div>
		</article><!-- #comment-## -->

	</li><!-- #comment-## -->
</ul><!-- .children -->
</li><!-- #comment-## -->
	<li class="comment even thread-odd thread-alt depth-1 highlander-comment" id="li-comment-710">
		<article id="comment-710" class="comment">
			<footer>
				<div class="comment-author vcard">
					<img alt='' src='http://0.gravatar.com/avatar/6766096e8ae81ad6b3b82b9c12be19e0?s=50&#038;d=monsterid&#038;r=G' class='avatar avatar-50' height='50' width='50' />				</div><!-- .comment-author .vcard -->
			</footer>

			<div class="comment-content">
								<div class="comment-meta commentmetadata">
					<cite class="fn"><a href='http://fitzgeraldnick.com/' rel='external nofollow' class='url'>Nick Fitzgerald</a></cite> <span class="says">says:</span>					<a href="http://javascriptweblog.wordpress.com/2010/09/27/the-secret-life-of-javascript-primitives/#comment-710"><time pubdate datetime="2010-09-27T11:17:03+00:00">
					September 27, 2010 at 11:17					</time></a>
									</div><!-- .comment-meta .commentmetadata -->
				<p>Very nice article, Angus! The returnMe and typeof interactions were all new to me, so I am very glad I read this!</p>
<p>Hasta,</p>
<p>Nick</p>
				<div class="reply">
					<a class='comment-reply-link' href='/2010/09/27/the-secret-life-of-javascript-primitives/?replytocom=710#respond' onclick='return addComment.moveForm("comment-710", "710", "respond", "1418")'>Reply</a>				</div><!-- .reply -->
			</div>
		</article><!-- #comment-## -->

	<ul class="children">
	<li class="comment byuser comment-author-angusjs bypostauthor odd alt depth-2 highlander-comment" id="li-comment-712">
		<article id="comment-712" class="comment">
			<footer>
				<div class="comment-author vcard">
					<img alt='' src='http://2.gravatar.com/avatar/52c6174ba60557536f93809b4e95d97c?s=50&#038;d=monsterid&#038;r=G' class='avatar avatar-50' height='50' width='50' />				</div><!-- .comment-author .vcard -->
			</footer>

			<div class="comment-content">
								<div class="comment-meta commentmetadata">
					<cite class="fn"><a href='http://javascriptweblog.wordpress.com' rel='external nofollow' class='url'>Angus Croll</a></cite> <span class="says">says:</span>					<a href="http://javascriptweblog.wordpress.com/2010/09/27/the-secret-life-of-javascript-primitives/#comment-712"><time pubdate datetime="2010-09-27T11:25:22+00:00">
					September 27, 2010 at 11:25					</time></a>
									</div><!-- .comment-meta .commentmetadata -->
				<p>@Nick &#8211; glad you liked it!</p>
				<div class="reply">
					<a class='comment-reply-link' href='/2010/09/27/the-secret-life-of-javascript-primitives/?replytocom=712#respond' onclick='return addComment.moveForm("comment-712", "712", "respond", "1418")'>Reply</a>				</div><!-- .reply -->
			</div>
		</article><!-- #comment-## -->

	</li><!-- #comment-## -->
</ul><!-- .children -->
</li><!-- #comment-## -->
	<li class="comment even thread-even depth-1 highlander-comment" id="li-comment-713">
		<article id="comment-713" class="comment">
			<footer>
				<div class="comment-author vcard">
					<img alt='' src='http://2.gravatar.com/avatar/882f228c4993ccf0a86e96394636415c?s=50&#038;d=monsterid&#038;r=G' class='avatar avatar-50' height='50' width='50' />				</div><!-- .comment-author .vcard -->
			</footer>

			<div class="comment-content">
								<div class="comment-meta commentmetadata">
					<cite class="fn"><a href='http://dmitrysoshnikov.com' rel='external nofollow' class='url'>Dmitry A. Soshnikov</a></cite> <span class="says">says:</span>					<a href="http://javascriptweblog.wordpress.com/2010/09/27/the-secret-life-of-javascript-primitives/#comment-713"><time pubdate datetime="2010-09-27T11:55:00+00:00">
					September 27, 2010 at 11:55					</time></a>
									</div><!-- .comment-meta .commentmetadata -->
				<p>@<b>Angus</b>, @<b>joseanpg</b>:</p>
<p>Annex C: <a href="http://ecma262-5.com/ELS5_HTML.htm#Annex_C" rel="nofollow">http://ecma262-5.com/ELS5_HTML.htm#Annex_C</a></p>
<blockquote><p>If this is evaluated within <em>strict mode code</em>, then the <em>this value is not coerced to an object</em>.</p></blockquote>
<p>Additionally: <a href="http://dmitrysoshnikov.com/ecmascript/es5-chapter-2-strict-mode/#this-value-restrictions" rel="nofollow">http://dmitrysoshnikov.com/ecmascript/es5-chapter-2-strict-mode/#this-value-restrictions</a></p>
<p>Dmitry.</p>
				<div class="reply">
					<a class='comment-reply-link' href='/2010/09/27/the-secret-life-of-javascript-primitives/?replytocom=713#respond' onclick='return addComment.moveForm("comment-713", "713", "respond", "1418")'>Reply</a>				</div><!-- .reply -->
			</div>
		</article><!-- #comment-## -->

	</li><!-- #comment-## -->
	<li class="comment odd alt thread-odd thread-alt depth-1 highlander-comment" id="li-comment-716">
		<article id="comment-716" class="comment">
			<footer>
				<div class="comment-author vcard">
					<img alt='' src='http://2.gravatar.com/avatar/efb2415f773b0a945ff2b15f48401c0b?s=50&#038;d=monsterid&#038;r=G' class='avatar avatar-50' height='50' width='50' />				</div><!-- .comment-author .vcard -->
			</footer>

			<div class="comment-content">
								<div class="comment-meta commentmetadata">
					<cite class="fn">joseanpg</cite> <span class="says">says:</span>					<a href="http://javascriptweblog.wordpress.com/2010/09/27/the-secret-life-of-javascript-primitives/#comment-716"><time pubdate datetime="2010-09-27T12:58:38+00:00">
					September 27, 2010 at 12:58					</time></a>
									</div><!-- .comment-meta .commentmetadata -->
				<p>Dmitry is right:</p>
<p><b>11.2.3 Function Calls</b><br />
1. Let ref be the result of evaluating MemberExpression.<br />
2. Let func be GetValue(ref). <b>[ToObject]</b><br />
6. If Type(ref) is Reference, if IsPropertyReference(ref) is true, then<br />
      let thisValue be GetBase(ref). [primitive]</p>
				<div class="reply">
					<a class='comment-reply-link' href='/2010/09/27/the-secret-life-of-javascript-primitives/?replytocom=716#respond' onclick='return addComment.moveForm("comment-716", "716", "respond", "1418")'>Reply</a>				</div><!-- .reply -->
			</div>
		</article><!-- #comment-## -->

	<ul class="children">
	<li class="comment byuser comment-author-angusjs bypostauthor even depth-2 highlander-comment" id="li-comment-718">
		<article id="comment-718" class="comment">
			<footer>
				<div class="comment-author vcard">
					<img alt='' src='http://2.gravatar.com/avatar/52c6174ba60557536f93809b4e95d97c?s=50&#038;d=monsterid&#038;r=G' class='avatar avatar-50' height='50' width='50' />				</div><!-- .comment-author .vcard -->
			</footer>

			<div class="comment-content">
								<div class="comment-meta commentmetadata">
					<cite class="fn"><a href='http://javascriptweblog.wordpress.com' rel='external nofollow' class='url'>Angus Croll</a></cite> <span class="says">says:</span>					<a href="http://javascriptweblog.wordpress.com/2010/09/27/the-secret-life-of-javascript-primitives/#comment-718"><time pubdate datetime="2010-09-27T13:19:26+00:00">
					September 27, 2010 at 13:19					</time></a>
									</div><!-- .comment-meta .commentmetadata -->
				<p>Yep Dmitry wins &#8211; good discussion guys! ( I added a note about strict mode to the article)</p>
				<div class="reply">
					<a class='comment-reply-link' href='/2010/09/27/the-secret-life-of-javascript-primitives/?replytocom=718#respond' onclick='return addComment.moveForm("comment-718", "718", "respond", "1418")'>Reply</a>				</div><!-- .reply -->
			</div>
		</article><!-- #comment-## -->

	</li><!-- #comment-## -->
</ul><!-- .children -->
</li><!-- #comment-## -->
	<li class="post pingback">
		<p>Pingback: <a href='http://javascript.darmowe-blogi.pisz.pl/bez-kategorii/the-secret-life-of-javascript-primitives-javascript-javascript.html' rel='external nofollow' class='url'>The Secret Life of JavaScript Primitives | JavaScript, JavaScript &#8211; javascript - dowiedz się więcej!</a></p>
	</li><!-- #comment-## -->
	<li class="comment odd alt thread-even depth-1 highlander-comment" id="li-comment-739">
		<article id="comment-739" class="comment">
			<footer>
				<div class="comment-author vcard">
					<img alt='' src='http://1.gravatar.com/avatar/7fff733ad25bb65da8f0db1c1a2d556e?s=50&#038;d=monsterid&#038;r=G' class='avatar avatar-50' height='50' width='50' />				</div><!-- .comment-author .vcard -->
			</footer>

			<div class="comment-content">
								<div class="comment-meta commentmetadata">
					<cite class="fn"><a href='http://regolit.com' rel='external nofollow' class='url'>Sergei Stolyarov</a></cite> <span class="says">says:</span>					<a href="http://javascriptweblog.wordpress.com/2010/09/27/the-secret-life-of-javascript-primitives/#comment-739"><time pubdate datetime="2010-10-01T00:28:34+00:00">
					October 1, 2010 at 00:28					</time></a>
									</div><!-- .comment-meta .commentmetadata -->
				<p>And another example, values vs. objects.</p>
<p>var s1 = new String(&#8220;ops&#8221;);<br />
var s2 = new String(&#8220;ops&#8221;);<br />
alert(s1 == s2);</p>
				<div class="reply">
					<a class='comment-reply-link' href='/2010/09/27/the-secret-life-of-javascript-primitives/?replytocom=739#respond' onclick='return addComment.moveForm("comment-739", "739", "respond", "1418")'>Reply</a>				</div><!-- .reply -->
			</div>
		</article><!-- #comment-## -->

	</li><!-- #comment-## -->
	<li class="comment even thread-odd thread-alt depth-1 highlander-comment" id="li-comment-742">
		<article id="comment-742" class="comment">
			<footer>
				<div class="comment-author vcard">
					<img alt='' src='http://0.gravatar.com/avatar/f8078acb93183ca46bf31c66addd1575?s=50&#038;d=monsterid&#038;r=G' class='avatar avatar-50' height='50' width='50' />				</div><!-- .comment-author .vcard -->
			</footer>

			<div class="comment-content">
								<div class="comment-meta commentmetadata">
					<cite class="fn">Bob</cite> <span class="says">says:</span>					<a href="http://javascriptweblog.wordpress.com/2010/09/27/the-secret-life-of-javascript-primitives/#comment-742"><time pubdate datetime="2010-10-01T04:55:22+00:00">
					October 1, 2010 at 04:55					</time></a>
									</div><!-- .comment-meta .commentmetadata -->
				<p>Good job.  Very readable.</p>
<p>You have a typo in the first listing though, you have:</p>
<p>typeof Number(&#8220;abc&#8221;); //&#8221;number&#8221;</p>
<p>and you meant to have:</p>
<p>typeof Number(123); //&#8221;number&#8221;</p>
				<div class="reply">
					<a class='comment-reply-link' href='/2010/09/27/the-secret-life-of-javascript-primitives/?replytocom=742#respond' onclick='return addComment.moveForm("comment-742", "742", "respond", "1418")'>Reply</a>				</div><!-- .reply -->
			</div>
		</article><!-- #comment-## -->

	<ul class="children">
	<li class="comment byuser comment-author-angusjs bypostauthor odd alt depth-2 highlander-comment" id="li-comment-746">
		<article id="comment-746" class="comment">
			<footer>
				<div class="comment-author vcard">
					<img alt='' src='http://2.gravatar.com/avatar/52c6174ba60557536f93809b4e95d97c?s=50&#038;d=monsterid&#038;r=G' class='avatar avatar-50' height='50' width='50' />				</div><!-- .comment-author .vcard -->
			</footer>

			<div class="comment-content">
								<div class="comment-meta commentmetadata">
					<cite class="fn"><a href='http://javascriptweblog.wordpress.com' rel='external nofollow' class='url'>Angus Croll</a></cite> <span class="says">says:</span>					<a href="http://javascriptweblog.wordpress.com/2010/09/27/the-secret-life-of-javascript-primitives/#comment-746"><time pubdate datetime="2010-10-01T08:35:47+00:00">
					October 1, 2010 at 08:35					</time></a>
									</div><!-- .comment-meta .commentmetadata -->
				<p>Whoops &#8211; thanks for the praise and for pointing out the typo</p>
				<div class="reply">
					<a class='comment-reply-link' href='/2010/09/27/the-secret-life-of-javascript-primitives/?replytocom=746#respond' onclick='return addComment.moveForm("comment-746", "746", "respond", "1418")'>Reply</a>				</div><!-- .reply -->
			</div>
		</article><!-- #comment-## -->

	</li><!-- #comment-## -->
</ul><!-- .children -->
</li><!-- #comment-## -->
	<li class="comment even thread-even depth-1 highlander-comment" id="li-comment-786">
		<article id="comment-786" class="comment">
			<footer>
				<div class="comment-author vcard">
					<img alt='' src='http://2.gravatar.com/avatar/2f2bb08ab51265d64000be003994b1ad?s=50&#038;d=monsterid&#038;r=G' class='avatar avatar-50' height='50' width='50' />				</div><!-- .comment-author .vcard -->
			</footer>

			<div class="comment-content">
								<div class="comment-meta commentmetadata">
					<cite class="fn"><a href='http://sum-on.com' rel='external nofollow' class='url'>Sumon</a></cite> <span class="says">says:</span>					<a href="http://javascriptweblog.wordpress.com/2010/09/27/the-secret-life-of-javascript-primitives/#comment-786"><time pubdate datetime="2010-10-07T21:02:05+00:00">
					October 7, 2010 at 21:02					</time></a>
									</div><!-- .comment-meta .commentmetadata -->
				<p>Great article. Thanks for sharing this post !</p>
				<div class="reply">
					<a class='comment-reply-link' href='/2010/09/27/the-secret-life-of-javascript-primitives/?replytocom=786#respond' onclick='return addComment.moveForm("comment-786", "786", "respond", "1418")'>Reply</a>				</div><!-- .reply -->
			</div>
		</article><!-- #comment-## -->

	</li><!-- #comment-## -->
	<li class="comment odd alt thread-odd thread-alt depth-1 highlander-comment" id="li-comment-4534">
		<article id="comment-4534" class="comment">
			<footer>
				<div class="comment-author vcard">
					<img alt='' src='http://2.gravatar.com/avatar/529a291a6eb6205d850ac47d2c38b24c?s=50&#038;d=monsterid&#038;r=G' class='avatar avatar-50' height='50' width='50' />				</div><!-- .comment-author .vcard -->
			</footer>

			<div class="comment-content">
								<div class="comment-meta commentmetadata">
					<cite class="fn">Francisc</cite> <span class="says">says:</span>					<a href="http://javascriptweblog.wordpress.com/2010/09/27/the-secret-life-of-javascript-primitives/#comment-4534"><time pubdate datetime="2011-09-06T05:11:46+00:00">
					September 6, 2011 at 05:11					</time></a>
									</div><!-- .comment-meta .commentmetadata -->
				<p>Very nice. Thank you.</p>
				<div class="reply">
					<a class='comment-reply-link' href='/2010/09/27/the-secret-life-of-javascript-primitives/?replytocom=4534#respond' onclick='return addComment.moveForm("comment-4534", "4534", "respond", "1418")'>Reply</a>				</div><!-- .reply -->
			</div>
		</article><!-- #comment-## -->

	</li><!-- #comment-## -->
	<li class="post pingback">
		<p>Pingback: <a href='http://labnotes.org/2011/09/12/rounded-corners-286-%e2%80%94/' rel='external nofollow' class='url'>Rounded Corners 286 — The secret life of JavaScript primitives /by @assaf</a></p>
	</li><!-- #comment-## -->
	<li class="post pingback">
		<p>Pingback: <a href='http://skilldrick.co.uk/2011/09/understanding-typeof-instanceof-and-constructor-in-javascript/' rel='external nofollow' class='url'>Skilldrick &raquo; Understanding typeof, instanceof and constructor in JavaScript</a></p>
	</li><!-- #comment-## -->
	<li class="comment even thread-even depth-1 highlander-comment" id="li-comment-4738">
		<article id="comment-4738" class="comment">
			<footer>
				<div class="comment-author vcard">
					<img alt='' src='http://0.gravatar.com/avatar/?s=50&#038;d=monsterid&#038;r=G' class='avatar avatar-50' height='50' width='50' />				</div><!-- .comment-author .vcard -->
			</footer>

			<div class="comment-content">
								<div class="comment-meta commentmetadata">
					<cite class="fn">Anonymous</cite> <span class="says">says:</span>					<a href="http://javascriptweblog.wordpress.com/2010/09/27/the-secret-life-of-javascript-primitives/#comment-4738"><time pubdate datetime="2011-09-20T14:50:35+00:00">
					September 20, 2011 at 14:50					</time></a>
									</div><!-- .comment-meta .commentmetadata -->
				<p>I want an objectpotamus.  Badly.</p>
				<div class="reply">
					<a class='comment-reply-link' href='/2010/09/27/the-secret-life-of-javascript-primitives/?replytocom=4738#respond' onclick='return addComment.moveForm("comment-4738", "4738", "respond", "1418")'>Reply</a>				</div><!-- .reply -->
			</div>
		</article><!-- #comment-## -->

	</li><!-- #comment-## -->
	<li class="post pingback">
		<p>Pingback: <a href='http://www.scoop.it/t/web-tools-and-technologies/p/501174316/the-secret-life-of-javascript-primitives' rel='external nofollow' class='url'>The Secret Life of&nbsp;JavaScript&nbsp;Primitives | Web tools and technologies | Scoop.it</a></p>
	</li><!-- #comment-## -->
	<li class="post pingback">
		<p>Pingback: <a href='http://diffdown.com/uncategorized/difference-between-java-and-javascript/' rel='external nofollow' class='url'>Difference Between Java and JavaScript | DiffDown</a></p>
	</li><!-- #comment-## -->
	<li class="comment byuser comment-author-dpeeva odd alt thread-odd thread-alt depth-1 highlander-comment" id="li-comment-60234">
		<article id="comment-60234" class="comment">
			<footer>
				<div class="comment-author vcard">
					<img alt='' src='http://0.gravatar.com/avatar/c2d6b4966bd4584903d39e55cd4c442d?s=50&#038;d=monsterid&#038;r=G' class='avatar avatar-50' height='50' width='50' />				</div><!-- .comment-author .vcard -->
			</footer>

			<div class="comment-content">
								<div class="comment-meta commentmetadata">
					<cite class="fn"><a href='http://dpeeva.wordpress.com/' rel='external nofollow' class='url'>dpeeva</a></cite> <span class="says">says:</span>					<a href="http://javascriptweblog.wordpress.com/2010/09/27/the-secret-life-of-javascript-primitives/#comment-60234"><time pubdate datetime="2014-05-10T15:05:31+00:00">
					May 10, 2014 at 15:05					</time></a>
									</div><!-- .comment-meta .commentmetadata -->
				<p>Reblogged this on <a href="http://dpeeva.wordpress.com/2014/05/11/the-secret-life-of-javascript-primitives/" rel="nofollow">dpeeva</a>.</p>
				<div class="reply">
					<a class='comment-reply-link' href='/2010/09/27/the-secret-life-of-javascript-primitives/?replytocom=60234#respond' onclick='return addComment.moveForm("comment-60234", "60234", "respond", "1418")'>Reply</a>				</div><!-- .reply -->
			</div>
		</article><!-- #comment-## -->

	</li><!-- #comment-## -->
		</ol>

		
	
	
									<div id="respond" class="comment-respond">
				<h3 id="reply-title" class="comment-reply-title">Leave a Reply <small><a rel="nofollow" id="cancel-comment-reply-link" href="/2010/09/27/the-secret-life-of-javascript-primitives/#respond" style="display:none;">Cancel reply</a></small></h3>
									<form action="http://javascriptweblog.wordpress.com/wp-comments-post.php" method="post" id="commentform" class="comment-form">
																										


												<input type="hidden" id="highlander_comment_nonce" name="highlander_comment_nonce" value="2eb090b9e4" /><input type="hidden" name="_wp_http_referer" value="/2010/09/27/the-secret-life-of-javascript-primitives/" />
<input type="hidden" name="hc_post_as" id="hc_post_as" value="guest" />

<div class="comment-form-field comment-textarea">
	<label for="comment">Enter your comment here...</label>
	<div id="comment-form-comment"><textarea id="comment" name="comment" title="Enter your comment here..."></textarea></div>
</div>

<div id="comment-form-identity">

	<div id="comment-form-nascar">
		<p>Fill in your details below or click an icon to log in:</p>
		<ul>
			<li class="selected" style="display:none;">
				<a href="#comment-form-guest" id="postas-guest" title="Guest">
					<span></span>
				</a>
			</li>
			<li>
				<a href="#comment-form-load-service:WordPress.com" id="postas-wordpress" title="WordPress.com">
					<span></span>
				</a>
			</li>
			<li>
				<a href="#comment-form-load-service:Twitter" id="postas-twitter" title="Twitter">
					<span></span>
				</a>
			</li>
			<li>
				<a href="#comment-form-load-service:Facebook" id="postas-facebook" title="Facebook">
					<span></span>
				</a>
			</li>
			<li>
			<iframe id="googleplus-sign-in" name="googleplus-sign-in" src="https://public-api.wordpress.com/connect/?googleplus-sign-in=http%3A%2F%2Fjavascriptweblog.wordpress.com" width="24" height="24" scrolling="no" allowtransparency="true" seamless="seamless" frameborder="0"></iframe>
			</li>
		</ul>
	</div>

	<div id="comment-form-guest" class="comment-form-service selected">
		<div class="comment-form-padder">
			<div class="comment-form-avatar">
<a href="https://gravatar.com/site/signup/" target="_blank">				<img src="http://1.gravatar.com/avatar/ad516503a11cd5ca435acc9bb6523536?s=25&amp;d=monsterid&amp;forcedefault=y&amp;r=G" alt="Gravatar" width="25" class="no-grav" />
</a>			</div>

				<div class="comment-form-fields">
				<div class="comment-form-field comment-form-email">
					<label for="email">Email <span class="nopublish">(Address never made public)</span></label>
					<div class="comment-form-input"><input id="email" name="email" type="email" value="" /></div>
				</div>
				<div class="comment-form-field comment-form-author">
					<label for="author">Name</label>
					<div class="comment-form-input"><input id="author" name="author" type="text" value="" /></div>
				</div>
				<div class="comment-form-field comment-form-url">
					<label for="url">Website</label>
					<div class="comment-form-input"><input id="url" name="url" type="text" value="" /></div>
				</div>
			</div>
	
		</div>
	</div>

	<div id="comment-form-wordpress" class="comment-form-service">
		<div class="comment-form-padder">
			<div class="comment-form-avatar">
				<img src="http://s2.wp.com/wp-content/mu-plugins/highlander-comments/images/wplogo.png?m=1391188133g" alt="WordPress.com Logo" width="25" class="no-grav" />
			</div>

				<div class="comment-form-fields">
				<input type="hidden" name="wp_avatar" id="wordpress-avatar" class="comment-meta-wordpress" value="" />
				<input type="hidden" name="wp_user_id" id="wordpress-user_id" class="comment-meta-wordpress" value="" />
				<input type="hidden" name="wp_access_token" id="wordpress-access_token" class="comment-meta-wordpress" value="" />
				<p class="comment-form-posting-as pa-wordpress"><strong></strong> You are commenting using your WordPress.com account. <span class="comment-form-log-out">(&nbsp;<a href="javascript:HighlanderComments.doExternalLogout( 'wordpress' );">Log&nbsp;Out</a>&nbsp;/&nbsp;<a href="#" onclick="javascript:HighlanderComments.switchAccount();return false;">Change</a>&nbsp;)</span></p>
			</div>
	
		</div>
	</div>

	<div id="comment-form-twitter" class="comment-form-service">
		<div class="comment-form-padder">
			<div class="comment-form-avatar">
				<img src="http://1.gravatar.com/avatar/ad516503a11cd5ca435acc9bb6523536?s=25&amp;d=monsterid&amp;forcedefault=y&amp;r=G" alt="Twitter picture" width="25" class="no-grav" />
			</div>

				<div class="comment-form-fields">
				<input type="hidden" name="twitter_avatar" id="twitter-avatar" class="comment-meta-twitter" value="" />
				<input type="hidden" name="twitter_user_id" id="twitter-user_id" class="comment-meta-twitter" value="" />
				<input type="hidden" name="twitter_access_token" id="twitter-access_token" class="comment-meta-twitter" value="" />
				<p class="comment-form-posting-as pa-twitter"><strong></strong> You are commenting using your Twitter account. <span class="comment-form-log-out">(&nbsp;<a href="javascript:HighlanderComments.doExternalLogout( 'twitter' );">Log&nbsp;Out</a>&nbsp;/&nbsp;<a href="#" onclick="javascript:HighlanderComments.switchAccount();return false;">Change</a>&nbsp;)</span></p>
			</div>
	
		</div>
	</div>

	<div id="comment-form-facebook" class="comment-form-service">
		<div class="comment-form-padder">
			<div class="comment-form-avatar">
				<img src="http://1.gravatar.com/avatar/ad516503a11cd5ca435acc9bb6523536?s=25&amp;d=monsterid&amp;forcedefault=y&amp;r=G" alt="Facebook photo" width="25" class="no-grav" />
			</div>

				<div class="comment-form-fields">
				<input type="hidden" name="fb_avatar" id="facebook-avatar" class="comment-meta-facebook" value="" />
				<input type="hidden" name="fb_user_id" id="facebook-user_id" class="comment-meta-facebook" value="" />
				<input type="hidden" name="fb_access_token" id="facebook-access_token" class="comment-meta-facebook" value="" />
				<p class="comment-form-posting-as pa-facebook"><strong></strong> You are commenting using your Facebook account. <span class="comment-form-log-out">(&nbsp;<a href="javascript:HighlanderComments.doExternalLogout( 'facebook' );">Log&nbsp;Out</a>&nbsp;/&nbsp;<a href="#" onclick="javascript:HighlanderComments.switchAccount();return false;">Change</a>&nbsp;)</span></p>
			</div>
	
		</div>
	</div>

	<div id="comment-form-googleplus" class="comment-form-service">
		<div class="comment-form-padder">
			<div class="comment-form-avatar">
				<img src="http://1.gravatar.com/avatar/ad516503a11cd5ca435acc9bb6523536?s=25&amp;d=monsterid&amp;forcedefault=y&amp;r=G" alt="Google+ photo" width="25" class="no-grav" />
			</div>

				<div class="comment-form-fields">
				<input type="hidden" name="googleplus_avatar" id="googleplus-avatar" class="comment-meta-googleplus" value="" />
				<input type="hidden" name="googleplus_user_id" id="googleplus-user_id" class="comment-meta-googleplus" value="" />
				<input type="hidden" name="googleplus_access_token" id="googleplus-access_token" class="comment-meta-googleplus" value="" />
				<p class="comment-form-posting-as pa-googleplus"><strong></strong> You are commenting using your Google+ account. <span class="comment-form-log-out">(&nbsp;<a href="javascript:HighlanderComments.doExternalLogout( 'googleplus' );">Log&nbsp;Out</a>&nbsp;/&nbsp;<a href="#" onclick="javascript:HighlanderComments.switchAccount();return false;">Change</a>&nbsp;)</span></p>
			</div>
	
		</div>
	</div>


	<div id="comment-form-load-service" class="comment-form-service">
		<div class="comment-form-posting-as-cancel"><a href="javascript:HighlanderComments.cancelExternalWindow();">Cancel</a></div>
		<p>Connecting to %s</p>
	</div>

	
</div>

<script type="text/javascript">
var highlander_expando_javascript = function(){
	var input = document.createElement( 'input' ),
	    comment = jQuery( '#comment' );

	if ( 'placeholder' in input ) {
		comment.attr( 'placeholder', jQuery( '.comment-textarea label' ).remove().text() );
	}

	// Expando Mode: start small, then auto-resize on first click + text length
	jQuery( '#comment-form-identity' ).hide();
	jQuery( '#comment-form-subscribe' ).hide();
	jQuery( '#commentform .form-submit' ).hide();

	comment.css( { 'height':'10px' } ).one( 'focus', function() {
		var timer = setInterval( HighlanderComments.resizeCallback, 10 )
		jQuery( this ).animate( { 'height': HighlanderComments.initialHeight } ).delay( 100 ).queue( function(n) { clearInterval( timer ); HighlanderComments.resizeCallback(); n(); } );
		jQuery( '#comment-form-identity' ).slideDown();
		jQuery( '#comment-form-subscribe' ).slideDown();
		jQuery( '#commentform .form-submit' ).slideDown();
	});
}
jQuery(document).ready( highlander_expando_javascript );
</script>

<div id="comment-form-subscribe">
	<p class="comment-subscription-form"><input type="checkbox" name="subscribe" id="subscribe" value="subscribe" style="width: auto;" tabindex="6"/> <label class="subscribe-label" id="subscribe-label" for="subscribe" style="display: inline;">Notify me of follow-up comments via email.</label></p><p class="post-subscription-form"><input type="checkbox" name="subscribe_blog" id="subscribe_blog" value="subscribe" style="width: auto;" tabindex="7"/> <label class="subscribe-label" id="subscribe-blog-label" for="subscribe_blog"  style="display: inline;">Notify me of new posts via email.</label></p></div>

												<p class="form-submit">
							<input name="submit" type="submit" id="comment-submit" value="Post Comment" />
							<input type='hidden' name='comment_post_ID' value='1418' id='comment_post_ID' />
<input type='hidden' name='comment_parent' id='comment_parent' value='0' />
						</p>
						<p style="display: none;"><input type="hidden" id="akismet_comment_nonce" name="akismet_comment_nonce" value="088773364c" /></p>
<input type="hidden" name="genseq" value="1401425959" />
<p style="display: none;"><input type="hidden" id="ak_js" name="ak_js" value="231"/></p>					</form>
							</div><!-- #respond -->
			<div style="clear: both"></div>
</div><!-- #comments .comments-area -->

			
			</div><!-- #content -->
		</div><!-- #primary .site-content -->




	</div><!-- #main -->

	<footer id="colophon" class="site-footer" role="contentinfo">
		<div class="site-info">
						<a href="http://wordpress.com/?ref=footer_blog">Blog at WordPress.com</a>.
			<span class="sep"> | </span>
			<a href="http://theme.wordpress.com/themes/ari/" title="Learn more about this theme">The Ari Theme</a>.		</div><!-- .site-info -->
	</footer><!-- .site-footer .site-footer -->
</div><!-- #page .hfeed .site -->

<script type='text/javascript' src='//0.gravatar.com/js/gprofiles.js?ver=201422x'></script>
<script type='text/javascript'>
/* <![CDATA[ */
var WPGroHo = {"my_hash":""};
/* ]]> */
</script>
<script type='text/javascript' src='http://s2.wp.com/wp-content/mu-plugins/gravatar-hovercards/wpgroho.js?m=1380573781g'></script>

	<script>
		//initialize and attach hovercards to all gravatars
		jQuery( document ).ready( function( $ ) {
			if ( typeof Gravatar.init !== "function" ) {
				return;
			}			

			Gravatar.profile_cb = function( hash, id ) {
				WPGroHo.syncProfileData( hash, id );
			};
			Gravatar.my_hash = WPGroHo.my_hash;
			Gravatar.init( 'body', '#wp-admin-bar-my-account' );
		});
	</script>

		<div style="display:none">
	<div class="grofile-hash-map-efb2415f773b0a945ff2b15f48401c0b">
	</div>
	<div class="grofile-hash-map-52c6174ba60557536f93809b4e95d97c">
	</div>
	<div class="grofile-hash-map-882f228c4993ccf0a86e96394636415c">
	</div>
	<div class="grofile-hash-map-6766096e8ae81ad6b3b82b9c12be19e0">
	</div>
	<div class="grofile-hash-map-7fff733ad25bb65da8f0db1c1a2d556e">
	</div>
	<div class="grofile-hash-map-f8078acb93183ca46bf31c66addd1575">
	</div>
	<div class="grofile-hash-map-2f2bb08ab51265d64000be003994b1ad">
	</div>
	<div class="grofile-hash-map-529a291a6eb6205d850ac47d2c38b24c">
	</div>
	<div class="grofile-hash-map-d41d8cd98f00b204e9800998ecf8427e">
	</div>
	<div class="grofile-hash-map-c2d6b4966bd4584903d39e55cd4c442d">
	</div>
	</div>
<script type='text/javascript'>
/* <![CDATA[ */
var HighlanderComments = {"loggingInText":"Logging In\u2026","submittingText":"Posting Comment\u2026","postCommentText":"Post Comment","connectingToText":"Connecting to %s","commentingAsText":"%1$s: You are commenting using your %2$s account.","logoutText":"Log Out","loginText":"Log In","connectURL":"http:\/\/javascriptweblog.wordpress.com\/public.api\/connect\/?action=request","logoutURL":"https:\/\/javascriptweblog.wordpress.com\/wp-login.php?action=logout&_wpnonce=e4d6db6dcc","homeURL":"http:\/\/javascriptweblog.wordpress.com\/","postID":"1418","gravDefault":"monsterid","enterACommentError":"Please enter a comment","enterEmailError":"Please enter your email address here","invalidEmailError":"Invalid email address","enterAuthorError":"Please enter your name here","gravatarFromEmail":"This picture will show whenever you leave a comment. Click to customize it.","logInToExternalAccount":"Log in to use details from one of these accounts.","change":"Change","changeAccount":"Change Account","comment_registration":"","userIsLoggedIn":"","isJetpack":"0"};
/* ]]> */
</script>
<script type='text/javascript' src='http://s0.wp.com/_static/??/wp-content/js/jquery/jquery.autoresize.js,/wp-content/mu-plugins/highlander-comments/script.js?m=1395185286j'></script>

	<div id="bit" class="loggedout-follow-normal">
		<a class="bsub" href="javascript:void(0)"><span id='bsub-text'>Follow</span></a>
		<div id="bitsubscribe">

					<h3><label for="loggedout-follow-field">Follow &ldquo;JavaScript, JavaScript...&rdquo;</label></h3>

			<form action="https://subscribe.wordpress.com" method="post" accept-charset="utf-8" id="loggedout-follow">
			<p>Get every new post delivered to your Inbox.</p>

			<p id="loggedout-follow-error" style="display: none;"></p>

						<p class="bit-follow-count">Join 459 other followers</p>
			<p><input type="email" name="email" value="Enter your email address" onfocus='this.value=(this.value=="Enter your email address") ? "" : this.value;' onblur='this.value=(this.value=="") ? "Enter email address" : this.value;'  id="loggedout-follow-field"/></p>

			<input type="hidden" name="action" value="subscribe"/>
			<input type="hidden" name="blog_id" value="12490669"/>
			<input type="hidden" name="source" value="http://javascriptweblog.wordpress.com/2010/09/27/the-secret-life-of-javascript-primitives/"/>
			<input type="hidden" name="sub-type" value="loggedout-follow"/>

			<input type="hidden" id="_wpnonce" name="_wpnonce" value="f148c354bf" /><input type="hidden" name="_wp_http_referer" value="/2010/09/27/the-secret-life-of-javascript-primitives/" />
			<p id='bsub-subscribe-button'><input type="submit" value="Sign me up" /></p>
			</form>
					<div id='bsub-credit'><a href="http://wordpress.com/signup/?ref=lof">Powered by WordPress.com</a></div>
		</div><!-- #bitsubscribe -->
	</div><!-- #bit -->
		<iframe src='http://widgets.wp.com/likes/master.html?ver=20140528#ver=20140528&amp;mp6=1' scrolling='no' id='likes-master' name='likes-master' style='display:none;'></iframe>
		<div id='likes-other-gravatars'><div class="likes-text"><span>%d</span> bloggers like this:</div><ul class="wpl-avatars sd-like-gravatars"></ul></div>
		<script type="text/javascript">
		//<![CDATA[
			var jetpackLikesWidgetQueue = [];
			var jetpackLikesWidgetBatch = [];
			var jetpackLikesMasterReady = false;

			function JetpackLikespostMessage( message, target ) {
				if ( "string" === typeof message ){
					try{
						message = JSON.parse( message );
					}
					catch(e) {
						return;
					}
				}

				pm( {
					target: target,
					type: 'likesMessage',
					data: message,
					origin: '*'
				} );
			}

			function JetpackLikesBatchHandler() {
				var requests = [];
				jQuery( 'div.jetpack-likes-widget-unloaded' ).each( function( i ) {
					if ( jetpackLikesWidgetBatch.indexOf( this.id ) > -1 )
						return;
					jetpackLikesWidgetBatch.push( this.id );
					var regex = /like-(post|comment)-wrapper-(\d+)-(\d+)-(\w+)/;
					var match = regex.exec( this.id );
					if ( ! match || match.length != 5 )
						return;

					var info = {
						blog_id: match[2],
						width:   this.width
					};

					if ( 'post' == match[1] ) {
						info.post_id = match[3];
					} else if ( 'comment' == match[1] ) {
						info.comment_id = match[3];
					}

					info.obj_id = match[4];

					requests.push( info );
				});

				if ( requests.length > 0 ) {
					JetpackLikespostMessage( { event: 'initialBatch', requests: requests }, window.frames['likes-master'] );
				}
			}

			function JetpackLikesMessageListener( event ) {
				if ( "undefined" == typeof event.event )
					return;

				if ( 'masterReady' == event.event ) {
					jQuery( document ).ready( function() {
						jetpackLikesMasterReady = true;

						var stylesData = {
								event: 'injectStyles'
						};

						if ( jQuery( 'iframe.admin-bar-likes-widget' ).length > 0 ) {
							JetpackLikespostMessage( { event: 'adminBarEnabled' }, window.frames[ 'likes-master' ] );

							stylesData.adminBarStyles = {
								background: jQuery( '#wpadminbar .quicklinks li#wp-admin-bar-wpl-like > a' ).css( 'background' ),
								isRtl: ( 'rtl' == jQuery( '#wpadminbar' ).css( 'direction' ) )
							};
						}

						if ( !window.addEventListener )
							jQuery( '#wp-admin-bar-admin-bar-likes-widget' ).hide();

						stylesData.textStyles = {
							color: jQuery( '.sd-text-color').css( 'color' ),
							fontFamily: jQuery( '.sd-text-color' ).css( 'font-family' ),
							fontSize: jQuery( '.sd-text-color' ).css( 'font-size' ),
							direction: jQuery( '.sd-text-color' ).css( 'direction' ),
							fontWeight: jQuery( '.sd-text-color' ).css( 'font-weight' ),
							fontStyle: jQuery( '.sd-text-color' ).css( 'font-style' ),
							textDecoration: jQuery( '.sd-text-color' ).css('text-decoration')
						};

						stylesData.linkStyles = {
							color: jQuery( '.sd-link-color' ).css('color'),
							fontFamily: jQuery( '.sd-link-color' ).css('font-family'),
							fontSize: jQuery( '.sd-link-color' ).css('font-size'),
							textDecoration: jQuery( '.sd-link-color' ).css('text-decoration'),
							fontWeight: jQuery( '.sd-link-color' ).css( 'font-weight' ),
							fontStyle: jQuery( '.sd-link-color' ).css( 'font-style' )
						};

						JetpackLikespostMessage( stylesData, window.frames[ 'likes-master' ] );

						JetpackLikesBatchHandler();

						jQuery( document ).on( 'inview', 'div.jetpack-likes-widget-unloaded', function() {
							jetpackLikesWidgetQueue.push( this.id );
						});
					});
				}

				if ( 'showLikeWidget' == event.event ) {
					jQuery( '#' + event.id + ' .post-likes-widget-placeholder'  ).fadeOut( 'fast', function() {
						jQuery( '#' + event.id + ' .post-likes-widget' ).fadeIn( 'fast', function() {
							JetpackLikespostMessage( { event: 'likeWidgetDisplayed', blog_id: event.blog_id, post_id: event.post_id, obj_id: event.obj_id }, window.frames['likes-master'] );
						});
					});
				}

				if ( 'clickReblogFlair' == event.event ) {
					wpcom_reblog.toggle_reblog_box_flair( event.obj_id );
				}

				if ( 'showOtherGravatars' == event.event ) {
					var $container = jQuery( '#likes-other-gravatars' );
					var $list = $container.find( 'ul' );

					$container.hide();
					$list.html( '' );

					$container.find( '.likes-text span' ).text( event.total );

					jQuery.each( event.likers, function( i, liker ) {
						$list.append( '<li class="' + liker.css_class + '"><a href="' + liker.profile_URL + '" class="wpl-liker" rel="nofollow" target="_parent"><img src="' + liker.avatar_URL + '" alt="' + liker.name + '" width="30" height="30" style="padding-right: 3px;" /></a></li>');
					} );

					var offset = jQuery( "[name='" + event.parent + "']" ).offset();

					$container.css( 'left', offset.left + event.position.left - 10 + 'px' );
					$container.css( 'top', offset.top + event.position.top - 33 + 'px' );

					var rowLength = Math.floor( event.width / 37 );
					var height = ( Math.ceil( event.likers.length / rowLength ) * 37 ) + 13;
					if ( height > 204 ) {
						height = 204;
					}

					$container.css( 'height', height + 'px' );
					$container.css( 'width', rowLength * 37 - 7 + 'px' );

					$list.css( 'width', rowLength * 37 + 'px' );

					$container.fadeIn( 'slow' );

					var scrollbarWidth = $list[0].offsetWidth - $list[0].clientWidth;
					if ( scrollbarWidth > 0 ) {
						$container.width( $container.width() + scrollbarWidth );
						$list.width( $list.width() + scrollbarWidth );
					}
				}
			}

			pm.bind( 'likesMessage', function(e) { JetpackLikesMessageListener(e); } );

			jQuery( document ).click( function( e ) {
				var $container = jQuery( '#likes-other-gravatars' );

				if ( $container.has( e.target ).length === 0 ) {
					$container.fadeOut( 'slow' );
				}
			});

			function JetpackLikesWidgetQueueHandler() {
				var wrapperID;
				if ( ! jetpackLikesMasterReady ) {
					setTimeout( JetpackLikesWidgetQueueHandler, 500 );
					return;
				}

				if ( jetpackLikesWidgetQueue.length > 0 ) {
					// We may have a widget that needs creating now
					var found = false;
					while( jetpackLikesWidgetQueue.length > 0 ) {
						// Grab the first member of the queue that isn't already loading.
						wrapperID = jetpackLikesWidgetQueue.splice( 0, 1 )[0];
						if ( jQuery( '#' + wrapperID ).hasClass( 'jetpack-likes-widget-unloaded' ) ) {
							found = true;
							break;
						}
					}
					if ( ! found ) {
						setTimeout( JetpackLikesWidgetQueueHandler, 500 );
						return;
					}
				} else if ( jQuery( 'div.jetpack-likes-widget-unloaded' ).length > 0 ) {
					// Grab any unloaded widgets for a batch request
					JetpackLikesBatchHandler();

					// Get the next unloaded widget
					wrapperID = jQuery( 'div.jetpack-likes-widget-unloaded' ).first()[0].id;
					if ( ! wrapperID ) {
						// Everything is currently loaded
						setTimeout( JetpackLikesWidgetQueueHandler, 500 );
						return;
					}
				}

				if ( 'undefined' === typeof wrapperID ) {
					setTimeout( JetpackLikesWidgetQueueHandler, 500 );
					return;
				}

				var $wrapper = jQuery( '#' + wrapperID );
				$wrapper.find( 'iframe' ).remove();

				if ( $wrapper.hasClass( 'slim-likes-widget' ) ) {
					$wrapper.find( '.post-likes-widget-placeholder' ).after( "<iframe class='post-likes-widget jetpack-likes-widget' name='" + $wrapper.data( 'name' ) + "' height='22px' width='68px' frameBorder='0' scrolling='no' src='" + $wrapper.data( 'src' ) + "'></iframe>" );
				} else {
					$wrapper.find( '.post-likes-widget-placeholder' ).after( "<iframe class='post-likes-widget jetpack-likes-widget' name='" + $wrapper.data( 'name' ) + "' height='55px' width='100%' frameBorder='0' src='" + $wrapper.data( 'src' ) + "'></iframe>" );
				}

				$wrapper.removeClass( 'jetpack-likes-widget-unloaded' ).addClass( 'jetpack-likes-widget-loading' );

				$wrapper.find( 'iframe' ).load( function( e ) {
					var $iframe = jQuery( e.target );
					$wrapper.removeClass( 'jetpack-likes-widget-loading' ).addClass( 'jetpack-likes-widget-loaded' );

					JetpackLikespostMessage( { event: 'loadLikeWidget', name: $iframe.attr( 'name' ), width: $iframe.width() }, window.frames[ 'likes-master' ] );

					if ( $wrapper.hasClass( 'slim-likes-widget' ) ) {
						$wrapper.find( 'iframe' ).Jetpack( 'resizeable' );
					}
				});
				setTimeout( JetpackLikesWidgetQueueHandler, 250 );
			}
			JetpackLikesWidgetQueueHandler();
		//]]>
		</script>
<script type='text/javascript' src='http://s0.wp.com/_static/??-eJzTLy/QTc7PK0nNK9EvyClNz8wr1i+uzCtJrMjITM/IAeKS1CJMEWP94uSizIISoOIM5/yiVL2sYh19yo1yKiotzvAKBvOBRtrn2hoaW5qbmxmZGhlmAQCbWUFH'></script>
<script type='text/javascript'>
	(function(){
		var corecss = document.createElement('link');
		var themecss = document.createElement('link');
		var corecssurl = "http://s0.wp.com/wp-content/plugins/syntaxhighlighter/syntaxhighlighter3/styles/shCore.css?m=1395343499g&amp;ver=3.0.83c";
		if ( corecss.setAttribute ) {
				corecss.setAttribute( "rel", "stylesheet" );
				corecss.setAttribute( "type", "text/css" );
				corecss.setAttribute( "href", corecssurl );
		} else {
				corecss.rel = "stylesheet";
				corecss.href = corecssurl;
		}
		document.getElementsByTagName("head")[0].insertBefore( corecss, document.getElementById("syntaxhighlighteranchor") );
		var themecssurl = "http://s0.wp.com/wp-content/plugins/syntaxhighlighter/syntaxhighlighter3/styles/shThemeDefault.css?m=1363304414g&amp;ver=3.0.83c";
		if ( themecss.setAttribute ) {
				themecss.setAttribute( "rel", "stylesheet" );
				themecss.setAttribute( "type", "text/css" );
				themecss.setAttribute( "href", themecssurl );
		} else {
				themecss.rel = "stylesheet";
				themecss.href = themecssurl;
		}
		//document.getElementById("syntaxhighlighteranchor").appendChild(themecss);
		document.getElementsByTagName("head")[0].insertBefore( themecss, document.getElementById("syntaxhighlighteranchor") );
	})();
	SyntaxHighlighter.config.strings.expandSource = '+ expand source';
	SyntaxHighlighter.config.strings.help = '?';
	SyntaxHighlighter.config.strings.alert = 'SyntaxHighlighter\n\n';
	SyntaxHighlighter.config.strings.noBrush = 'Can\'t find brush for: ';
	SyntaxHighlighter.config.strings.brushNotHtmlScript = 'Brush wasn\'t configured for html-script option: ';
	SyntaxHighlighter.defaults['pad-line-numbers'] = false;
	SyntaxHighlighter.defaults['toolbar'] = false;
	SyntaxHighlighter.all();
</script>
<script type='text/javascript' src='http://s1.wp.com/_static/??/wp-content/js/devicepx.js,/wp-content/themes/pub/ari/js/small-menu.js,/wp-includes/js/comment-reply.min.js,/wp-content/mu-plugins/akismet-3.0/_inc/form.js?m=1399919068j'></script>
<script type="text/javascript">
// <![CDATA[
(function() {
try{
  if ( window.external &&'msIsSiteMode' in window.external) {
    if (window.external.msIsSiteMode()) {
      var jl = document.createElement('script');
      jl.type='text/javascript';
      jl.async=true;
      jl.src='/wp-content/plugins/ie-sitemode/custom-jumplist.php';
      var s = document.getElementsByTagName('script')[0];
      s.parentNode.insertBefore(jl, s);
    }
  }
}catch(e){}
})();
// ]]>
</script><script src="http://s.stats.wordpress.com/w.js?21" type="text/javascript"></script>
<script type="text/javascript">
st_go({'blog':'12490669','v':'wpcom','tz':'-7','user_id':'0','post':'1418','subd':'javascriptweblog'});
ex_go({'crypt':'UE5XaGUuOTlwaD85flAmcm1mcmZsaDhkV11YdWtpP0NsWnVkPS9sL0ViLndld3AsdkJ1cXFURjg1cDR0TiZMSUN0L35CWTZMdEF1R3k5OW1SUEZfNm1YbzBjSiZPUm1BPSVlX2kmQi9MYTV1SDV8cWxnOHJ4QWpnRTFRJlJHd3JBVUpoUmp2UkU9dXcxW2hXZFhicUtdS3EzMXVnQWFhQlBXZkFCLTZwVk5IZ35XRHJRWExXV1YtSmR3LmhIYS1SMHNQLk9PVFBQenhzRXd+QStmMHAwbG1+eC9CLUJ6JW5PSERuLGYlYXNVelZ1Wzc2N2huOEQ9ZXcsdlJPWmEzfk55cVcwR3gzdXovT1cvNVliYlEuLnU2WHE2PXU2JWJrQllmRHpBQ2pBaVYwfg=='});
addLoadEvent(function(){linktracker_init('12490669',1418);});
	</script>
<noscript><img src="http://stats.wordpress.com/b.gif?v=noscript" style="height:0px;width:0px;overflow:hidden" alt="" /></noscript>
<script>
if ( 'object' === typeof wpcom_mobile_user_agent_info ) {

	wpcom_mobile_user_agent_info.init();
	var mobileStatsQueryString = "";
	
	if( false !== wpcom_mobile_user_agent_info.matchedPlatformName )
		mobileStatsQueryString += "&x_" + 'mobile_platforms' + '=' + wpcom_mobile_user_agent_info.matchedPlatformName;
	
	if( false !== wpcom_mobile_user_agent_info.matchedUserAgentName )
		mobileStatsQueryString += "&x_" + 'mobile_devices' + '=' + wpcom_mobile_user_agent_info.matchedUserAgentName;
	
	if( wpcom_mobile_user_agent_info.isIPad() )
		mobileStatsQueryString += "&x_" + 'ipad_views' + '=' + 'views';

	if( "" != mobileStatsQueryString ) {
		new Image().src = document.location.protocol + '//stats.wordpress.com/g.gif?v=wpcom-no-pv' + mobileStatsQueryString + '&baba=' + Math.random();
	}
	
}
</script>
</body>
</html>