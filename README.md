# 18v18vBatteryAdapter
This is info page for all 18v to 18v output battery adapters, last updated 01-31-2025<br>
Available at https://github.com/JPElectron/18v18vBatteryAdapter<br>
<br>
Scroll down to find which adapter is go or no-go based on which tool you plan to use it in.<br>
<br>
**Note:** Adapters dropped on hard concrete floors will break!  These are [available for sale](https://www.etsy.com/shop/JPElectron) assembled and tested.<br>
<br>
All adapters have been tested, in a variety of tools, but assessing the age or condition or temperature of every battery pack is unreasonable, as such you assume any/all risks of fire or equipment or property damage, regardless of how or where you use any of these adapters.  See additional safety information section below.<br>
<br>
If you want to know why other brands of batteries should NOT be used with Ryobi tools, nor in Power Wheels kids ride-on toys, scroll to the bottom of this page!<br>
<br>
For 18v to 40v battery adapters see: https://github.com/JPElectron/18v40vBatteryAdapter

<br>
<hr style="border: 1px; height: 1px; background: #AAAAAA;">

Begining in May 2024, some assemblies that were previously hard-wired together are now shipped with a [Anderson PowerPole connector](https://powerwerx.com/anderson-power-powerpole-sb-connectors#?specs=304,305,306) and connecting cable.  This facilitates quicker build up of on-hand inventory so only the custom length connecting cable needs to be built on demand.

The dual adapters look similar, but you should only use the 18v output version with 18v tools, and the 40v output version with 40v tools...

![How to ID dual battery adapter output voltage](https://github.com/JPElectron/18v40vBatteryAdapter/blob/main/How%20to%20ID%20dual%20battery%20adapter%20output%20voltage.jpg?raw=true)

Circuit diagram...

![Circuit diagram](https://github.com/JPElectron/18v40vBatteryAdapter/blob/main/circuit.png?raw=true)

<br>
<br>

<hr style="border: 1px; height: 1px; background: #AAAAAA;">

Confirmed **DO NOT USE** any adapter in....

   - RYi1802BT or RYi1802B6 or RYi818BT or RYi818BG 1800-Watt Portable Battery Power Station Inverter Generator
   ...because it cannot communicate with the battery pack extra data/temperature pins, it does not recognize the battery at all
   ...you can only put a single genuine battery in a slot

   - P2507 Chainsaw 12"
   ...because it draws too much amperage resulting in melted contacts

   - PBLSV717 or PWV200 Vacuum (very possibly any vacuum)
   ...because these draw close to 13 amps, if two or less batteries are left carrying the entire load this is close to the diode's limit resulting in melted contacts

Custom solutions for high-amperage loads are available, inquire via [Etsy](https://www.etsy.com/shop/JPElectron).  By using external diode combiners with a heat sink, thereby moving the diodes and heat away from the battery terminals, and fixing battery terminals in place with [J-B Weld High Heat Epoxy](https://www.amazon.com/J-B-Weld-High-Epoxy-Syringe/dp/B09Q8DQLJ2), is effective to keep the 3D printing material as PETG.

<br>
<br>

<hr style="border: 1px; height: 1px; background: #AAAAAA;">

18v adapters can be paralleled, which adds additional runtime, using any of these splitters...<br>
<br>
   - https://www.amazon.com/dp/B0CFL1VK99 (2, 3)
   - https://www.amazon.com/dp/B0D7ZFX85V (2, 3, 4)
   - https://www.amazon.com/dp/B07R56HCSN (5)

Additional diode isolation is not required since each 18v adapter already contains a diode for each battery.<br>
DO NOT mix 18v output and 40v output adapters, these can NOT be paralleled.<br>
Paralelling batteries of different Ah ratings has not been tested and is not recomended, lower Ah rated batteries will drain before the others.<br>
Paralelling more than 12 (twelve) 18v batteries has not been tested and is not recomended.

<br>
<br>

<hr style="border: 1px; height: 1px; background: #AAAAAA;">

18v tool amperage draw examples...<br>
<br>
   - P755 Blower 14.75A / 6.40A / 4.20A<br>
   - PCL661 Floodlight 1.64A / 0.80A / 0.43A<br>
   - PCLCW01 Small Chainsaw 10A<br>
   - Dual train horn 21A<br>

<br>
<br>

<hr style="border: 1px; height: 1px; background: #AAAAAA;">

More information on 18v batteries is available from toolboy's excellent site: [https://toolboyworld.com/eBay/Ryobi_Batteries.htm](https://toolboyworld.com/eBay/Ryobi_Batteries.htm)

<br>
<br>

<hr style="border: 1px; height: 1px; background: #AAAAAA;">

Safety reminder...

Never try to charge two Ryobi Li-Ion batteries in series or parallel (this means no putting any dual adapter in a 18v or 40v charger) as damage to the internal Battery Management System (BMS) or the charger is possible. The charger cannot communicate with the battery pack extra pins to get temperature or charge current, without this info the charger may assume the wrong data and create a fire hazard, so always charge batteries individually and in approved chargers.  Genuine Ryobi chargers appear to do the right thing and not even attempt to charge, but 3rd party/aftermarket chargers may not be as smart.

I admit I am overly paranoid about charging Lithium-ion batteries: I only charge when I am at home, I only charge within the house (a temperature controlled environment) and never a garage or shed (subject to extreme heat or cold). I have the charger plugged into a z-wave smart outlet with the following logic via HomeSeer software and some custom scripts: If I ever leave (my phone un-associates from the house WiFi) the z-wave outlet will turn off power to the charger, A smoke detector is positioned directly above the charger, If the smoke detector goes into alarm then the z-wave outlet will turn off power to the charger. You too should strongly consider that charging unattended or in extreme temperatures is unnecessary risk, stay safe out there.

<br>
<br>

<hr style="border: 1px; height: 1px; background: #AAAAAA;">

Why can't I use other brands of batteries in Ryobi tools or in Power Wheels kids ride-on toys?

Due to the additional complexity and cost of having to include a LVD (low-voltage disconnect) circuit, I will not offer adapters that use other Li-Ion batteries. A full technical explanation is below if your interested...

Although TTI is the parent company of Hart, Milwaukee, and Ryobi, (also there is Ridgid, which TTI licenses from Emerson, but does not own outright) only the Ryobi brand of batteries contain a BMS (Battery Management System) which provides BOTH cell balancing and LVD (low-voltage disconnect) functions. LVD is important because if any cell in the pack goes below a certain voltage, that cell is permanently damaged and the pack will never charge again, this is true of all battery packs that contain Li-Ion cells. In the case of Ryobi tools, the tool has no LVD circuitry, and will keep taking power from the battery as long as you hold the trigger down, rather the LVD protection is in the Ryobi battery itself. So for all of the Ryobi 18v and 40v product lines, the battery is what cuts off power when the voltage gets lower than the point of no return. The tool is more or less "dumb" and will always draw power. In the case of connecting some other battery, a Ryobi tool can and will keep draining that battery past point of no return and damage it. Alternatively most other brands (Hart, DeWalt, and Milwaukee included) have the LVD disconnect in the tool, and no such protection in the battery pack itself.

For this same reason, non-Ryobi battery packs CANNOT be run in series or parallel, because additional custom circuitry would be required to gage which cells are approaching the LVD voltage.

For this same reason, non-Ryobi battery packs should NOT be used in Power Wheels kids ride-on toys, the pack will be run down past the point of no return.

<br>
<br>

<hr style="border: 1px; height: 1px; background: #AAAAAA;">

[END]
