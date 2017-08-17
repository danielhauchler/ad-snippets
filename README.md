# html5-ad-components
Contains personal necessary code snippets to produce an html5 ad.

### GSAP
Include the gsap library into your html file, specified by your adserver.
```bash
<script type="text/javascript" src="http://sharedlibraries.danielhauchler.de/anim_panel.js"></script>
```
#### variables & timeline
```bash
  function startAnimation() {
  
    // Assets
    var $ad 		= $('#ad'),
    	$background	= $('#background'),
        
        tl = new TimelineMax();
        
    // GSAP Animation
    tl.add('01')
    .to($ad, .6, {opacity:1})
    
  }
  startAnimation()
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

#### timeline duration
```bash
    //count animation duration
    var currentDuration = tl2.duration();
    console.log(currentDuration);
```

#### merge timelines
```bash
    //Merge timelines to master timeline
    masterTimeline.add([tl1, tl2]);
```

### Tools
#### AnimPanel
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

### Sizmek 
#### Shared Libraries
```bash
<script src="https://secure-ds.serving-sys.com/BurstingcachedScripts/libraries/jquery/1_11_3/jquery.min.js"></script>
<script src="https://secure-ds.serving-sys.com/BurstingcachedScripts/libraries/greensock/1_19_0/TweenMax.min.js"></script>
```

#### Necessary Scripts
```bash
<script src="EBLoader.js"></script>
<script src="scripts.js"></script>
```
