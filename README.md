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
! uBO built-in filters works at Mon, 18 Apr 2022 09:10:14 GMT

! Prevent ad-shield loading alternative ads.
! maple.inven.co.kr,ppss.kr,ygosu.com##+js(avotoko-abort-on-mutation, Promise, /attr IMG\.\S+ src old:data:\S+ new:https:(?!.*?loading(_m)?\.gif$).*$/)
! Prevent ad-shield unloading content images.
! maple.inven.co.kr,ppss.kr,ygosu.com##+js(avotoko-abort-on-mutation, Element.prototype.removeAttribute, /attr IMG\.\S+ src old:data:\S+ new:https:(?!.*?loading(_m)?\.gif$).*$/)
! To output the mutation log, append ',,log:1' to the end.
! ppss.kr,ygosu.com##+js(avotoko-abort-on-mutation, Promise, /attr IMG\.\S+ src old:data:\S+ new:https:(?!.*?loading(_m)?\.gif$).*$/,,log:1)

! https://github.com/uBlockOrigin/uAssets/issues/8489
! https://github.com/uBlockOrigin/uAssets/issues/14426
! Update at Wed, 02 Aug 2023 08:22:48 GMT
! Currently uBO's native scriptlets can solve the issue.
! block ad network
||adskeeper.com^$script,domain=forum.release-apk.com
! Hide top ad placeholder.
forum.release-apk.com##div[data-phpbb-ads-id]
! Disable ad display status judgment code.
forum.release-apk.com##+js(rpnt, script, /\(\n\s+(.|\n)+?\n\s+\)/, true)
! Disable brute-force time elapsed wait functions.
forum.release-apk.com##+js(rpnt, script, /\b\w{10}\(\d{4}\)/, true)

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
