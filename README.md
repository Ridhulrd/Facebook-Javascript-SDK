<!DOCTYPE html>
<html>
	<head>
		<title>Title of the document</title>
		<link rel="stylesheet" type="text/css" href="">
		<script type="text/javascript">
		</script>
	</head>
	<body>
		<div id="fb-root"></div>
		<script>
		    window.fbAsyncInit = function () {
		        FB.init({
		            appId: '**appId**',                    
		            channelUrl: '//local.facebook-test/channel.html',
		            status: true,                                
		            xfbml: true,                                 
		            oauth: true                                  
		        });
		        FB.login(function (response) {
		            if (response.authResponse) {
		                 var opts = {
		                    message: 'My first post on facebook page',
		                    access_token: '**PageAccessToken**',
		                	  name : '**name**',
		                	  link: 'https://developers.facebook.com/docs/reference/dialogs/',
		                	  description : '**description**',
		                 };
		                 FB.api('/me/feed', 'post', opts, function(response)
		                 {
		                 	if (!response || response.error)
		                 	{
		                 		console.log(response.error);
		                 		alert('Posting error occured');
		                 	}else{
		                 		alert('Success - Post ID: ' + response.id);
		                 	}
		                 });
		            } else {
		                alert('Not logged in');
		            }
		        }, { scope: 'manage_pages, publish_actions, user_photos' });

		    };
		    (function (d, s, id) {
		        var js, fjs = d.getElementsByTagName(s)[0];
		        if (d.getElementById(id)) { return; }
		        js = d.createElement(s); js.id = id;
		        js.src = "//connect.facebook.net/en_US/all.js";
		        fjs.parentNode.insertBefore(js, fjs);
		    }(document, 'script', 'facebook-jssdk'));
        </script>
	</body>
</html>
