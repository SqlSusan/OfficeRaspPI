# Raspberry Pi Zero Client
## Hardware setup
Fearful of not having enough RAM, I opted for the 8GB model of the pi. As it turns out, Citrix rarely spikes above 550MB of memory so the 4GB model would have been enough! Oh well.

Anyway, here are all the components for a mountable zero client for Citrix (from <a href>https://thepihut.com/</a>):
Component | SKU | Cost
--- | --- | ---
<a href="https://thepihut.com/products/raspberry-pi-4-case-with-cooling-fan">Raspberry Pi 4 Case (With Cooling Fan) (v3.0)</a> | SKU: TPH-001-GRY | £10
<a href="https://thepihut.com/products/vesa-mounting-plate-for-the-pi-hut-cases">VESA Mounting plate for The Pi Hut Cases1</a> | SKU: TPH-055 | £2.50
<a href="https://thepihut.com/products/usb-c-cable-with-switch">USB-C Cable with On/Off Switch</a> | SKU: 102509 | £3
<a href="https://thepihut.com/products/raspberry-pi-psu-uk">Official UK Raspberry Pi 4 Power Supply (5.1V 3A)</a> | SKU: SC0216 | £8
<a href="https://thepihut.com/products/raspberry-pi-4-model-b">Raspberry Pi 4 Model B (4GB or 8GB)</a> | SKU: SC0195 | £54\£74
<a href="https://thepihut.com/products/micro-hdmi-to-standard-hdmi-a-cable">Official Raspberry Pi 4 MicroHDMI Cable (1M)</a> | SKU: SC0270 | £10

I found the fan with the pi just slightly noisy, so opted to buy a non-pi branded fan (this needs some manual adjustments, I'd recommend not doing this):

<a href="https://www.amazon.co.uk/dp/B00NEMGCIA/ref=cm_sw_em_r_mt_dp_64RtFbTEEVBVS">Noctua NF-A4x10 5V, Premium Quiet Fan, 3-Pin, 5V Version (40x10mm, Brown)</a>

Seemed like a great idea, the fan turned up in lovely packaging, loads of different connectors. But, the Raspberry pi case is really small, and the cable supplied with the fan is really long. Years of playing snake wouldn't help here. 

The fan just fits over the top of the inside row GPIO pins. To mount it to the case, you will need to drill 5mm holes (I'd recommend creating a template to do this).

To adjust the cable length, you will need to cut it! Before doing so, make sure you have these components ready to create a new jumper:

<a href="https://www.amazon.co.uk/dp/B07L9X221F/ref=cm_sw_em_r_mt_dp_08RtFb1Q014G9">CAMWAY 50PCS Heat Shrink Solder Sleeves Electrical Wire Butt Terminals Non Crimp Wire Splice Connectors 26-24 AWG</a>

<a href="https://www.amazon.co.uk/dp/B00Q2GQXAC/ref=cm_sw_em_r_mt_dp_idStFb7QEAQVS">3pcs 20cm Multicolored 40-pin Male to Female /Male to Male /Female to Female Breadboard Jumper Wires Ribbon Cables by Celelin</a>

Leave about 4cm of cable after the fan, then carefully bare the wire ends (tucking back the yellow ground wire as that isn't required)). Snip one of the female breadboard cables with about 3cm of cable, bare the end, then use the heat shrink solder sleeve to join the two together (I just used a tealight candle to melt it). Do this for the red and black wire, then connect to your pi!

