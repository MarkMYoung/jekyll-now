---
layout: post
title: Adding Animations to Angular Unobtrusively
---

Add Angular's animate module to the page and bring an animation library like [animate.css](https://github.com/daneden/animate.css).
```html
<link rel="stylesheet" type="text/css" href="https://cdnjs.cloudflare.com/ajax/libs/animate.css/3.5.2/animate.min.css"/>
<script type="text/javascript" src="https://ajax.googleapis.com/ajax/libs/angularjs/1.6.4/angular.min.js"></script>
<script type="text/javascript" src="https://ajax.googleapis.com/ajax/libs/angularjs/1.6.4/angular-animate.min.js"></script>
```

Reference the module in your project.
```javascript
angular.module( 'NameOfTheApp.appMod',
[
	'ngAnimate',
	...
```

Tie Angular animatable "events" to CSS animations (in a file mabye named `angular-animate.css`).
```css
/* Angular animation classes using animations from 'animate.css'.
*	@see https://github.com/daneden/animate.css
*	@see https://daneden.github.io/animate.css/
*	@see https://docs.angularjs.org/guide/animations
*
* Notes:
*	To prevent flicker, consider using '.ng-enter-prepare' (or '.ng-leave-prepare' or '.ng-move-prepare').
*/
/*=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=*/
.enterLeave-fadeIn-fadeOut
{animation-duration:1s;}
.enterLeave-fadeIn-fadeOut.ng-enter
{animation-name:fadeIn;}
.enterLeave-fadeIn-fadeOut.ng-leave
{animation-name:fadeOut;}
/*=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=*/
.enterLeave-slideInLeft-slideOutRight
{animation-duration:1s;}
.enterLeave-slideInLeft-slideOutRight.ng-enter
{animation-name:slideInLeft;}
.enterLeave-slideInLeft-slideOutRight.ng-leave
{animation-name:slideOutRight;}
/*=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=*/
```

Reference the animation in your view.
```html
<li data-ng-repeat="..." class="enterLeave-fadeIn-fadeOut">...
```
