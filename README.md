<h1>MacOS Catalina on Dell Vostro 3000 series using Clover</h1>
<h2>Laptop Specs</h2>
<table>
  <thead>
    <tr>
      <td style="text-align: center">Feature</td>
      <td style="text-align: center">Specification</td>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Model</td>
      <td>Dell Vostro 3468</td>
    </tr>
    <tr>
      <td>Processor type</td>
      <td>Intel Core i5 7200U</td>
    </tr>
     <tr>
      <td>VGA</td>
      <td>Intel HD Graphics 620</td>
    </tr>
    <tr>
      <td>Controller</td>
      <td>Realtek ALC3246/256 (layout-id: 11)</td>
    </tr>
    <tr>
    </tr>
  </tbody>
</table>

## Important info

This project is not maintained. I'm working in a OpenCore version of this in [dell-vostro-3468-hackintosh](https://github.com/ahianf/dell-vostro-3468-hackintosh).

I recommend you use this Clover version, find what is working, and what not; apply your specific tweaks and then migrate to OpenCore using my other repo as a guide.

## What is working

### Completely supported

#### CPU

XCPM power management is native supported. HWP is fully enabled as well.

#### Wi-Fi & Bluetooth

This laptop comes with an Intel WiFi + Bluetooth combo. I replaced mine with BCM94352Z (DM1560). Airport, Handoff are working correctly.

#### Camera

Camera is functioning normally.

#### Battery

Battery readings working.

#### USB

USB ports are working as expected.

Use USBInject-All.kext then with Hackintool you should disable all unused ports and generate a USBPorts.kext.

#### Ethernet

Functioning normally.

#### Display

Working fine with hardware acceleration.

#### Audio

Driven by AppleALC with `layout-id: 11`. Working fine but headphone jack requires a workaround and is not detected by default (HDMI Audio output has not been tested).

Built-in mic is working

#### Sleep and Wake

Working just fine

### Partially working

Audio and microphone works, but headphone jack requires a workaround.

#### Keyboard

Functioning except the AltGr key, (which I don't know how to map it correctly) and Fn Keys.

#### Touchpad

Functioning with multigestures, but weird behavior when clicking and moving cursor with other finger, cursor "teleports".

#### Headphone jack

Requires a workaround and is not detected.

### Not working

#### Others

Internal SD card Reader

### Not tested

HDMI output

### Additional info, quirks, findings, etc 

Remove kexts asociated with BCM94352Z(DW1560) if you do not have installed one.

ACPI patches _OSI->XOSI, OSID->XSID and SSDT-XOSI.aml are necessary, if not present the laptop will halt when power adapter is connected/disconnected.

If patch GFX0 to iGPU is disabled, you won't be able to control brightness.

