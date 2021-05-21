# uBOXSR: uBlock Origin Experimental Scriptlets Resource
uBlock Origin scriptlets for anti anti-adblock  
Tested with firefox and chrome on Windows.

## Installation
Add uBOXSR URL to end of 'userResourcesLocation' in 'advanced settings'  
e.g. `userResourcesLocation unset https://raw.githubusercontent.com/avotoko/ubo-resource/main/avotoko-ubo-resource.txt`
## Usage
#### examples
```
! https://github.com/uBlockOrigin/uAssets/issues/8769
! https://dropgalaxy.in/fkqlb29nxfdk
! May 21 2021
!#if env_firefox
techssting.com##+js(avotoko-fake-element-property, .adsbygoogle, outerHTML:"<ins class=\"adsbygoogle adsbygoogle-noablate\" style=\"display: none !important;\" data-adsbygoogle-status=\"done\" data-ad-status=\"unfilled\"><ins id=\"aswift_0_expand\" style=\"display:inline-table;border:none;height:0px;margin:0;padding:0;position:relative;visibility:visible;width:0px;background-color:transparent;\" tabindex=\"0\" title=\"Advertisement\" aria-label=\"Advertisement\"><ins id=\"aswift_0_anchor\" style=\"display:block;border:none;height:0px;margin:0;padding:0;position:relative;visibility:visible;width:0px;background-color:transparent;\"><iframe id=\"aswift_0\" name=\"aswift_0\" style=\"left:0;position:absolute;top:0;border:0;width:undefinedpx;height:undefinedpx;\" sandbox=\"allow-forms allow-popups allow-popups-to-escape-sandbox allow-same-origin allow-scripts allow-top-navigation-by-user-activation\" src=\"https://googleads.g.doubleclick.net/pagead/ads?client=ca-pub-9528158350237228&amp;output=html&amp;adk=3333&amp;adf=3333&amp;lmt=3333&amp;plat=%3A%3A&amp;format=0x0&amp;url=https%3A%2F%2Ftechssting.com%2F&amp;ea=0&amp;flash=0&amp;pra=5&amp;wgl=1&amp;dt=33&amp;bpp=3&amp;bdt=3333&amp;idt=33&amp;shv=r333&amp;cbv=%2Fr333&amp;ptt=8&amp;saldr=bb&amp;abxe=0&amp;cookie=ID%3D3333&amp;nras=0&amp;correlator=3333&amp;frm=30&amp;pv=3&amp;ga_vid=3.3&amp;ga_sid=333&amp;ga_hid=333&amp;ga_fc=3&amp;u_tz=333&amp;u_his=33&amp;u_java=3&amp;u_h=33&amp;u_w=33&amp;u_ah=33&amp;u_aw=333&amp;u_cd=33&amp;u_nplug=3&amp;u_nmime=3&amp;adx=-333&amp;ady=-333&amp;biw=33&amp;bih=33&amp;scr_x=3&amp;scr_y=3&amp;oid=3&amp;pvsid=3333&amp;pem=33&amp;ref=https%3A%2F%2Fwww.google.com%2F&amp;eae=2&amp;fc=1333&amp;brdim=333%2C&amp;vis=1&amp;rsz=3%7C%7C&amp;abl=NS&amp;fu=33&amp;bc=33&amp;ifi=3&amp;uci=a!3&amp;fsb=3&amp;dtd=333\" marginwidth=\"0\" marginheight=\"0\" vspace=\"0\" hspace=\"0\" allowtransparency=\"true\" scrolling=\"no\" allowfullscreen=\"true\" data-google-container-id=\"a!1\" data-load-complete=\"true\" frameborder=\"0\"></iframe></ins></ins></ins>", , dd<@https://techssting.com, debug:1, log:1, st:30)
||tpc.googlesyndication.com/sodar/sodar2.js$script,domain=techssting.com,important
||pagead2.googlesyndication.com/getconfig/sodar$xhr,domain=techssting.com,important
||pagead2.googlesyndication.com/pagead/js/r20210517/r20190131/show_ads_impl_fy2019.js$script,domain=techssting.com,important
!#endif

! https://www.reddit.com/r/uBlockOrigin/comments/n71ene/this_website_can_detect_that_i_am_using/
! https://thehouseofportable.com/download/?id=351&k=6
! May 19 2021
thehouseofportable.com##+js(avotoko-fake-promise, resolve, false, 'on/favicon')

! https://github.com/uBlockOrigin/uAssets/issues/7320
! https://www.joysound.com/web/search/song/746956
! May 19 2021
joysound.com##body:style(-moz-user-select:text!important; -webkit-user-select:text!important; user-select:text!important)
joysound.com##+js(avotoko-on-handler-defuser, body, copy|selectstart|contextmenu)
```
