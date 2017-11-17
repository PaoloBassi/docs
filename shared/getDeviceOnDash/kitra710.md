In order to get resinOS up and running on your **{{ $device.name }}**, you need to first set it up to boot from your {{ $device.bootMedia }} rather than its
internal [eMMC memory][emmc-link]. To do this, you need to set the dip switch labeled `artik boot` (near the audio microphone jack) to position `1:off`, `2:off`, `3:off`, `4:on`, and insert your {{ $device.bootMedia }}
into the boards microSD slot.

__Note:__ ResinOS will completely write over the existing eMMC, so ensure the current eMMC storage does not have any important info or work stored on it.

If you selected WiFi as your connectivity type, remember to attach the WiFi antennas before booting the board.

You can now insert the 12VDC power cable and press and hold the power button for 1 second until the RGB LED in the centre of the board starts blinking. The board will now boot from your {{ $device.bootMedia}} and flash the device's internal storage with resinOS.

After a few seconds you should see your **{{ $device.name }}** appear on the resin.io dashboard in a configuring state.
If it still hasn't appeared after 1 or 2 minutes, double check your ethernet connection or that you entered the right WiFi credentials at download time.

Your **{{ $device.name }}** will now flash resinOS onto the internal eMMC so that you can remove the {{ $device.bootMedia }}. This will take 2 or 3 minutes. Once it has finished it will shut itself down and you will see the device on the dashboard in a `Post-Provisioning` state.
At this point you need to:

1. Power down the device.
2. Remove the {{ $device.bootMedia }}.
3. Set `artik boot` dip switch to position `1:off`, `2:off`, `3:off`, `4:off`.

Power the board back on again. If all went according to plan you should
now have a freshly provisioned **{{ $device.name }}** sitting in an `IDLE` state on our dashboard, ready and waiting to receive some code.

Now it's time to deploy some code!

[emmc-link]:http://www.datalight.com/solutions/technologies/emmc/what-is-emmc
