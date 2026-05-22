# ShutdownMonitor

This software installs a possibility to perform a clean shutdown of the Venus OS via the
menu system.

## Usage

### dbus

The ShutdownMonitor runs as a service and creates a dbus service with a single
parameter: ``/Shutdown``. Setting ``/Shutdown`` to ``1`` will trigger a clean OS shutdown.

### Menu

A shutdown submenu is added to the *Device List* (main menu). A submenu is used to alert
the user that a power cycle is needed to restart the GX device.

**Note**: A Cerbo GX restarts itself after a shutdown so this addition may not be useful
in all situations.

### Raspberry GPIO

For Raspberry PI platforms, the Shutdown menu shows whether the shutdown button is
pressed (GPIO #16 low), even when pin shutdown is disabled. Pulling the pin low for
about 3 seconds will trigger a shutdown if enabled in the Shutdown menu. This requires
[RpiGpioSetup](https://github.com/kwindrem/RpiGpioSetup) with Version v3.4 or later to
activate the GPIO pin.

## Installation

ShutdownMonitor requires that SetupHelper is installed first.

The easiest way to install ShutdownMonitor is to do a "blind install" of SetupHelper
	and then add the ShutdownMonitor package via the PackageManager menus.

Refer to the SetupHelper ReadMe for instructions and for other install options:
	https://github.com/kwindrem/SetupHelper
