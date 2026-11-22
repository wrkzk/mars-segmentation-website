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
Semantic image segmentation is an incredibly important task in autonomous driving in order for vehicles to differentiate between types of traversable surfaces or avoid potential obstacles. Despite its prevalence in autonomous systems on Earth, semantic segmentation is not implemented in most autonomous Martian rovers which has resulted in damage when driving on certain Martian terrain. Implementing semantic segmentation for terrain classification in rovers would allow them to make more informed navigation decisions and improve rate of success on missions. The semantic segmentation model implemented into rovers must also perform well in reduced-visibility conditions due to Mars' frequent and intense dust storms. We investigate the performance of two semantic segmentation models, U-Net and SegFormer, on segmenting images of Martian terrain in both clear and simulated reduced-visibility conditions. We find that when trained on clear images, SegFormer greatly outperforms U-Net. When trained with random dust, both models' mean weighted IoU increases, and U-Net and SegFormer perform more comparably across all dust conditions. We hypothesize that SegFormer performs better due to its enhanced ERF brought about by self-attention, but the largest factor that impacts segmentation accuracy is training with data augmentation.
</div>
