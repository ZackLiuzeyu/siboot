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

See [the Minis build instructions](minis/README.md#building) to build
from source. The upstream bootstrap and binaries remain upstream.
