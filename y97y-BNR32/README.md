# Realistic Nissan Skyline R32 GT-R handling

This is my attempt at a realistic handling for the Skyline R32 GT-R.

## Performance details and methodology

Basic numbers:
0-100 km/h: ~5.2 seconds
0-150 km/h: ~11.5 seconds
0-200 km/h: ~22 seconds
Top speed: 250-ish kph (power/drag-limited, 5th gear allows up to 290 kph)

Methodology and data sources:
- Base handling is Aquaphobics' GT-R R32 handling
- Acceleration times and gear ratios based on: https://www.automobile-catalog.com/car/1994/2135600/nissan_skyline_gt-r_v-spec_ii.html
- Turbo boost based on non-turbo RB26 and RB26DETT performance difference, turbo adds about 13.5% more power: 
    RB26DE (non-turbo) -> fInitialDriveForce = 0.1875
        Power: 220 PS -> 161 kW @ 6600rpm
        Torque: 25.0 kgm (245 Nm) at 5200rpm
        Source: R33_GTS-t in https://www.gtr.co.uk/threads/naturally-aspirated-rb26.52387/
        https://www.youtube.com/watch?v=vyV0UgKxomg
    RB26DETT (turbo)
        Power: 320 PS -> 235 kW @ 6800rpm
        Torque: 35.9 kgm (353 Nm) at 4400rpm
        Source: https://en.wikipedia.org/wiki/Nissan_RB_engine#RB26DETT
- fInitialDriveForce and fInitialDragCoeff tuned to match 0-100, 0-150, 0-200 times (within a second)
- Adaptive AWD set from a base 1/99 (basically RWD) to 50/50, based on ATTESA implementation descriptions for this GT-R R32.
- Curb boost eliminated, thanks to Aquaphobic for describing that advanced flags' behavior.
- Tyre grip values based on various Nordschleife recordings and dash-cams with G-force readouts.

Tyre grip should be generic to most (sports) road tyres, at about 1.3G sustained through a relatively flat corner.

Accuracy:
- Acceleration times are roughly within 1 second, though on the fast side
- There is no engine power/torque curve due to game limitations
- Turbo settings are just based on data and guesstimates

Result:
- Nordschleife run: 7:56 (BTG) / <8:20> (Full lap)
- My lap: https://www.youtube.com/watch?v=i_TwsrAuFLM
- Reference lap: https://www.youtube.com/watch?v=G50LuP28PGM

Credits:
Aquaphobic for the base handling (https://www.gta5-mods.com/vehicles/realistic-handling-packs)
Eddlm for the basic suspension settings

## Installation

Required:
- Nissan Skyline GT-R (BNR32) by y97y: https://www.gta5-mods.com/vehicles/nissan-skyline-gt-r-bnr32
- Manual Transmission: https://www.gta5-mods.com/scripts/manual-transmission-ikt
- Handling Replacement Library : https://www.gta5-mods.com/tools/handling-replacement-library
- TurboFix: https://www.gta5-mods.com/scripts/turbofix-2
- Custom Gear Ratios: https://www.gta5-mods.com/scripts/custom-gear-ratios

Optional:
- 300 km/h dial for y97y's GT-R (BNR32): https://www.gta5-mods.com/misc/300-km-h-dial-for-y97y-s-nissan-skyline-gt-r-bnr32
- Dial Accuracy Fix: https://www.gta5-mods.com/scripts/dial-accuracy-fix
- InversePower: https://www.gta5-mods.com/scripts/inversepower

Installation steps:
- Install all required items (and optional items)
- Replace the handling file:
    - Handling\handling.meta -> Grand Theft Auto V\mods\update\x64\dlcpacks\r32\dlc.rpf\data\handling.meta
- Extract the other configuration files to the game folder
    - ManualTransmission\Vehicles\R32.ini -> Grand Theft Auto V\ManualTransmission\Vehicles\R32.ini
    - CustomGearRatios\Configs\r32_5_290kph_R32.xml -> Grand Theft Auto V\CustomGearRatios\Configs\r32_5_290kph_R32.xml
    - TurboFix\Configs\R32.ini -> Grand Theft Auto V\TurboFix\Configs\R32.ini
- Install the optional items. Read the instructions of each one for their respective requirements and installation.

## Changelog

1.0 - Initial release
