# S.A.F.E. Project - Samsung Android FOSS Environment
Shed the bloat. Shield your data. Switch to FOSS. (Work in progress)

Instructions to build a S.A.F.E., the Samsung Android FOSS Environment. Samsung devices offer some of the best mobile hardware available today, but their stock software/UI comes loaded with proprietary bloatware, invasive telemetry, and hidden trackers. S.A.F.E. is designed to give you the best of both worlds: premium hardware paired with a clean, privacy-respecting software experience.

This project provides a comprehensive debloat script and a step-by-step setup guide to transform your stock OneUI device. Without the hassle of unlocking bootloaders or flashing custom ROMs, S.A.F.E. safely strips away OEM spyware and replaces closed-source applications with trusted, free, and open-source software alternatives.

By seamlessly integrating Tracker Control with this setup, we effectively neutralize background tracking and silent data harvesting. Reclaim your digital privacy, extend your daily battery life, and take true ownership of your Samsung device. Get ready to use a smarter, safer, and fully untracked mobile phone.

## Packages that will be debloated when you run the script -->

android.autoinstalls.config.samsung

com.android.apps.tag

com.android.avatarpicker

com.android.backupconfirm

com.android.bips

com.android.bluetoothmidiservice

com.android.bookmarkprovider

com.android.calllogbackup

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
