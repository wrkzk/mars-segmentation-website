+++
date = '2026-11-20T19:48:38-06:00'
draft = false
title = ''
+++
<pre class='ascii'>


                                                                    ||
                                                  __..--".          ||
                                 __..--""`._..--"" . . . .`.        ||
                         __..--"". . . . . . .`. . . . . . .`.      ||
                 __..--"". . . . .`. . . . . . .`. . . . . . .`.   //
         __..--"". . `.  . . . . . .`. . . . . . .`. . . . . . .`.//
  _..--""  . . . . . . `.  . . . . . .`. . . . . . .`. . . . . . .||
:". . . .`.  . . . . . . `.  . . . . . .`. . . . . . .`. . . . . .||`.
`:. . . . .`.  . . . . . . `.  . . . . . .`. . . . . . .`. . . . .||__>
  `:. . . . .`.  . . . . . . `.  . . . . . .`. . . . . . .`.__..-o||
    `:. . . . .`.  . . . . . . `.  . . . . . .`. . . . .`;Y"->.  ""
      `:. . . . .`.  . . . . . . `.  . . . . . .`. . . __.>.:'
        `:. . . . .`.  . . . . . . `.  . . . . __..--"" ..+"`.
   _..-._ `:. . . . .`.  . . . . . . `.__..--"" ....:::::.|   `.
 ."`` \_--" >:. . . . .`.  . . __..,-|" . ..::::::::::::::`--""-:.
' ..`\J.-  "8-`:. . .  __..--"" ...-I  \ `. `::::::::::::::::::::".
`/'\\88o. ,O \  `:.--""....:|:::'''`'\ ='. }-._'::::::::::::::::::|
8  8|PP|"(:. \-" ""`:::::::|:::.((::='/ .\""-.:_ ':::::::::::''_.'  _..
 8  8|::/ \`::Y  _____`:::::|::::.\\[ .\ "/"..* *"-. '''__..--"")\,"".-.\_
`\b d/""===\==V::.--..__`:::|:::::.|,'*."".:.. "_-.*`.""    _.-"-""\? "_=``.
\\`".`"' .: :-.::.        `:|:::.'.'*.' __..--""   `.*`:--"".-"?,  .)=""`\ \\
 `.``...''_/   ``::      _\\--.'.'*.'-""   _..-._ _..>.*;-""@_.-/-" `\.-"""-.\
   `-::--"            .-"@"}.'.'*.:)     ."\` \ \`.--'_`-'     `\. \-'-""-   `.
                     <\  _...'*.'      .' \.`\ `\ \\""         `\ `' ' .-.\   |
                     _\"" .---'        -\. `\.-"""-.\           \`|    ._)/   '
                   ."\.`-"\`.         `\. \-'-""-   `.           \\  `---"   /
                 .' \.`\ `\ \\        `\ `' ' .-.\   |            `.       _/
                 -\. `\.-"""-.\        \`|    ._)/   '              `-..--"
                `\. \-'-""-   `.        \\  `---"   /
                `\ `' ' .-.\   |         `.       _/
                 \`|    ._)/   '           `-..--"
                  \\  `---"   /
                   `.       _/
                     `-..--"
</pre>

### Abstract
<div class="abstract">
Semantic image segmentation is an incredibly important feature of autonomous driving that allows vehicles to differentiate between different traversable surfaces. However, despite its prevalence in autonomous systems on Earth, semantic segmentation is not implemented in most autonomous Martian rovers. Instead, Martian rovers use NASA’s geometry-based navigation system AutoNav, which in the past has caused them to be damaged by driving on certain Martian terrain. These damages have slowed or terminated missions, wasting time and money for NASA during their pursuit to investigate Mars. Implementing semantic segmentation for terrain classification in rovers would allow them to make more informed navigation decisions and improve the success of missions. The semantic segmentation model implemented into rovers must also perform well in reduced-visibility conditions due to Mars’ frequent and intense dust storms. We investigate the performance of U-Net and SegFormer on segmenting images of Martian terrain, classifying it into sand, soil, big rock, or bedrock, in both clear and simulated reduced-visibility conditions. We find that when trained on clear images, SegFormer greatly outperforms U-Net. When trained on images with blur and noise augmentation, both models’ mean weighted IoU increases, and U-Net and SegFormer perform comparably across clear, mild, and medium dust amounts. We argue that SegFormer performs marginally better due to efficient self-attention, but the largest factor that impacts segmentation accuracy is training with data augmentation.
</div>
