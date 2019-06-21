
# Add AtomJump Messaging to your site

* Demo: https://fiddle.jshell.net/rh97gy06/show/
* You can also use this jsfiddle https://jsfiddle.net/rh97gy06/. 
* Or see the full source https://github.com/atomjump/atomjump-messaging-example/blob/master/index.html of this demo page.

Now, try adding this to your own site, by following the 3 steps below.
1. Copy and paste the following into the <head> section of your HTML page:

```
<!-- AtomJump Feedback Starts -->
   <link rel="StyleSheet" href="https://AtomJump.com/bower_components/bootstrap/dist/css/bootstrap.min.css" rel="stylesheet">
	
	<!-- AtomJump Feedback CSS -->
	<link rel="StyleSheet" href="https://AtomJump.com/bower_components/atomjump/css/releases/comments-0.9.1.css?ver=1">
	
	<!-- Bootstrap HTML5 shim and Respond.js IE8 support of HTML5 elements and media queries -->
	<!--[if lt IE 9]>
	  <script src="https://oss.maxcdn.com/libs/html5shiv/3.7.0/html5shiv.js"></script>
	  <script src="https://oss.maxcdn.com/libs/respond.js/1.4.2/respond.min.js"></script>
	<![endif]-->
	
	<!-- Include your version of jQuery here. -->
	<script type="text/javascript" src="https://code.jquery.com/jquery-1.9.1.min.js"></script>
	
	<script>
		//Add your configuration here for AtomJump Feedback
		var ajFeedback = {
			"uniqueFeedbackId" : "aj_public_changeme",		//This can be anything globally unique to your company/page	
			"myMachineUser" : "192.104.113.117:8",			
			"server":  "https://AtomJump.com/api",
			"cssFeedback": "https://AtomJump.com/bower_components/atomjump/css/releases/comments-0.9.1.css?ver=1",
			"cssBootstrap": "https://AtomJump.com/bower_components/bootstrap/dist/css/bootstrap.min.css"
		}
	</script>
	<script type="text/javascript" src="https://AtomJump.com/js/chat-0.9.2.js"></script>
<!-- AtomJump Feedback Ends -->
```

2. Copy and paste the following into the <body> section of your page:

```
<!-- holds the popup comments. Can be anywhere between the <body> tags -->
<div id="comment-holder"></div>
```

3. Copy and paste the following link, where you want a link to open the messaging on your site:

```
<a class="comment-open" href="javascript:">Click me for messaging</a>
```

Or for more details on integration with your site, see the AtomJump Loop project: https://github.com/atomjump/loop#loop
