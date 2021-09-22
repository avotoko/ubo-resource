# uBOXSR: uBlock Origin Experimental Scriptlets Resource
uBlock Origin scriptlets for anti anti-adblock  
Tested with firefox and chrome on Windows.

## Installation
Add uBOXSR URL to end of 'userResourcesLocation' in 'advanced settings'  
e.g. `userResourcesLocation unset https://raw.githubusercontent.com/avotoko/ubo-resource/main/avotoko-ubo-resource.txt`
## Usage
#### examples
```
! https://www.reddit.com/r/uBlockOrigin/comments/p29y3w/these_guys_boast_combatting_all_adblocks/
! https://github.com/uBlockOrigin/uAssets/issues/9754
! https://github.com/AdguardTeam/AdguardFilters/issues/90634
! https://github.com/AdguardTeam/AdGuardExtra/issues/236
! https://ad-shield.io/en/
! https://ygosu.com/
! https://ppss.kr/
! Sep. 17 2021 update

! uBlock filters is working.
! Hide alternative ads.
! ygosu.com##+js(avotoko-no-shadow-root)
! Protect avotoko-no-shadow-root
! ygosu.com##+js(avotoko-fom, Element.prototype.attachShadow.toString, "function attachShadow(){ [native code] }")

! Hide ads.
ppss.kr###custom_html-2
! uBlock filters is working.
! Hide alternative ads.
! ppss.kr##+js(avotoko-no-shadow-root)
! Protect avotoko-no-shadow-root
! ppss.kr##+js(avotoko-fom, Element.prototype.attachShadow.toString, "function attachShadow(){ [native code] }")

! Hide alternative ads.
ad-shield.io##+js(avotoko-no-shadow-root)
! Protect avotoko-no-shadow-root
ad-shield.io##+js(avotoko-fom, Element.prototype.attachShadow.toString, "function attachShadow(){ [native code] }")

! https://github.com/uBlockOrigin/uAssets/issues/8489
! https://forum.release-apk.com/viewforum.php?f=41
! Aug. 20 2021 update
! Block handlers that might overload the cpu.
forum.release-apk.com##+js(acis, jQuery, 'load')
! hide ad space
forum.release-apk.com##ins[class^="adsbygoogle"]:not([class$="adsbygoogle-noablate"])
forum.release-apk.com##.google-auto-placed
! bypass iframe checking
forum.release-apk.com##+js(avotoko-fake-queryselector-argument, document, querySelectorAll, ins[class^="adsbygoogle"]:not([class$="adsbygoogle-noablate"]) iframe[src^="https://googleads.g.doubleclick.net/pagead/ads"], #wrap, /^.+view(forum|topic).php\?f=\d+(&.+)?:\d{3}:\d+/)
forum.release-apk.com##+js(avotoko-fake-element-property, #wrap, name:"wrap", dataset:{"loadComplete":"true"})
! bypass other checking
forum.release-apk.com##+js(avotoko-fake-computed-style, ins[class^="adsbygoogle"]:not([class$="adsbygoogle-noablate"])\, div[class^="phpbb-ads-center"], , display:block; height:200px; width:200px, /view(forum|topic).php\?f=\d+(&.+)?:\d{3}:\d+/)
! increase display speed
forum.release-apk.com##+js(avotoko-fake-gettime-speed, 1000, /^.+view(forum|topic).php\?f=\d+(&.+)?:\d{3}:\d+/)
! July 10 2021 The site has implemented a new anti-adblock. And others.
! Prevent new anti-adblock script from loading
||forum.release-apk.com/ext/*.php?$script,1p
! bypass checking
forum.release-apk.com##+js(avotoko-fake-computed-style, .adsbygoogle, , display:block, /view(forum|topic).php\?f=\d+(&.+)?:\d{3}:\d+/)
forum.release-apk.com##+js(avotoko-fake-element-property, ins[class^="adsbygoogle"]:not([class$="adsbygoogle-noablate"]), dataset:{"adsbygoogleStatus":"done"}, , /^.+view(forum|topic).php\?f=\d+(&.+)?:\d{3}:\d+/)

! https://github.com/uBlockOrigin/uAssets/issues/8769
! https://dropgalaxy.in/d9pk321i9crb
! Sep 22 2021
! The site has changed the way it detects adblock. 'uBlock filters' will be fixed soon.

! https://www.reddit.com/r/uBlockOrigin/comments/n71ene/this_website_can_detect_that_i_am_using/
! https://thehouseofportable.com/download/?id=351&k=6
! June 7 2021 update
! Bypass the anti-adblock.
thehouseofportable.com##+js(avotoko-fake-promise, resolve, false, 'on/favicon')
! Increase the speed of generating links.
thehouseofportable.com##+js(avotoko-fake-object-property, setTimeout, hasOwnProperty: false)
thehouseofportable.com##+js(avotoko-fake-object-property, setTimeout, toString: "function(){[native code]}")
thehouseofportable.com##+js(nano-stb,, 1000)
thehouseofportable.com##+js(nano-stb,, 2000)
thehouseofportable.com##+js(nano-stb,, 3000)
thehouseofportable.com##+js(nano-stb,, 4000)
thehouseofportable.com##+js(nano-stb,, 5000)
thehouseofportable.com##+js(nano-stb,, 6000)

! https://github.com/uBlockOrigin/uAssets/issues/7320
! https://www.joysound.com/web/search/song/746956
! May 19 2021
joysound.com##body:style(-moz-user-select:text!important; -webkit-user-select:text!important; user-select:text!important)
joysound.com##+js(avotoko-on-handler-defuser, body, copy|selectstart|contextmenu)
```
