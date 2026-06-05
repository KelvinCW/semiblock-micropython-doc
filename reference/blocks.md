# Full block reference (alphabetical)

Every block `type` available in the SemiBlock MicroPython toolbox, grouped by
category in the order the categories appear in `src/toolbox.js`. Within each
category the blocks are listed in toolbox order. Each entry has a one-line
description of what the block does.

## Machine

| Block `type` | Description |
| --- | --- |
| `createMainMethod` | The program entry point; wraps imports and the `### start` body. |
| `softReset` | Soft-reset the interpreter (`machine.soft_reset()`). |
| `hardReset` | Hard-reset the board (`machine.reset()`). |
| `sleep` | Pause for a number of seconds. |
| `sleep_ms` | Pause for a number of milliseconds. |
| `sleep_us` | Pause for a number of microseconds. |
| `connectWifi` | Connect to a Wi-Fi network by SSID and password. |
| `mem8Read` | Read an 8-bit value from a memory address. |
| `mem16Read` | Read a 16-bit value from a memory address. |
| `mem32Read` | Read a 32-bit value from a memory address. |
| `mem8Write` | Write an 8-bit value to a memory address. |
| `mem16Write` | Write a 16-bit value to a memory address. |
| `mem32Write` | Write a 32-bit value to a memory address. |
| `getCPUFreq` | Read the current CPU frequency. |
| `setCPUFreq` | Set the CPU frequency. |
| `ticksMs` | Read the millisecond tick counter. |
| `ticksDiff` | Difference between two tick values. |
| `bytearrayInit` | Create a `bytearray`. |

## Motion (sprite)

| Block `type` | Description |
| --- | --- |
| `spriteMoveSteps` | Move the sprite forward a number of steps. |
| `spriteTurnRight` | Rotate the sprite clockwise. |
| `spriteTurnLeft` | Rotate the sprite anticlockwise. |
| `spriteGoToMenu` | Go to a target chosen from a menu. |
| `spriteGoToXY` | Go to an absolute X/Y position. |
| `spriteGlideToMenu` | Glide to a menu target over a number of seconds. |
| `spriteGlideToXY` | Glide to an X/Y position over a number of seconds. |
| `spritePointInDirection` | Point in a specific direction (degrees). |
| `spritePointTowards` | Point towards a target. |
| `spriteChangeX` | Change the sprite's X by an amount. |
| `spriteSetX` | Set the sprite's X position. |
| `spriteChangeY` | Change the sprite's Y by an amount. |
| `spriteSetY` | Set the sprite's Y position. |
| `spriteIfOnEdgeBounce` | Bounce when touching the stage edge. |
| `spriteSetRotationStyle` | Set the rotation style. |
| `spriteGetX` | Report the sprite's X position. |
| `spriteGetY` | Report the sprite's Y position. |
| `spriteGetDirection` | Report the sprite's direction. |

## Looks (sprite)

| Block `type` | Description |
| --- | --- |
| `spriteShow` | Show the sprite. |
| `spriteHide` | Hide the sprite. |
| `spriteSwitchCostume` | Switch to another costume. |
| `spriteSetSize` | Set the sprite size (percent). |
| `spriteGetSize` | Report the sprite size. |

## Events (sprite)

| Block `type` | Description |
| --- | --- |
| `spriteWhenClicked` | Run blocks when the sprite is clicked. |

## Waveshare 3.5

| Block `type` | Description |
| --- | --- |
| `waveshare35Init` | Initialise the Waveshare 3.5" all-in-one display board. |

## Language

| Block `type` | Description |
| --- | --- |
| `freeCode` | Insert a raw line of MicroPython. |
| `importCode` | `import <library>`. |
| `importCode2` | `import <library> as <alias>`. |
| `fromImportCode` | `from <library> import <component>`. |
| `forLoop` | `for` loop over a range. |
| `whileLoop` | `while` loop. |
| `ifLoop` | `if` statement. |
| `elseIfLoop` | `elif` branch. |
| `elseLoop` | `else` branch. |
| `print` | Print a value to the REPL. |
| `variable` | Assign a value to a variable. |
| `comment` | A `#` comment line. |
| `pass` | The `pass` statement. |
| `def` | Define a function. |
| `startThread` | Start a new thread with `_thread`. |

## List

| Block `type` | Description |
| --- | --- |
| `createList` | Create a list literal. |
| `appendList` | Append a value. |
| `insertList` | Insert a value at an index. |
| `removeList` | Remove a value. |
| `popList` | Pop an item at an index. |
| `sortList` | Sort the list in place. |
| `reverseList` | Reverse the list in place. |
| `lenList` | Length of the list. |
| `getList` | Get the item at an index. |
| `getListSlice` | Slice `[start:end]`. |
| `getListSlice2` | Slice `[start:]`. |
| `getListSlice3` | Slice `[:end]`. |
| `getListSlice4` | Copy slice `[:]`. |

## Dictionary

| Block `type` | Description |
| --- | --- |
| `createDict` | Create an empty dict. |
| `dictSet` | Set `dict[key] = value`. |
| `dictGet` | Get `dict[key]`. |
| `dictKeys` | Get `dict.keys()`. |
| `dictValues` | Get `dict.values()`. |
| `dictItems` | Get `dict.items()`. |
| `dictPop` | Pop a key. |
| `dictUpdate` | Update from another dict. |
| `dictClear` | Clear the dict. |

## Math

| Block `type` | Description |
| --- | --- |
| `integerInit` | An integer literal. |
| `mathAdd` | Addition. |
| `mathSubtract` | Subtraction. |
| `mathMultiply` | Multiplication. |
| `mathDivide` | Division. |
| `mathModulo` | Modulo. |
| `mathPower` | Exponentiation. |
| `mathSqrt` | Square root. |
| `mathSin` | Sine. |
| `mathCos` | Cosine. |
| `mathTan` | Tangent. |
| `mathLog` | Logarithm. |
| `mathExp` | Exponential. |
| `mathAbs` | Absolute value. |
| `mathFloor` | Floor. |
| `mathCeil` | Ceiling. |
| `mathRound` | Round. |
| `mathMin` | Minimum. |
| `mathMax` | Maximum. |
| `mathPi` | The constant π. |
| `mathE` | The constant e. |
| `mathRandom` | Random float. |
| `mathRandomInt` | Random integer. |
| `divmod` | `divmod()` quotient and remainder. |
| `hex` | Hexadecimal string. |
| `ord` | Unicode code point. |

## String

| Block `type` | Description |
| --- | --- |
| `stringInit` | A string literal. |
| `stringUpper` | Upper-case. |
| `stringLower` | Lower-case. |
| `stringStrip` | Strip whitespace. |
| `stringReplace` | Replace substring. |
| `stringFind` | Find substring index. |
| `stringSplit` | Split on a delimiter. |
| `stringJoin` | Join a list with a delimiter. |
| `stringStartsWith` | Prefix test. |
| `stringEndsWith` | Suffix test. |
| `stringLength` | String length. |

## Random

| Block `type` | Description |
| --- | --- |
| `random` | Random float in `[0, 1)`. |
| `randint` | Random integer in a range. |
| `choice` | Random element from a sequence. |
| `shuffle` | Shuffle a sequence in place. |
| `uniform` | Random float in a range. |
| `randrange` | Random value from a range with a step. |
| `sample` | Random sample of unique elements. |

## Exception

| Block `type` | Description |
| --- | --- |
| `tryExcept` | `try` / `except` block. |
| `raiseException` | `raise` an exception. |
| `assertStatement` | `assert` a condition. |
| `finallyBlock` | `finally` clause. |

## Regex

| Block `type` | Description |
| --- | --- |
| `reMatch` | `re.match`. |
| `reSearch` | `re.search`. |
| `reFindAll` | `re.findall`. |
| `reFindIter` | `re.finditer`. |
| `reSub` | `re.sub`. |
| `reSplit` | `re.split`. |
| `reCompile` | `re.compile`. |

## Requests

| Block `type` | Description |
| --- | --- |
| `urequestsGet` | HTTP `GET`. |
| `urequestsPost` | HTTP `POST` with data. |
| `urequestsPut` | HTTP `PUT` with data. |
| `urequestsDelete` | HTTP `DELETE`. |
| `urequestsHead` | HTTP `HEAD`. |

## SemiBlock IoT

| Block `type` | Description |
| --- | --- |
| `iotConnect` | Set the IoT server, device ID, and secret. |
| `iotPushReading` | Push a single sensor reading to the cloud. |
| `iotPushValue` | Push a keyed value to the cloud. |

## CSV

| Block `type` | Description |
| --- | --- |
| `csvRead` | Read all rows of a CSV file into a list. |
| `csvWrite` | Write rows to a CSV file. |
| `csvAppend` | Append a row to a CSV file. |

## OS

| Block `type` | Description |
| --- | --- |
| `osListDir` | List directory contents. |
| `osRemove` | Remove a file. |
| `osRename` | Rename a file. |
| `osMkdir` | Make a directory. |
| `osRmdir` | Remove a directory. |
| `osGetcwd` | Current working directory. |
| `osChdir` | Change directory. |
| `osStat` | File status. |
| `osUname` | System information. |
| `osSync` | Flush filesystem buffers. |
| `osSystem` | Run a system command. |
| `osUrandom` | Random bytes. |

## Display (SSD1306)

| Block `type` | Description |
| --- | --- |
| `ssd1306` | Create an SSD1306 I²C display object. |
| `ssd1306_fill` | Fill the screen buffer. |
| `ssd1306_show` | Flush the buffer to the screen. |
| `ssd1306_contrast` | Set contrast. |
| `ssd1306_invert` | Invert colours. |
| `ssd1306_rotate` | Rotate the display. |
| `ssd1306_text` | Draw text. |
| `ssd1306_pixel` | Set a pixel. |
| `ssd1306_hline` | Horizontal line. |
| `ssd1306_vline` | Vertical line. |
| `ssd1306_line` | Arbitrary line. |
| `ssd1306_rect` | Rectangle outline. |
| `ssd1306_fillRect` | Filled rectangle. |
| `ssd1306_circle` | Circle outline. |
| `ssd1306_fillCircle` | Filled circle. |
| `ssd1306_scroll` | Scroll the buffer. |
| `imageEditor` | Draw a bitmap in the SemiBlock image editor. |
| `drawPixels` | Render an edited bitmap to the display. |
| `ssd1306_setColor` | Set the draw colour. |
| `ssd1306_setFontSize` | Set the font size. |

## LVGL

| Block `type` | Description |
| --- | --- |
| `lvglInit` | `import lvgl as lv`. |
| `importLcdBus` | Import the LCD bus module. |
| `importSt7796` | Import the ST7796 driver. |
| `importSt7735` | Import the ST7735 driver. |
| `importTaskHandler` | Import the task handler. |
| `importFsDriver` | Import the filesystem driver. |
| `lcdSpiBusInit` | Initialise the LCD SPI bus. |
| `allocateFramebuffer` | Allocate a framebuffer. |
| `st7796Init` | Initialise an ST7796 panel. |
| `st7735Init` | Initialise an ST7735 panel. |
| `displayInit` | Generic display init. |
| `displayInitWithType` | Display init with a panel type. |
| `displaySetRotation` | Set screen rotation. |
| `displaySetColorInversion` | Toggle colour inversion. |
| `displaySetBacklight` | Set backlight level. |
| `taskHandlerInit` | Initialise the LVGL task handler. |
| `lvglFsDrvtInit` | Initialise the LVGL FS driver. |
| `lvglFsRegister` | Register the FS driver. |
| `lvglSetScrollbarMode` | Set scrollbar mode. |
| `lvglScreenCreate` | Create a screen object. |
| `lvglScreenLoad` | Load a screen. |
| `lvglScreenActive` | Get the active screen. |
| `lvglRefrNow` | Force an immediate refresh. |
| `lvglTaskHandler` | Run one task-handler pass. |
| `lvglLabelCreate` | Create a label. |
| `lvglLabelSetText` | Set label text. |
| `lvglButtonCreate` | Create a button. |
| `lvglContainerCreate` | Create a container. |
| `lvglSetPos` | Set object position. |
| `lvglSetSize` | Set object size. |
| `lvglSetWidth` | Set object width. |
| `lvglSetHeight` | Set object height. |
| `lvglSetX` | Set object X. |
| `lvglSetY` | Set object Y. |
| `lvglAlign` | Align an object. |
| `lvglSliderCreate` | Create a slider. |
| `lvglSliderSetValue` | Set slider value. |
| `lvglSliderGetValue` | Get slider value. |
| `lvglBarCreate` | Create a bar. |
| `lvglBarSetValue` | Set bar value. |
| `lvglArcCreate` | Create an arc. |
| `lvglArcSetValue` | Set arc value. |
| `lvglCheckboxCreate` | Create a checkbox. |
| `lvglCheckboxSetText` | Set checkbox text. |
| `lvglSwitchCreate` | Create a switch. |
| `lvglTextareaCreate` | Create a text area. |
| `lvglTextareaSetText` | Set text-area text. |
| `lvglDropdownCreate` | Create a dropdown. |
| `lvglDropdownSetOptions` | Set dropdown options. |
| `lvglRollerCreate` | Create a roller. |
| `lvglRollerSetOptions` | Set roller options. |
| `lvglImageCreate` | Create an image. |
| `lvglImageSetSrc` | Set image source. |
| `lvglImageSetSrcCostume` | Set image source from a costume. |
| `lvglLedCreate` | Create an LED widget. |
| `lvglLedOn` | Turn the LED widget on. |
| `lvglLedOff` | Turn the LED widget off. |
| `lvglLedToggle` | Toggle the LED widget. |
| `lvglLedSetBrightness` | Set LED-widget brightness. |
| `lvglKeyboardCreate` | Create a keyboard. |
| `lvglKeyboardSetTextarea` | Bind keyboard to a text area. |
| `lvglTabviewCreate` | Create a tab view. |
| `lvglTabviewAddTab` | Add a tab. |
| `lvglSetBgColor` | Set background colour. |
| `lvglSetTextColor` | Set text colour. |
| `lvglSetOpacity` | Set opacity. |
| `lvglSetStyleTextFont` | Set the text font style. |
| `lvglSetStyleBgOpa` | Set the background-opacity style. |
| `lvglSetStyleRadius` | Set the corner-radius style. |
| `lvglSetStylePad` | Set the padding style. |
| `lvglSetStyleBorderWidth` | Set the border-width style. |
| `lvglSetStyleBorderColor` | Set the border-colour style. |
| `lvglSetStyleShadowWidth` | Set the shadow-width style. |
| `lvglSetStyleShadowColor` | Set the shadow-colour style. |
| `lvglColorHex` | Make a colour from a hex value. |
| `lvglGetDisplay` | Get the display handle. |
| `lvglAddEventCb` | Add an event callback. |
| `lvglSpinnerCreate` | Create a spinner. |
| `lvglChartCreate` | Create a chart. |
| `lvglChartAddSeries` | Add a chart series. |
| `lvglChartSetPoint` | Set a chart point. |
| `lvglMeterCreate` | Create a meter. |
| `lvglAddFlag` | Add an object flag. |
| `lvglClearFlag` | Clear an object flag. |
| `lvglRemoveFlag` | Remove an object flag. |
| `lvglAnimCreate` | Create an animation. |
| `lvglAnimInit` | Initialise an animation. |
| `lvglAnimSetVar` | Set the animation target. |
| `lvglAnimSetTime` | Set the animation duration. |
| `lvglAnimSetValues` | Set the animation start/end. |
| `lvglAnimStart` | Start an animation. |
| `lvglObjDelete` | Delete an object. |
| `lvglObjClean` | Remove an object's children. |
| `lvglObjInvalidate` | Mark an object for redraw. |
| `lvglCanvasCreate` | Create a canvas. |
| `lvglCanvasSetBuffer` | Set the canvas buffer. |
| `lvglCanvasFillBg` | Fill the canvas background. |
| `lvglCanvasSetPx` | Set a canvas pixel. |
| `lvglTickInc` | Advance the LVGL tick counter. |

## Pin

| Block `type` | Description |
| --- | --- |
| `pin` | Create a `Pin` with a direction. |
| `pin2` | Create a `Pin` with input + pull type. |
| `on` | Drive the pin high. |
| `off` | Drive the pin low. |
| `pinValue` | Read the pin value. |
| `uartInit` | Initialise a UART. |
| `uartRead` | Read bytes from UART. |
| `uartWrite` | Write to UART. |
| `neoPixel` | Create a NeoPixel strip. |
| `neoPixelWrite` | Set and write a NeoPixel colour. |

## Timer

| Block `type` | Description |
| --- | --- |
| `timerInit` | Create a `Timer`. |
| `timerStart` | Start a periodic/one-shot timer. |
| `timerStop` | De-initialise the timer. |

## PWM

| Block `type` | Description |
| --- | --- |
| `pwmInit` | Create a PWM on a pin. |
| `pwmSetFreq` | Set PWM frequency. |
| `pwmSetDuty` | Set PWM duty cycle. |
| `pwmDeinit` | De-initialise PWM. |

## ADC

| Block `type` | Description |
| --- | --- |
| `adcInit` | Create an ADC on a pin. |
| `adcRead` | Read the ADC. |
| `dacInit` | Create a DAC on a pin. |
| `dacWrite` | Write to the DAC. |

## SPI

| Block `type` | Description |
| --- | --- |
| `spiInit` | Create a hardware SPI. |
| `spiBusInit` | Initialise an SPI bus. |
| `spiRead` | Read from SPI. |
| `spiWrite` | Write to SPI. |
| `spiReadWrite` | Full-duplex read into a buffer. |

## I2C

| Block `type` | Description |
| --- | --- |
| `i2cInit` | Create an I²C bus. |
| `i2cScan` | Scan for I²C addresses. |
| `i2cRead` | Read from a device. |
| `i2cWrite` | Write to a device. |

## WatchDog (RTC, WDT, deep sleep)

| Block `type` | Description |
| --- | --- |
| `rtcInit` | Create an `RTC`. |
| `rtcSetTime` | Set the RTC datetime. |
| `rtcGetTime` | Get the RTC datetime tuple. |
| `rtcGetYear` | Get the year. |
| `rtcGetMonth` | Get the month. |
| `rtcGetDay` | Get the day. |
| `rtcGetHour` | Get the hour. |
| `rtcGetMinute` | Get the minute. |
| `rtcGetSecond` | Get the second. |
| `wdtInit` | Create a watchdog timer. |
| `wdtFeed` | Feed the watchdog. |
| `deepSleep` | Enter deep sleep for a duration. |

## SD Card

| Block `type` | Description |
| --- | --- |
| `sdCardInit` | Create an `SDCard`. |
| `sdCardMount` | Mount the card. |
| `sdCardUnmount` | Unmount the card. |
| `sdCardFileWrite` | Write a file to the card. |
| `sdCardFileRead` | Read a file from the card. |

## RMT

| Block `type` | Description |
| --- | --- |
| `rmtInit` | Create an RMT channel. |
| `rmtWrite` | Write RMT pulses. |
| `rmtDeinit` | De-initialise RMT. |

## One-Wire

| Block `type` | Description |
| --- | --- |
| `oneWireInit` | Create a OneWire bus. |
| `oneWireScan` | Scan for OneWire devices. |
| `oneWireRead` | Read a byte. |
| `oneWireWrite` | Write a byte. |

## Capacitive Touch

| Block `type` | Description |
| --- | --- |
| `touchInit` | Create a `TouchPad`. |
| `touchRead` | Read the touch value. |

## DHT

| Block `type` | Description |
| --- | --- |
| `dhtInit` | Create a DHT sensor. |
| `dhtReadTemperature` | Measure and read temperature. |
| `dhtReadHumidity` | Measure and read humidity. |

## HC-SR04 Sonar

| Block `type` | Description |
| --- | --- |
| `hcsr04Init` | Define the driver and create an HC-SR04 sensor. |
| `hcsr04DistanceCm` | Read distance in centimetres. |
| `hcsr04DistanceMm` | Read distance in millimetres. |

## Sensors

| Block `type` | Description |
| --- | --- |
| `temperature` | Read an analog thermistor via `getTemperature`. |
| `fourDigitDisplay` | Create a TM1637 4-digit display. |
| `fourDigitDisplay_setNumber` | Show a number on the display. |
| `motor` | Create a DC-motor control pin. |
| `motorOn` | Turn the motor on. |
| `motorOff` | Turn the motor off. |
| `servo` | Create a servo. |
| `servoAngle` | Set the servo angle. |

## Generative AI

| Block `type` | Description |
| --- | --- |
| `askDeepSeek` | Ask a DeepSeek LLM a question and store the answer. |

## Open Data

| Block `type` | Description |
| --- | --- |
| `getOpenDataTemperature` | Get temperature for a location. |
| `getOpenDataRainfall` | Get rainfall for a location. |
| `getOpenDataHumidity` | Get humidity. |
| `getPublicHoliday` | Get public holiday data. |
| `getBusStopID` | Look up a bus stop ID. |
| `getBusRouteNo` | Look up a bus route number. |
| `getBusArrivalTime` | Get bus arrival time. |
| `getFlightList` | Get a flight list. |
| `getMTR` | Get MTR information. |

---

**Next:** [Category color legend](categories.md)
