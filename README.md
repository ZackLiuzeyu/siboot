To use it, follow the following instructions: https://sideinstaller.net/install.html

iOS 27+ is required

## Punovia fork

SideInstaller by FrizzleM: https://github.com/FrizzleM/SideInstaller.

This fork changes Minis signing to request Increased Memory Limit before
fetching the Apple provisioning profile, on both install and refresh.
If the developer service rejects the capability, signing continues with
the permissions Apple grants. This change does not request Extended
Virtual Addressing. In Henge, check Settings → Memory → Extra memory
after both installation and refresh.

### Use the source build with the Henge guide

Build from source using [the Minis build instructions](minis/README.md#building).
Save the resulting ARM64 Linux binary as `siboot-memory` in Files →
On My iPad → Minis → shared. With Wi-Fi and LocalDevVPN connected, open
the Minis terminal and run:

```sh
cp /home/siboot-memory "$HOME/.siboot-memory"
chmod 755 "$HOME/.siboot-memory"
```

For a device that has already signed Henge in Minis, use the original
Apple Account and the same IPA URL for installation or renewal. For
the Punovia edition:

```sh
"$HOME/.siboot-memory" --ipa https://punovia.com/henge-download/0.3-punovia/Henge.ipa
```

For the upstream Henge edition:

```sh
"$HOME/.siboot-memory" --ipa https://punovia.com/henge-download/0.3/Henge.ipa
```

If the saved pairing is missing and you copied `rp_pairing_file.plist`
to Minis → shared, append `--pairing-file /home/rp_pairing_file.plist`.
Keep the original Henge installed when renewing. The separate command
allows the upstream Minis installer to keep its own binary.
