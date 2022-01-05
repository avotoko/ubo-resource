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
! update at Tue, 07 Dec 2021 10:54:22 GMT

! Disable the filter, uBlock filters: /\/\/ygosu\.com\/[A-Z]{1,}.*[a-z]{1,}.*/$image,1p,match-case, triggering the anti-adblock. 
@@||ygosu.com^$image,1p
! disable not working filter
ppss.kr,ygosu.com#@#+js(aost, XMLHttpRequest.prototype.send, /th:\d+\s+[a-zA-Z]\d\/<@[^\t]+\t\s[a-zA-Z]\d@|th:\d+\s+in[a-zA-Z\d:;]+\t\s[a-zA-Z]\d\si/)
! Terminate the script before loading alternative ads.
ppss.kr,ygosu.com##+js(avotoko-abort-on-mutation, Promise, /attr IMG\.\S+ src old:data:\S+ new:https:(?!.*?loading(_m)?\.gif$).*$|add DIV#ad-unit/)
! To output the mutation log, append ',,log:1' to the end.
! ppss.kr,ygosu.com##+js(avotoko-abort-on-mutation, Promise, /attr IMG\.\S+ src old:data:\S+ new:https:(?!.*?loading(_m)?\.gif$).*$|add DIV#ad-unit/,,log:1)
! Hide ads.
ppss.kr###custom_html-2

! Hide alternative ads.
ad-shield.io##+js(avotoko-no-shadow-root)

! https://github.com/uBlockOrigin/uAssets/issues/8489
! https://forum.release-apk.com/viewtopic.php?t=132895
! Update at Wed, 05 Jan 2022 03:18:51 GMT
! Block handlers that might overload the cpu.
forum.release-apk.com##+js(acis, jQuery, 'load')
! hide ad space.
forum.release-apk.com##ins[class^="adsbygoogle"]:not([class$="adsbygoogle-noablate"])
forum.release-apk.com##.google-auto-placed
! bypass iframe checking
forum.release-apk.com##+js(avotoko-fake-queryselector-argument, document, querySelectorAll, ins[class^="adsbygoogle"]:not([class$="adsbygoogle-noablate"]) iframe[src^="https://googleads.g.doubleclick.net/pagead/ads"], #wrap, /^.+view(forum|topic).php\?[ft]=\d+(&.+)?:\d{3}:\d+/,debug:1,log:1,st:10)
forum.release-apk.com##+js(avotoko-fake-element-property, #wrap, name:"wrap", dataset:{"loadComplete":"true"})
! bypass other checking
forum.release-apk.com##+js(avotoko-fake-computed-style, ins[class^="adsbygoogle"]:not([class$="adsbygoogle-noablate"])\, div[class^="phpbb-ads-center"], , display:block; height:200px; width:200px, /view(forum|topic).php\?[ft]=\d+(&.+)?:\d{3}:\d+/)
! increase display speed
forum.release-apk.com##+js(avotoko-fake-gettime-speed, 1000, /^.+view(forum|topic).php\?[ft]=\d+(&.+)?:\d{3}:\d+/)
! July 10 2021 The site has implemented a new anti-adblock. And others.
! Prevent new anti-adblock script from loading
||forum.release-apk.com/ext/*.php?$script,1p
! bypass checking
forum.release-apk.com##+js(avotoko-fake-computed-style, .adsbygoogle, , display:block, /view(forum|topic).php\?[ft]=\d+(&.+)?:\d{3}:\d+/)
forum.release-apk.com##+js(avotoko-fake-element-property, ins[class^="adsbygoogle"]:not([class$="adsbygoogle-noablate"]), dataset:{"adsbygoogleStatus":"done"}, , /^.+view(forum|topic).php\?[ft]=\d+(&.+)?:\d{3}:\d+/)

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
