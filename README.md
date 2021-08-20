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
! Aug. 20 2021 update

! Hide ad.
ad-shield.io###demo_button ~ *
! Fakes elements that are hidden as visible.
ad-shield.io##+js(avotoko-fake-computed-style, #demo_button ~ *, , display:block)
! block tracking
||ad-shield.io^$xhr,1p

! hide ads.
ygosu.com###left_nav, #right_nav, .main_preview + div
! Fakes elements that are hidden as visible.
ygosu.com##+js(avotoko-fake-computed-style, #left_nav\, #right_nav\, .main_preview + div, , display:block)
! block tracking
||ygosu.com^$xhr,1p
@@||ygosu.com/*/$xhr,1p

! Ad-Shield is running but not working properly.
ppss.kr###custom_html-2
! block tracking
||ppss.kr^$xhr,1p

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
! https://dropgalaxy.in/fkqlb29nxfdk
! May 21 2021
!#if env_firefox
techssting.com##+js(avotoko-fake-element-property, .adsbygoogle, outerHTML:"<ins class=\"adsbygoogle adsbygoogle-noablate\" style=\"display: none !important;\" data-adsbygoogle-status=\"done\" data-ad-status=\"unfilled\"><ins id=\"aswift_0_expand\" style=\"display:inline-table;border:none;height:0px;margin:0;padding:0;position:relative;visibility:visible;width:0px;background-color:transparent;\" tabindex=\"0\" title=\"Advertisement\" aria-label=\"Advertisement\"><ins id=\"aswift_0_anchor\" style=\"display:block;border:none;height:0px;margin:0;padding:0;position:relative;visibility:visible;width:0px;background-color:transparent;\"><iframe id=\"aswift_0\" name=\"aswift_0\" style=\"left:0;position:absolute;top:0;border:0;width:undefinedpx;height:undefinedpx;\" sandbox=\"allow-forms allow-popups allow-popups-to-escape-sandbox allow-same-origin allow-scripts allow-top-navigation-by-user-activation\" src=\"https://googleads.g.doubleclick.net/pagead/ads?client=ca-pub-9528158350237228&amp;output=html&amp;adk=3333&amp;adf=3333&amp;lmt=3333&amp;plat=%3A%3A&amp;format=0x0&amp;url=https%3A%2F%2Ftechssting.com%2F&amp;ea=0&amp;flash=0&amp;pra=5&amp;wgl=1&amp;dt=33&amp;bpp=3&amp;bdt=3333&amp;idt=33&amp;shv=r333&amp;cbv=%2Fr333&amp;ptt=8&amp;saldr=bb&amp;abxe=0&amp;cookie=ID%3D3333&amp;nras=0&amp;correlator=3333&amp;frm=30&amp;pv=3&amp;ga_vid=3.3&amp;ga_sid=333&amp;ga_hid=333&amp;ga_fc=3&amp;u_tz=333&amp;u_his=33&amp;u_java=3&amp;u_h=33&amp;u_w=33&amp;u_ah=33&amp;u_aw=333&amp;u_cd=33&amp;u_nplug=3&amp;u_nmime=3&amp;adx=-333&amp;ady=-333&amp;biw=33&amp;bih=33&amp;scr_x=3&amp;scr_y=3&amp;oid=3&amp;pvsid=3333&amp;pem=33&amp;ref=https%3A%2F%2Fwww.google.com%2F&amp;eae=2&amp;fc=1333&amp;brdim=333%2C&amp;vis=1&amp;rsz=3%7C%7C&amp;abl=NS&amp;fu=33&amp;bc=33&amp;ifi=3&amp;uci=a!3&amp;fsb=3&amp;dtd=333\" marginwidth=\"0\" marginheight=\"0\" vspace=\"0\" hspace=\"0\" allowtransparency=\"true\" scrolling=\"no\" allowfullscreen=\"true\" data-google-container-id=\"a!1\" data-load-complete=\"true\" frameborder=\"0\"></iframe></ins></ins></ins>", , dd<@https://techssting.com)
||tpc.googlesyndication.com/sodar/sodar2.js$script,domain=techssting.com,important
||pagead2.googlesyndication.com/getconfig/sodar$xhr,domain=techssting.com,important
||pagead2.googlesyndication.com/pagead/js/r20210517/r20190131/show_ads_impl_fy2019.js$script,domain=techssting.com,important
!#endif

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
