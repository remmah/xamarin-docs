---
title: "Troubleshooting Xamarin Workbooks on Android"
ms.topic: article
ms.prod: xamarin
ms.assetid: F1BD293B-4EB7-4C18-A699-718AB2844DFB
ms.technology: xamarin-cross-platform
author: topgenorth
ms.author: toopge
---

# Troubleshooting Xamarin Workbooks on Android

## Emulator Support

To run an Android workbook, an Android emulator must be available for
use. Physical Android devices are not supported.

We recommend Google's emulator along with HAXM if your computer supports it.
If you must have Hyper-V enabled on your system, go with the Visual Studio
Android Emulator instead.

You must have an emulator that runs Android 5.0 or later. ARM emulators are
not supported. Use `x86` or `x86_64` devices only.

Please read [our documentation on setting up Android emulators][android-emu]
if you are not familiar with the process.

> [!NOTE]
> Workbooks 1.1 and earlier will try (and fail!) to use ARM emulators
> if they are available. To work around this, launch the x86 emulator of your
> choice before opening or creating an Android workbook. Workbooks will always
> prefer to connect to a running emulator, as long as it is compatible.

## Workbooks Won't Load

### Workbook window spins forever, never loads (Windows)

First, check that your emulator has fully-working network access by testing any
website in the emulator's web browser.

### Visual Studio Android Emulator cannot connect to the internet

If your emulator does not have network access, you may need to follow these
steps to fix your Hyper-V network switch. If you switch between Wi-Fi networks
frequently you may need to repeat this periodically:

0. **Make sure any critical network operations are complete, as this may
   temporarily disconnect Windows from the internet.**
1. Close emulators.
2. Open `Hyper-V Manager`.
3. Under `Actions`, open `Virtual Switch Manager...`.
4. Delete all virtual switches.
5. Click `OK`.
6. Launch VS Android Emulator. You will probably be prompted to recreate
   virtual network switch.
7. Test that VS Android Emulator's browser can access the internet.

[android-emu]: https://developer.xamarin.com/guides/android/deployment,_testing,_and_metrics/debug-on-emulator/


## Related Links

- [Reporting Bugs](~/tools/workbooks/install.md#reporting-bugs)
