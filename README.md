# DU-LightControl

Light control script for Dual universe.

Will recolor all connected Lights.

it also sends RGBH values to all connected screens via setScriptInput(json.encode(XXXX))

can be fetched in connected screens with:
```
local json = require('json')
color1 = {r=1,g=0,b=0}              -- default fallback color if no input was ever send to the screen.
    if getInput():len() > 0 then    -- checks if an string was received
RGB = json.decode(getInput())       -- sets color to the received string value.
color1 = {r=RGB.r*RGB.h,g=RGB.g*RGB.h,b=RGB.b*RGB.h}
    end
```
based on the code from Krengus
https://github.com/Krengus/DU_ASTco/tree/main/ScreenLightControl
