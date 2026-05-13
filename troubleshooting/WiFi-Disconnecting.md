# Raspberry Pi Disconnecting on Wi-Fi

> **Symptom:** Your Klipper/Mainsail/Fluidd web interface drops out randomly, SSH connections time out, or the Pi becomes unreachable over the network — but comes back on its own after a minute or two.

This is almost always caused by **Wi-Fi power saving mode**. Linux enables it by default to save energy, but it causes the wireless adapter to periodically sleep and drop the connection. Disabling it permanently fixes the issue.

---

## What You'll Need

- A PC on the same network as your Pi
- [PuTTY](https://www.putty.org/) (free SSH client for Windows) — or any terminal with SSH
- Your Pi's IP address (find it in your router's device list, or check Mainsail/Fluidd's settings)

---

## Step 1 — Connect to Your Pi via SSH

1. Open **PuTTY**
2. In the **Host Name** field, enter your Pi's IP address (e.g. `192.168.1.100`)
3. Make sure **Port** is set to `22` and **Connection type** is `SSH`
4. Click **Open**
5. If prompted with a security warning about the host key, click **Accept**
6. Log in with your Pi credentials:
   - **Username:** `pi` (or whatever you set during setup — Klipper installs often use `pi`)
   - **Password:** your password

> 💡 **Tip:** If you don't know your Pi's IP, check your router's admin page, or use a tool like [Angry IP Scanner](https://angryip.org/). Mainsail and Fluidd also show the IP address in their interface.

---

## Step 2 — Check If Power Saving Is Enabled

Once logged in, run this command to check your current Wi-Fi power management state:

```bash
iwconfig wlan0 | grep "Power Management"
```

**If the output shows:**
```
Power Management:on
```
Power saving is active and is likely causing your disconnects. Continue to Step 3.

**If the output shows:**
```
Power Management:off
```
Power saving is already disabled — your disconnects may have a different cause (weak signal, interference, etc.).

---

## Step 3 — Disable Wi-Fi Power Saving Permanently

The cleanest way to permanently disable power saving is via a `udev` rule. This runs automatically every time the Pi boots and ensures the setting survives reboots and kernel updates.

Run the following command to open a new config file in the nano text editor:

```bash
sudo nano /etc/udev/rules.d/70-wifi-powersave.conf
```

The file will be empty. Type (or paste) the following line exactly:

```
ACTION=="add", SUBSYSTEM=="net", KERNEL=="wlan0", RUN+="/sbin/iw dev wlan0 set power_save off"
```

> 💡 **Tip:** To paste in PuTTY, simply right-click in the terminal window.

---

## Step 4 — Save and Exit

1. Press **Ctrl + O** to write (save) the file
2. Press **Enter** to confirm the filename
3. Press **Ctrl + X** to exit nano

---

## Step 5 — Reboot the Pi

Apply the change by rebooting:

```bash
sudo reboot
```

Your SSH session will disconnect — this is normal. Wait about 30 seconds for the Pi to come back up, then reconnect via PuTTY.

---

## Step 6 — Verify the Fix

Once back in SSH, run the check again:

```bash
iwconfig wlan0 | grep "Power Management"
```

You should now see:

```
Power Management:off
```

Power saving is permanently disabled. Your Pi should no longer drop its Wi-Fi connection.

---

## Still Disconnecting?

If the problem persists after disabling power saving, check these:

| Possible Cause | What to Check |
|---|---|
| Weak Wi-Fi signal | Move the Pi closer to your router, or use a Wi-Fi extender |
| 2.4 GHz congestion | Switch to 5 GHz if your Pi model supports it (Pi 3B+, Pi 4, Pi 5) |
| Router DHCP lease expiry | Set a **static IP** for your Pi in your router settings |
| Overheating Pi | Check CPU temp with `vcgencmd measure_temp` — keep below 80°C |
| Dodgy USB power supply | A Pi starved of power will behave erratically — use a quality PSU rated for your Pi model |

---

*← [Back to README](../README.md)*
