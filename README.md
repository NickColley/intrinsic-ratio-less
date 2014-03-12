intrinsic-ratio-less
====================

Little less mixin for ratio aware responsive video

Fork of https://github.com/hzdg/bedrock/blob/master/mixins/intrinsic-ratio.less

## Variables
```javascript
// Default variables
// Make sure to move these somewhere where
// they can be easily overridden.
// 
// e.g.
// @import: 'variables.less'; <- In here
// @import: 'mixins.less'

@ir-ratio: 16/9;
@ir-width: 100%;
@ir-margin: auto;
```
## Mixin
```javascript
.ir(@ratio: @ir-ratio, @width: @ir-width, @margin: @ir-margin) {
	position: relative;
	margin: @margin;
	width: unit(@width, ~'%');
	height: 0;
	padding-bottom: unit(@width / @ratio, ~'%');
	> iframe, > video {
		width: 100%;
		height: 100%;
	}
}

.video-responsive { .ir(); }
```
## Custom helpers
```javascript
// Default helper class
// Can be customized or mixed in as you desire

.video-responsive-example { .ir(4/3, 50%, 10px); }
.ir-16-9 { .ir(16/9); }
.ir-4-3 { .ir(4/3); }
```
