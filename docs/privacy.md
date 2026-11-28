---
title: Media Companion Privacy Policy
permalink: /privacy.html
---

# Media Companion Privacy Policy

Effective November 28, 2026

This policy applies to Media Companion (观影助手) on Apple platforms. The services your device contacts and the information it shares depend on the features available in your version and the services you choose to use.

## Your media library, searches, and playback

- **Emby.** When you connect to an Emby server, the app uses the server address and credentials you provide to read your library, media versions, audio tracks, subtitles, and viewing status. It sends changes such as playback progress and watched status to that server according to your settings.
- **TMDB and film information.** When you search for a title, person, collection, or ID, the app sends the relevant search terms, language, region, and required authentication information to the TMDB endpoint you configured. Your device requests posters and cast photos from the corresponding image service. If you open an external link, such as Douban or IMDb, your device contacts that website.
- **MoviePilot.** When you add, edit, pause, resume, or cancel a subscription to a title, the app sends the title identifier and the options needed for that action to your configured MoviePilot server. It also reads subscription status from that server.
- **External playback.** When you select Play, the app passes the playback URL and other information needed to start playback to the external player you choose. The player uses that information to connect to your media server. Playback URLs may contain access credentials. Please keep them private.
- **Demo mode.** You can browse the sample library and try simulated subscriptions using examples included with the app, without entering credentials for a personal media server.

## Device storage and iCloud

Media Companion stores connection settings, preferences, and cached media information on your device. If you enable iCloud sync, the app stores selected language and display preferences, custom lists, manual title corrections, and service connection settings in your Apple Account’s private CloudKit database. Connection settings may include server addresses, access tokens, and API keys. The app writes the synced content to encrypted CloudKit fields.

You can turn off sync in Settings. To remove the cloud copy, choose the option to delete iCloud data. This also turns off sync. Settings already stored on your devices and records held by your media server are kept separately.

## Purchases and online services

In versions that offer Media Companion Pro, Apple processes purchases and restores. The app uses StoreKit to verify your purchase and unlock Pro features. Apple does not provide the developer with your payment card number.

When you load or refresh online preset lists, your device requests list data from GitHub. Some distributions also contact GitHub to check for or download app updates.

The servers, image services, and websites your device contacts may receive your IP address and other information needed to process a request. Each service operator determines how long it keeps its request logs.

## Managing and deleting information

You can manage service connections and clear cached data in the app. You can manage viewing history on your media server and title subscriptions in MoviePilot. If you manually export a backup, you can delete the file from the location where you saved it. To invalidate an access token, revoke it with the service that issued it.

## User support {#support}

For help with Media Companion, privacy questions, or a request to delete information you sent to support, [email Media Companion support](mailto:finly@outlook.com).

If you email support, the developer receives your email address and the information you choose to send and uses them to respond to your request. Please leave out passwords, API keys, and playback URLs containing access tokens.
