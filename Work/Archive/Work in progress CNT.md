Tested with 2026.1 (RC[DSRT-1255]-251217.1503) (64-bit) and Obsidian FW: lx_2025.3.0.2_jira-dsrt-1255-fixes_d9f5fb36.dxu

- [x] to 1.1) Default FreqLimit = 1Hz. Question: shall this use the set default out of Settings, or will it be always 1Hz in Standalone mode?
- [x] to 2) Limit checks for EditFields got better, but ..
	- [x] add 2.1) CustomGearTooth has always +/- 1 Teeth Limit for OffsetZero
	- [x] add 2.2) CustomGearTooth has always FreqLimit= 1Hz
	- [x] add 2.3) FreqDropTime limit shows 1000sec, but when you close and reopen CNTChannelSetupScreen it is reset to 1 (looks like it just takes the set FreqLimit?)
	- [x] add 2.4) ZeroOffset Teeth is not updated/re-checked after a sensor got changed in SensorEditor
	- [x] add 2.5) LinEncoder and LinPulses sensor should not allow ZeroOffset

- [x] Beside this, well it shows still Angle/Freq (same in white mode), but here the units are missing as well.

- [x] At Angle it should something like [m], and at Freq even a list “m/s; m/min … “
- [x] to3) Edit width’s are better now, Wrapping Edit could need a little extra width

to4) Live values in CNTChannelSetupScreen are much better now but if SetupSampleRate from Settings is smaller as DeviceSampleRate the update becomes slow.

What you see in video:

- [x] **First DeviceSR=SetupSampleRate=20kHz. When my sensor starts it shows really quick a live value. Then I change SetupSampleRate=5kHz. No it takes about 3-5sec before my sensor action reflects on live values. (both, SetupList and ChannelSetupScreen).**

- [x] to5) Enable/Disable Angle/Freq/CntTicks in CalcSetup, if you do it for a while or quick it leads still to AccessViolations. Old Video is still valid.

- [x] to6) Default ChannelMin/Max: nothing has changed? so still open.
	- [ ] Check if raw count changed depending on the sensor in white mode

- [x] **to8) Basic encoder mode does not show EncoderProps (Pulses, Zero Enabled) Now it shows Encoder props, but “Pulses” prop is always missing if not in Advanced?**

- [x] to9) When comming from Encoder sensor and going back to EventCounting, it sets BasicEncoder. Partly Done.
	- [x] Now it sets BasicEvent counting as done with all other CNTs. But it keeps the Zero-Signal if it was enabled on Sensor. Should set to default BasicEvent counting, always with Zero disabled.

- [x] to13) Changing Sensor in SensorEditor out of CNTChannelSetupscreen does not update setupscreen. If the sensor type stays the same it seems to update correct, but if I add in SensorEditor and new Sensor (like GTwithDblTeeth to Encoder) it shows wrong connection picture, still the one of GTwithDblTeeth.
	- [x] add 13.1) Encoder X mode is not taken from Sensor on first time selection
- [x] MemCheck



Count mode: 0...10000 or -10000...10000
Waveform timing 0...100 DC, 0...1000 timings
Sensor mode: raw: 0....1000