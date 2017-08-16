# ad-production-lines
Contains personal necessary code snippets for ad productions.

### GSAP
#### variables & timeline
```bash
  function startAnimation() {
  
    // Assets
    var $ad = $('#ad'),
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
    ...
    .from($rectangle, .6, { width:100, height: 100, ease: Power4.easeOut }, '+=.6')
    
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
    	    TweenMax.to(ad, 1.3, {opacity:0, ease: Power3.easeInOut, onComplete:done},13.3);
    	} else {
	    tl.stop('end')
    	}
    }
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
