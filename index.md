<html lang="en" >
<head>
  <meta content='width=device-width,initial-scale=1.0,minimum-scale=1.0,maximum-scale=1.0' name='viewport'/>

	<meta charset="UTF-8">
	<title>Drive Video Player</title>
	<link rel="shortcut icon" href="https://cdn.discordapp.com/attachments/857845513814540319/943398929804976148/20210622_234449.png" type="image/x-icon">
</head>
</script>
<body>

	<style>
     		body {
			padding: 0;
			margin: 0;
		}

		video {
			width: 100%;
			height: 100%;
			position: absolute;
		}
.embed {
    position: absolute;
    background: none;
    top: 2px;
    z-index: 999;
    color: aqua;
    font-family: sans-serif;
    font-size: 18px;
    border: 0;
    font-weight: 600;
    right: 10px;
}
.post-body img, .post-body .tr-caption-container {
padding: 0;
width:auto;
max-width:100%;
height:auto;
}
      
<!--ini-->      
      
	</style>
	<script src="https://cdn.fluidplayer.com/v3/current/fluidplayer.min.js">
	</script>
	<script>
		var apikey = "AIzaSyAHIDPKFSVbDwk-NdlAW8n3uh2q6AJkyAA";//Your Drive Api Key
        var eid="";
        var video="";
        var embed="";

        if(!getParameterByName('id') || getParameterByName('ib')){
          var eid = prompt('Enter Drive Video ID :- ');
          embed = `
<iframe width="100%" height="100%" 
scrolling="no"
src="${location.href}?id=${eid}" 
frameborder="0" ; autoplay; clipboard-write; encrypted-media; 
gyroscope; picture-in-picture" allowfullscreen>
</iframe>
          `;
          prompt('Here is Your Embed Code :- ',embed);
          window.location.href = window.location.href+'?id='+eid;
        } 
        video = getParameterByName('id') ;
        if(getParameterByName('ib')){
            video = btoa(getParameterByName('ib'));
        }
        var vidurl = "https://www.googleapis.com/drive/v3/files/"+video+"?alt=media&key="+apikey;
        document.write("<video controls id='video' src="+vidurl+"></video>");


function getembed(){
            var code = `
<iframe width="100%" height="100%" 
scrolling="no"
src="${location.href}?id=${video}" 
frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; 
gyroscope; picture-in-picture" allowfullscreen>
</iframe>
          `;
          prompt('Here is Your Embed Code :- ',code);
}

function getParameterByName(name, url = window.location.href) {
    name = name.replace(/[\[\]]/g, '\\$&');
    var regex = new RegExp('[?&]' + name + '(=([^&#]*)|&|#|$)'),
        results = regex.exec(url);
    if (!results) return null;
    if (!results[2]) return '';
    return decodeURIComponent(results[2].replace(/\+/g, ' '));
}
	</script>

<script>
    var myFP = fluidPlayer(
        'video',	{
	"layoutControls": {
		"controlBar": {
			"autoHideTimeout": 3,
			"animated": true,
			"autoHide": true
		},
		"htmlOnPauseBlock": {
			"html": '<button class=\"embed\" onclick=\"getembed()\">Embed</button>\n',
			"height": null,
			"width": null
		},
		"autoPlay": false,
		"mute": false,
		"allowTheatre": true,
		"playPauseAnimation": false,
		"playbackRateEnabled": true,
		"allowDownload": false,
		"playButtonShowing": true,
		"fillToContainer": false,
		"primaryColor": "#ff3d2d",
		"posterImage": "https://blogger.googleusercontent.com/img/a/AVvXsEibuGmrk8yWN-OD_9mSse1ULDQ2iOlNqyuTGHK293mkte1xj1kBNK-KUJ_IN9SakHejgjb3yQzkC1wicabq79NMEYPBguZdJfp5DDFuTEC9Oa5zO6tXx1kcDbExbneoN1-lNdFfoDDmS_h2kWggm9KHh8X3dtRQ5x41PNg9gdw-77BFULEfhBvcr6jGQA=s1920"
	},
	"vastOptions": {
		"adList": [],
		"adCTAText": false,
		"adCTATextPosition": ""
	}
})
</script>
  
</body>

</html>
