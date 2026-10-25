# S.A.F.E. Project - Samsung Android FOSS Environment
Shed the bloat. Shield your data. Switch to FOSS. (Work in progress)

### Instructions to build a S.A.F.E., the Samsung Android FOSS Environment ->

Samsung devices offer some of the best mobile hardware available today, but their stock software/UI comes loaded with proprietary bloatware, invasive telemetry, and hidden trackers. S.A.F.E. is designed to give you the best of both worlds: premium hardware paired with a clean, privacy-respecting software experience.

This project provides a comprehensive debloat script and a step-by-step setup guide to transform your stock OneUI device. Without the hassle of unlocking bootloaders or flashing custom ROMs, S.A.F.E. safely strips away OEM spyware and replaces closed-source applications with trusted, free, and open-source software alternatives.

By seamlessly integrating *Tracker Control* with this setup and deleting/debloating Google's applications and services, we effectively neutralize background tracking and silent data harvesting. Reclaim your digital privacy, extend your daily battery life, and take true ownership of your Samsung device. Get ready to use a smarter, safer, and fully untracked mobile phone.

## Packages that will be debloated when you run the script -->

- **android.autoinstalls.config.samsung ->** pre-installed system component on Samsung Android devices that facilitates the automatic installation of recommended or required apps during the initial device setup or after a factory reset. It functions as part of *Google's Play Auto Install (PAI) service*, where it reads a configuration file to pass a list of specific application package names to the system's package manager. This process allows manufacturers or carriers to suggest or enforce the installation of apps without permanently baking them into the device's core software.

- **com.android.apps.tag ->** developed by Google and part of the *Android Open Source Project (AOSP)*, this package handles one very specific job: interpreting `NFC (Near Field Communication)` tags. NFC is the short-range wireless tech that lets your phone do things like tap-to-pay, connect to smart devices, or scan a hotel card. It’s the same invisible tech that powers Android Beam (now deprecated), tap-to-pair accessories, and contactless transit.

- **com.android.avatarpicker ->** The *com.android.avatarpicker* package is the system app responsible for Android’s profile picture selection interface, allowing users to choose or change their avatar for device user profiles. **Google Account Sync (Android 15+):** On newer devices, it integrates with the Google Pixel Avatar App to allow users to sync their Android profile picture with their Google Account photo, ensuring consistency across the status bar and user switcher. Removing it may disrupt profile picture functionality.

- **com.android.backupconfirm ->** *com.android.backupconfirm* is a core Android system component that displays a confirmation dialog when a full backup or restore operation is initiated. It serves as a security measure to prevent silent data extraction by requiring explicit user authorization.

**Key functions include:**

**User Confirmation:** It pauses the process to ask the user to confirm if the requested full backup or restore is legitimate.
 
**Timeout Mechanism:** If the user does not respond within a designated interval (typically 30 seconds) or explicitly denies the request, no data is transferred.
 
**Trigger Events:** It is launched by system services when using ADB backup/restore, flashing custom recoveries, or performing factory data resets.

- **com.android.bips ->** *com.android.bips* is the system package for Android's `BuiltInPrintService`, which provides the Default Print Service functionality on Android devices. It enables users to discover and print to nearby printers via Wi-Fi, Wi-Fi Direct (P2P), and network protocols like `IPP` and `IPPS` without requiring third-party apps. The service handles printer discovery, certificate verification for secure connections, and manages print job queues. It is considered a standard system app and is often listed as safe-to-remove bloatware on devices like Samsung phones if printing features are not needed.

- **com.android.bluetoothmidiservice ->** The *com.android.bluetoothmidiservice* package provides the Bluetooth MIDI Service, a system-level Android service that enables Musical Instrument Digital Interface (MIDI) communication over Bluetooth and Bluetooth Low Energy (BLE). It allows Android devices to connect to external MIDI peripherals, such as keyboards or controllers, by managing the pairing and data transmission via the `MidiManager` API. Applications can use this service to open Bluetooth MIDI devices for reading and writing MIDI data, facilitating wireless connectivity for music production or control applications.

- **com.android.bookmarkprovider ->** The *com.android.bookmarkprovider* package is a system-level content provider on Android devices that centrally manages and stores web bookmarks. Its primary function is to allow multiple browser applications to access, modify, and share saved bookmark data through a standardized interface, preventing the loss of favorites when specific browsers are uninstalled. On many devices, this system component also facilitates the injection of pre-installed partner bookmarks via the related `com.android.providers.partnerbookmarks` service. This allows device manufacturers and mobile carriers to preload curated links for support pages, promotional services, or ecosystem apps directly into the user’s browser experience.

- **com.android.calllogbackup ->** The *com.android.calllogbackup* package is a built-in Android system component responsible for securely backing up and restoring your phone's call history. It operates in the background as part of the Android operating system (specifically within the `CallLogProvider` module) and performs the following functions:

**Cloud Syncing:** It syncs your incoming, outgoing, and missed call logs to your Google account (via Google Drive).

**Device Restoration:** When you upgrade to a new Android phone or factory reset your current one, this package is what pulls your saved call history from the cloud and restores it to your phone app.

**Differential Backups:** To save data and battery, the package compares your current call log with the last backup, identifying and uploading only the new calls while removing records of calls you've deleted.

**Note:** Because it is a core system function, you don't need to interact with it directly. It runs automatically when you have **Backup to Google Drive** enabled in your Android device settings.

com.android.cameraextensions

com.android.chrome

com.android.dreams.basic

com.android.dreams.phototable

com.android.egg

com.android.externalstorage

com.android.hotwordenrollment.okgoogle

com.android.hotwordenrollment.xgoogle

com.android.nfc

com.android.ons

com.android.printspooler

com.android.providers.partnerbookmarks

com.android.proxyhandler

com.android.sharedstoragebackup

com.android.traceur

com.android.wallpaper.livepicker

com.android.wallpaperbackup

com.android.wallpapercropper

com.aura.oobe.samsung

com.diotek.sec.lookup.dictionary

com.facebook.appmanager

com.facebook.services

com.facebook.system

com.google.android.adservices.api

com.google.android.apps.carrier.carrierwifi

com.google.android.apps.maps

com.google.android.apps.messaging

com.google.android.apps.restore

com.google.android.apps.setupwizard.searchselector

com.google.android.apps.tachyon

com.google.android.apps.turbo

com.google.android.appsearch.apk

com.google.android.as

com.google.android.as.oss

com.google.android.cellbroadcastreceiver

com.google.android.cellbroadcastservice

com.google.android.ext.shared

com.google.android.federatedcompute

com.google.android.feedback

com.google.android.gm

com.google.android.gms.location.history

com.google.android.googlequicksearchbox

com.google.android.health.connect.backuprestore

com.google.android.healthconnect.controller

com.google.android.ondevicepersonalization.services

com.google.android.onetimeinitializer

com.google.android.overlay.modules.cellbroadcastreceiver

com.google.android.overlay.modules.cellbroadcastservice

com.google.android.partnersetup

com.google.android.printservice.recommendation

com.google.android.projection.gearhead

com.google.android.syncadapters.calendar

com.google.android.tts

com.google.android.youtube

com.google.ar.core

com.google.audio.hearing.visualization.accessibility.scribe

com.google.mainline.adservices

com.hiya.star

com.microsoft.appmanager

com.microsoft.skydrive

com.monotype.android.font.foundation

com.monotype.android.font.samsungone

com.mygalaxy

com.opera.max.oem

com.osp.app.signin

com.samsung.aasaservice

com.samsung.adaptivebrightnessgo

com.samsung.android.accessibility.talkback

com.samsung.android.aircommandmanager

com.samsung.android.alive.service

com.samsung.android.aliveprivacy

com.samsung.android.allshare.service.mediashare

com.samsung.android.app.camera.sticker.facearavatar.preload

com.samsung.android.app.clipboardedge

com.samsung.android.app.contacts

com.samsung.android.app.dofviewer

com.samsung.android.app.dressroom

com.samsung.android.app.omcagent

com.samsung.android.app.parentalcare

com.samsung.android.app.reminder

com.samsung.android.app.routines

com.samsung.android.app.sharelive

com.samsung.android.app.smartcapture

com.samsung.android.app.spage

com.samsung.android.app.taskedge

com.samsung.android.app.updatecenter

com.samsung.android.app.watchmanagerstub

com.samsung.android.aremoji

com.samsung.android.aremojieditor

com.samsung.android.audiomirroring

com.samsung.android.authfw

com.samsung.android.aware.service

com.samsung.android.bbc.bbcagent

com.samsung.android.beaconmanager

com.samsung.android.bixbyvision.framework

com.samsung.android.bluelightfilter

com.samsung.android.calendar

com.samsung.android.cameraxservice

com.samsung.android.da.daagent

com.samsung.android.dqagent

com.samsung.android.dynamiclock

com.samsung.android.easysetup

com.samsung.android.emergency

com.samsung.android.forest

com.samsung.android.game.gamehome

com.samsung.android.game.gametools

com.samsung.android.ipsgeofence

com.samsung.android.kidsinstaller

com.samsung.android.knox.analytics.uploader

com.samsung.android.knox.attestation

com.samsung.android.knox.containercore

com.samsung.android.knox.kpecore

com.samsung.android.knox.mpos

com.samsung.android.knox.pushmanager

com.samsung.android.location

com.samsung.android.mcfserver

com.samsung.android.mdecservice

com.samsung.android.mdm

com.samsung.android.mdx

com.samsung.android.mdx.kit

com.samsung.android.messaging

com.samsung.android.mfi

com.samsung.android.mobileservice

com.samsung.android.motionphoto.app

com.samsung.android.net.wifi.wifiguider

com.samsung.android.networkdiagnostic

com.samsung.android.photoremasterservice

com.samsung.android.privateaccesstokens

com.samsung.android.provider.filterprovider

com.samsung.android.rubin.app

com.samsung.android.samsungpass

com.samsung.android.samsungpassautofill

com.samsung.android.samsungpositioning

com.samsung.android.scloud

com.samsung.android.sdk.handwriting

com.samsung.android.sdm.config

com.samsung.android.service.peoplestripe

com.samsung.android.setupindiaservicestnc

com.samsung.android.shortcutbackupservice

com.samsung.android.singletake.service

com.samsung.android.sm.devicesecurity

com.samsung.android.smartcallprovider

com.samsung.android.smartface

com.samsung.android.smartmirroring

com.samsung.android.smartsuggestions

com.samsung.android.smartswitchassistant

com.samsung.android.spayfw

com.samsung.android.stickercenter

com.samsung.android.svcagent

com.samsung.android.themestore

com.samsung.android.video

com.samsung.android.visionintelligence

com.samsung.android.vtcamerasettings

com.samsung.android.wallpaper.res

com.samsung.android.widget.pictureframe

com.samsung.android.wifi.softap.resources

com.samsung.app.newtrim

com.samsung.cmh

com.samsung.crane

com.samsung.discover

com.samsung.discover.sep

com.samsung.ecomm.global.in

com.samsung.faceservice

com.samsung.ipservice

com.samsung.knox.securefolder

com.samsung.logwriter

com.samsung.safetyinformation

com.samsung.sec.android.application.csc

com.samsung.SMT

com.samsung.SMT.lang_es_mx_f00

com.samsung.SMT.lang_pt_br_f00

com.samsung.storyservice

com.sec.android.app.billing

com.sec.android.app.camera

com.sec.android.app.chromecustomizations

com.sec.android.app.clockpackage

com.sec.android.app.factorykeystring

com.sec.android.app.fm

com.sec.android.app.hwmoduletest

com.sec.android.app.parser

com.sec.android.app.personalization

com.sec.android.app.quicktool

com.sec.android.app.safetyassurance

com.sec.android.app.samsungapps

com.sec.android.app.SecSetupWizard

com.sec.android.app.servicemodeapp

com.sec.android.app.setupwizardlegalprovider

com.sec.android.app.soundalive

com.sec.android.app.vepreload

com.sec.android.app.wlantest

com.sec.android.daemonapp

com.sec.android.diagmonagent

com.sec.android.easyMover

com.sec.android.easyMover.Agent

com.sec.android.easyonehand

com.sec.android.emergencylauncher

com.sec.android.gallery3d

com.sec.android.mimage.avatarstickers

com.sec.android.mimage.photoretouching

com.sec.android.RilServiceModeApp

com.sec.android.widgetapp.easymodecontactswidget

com.sec.app.RilErrorNotifier

com.sec.automation

com.sec.bcservice

com.sec.epdg

com.sec.epdgtestapp

com.sec.factory.camera

com.sec.factory.cameralyzer

com.sec.hearingadjust

com.sec.imslogger

com.sec.location.nsflp2

com.sec.modem.settings

com.sec.phone

com.sec.spp.push

com.sec.sve

com.sec.usbsettings

com.sec.vsim.ericssonnsds.webapp

com.skms.android.agent

com.snap.camerakit.plugin.v1

com.wsomacp
