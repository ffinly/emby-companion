<p><img src="assets/images/app-icon.png" alt="Emby Companion" width="96" height="96"></p>

# Emby Companion

[简体中文](README.md) | [繁體中文](README.zh-TW.md) | **English**

---

**Discover titles, browse your library, play, and subscribe**

Emby Companion is a macOS app that brings together movie and TV lists, TMDB title and person metadata, your Emby library, and MoviePilot subscriptions.

Find something to watch through lists, title searches, or a person's filmography, then check whether it is in your library or has missing episodes. For available titles, choose a media version, server route, and external player. Send missing movies or incomplete seasons to MoviePilot for subscription.

This repository provides releases, documentation, and issue tracking. The application is closed source.

[Download Latest](https://github.com/ffinly/emby-companion/releases/latest) · [Release History](https://github.com/ffinly/emby-companion/releases) · [Report an Issue](https://github.com/ffinly/emby-companion/issues)

## Main Features

### Discover Titles Through Lists

- Browse movie and TV lists from IMDb, Douban, TMDB Popular and Weekly Trending, film festivals, and awards. See rankings and whether each title is in your library.
- View every list that includes a title from its detail page, then open a list in its original order.
- Fetch the latest list definitions from [emby-collection-sync](https://github.com/ffinly/emby-collection-sync) during synchronization, including additions, edits, removals, groups, and ordering.
- Use “Add Custom List” on the home page to add a TMDB list, or create a local list to organize your own selections.

### Home Statistics and Core List Coverage

The home page shows separate statistics for TMDB lists and your Emby library. The TMDB panel includes total lists, preset and custom list counts, unique titles across all lists, and the number of those titles already in your library.

“Core List Coverage” includes preset tiers 1–3 by default. Click the metric or “Core List Settings” to select tiers or include and exclude individual lists. Search and select all currently displayed results, then save to update the statistics. This scope affects only the coverage metric; it does not change the unique title or in-library counts across all lists.

### Search Titles and Explore Filmographies

- Search TMDB by localized or original title, person name, or TMDB ID.
- Person searches cover actors, including voice actors, directors, writers, source authors, producers, and music composers. Open a person's filmography to browse related movies and TV shows and check library availability.
- View overviews, posters, available ratings, credits, and notable works. Filter title search results by media type and library availability.
- Search for people within your Emby library and see their works in your library. Search suggestions prioritize movies and TV shows.
- Detail pages provide links to Douban, IMDb, and TMDB. Known IDs open the corresponding title directly. Without a Douban ID, search by IMDb ID first, then by title; IMDb searches use the title when no IMDb ID is available.

For titles matched to TMDB, title metadata, people, credit roles, characters, and profile image URLs come from TMDB. Unmatched titles, or titles confirmed missing from TMDB, use Emby metadata, people, and images. TMDB synchronization and manual refresh update local app data only; they do not change metadata on your Emby server.

### Choose Interface, List, and Metadata Languages Independently

Configure Interface Language, Preset List Language, TMDB Metadata Language, and Poster Language under “Connections & Settings → Language.” The interface supports System, Simplified Chinese, Traditional Chinese, and English. List and metadata languages can follow the interface or independently use any of the three languages. All three sets of preset list names are read from the upstream project.

Matched titles and people use your chosen TMDB metadata language, independently of the language used by your Emby server. Each language is cached separately and can be reused when you switch back. Changing the metadata language stops synchronization for the previous language and continues with the new one. “Refresh Details” requests the latest TMDB metadata in the current language; existing data is retained if the request fails.

Library name mapping automatically loads Chinese–English presets for common names such as movies, TV series, documentaries, concerts, Blu-ray discs, children's content, and animation. It is enabled by default in the English interface and can be enabled as needed in Chinese. The mapping window reads libraries for the current account and lets you customize display names, clear preset mappings, or reset to presets. Unmatched or blank names keep the original library name. Only the app's display names change; the Emby server is unchanged.

### Browse Your Emby Library and Collections

- Browse movies, TV shows, and Emby collections, including seasons, episodes, and playable versions.
- Combine library, media type, country or region, release year, genre, TMDB match status, and watch status filters. Year groups include the 1960s, 1950s, 1940s, and earlier years. Invalid or missing years appear under “Unknown,” and empty groups are hidden.
- Filter options keep their existing order. Use “More” to expand additional options, or double-click an empty part of the filter area to expand or collapse it.
- Sort by name, date added, release date, year, or TMDB rating.
- View and manage Watched, Watching, and Unwatched states. “Hide Watch History” temporarily hides watch status and progress; switching it off restores their display.

### Check Library Availability and Missing Episodes

Check Emby availability from lists, TMDB search, and title details. For TV shows, compare TMDB episode counts with actual episode numbers in Emby for each season. Seasons that have not been checked or have an unknown total are shown separately.

### Subscribe to Missing Content Through MoviePilot

After connecting MoviePilot, subscribe to missing movies below their posters or open the season selection panel to subscribe to incomplete seasons. Submission shows loading, checking, and processing progress immediately, and skips movies already in your library, complete seasons, and existing subscriptions.

“Subscriptions” shows movie and TV subscription counts and states separately, refreshes in the background when opened, and loads more results as you scroll. Search, refresh, pause, resume, or cancel subscriptions individually or in batches. Completed records can be resubscribed or deleted individually or in batches. A subscribed title's context or badge menu also provides cancellation and access to subscription management.

MoviePilot is optional. Downloads and library imports are handled by your configured MoviePilot service.

### Use Multiple Emby Routes and External Players

Configure multiple addresses for the same Emby server, with separate metadata synchronization and playback routes. Choose a media version, route, and SenPlayer, Infuse, or VidHub to start playback.

Version cards show file type, video quality, audio and subtitle counts, file size, bitrate, and recognizable release groups. Sources with identical full filenames and original file sizes appear together. Click a card to play. Movies with saved progress can resume or start over; TV episodes resume by default. Watched titles can still resume from the current saved position. When multiple versions provide playback timestamps, the latest record takes priority.

Episode cards show air date, overview, watch status, and progress. Playback settings control episode overviews and movie release group labels. Episode titles and overviews follow the TMDB metadata language. Metadata is fetched for a whole season and cached by show, season, and language; missing metadata retains the Emby content. Playable files, watch status, and progress still come from Emby.

Supported player versions return progress when the playback page closes normally. The app then synchronizes it to Emby. Verified progress that fails to synchronize due to a network problem is retained for retry; you can also retry from the home page. A new playback request for the same title invalidates an older retry. See [Emby Routes and Players](#en-emby-routes-and-players) for supported versions.

### Synchronize Metadata and Load Images on Demand

A full Emby library sync automatically starts TMDB metadata synchronization, fetching overviews, ratings, credits, full-season episode metadata for seasons in your library, and poster candidate URLs. Original-language, English, Chinese, and language-neutral poster candidates are cached together; image files download as you browse.

Overviews, taglines, runtimes, and credits are stored locally. Startup restores media and list caches in stages, while people and search indexes load in the background, so available content can be browsed first.

Poster Language offers Original Language, Chinese, and English. Once candidate metadata is complete, switching poster language does not require another TMDB query. Cached images can be reused immediately, while images not yet downloaded still require a connection. Metadata synchronization fills missing poster candidates in older caches without requiring you to clear them first.

Use “View Sync Details” on the home page to inspect the latest result, time, and failure reason for each title and retry failed items. Temporary network errors follow the retry policy. Titles confirmed missing from TMDB use Emby metadata, are not counted as failures, and are not repeatedly queried automatically.

## Download and Install

- Requires **macOS 14 or later**.
- Universal macOS packages support **Apple Silicon and Intel**.
- Download **Emby-Companion-v1.1.0.dmg** from the [latest Release](https://github.com/ffinly/emby-companion/releases/latest). Open it and drag **Emby Companion.app** to Applications. Quit the old version before replacing it.

Download packages from this repository's Releases. The app does not provide media files, server accounts, or third-party service credentials.

### First Launch: macOS Security Prompts

The current package is locally signed and **does not have an Apple Developer ID signature or notarization**. On first launch, macOS may report that it cannot verify the developer or the app.

After confirming that the package came from this repository's Releases:

1. Drag the app to Applications and try opening it once.
2. If macOS blocks it, open **System Settings → Privacy & Security**.
3. Find the Emby Companion notice and click **Open Anyway**.
4. Authenticate as requested, then click **Open** in the confirmation dialog.

The app can usually open normally afterward. If macOS reports that the app is damaged, detects malware, or provides no matching approval option, verify the download source, download it again, and report the exact message. Do not treat every block as the same signature prompt.

See [Apple's guidance on opening apps safely on your Mac](https://support.apple.com/zh-cn/102445). Button labels can differ between macOS versions. Refer to each Release for the signing and notarization status of later packages.

## Getting Started

1. Enter your Emby server address and sign in under “Connections & Settings.”
2. Before using TMDB features, request your own API Key in [TMDB API settings](https://www.themoviedb.org/settings/api) and enter it in the app. Read the [API terms of use](https://www.themoviedb.org/api-terms-of-use) first.
3. Run “Full Library Sync” and synchronize lists from the home page. Library synchronization automatically starts TMDB metadata synchronization. List synchronization fetches the latest definitions and expands list groups when complete. Follow progress and results on the home page.
4. Install SenPlayer, Infuse, or VidHub. Open an available title and choose a media version, playback route, and player.
5. To subscribe to missing content, copy the API token from MoviePilot's “Settings → System → Basic Settings” and enter it in the app's MoviePilot configuration. Configure an HTTP or SOCKS proxy for TMDB in the app settings if needed.

<a id="en-emby-routes-and-players"></a>

### Emby Routes and Players

Multiple routes to the same Emby server share the local library cache. The synchronization route reads media, episode files, and collections. Playback routes handle playback and watch-history-only synchronization. Set a default playback route; route selection is omitted when only one valid route exists. You can also open an `ecplayer://importserver` link in a browser to preview the account and route purposes before confirming an import. See “Emby Routes → Import Emby via Link” for the format. The same server and account reuse local caches; importing does not clear TMDB metadata, posters, lists, or MoviePilot settings.

| External Player | Versions Supporting Progress Callbacks |
| --- | --- |
| SenPlayer | 6.1.1 or later |
| Infuse | 8.4.7 or later |
| VidHub | 2.3.5 or later |

Enable “Sync Progress After Playback” in settings and close the player's playback page normally. Once a callback is received, the app synchronizes progress to Emby. Force-quitting the player or receiving no callback prevents that callback from updating progress. Players must be installed separately; callback support depends on the player version and the data it returns.

You need to provide your own Emby server, external players, and MoviePilot service. MoviePilot is needed only for subscriptions, not for browsing your library or launching a player.

## Versions and Updates

View the current version and update-check time under “Connections & Settings → Software Update.” GitHub project, Releases, and issue links are under “About.”

- **Check for Updates** checks the latest stable GitHub Release, skipping prereleases and drafts.
- **Automatically Check for Updates** checks every 24 hours while the app is running. You can also check manually; failed checks or downloads are retried later.
- **Automatically Download Updates** downloads a discovered update without immediately quitting the app.
- **Install Update** guides you through installation and relaunch after verification.

Update packages use a separate signature and integrity verification. A failed download or verification stops installation; retry or download from GitHub instead.

## Cache & Data

“Connections & Settings → Cache & Data” provides information and maintenance options for three areas:

- **TMDB Cache:** View metadata, poster and person image storage, usage by metadata language, and the number of TMDB people linked to titles in your library. Clear the full TMDB cache or choose individual cleanup categories in “TMDB Cache Cleanup.”
- **Emby Cache:** View media, episode file, collection, and Emby image counts. Clearing removes those local records, Emby images, cached watch history, and related indexes while retaining TMDB API metadata, posters, and person image files. Synchronize again from the home page afterward. Connection settings, sign-in information, and server data are retained.
- **Local Search Index:** Automatically maintained from local Emby titles, collections, and people. Rebuild it if search behaves incorrectly; rebuilding needs no connection and does not modify watch history.

“TMDB Cache Cleanup” can remove title and episode metadata in other languages, images outside your poster language preference, and caches no longer referenced by lists or your library. Other-language metadata cleanup retains the current language, poster paths, and images. Image cleanup retains images needed for the selected preference and its fallbacks; Chinese posters include both Simplified and Traditional Chinese.

Caches with no references, additions, or updates for seven consecutive days are cleaned automatically while the app is idle and its reference information is complete. Switching languages alone does not delete other-language metadata. After clearing the full TMDB cache, synchronize lists and your library again from the home page; images continue to download on demand. Routine use does not require rebuilding the search index manually.

## Backup & Restore

Export configuration and local data as an encrypted backup, or restore a backup, under “Connections & Settings → Backup & Restore.”

| Backup Component | Included Data |
| --- | --- |
| TMDB API Configuration | API address and API Key |
| MoviePilot API Configuration | Service address and API token |
| TMDB Lists | List contents, local lists, list settings, and core list selection |
| TMDB Cache | Title and person metadata, posters, and person images |
| Emby Configuration | Server, routes, current account, sign-in token, and watch history |
| Emby Cache | Library, collections, episodes, and Emby images |
| Preferences | Interface, list, metadata, and poster languages; name mappings; player and display preferences |

Choose which components to export. Enter and confirm a password of at least eight characters, then save the `.ecbackup` file.

To restore, select a backup and enter its password. Only components contained in that backup are shown, and you can choose which to restore. Selected configuration, lists, and preferences replace the corresponding local data; caches are merged and search indexes update automatically.

Selected core tiers and individual list inclusions and exclusions are backed up and restored with “TMDB Lists.” Restoring only lists leaves unselected language, playback, and display preferences unchanged.

Watch history is included with Emby configuration and contains only the current account's watch states and playback progress. Restore checks the server and account and keeps newer watch history.

Backups contain API keys and sign-in information. Keep the file and its password secure.

## Network Access and Privacy

Connection information and caches are stored locally. Depending on the features you use, the app sends requests to your configured services, TMDB, and GitHub. GitHub list-definition and update requests do not contain your TMDB API Key or Emby credentials.

When reporting an issue, include the app version, macOS version, steps to reproduce, and error message. Hide server addresses, accounts, passwords, API keys, proxy credentials, and other private information in screenshots or logs.

## 📈 Star History

<a href="https://www.star-history.com/?repos=ffinly%2Femby-companion&amp;type=date&amp;legend=top-left">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://api.star-history.com/chart?repos=ffinly/emby-companion&amp;type=date&amp;theme=dark&amp;legend=top-left" />
    <source media="(prefers-color-scheme: light)" srcset="https://api.star-history.com/chart?repos=ffinly/emby-companion&amp;type=date&amp;legend=top-left" />
    <img alt="Star History Chart" src="https://api.star-history.com/chart?repos=ffinly/emby-companion&amp;type=date&amp;legend=top-left" />
  </picture>
</a>

## License and Third-Party Notices

See the [software license](LICENSE.txt) for the application's terms of use.

Rights to media content, metadata, images, likenesses, and third-party marks belong to their respective owners. The independent open-source components used by the app have their own licenses; see [Third-Party Notices](THIRD_PARTY_NOTICES.md). The app's license does not replace the terms of the services you use.

## TMDB Attribution

<a href="https://www.themoviedb.org"><img src="assets/images/tmdb-logo.svg" alt="TMDB" width="120"></a>

This product uses the TMDB API but is not endorsed or certified by TMDB.

[The Movie Database](https://www.themoviedb.org) · [API Terms of Use](https://www.themoviedb.org/api-terms-of-use)

The names and marks of Emby, MoviePilot, the players, and TMDB belong to their respective owners. This app is not affiliated with or endorsed by those services.
