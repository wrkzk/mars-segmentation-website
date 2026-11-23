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
Semantic image segmentation is an important task in autonomous driving, allowing vehicles to differentiate between types of traversable surfaces or avoid potential obstacles. Most autonomous Martian rovers do not use semantic segmentation, a gap that has contributed to rover damage on certain Martian terrain. Implementing semantic segmentation for terrain classification in rovers would allow them to make more informed navigation decisions and improve mission success rates. Any segmentation model deployed on a rover must also perform well in reduced-visibility conditions due to Mars' frequent and intense dust storms. We compare two semantic segmentation models, U-Net and SegFormer, on images of Martian terrain under both clear and simulated dusty conditions. We find that when trained on clear images, SegFormer greatly outperforms U-Net. When trained with random dust, the mean weighted IoU of both models increases, and U-Net and SegFormer perform more comparably across all dust conditions. We hypothesize that SegFormer's advantage stems from the larger effective receptive field (ERF) provided by self-attention. However, training with data augmentation has the largest effect on segmentation accuracy.
</div>
