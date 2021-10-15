# Realistic Subaru Impreza WRX STI (2004) handling

This is my attempt at a realistic handling for the Subaru Impreza WRX STI (2004).

## Engine

EJ20, Turbocharged

### RPM Data

IdleRPM = 750
RevLimitRPM = 6700

### Performance

EJ20 NA

* Data from https://en.wikipedia.org/wiki/Subaru_EJ_engine#Naturally_aspirated
* ~140 kW (2003-2009 190 PS (140 kW; 187 hp)) -> No torque numbers
* Torque deduced from EJ22: 100 kW, 202 N-m, so at 140 kW it should make like 280 N-m
* fDriveForce = 280/1480 -> 0.189, but round up to 0.190 for fun

Gearbox: https://en.wikipedia.org/wiki/List_of_Subaru_transmissions#Six-speed_2

* 1st 3.636
* 2nd 2.375
* 3rd 1.761
* 4th 1.346
* 5th 0.971
* 6th 0.756
* Rev 3.545

Final torque/horsepower:

* (https://www.edmunds.com/subaru/impreza/2004/wrx-sti/features-specs/)
* 195 kW or 265 PS or 261 HP @ 6000 RPM
* 253 lb-ft or 343 Nm @ 4000 RPM

Turbofix to achieve that:

343/280 -> 1.225x -> 2.25

Top speed:

145 mph (limited) (233 kph)

Actual, using https://www.blocklayer.com/rpm-gear.aspx:

* RPM: 6700
* Gear: 6th (0.756)
* Tire diameter: 635mm (https://tiresize.com/tires/Subaru/Impreza/2004/WRX-STI/)
* Diff ratio: 3.900
* Result: 272 kph -> Final drive @ 1.0 gear ratio: 57.12 m/s
* fInitialDriveMaxFlatVel -> 272 * 0.75 = 204

Center diff (default?) DCCD: 35/65 (transitions to 50/50)

Torque curve:

http://australiancar.reviews/_subaru/reviews/subaru_ej204_engine_ser1_02.jpg

http://australiancar.reviews/Subaru_EJ204_Engine.php

(Mapped with https://apps.automeris.io/wpd/)

```csv
RPM,        RpmMapped, TorqueNm,  TorqueMapped
1634.92063, 0.244,     158.08314, 0.846
1912.69841, 0.285,     163.27945, 0.873
2047.61905, 0.305,     165.35797, 0.885
2214.28571, 0.330,     166.91686, 0.893
2357.14286, 0.351,     168.99538, 0.904
2492.06349, 0.371,     171.76674, 0.919
2595.23810, 0.387,     174.88453, 0.936
2706.34921, 0.403,     178.34873, 0.954
2825.39683, 0.421,     181.46651, 0.971
2984.12698, 0.445,     184.06467, 0.985
3126.98413, 0.466,     186.14319, 0.996
3269.84127, 0.488,     186.83603, 1.000
3444.44444, 0.514,     186.31640, 0.997
3619.04762, 0.540,     185.62356, 0.993
3793.65079, 0.566,     185.62356, 0.993
3968.25397, 0.592,     185.62356, 0.993
4142.85714, 0.618,     185.45035, 0.992
4301.58730, 0.642,     184.58430, 0.987
4492.06349, 0.670,     184.75751, 0.988
4658.73016, 0.695,     185.62356, 0.993
4777.77778, 0.713,     185.96998, 0.995
4912.69841, 0.733,     185.10393, 0.990
5055.55556, 0.754,     183.54503, 0.982
5190.47619, 0.774,     182.15935, 0.974
5357.14286, 0.799,     181.81293, 0.973
5500.00000, 0.820,     181.98614, 0.974
5634.92063, 0.841,     181.98614, 0.974
5841.26984, 0.871,     181.98614, 0.974
6015.87302, 0.897,     181.29330, 0.970
6190.47619, 0.923,     179.90762, 0.962
6301.58730, 0.940,     178.52194, 0.955
6396.82540, 0.954,     175.40416, 0.938
6523.80952, 0.973,     172.28637, 0.922
6603.17460, 0.985,     170.20785, 0.911
6682.53968, 0.997,     168.12933, 0.899
6746.03175, 1.006,     165.70439, 0.886
6841.26984, 1.021,     163.10624, 0.872
6952.38095, 1.037,     160.50808, 0.859
7047.61905, 1.051,     158.25635, 0.847
7150.79365, 1.067,     155.83141, 0.834
```

## Installation

Required:

* [2004 Subaru Impreza WRX STI by AlperB](https://www.gta5-mods.com/vehicles/subaru-impreza-wrx-sti-2004-add-on-tuning)
* [Manual Transmission](https://www.gta5-mods.com/scripts/manual-transmission-ikt)
* [Handling Replacement Library](https://www.gta5-mods.com/tools/handling-replacement-library)
* [TurboFix](https://www.gta5-mods.com/scripts/turbofix-2)
* [Custom Gear Ratios](https://www.gta5-mods.com/scripts/custom-gear-ratios)
* [Custom Torque Map](https://www.gta5-mods.com/scripts/custom-gear-map)

Optional:

* [Dial Accuracy Fix](https://www.gta5-mods.com/scripts/dial-accuracy-fix)
* [InversePower](https://www.gta5-mods.com/scripts/inversepower)

Installation steps:

* Install all required items (and optional items)
* Replace the handling file
* Extract the other configuration files to the game folder
  * Drag and drop everything except this readme in the main GTA V folder, the files end up in the correct location

## Changelog

1.0 - Initial release
