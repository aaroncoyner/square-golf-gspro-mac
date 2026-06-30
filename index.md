# Connect Square Golf to GSPro on a Mac

This guide explains how to run **GSPro on macOS** using **CrossOver** and connect a **Square Golf launch monitor** through GSPro's **OpenAPI/Open Connect** interface using the community SquareGolf Connector.

```text
Square Golf Launch Monitor
        ↓ Native Mac Bluetooth
SquareGolf Connector
        ↓ GSPro OpenAPI / Open Connect
GSPro running in CrossOver
```

## Important notes

This is an unofficial community guide. It is not affiliated with SquareGolf, GSPro, CodeWeavers/CrossOver, or the SquareGolf Connector author.

Use the original connector repository first whenever possible:

```text
https://github.com/brentyates/squaregolf-connector
```

Backup files may be provided in this repo's Releases page only in case the original connector release becomes unavailable.

## What you need

- A Mac with Bluetooth
- A Square Golf launch monitor
- CrossOver for Mac
- A GSPro license
- GSPro set up with **OpenAPI/Open Connect**
- SquareGolf Connector from [Brent Yates' GitHub repository](https://github.com/brentyates/squaregolf-connector)


## Recommended setup

The recommended Mac setup is:

1. Run **GSPro** inside a CrossOver **Windows 10 bottle**.
2. Run the **macOS version** of SquareGolf Connector natively on the Mac.
3. Let the connector send shot data to GSPro **using OpenAPI/Open Connect**.


## 1. Install CrossOver

1. Download and install CrossOver for Mac from CodeWeavers.
2. Open CrossOver.
3. Create a new bottle.
4. Choose **Windows 10** as the bottle type.
5. Name the bottle something clear, such as:

```text
GSPro
```

Keeping GSPro in its own bottle makes troubleshooting easier.


## 2. Install GSPro inside the Windows 10 bottle

1. Download the GSPro installer from your GSPro account.
2. Open CrossOver.
3. Select the **GSPro** Windows 10 bottle.
4. Choose **Install**.
5. If GSPro is not listed, choose **Install an Unlisted Application**.
6. Select the GSPro installer file.
7. Install GSPro into the **GSPro** bottle.
8. Launch GSPro from CrossOver.

When GSPro asks which launch monitor or interface you are using, choose the **OpenAPI**, **Open Connect**, or equivalent open connector option.

If you already installed GSPro and selected the wrong launch monitor, you can easily submit a change request when launching GSPro.


## 3. Install SquareGolf Connector

Go to the original connector repository:

```text
https://github.com/brentyates/squaregolf-connector
```

Then:

1. Open the latest release.
2. Download the macOS release zip.
3. Unzip it.
4. Move `SquareGolf Connector.app` to your `Applications` folder if desired.
5. Open `SquareGolf Connector.app`.

### If macOS blocks the app

macOS may block community-built apps the first time they are opened.

Try this:

1. Open the app once and close the warning.
2. Right-click `SquareGolf Connector.app`.
3. Choose **Open**.
4. Click **Open** again.
5. If needed, go to **System Settings → Privacy & Security** and choose **Open Anyway**.


## 4. Start everything in order

For a clean startup:

1. Turn on the Square Golf launch monitor.
2. Make sure Bluetooth is enabled on your Mac.
3. Open GSPro from the CrossOver **GSPro** bottle.
4. Confirm GSPro is using **OpenAPI/Open Connect**.
5. Open `SquareGolf Connector.app` on macOS.
6. In the connector, scan for your Square Golf device.
7. Select the launch monitor and connect.
8. Connect the connector to GSPro.
9. If manual OpenAPI/Open Connect settings are needed, use:

```text
Host: 127.0.0.1
Port: 0921
```

10. Return to GSPro and confirm that it shows as connected.
11. Hit a test shot.

Once GSPro and the connector are both connected, you should be ready to play!

## Troubleshooting

### GSPro does not receive shots

Check these first:

- GSPro is open.
- GSPro is set to **OpenAPI/Open Connect**.
- SquareGolf Connector is connected to the Square Golf launch monitor.
- SquareGolf Connector is connected to GSPro.
- The connector is using `127.0.0.1` and port `0921` if manual settings are needed.
- GSPro shows a connected/green status.

If it still does not work, close both apps and reopen them in this order:

1. GSPro through CrossOver
2. SquareGolf Connector
3. Connect the Square Golf device
4. Connect the connector to GSPro

### Square Golf does not appear in the connector

Try:

- Confirming the launch monitor is powered on
- Confirming Bluetooth is enabled on the Mac
- Moving the launch monitor closer to the Mac
- Restarting the connector
- Restarting Bluetooth on the Mac
- Checking macOS Bluetooth permissions for the connector

### macOS says the connector cannot be opened

Right-click the app and choose **Open**. If needed, approve it under **System Settings → Privacy & Security**.

### GSPro is laggy in CrossOver

Try:

- Lowering GSPro graphics settings
- Reducing projector or external display resolution
- Closing other apps
- Using a wired external display connection instead of AirPlay or wireless mirroring
- Keeping GSPro in its own CrossOver bottle


### Native macOS connector cannot connect to GSPro

The macOS connector is the recommended first attempt. If it cannot communicate with GSPro, there is a Windows connector from Brent Yates that you can download and install inside the same CrossOver bottle as GSPro:

1. Download the Windows release zip from the connector repository.
2. Open the **GSPro** bottle in CrossOver.
3. Run the connector `.exe` inside that same bottle.
4. Keep the connector `.exe` and any required folders together.
5. Open GSPro and the Windows connector from the same bottle.

This may help with same-bottle localhost communication, but Bluetooth behavior may be less reliable than using the native macOS connector.


## Backup downloads

Use the original connector repository first. If the original repository or a specific release is unavailable, check this repo's **Releases** page for archived connector files.

Backup files can be found in this repositories "Releases."


## Credits

SquareGolf Connector is a community project by Brent Yates. This guide is only a Mac setup walkthrough for using that connector with GSPro through CrossOver.
