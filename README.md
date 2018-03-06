# html5-ad-components
Contains personal necessary code snippets to produce an html5 ad.

#### HTML
```bash
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title></title>
  <meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1, minimum-scale=1"/>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <div id="ad">
    <div id="hl"></div>
    <div id="sl"></div>
    <div id="logo"></div>
  </div>
  <script type="text/javascript">
	
	// Place your animation here.
	
  </script>
</body>
</html>
```

#### CSS
```bash
#ad {
  position:absolute;
  top: 0;
  left: 0;
  width: 300px;
  height: 250px;
  overflow:hidden;
  -moz-user-select: -moz-none;
  -khtml-user-select: none;
  -webkit-user-select: none;
  -ms-user-select: none;
  user-select: none;
  cursor: pointer;
}
.el {
  position: absolute;
  top:0;
  left:0;
  width: 100%;
  height: 100%;
  background-size: 100% 100%;
}
#logo {
  z-index: 1;
  background-image: url('images/logo.png');
}
#hl {
  z-index: 2;
  background-image: url('images/hl.png');
}
#sl {
  z-index: 3;
  background-image: url('images/sl.png');
}
```

### GSAP
Include the gsap library into your html file, specified by your adserver.
```bash
<script type="text/javascript" src="https://cdnjs.cloudflare.com/ajax/libs/gsap/1.20.2/TweenMax.min.js"></script>
```
#### Timelines & Animations
```bash
  function startAnim() {
  
    // Assets
    var $ad 		= $('#ad'),
    	$background	= $('#background'),
        
        tl = new TimelineMax();
        
    // GSAP Animation
    tl.add('01')
    .to($ad, .6, {opacity:1})
    
  }
  startAnim()
```

#### loops
```bash
    // Callabck function
    .addCallback( restart, "+=.2");
    
    // Restart the ad according to the desired loops
    function done() {
    	tl.restart();
    }
	
    // Loop Counter
    var i = 0

    // Loop function with Counter
    function restart() {
    	if (i < 1) {
    	    i++;
    	    TweenMax.to($ad, 1.3, {opacity:0, ease: Power3.easeInOut, onComplete:done},13.3);
    	} else {
	    tl.stop('end')
    	}
    }
```

#### onComplete function
```bash
    function youtFunction() {
  	tl.play(3)
    }

    TweenMax.from(element, 14, {opacity:0, onComplete:youtFunction});
```

#### hover events
```bash
    function handleHover() {
	TweenMax.to(... {...});
    }
    function handleOut() {
        TweenMax.to(... {...});
    }

    $ad.addEventListener("mouseover", handleHover);
    $ad.addEventListener("mouseout", handleOut);
```

#### merge timelines
```bash
    var masterTimeline = new TimelineMax({paused:true}),
               	   tl1 = new TimelineMax(),
                   tl2 = new TimelineMax();
		   
    //Merge timelines to master timeline
    masterTimeline.add([tl1, tl2]);
    
    window.onload = function(){
        masterTimeline.play();
    }
```

### tools
#### anim panel
include it in your HTML:
```bash
<script type="text/javascript" src="http://sharedlibraries.danielhauchler.de/anim_panel.js"></script>
```
Create the AnimPanel, passing it your Timeline instance
```bash
<script>
  new AnimPanel(tl);
</script>

```

#### timeline duration
```bash
    //count animation duration
    var currentDuration = tl2.duration();
    console.log(currentDuration);
```

### Clicktags
#### catcher utility
```bash
    if(this.getUriParams.clicktag) window.clicktag = this.getUriParams.clicktag;
    if(this.getUriParams.clickTag) window.clicktag = this.getUriParams.clickTag;
    if(this.getUriParams.clickTAG) window.clicktag = this.getUriParams.clickTAG;
```
 

### sizmek 
#### shared libraries
```bash
<script src="https://secure-ds.serving-sys.com/BurstingcachedScripts/libraries/jquery/1_11_3/jquery.min.js"></script>
<script src="https://secure-ds.serving-sys.com/BurstingcachedScripts/libraries/greensock/1_19_0/TweenMax.min.js"></script>
```

#### necessary includes
```bash
<script src="EBLoader.js"></script>
<script src="scripts.js"></script>
```

### Google
#### shared libraries
```bash
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.2.1/jquery.min.js"></script>
<script src="https://s0.2mdn.net/ads/studio/cached_libs/tweenmax_1.19.1_92cf05aba6ca4ea5cbc62b5a7cb924e3_min.js"></script>```
```

