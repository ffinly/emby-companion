<p><img src="assets/images/app-icon.png" alt="Emby Companion" width="96" height="96"></p>

# Emby Companion

[简体中文](README.md) | [繁體中文](README.zh-TW.md) | **English**

---

**Elegantly Explore, Subscribe, and Play Your Emby Library**

Emby Companion is a macOS app for finding your next movie or TV show. Explore curated lists, studios, and the work of your favorite actors and directors. Connect Emby to check library availability and missing episodes, then keep watching with your preferred player as progress syncs back to your library.

**An Emby server is optional.** Add your own TMDB API Key to browse lists, explore 48 studios and platforms, search titles and people, and view ratings and overviews. Connect Emby and a subscription service whenever you need them.

[Download Latest](https://github.com/ffinly/emby-companion/releases/latest) · [SSPAI article (Chinese)](https://sspai.com/post/116958) · [Release History](https://github.com/ffinly/emby-companion/releases) · [Issues & Suggestions](https://github.com/ffinly/emby-companion/issues/new/choose)

This repository provides releases, documentation, and issue tracking. The app is closed source and does not provide media, server accounts, or third-party credentials.

## Interface Preview

Screenshots show Liquid Glass on macOS 26 or later and automatically switch with the page’s light or dark theme. Earlier versions use the classic appearance.

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/images/home.en.dark.png">
  <source media="(prefers-color-scheme: light)" srcset="assets/images/home.en.png">
  <img src="assets/images/home.en.png" alt="Emby Companion: Home and studio discovery">
</picture>

*Explore studios from Home. Connect and sync Emby to show your libraries; Continue Watching appears when resumable items are available.*

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/images/poster-wall.en.dark.png">
  <source media="(prefers-color-scheme: light)" srcset="assets/images/poster-wall.en.png">
  <img src="assets/images/poster-wall.en.png" alt="Emby Companion: list filters and poster grid">
</picture>

*Browse movie and TV lists, filter titles, and check availability in your Emby library.*

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/images/what-to-watch.en.dark.png">
  <source media="(prefers-color-scheme: light)" srcset="assets/images/what-to-watch.en.png">
  <img src="assets/images/what-to-watch.en.png" alt="Emby Companion: What to Watch">
</picture>

*What to Watch: Find your next movie or TV show in Core Lists or your library.*

## Main Features

### Discover Movies and TV

- **What to Watch:** After connecting Emby, syncing your library, and completing its TMDB metadata, pick movies and TV shows from titles available in Core Lists or your entire library, with unwatched filtering, a full-screen poster wall, and independent light and dark appearance. Collection sync and metadata completion for titles outside your library do not block entry.
- **Discover through lists:** Browse IMDb, Douban, TMDB, festival, and award lists with rankings and library status. See which lists include a title from its details. Presets follow [emby-collection-sync](https://github.com/ffinly/emby-collection-sync/blob/main/README.en.md); import online lists through “Add TMDB List.”
- **Studio discovery:** Explore titles from 48 studio and platform entries across Movie Studios, Animation Studios, Western TV, and Asian TV, with filters and library, watch, and subscription status.
- **Search titles and people:** Search by title, person, collection name, or ID, including TMDB and IMDb IDs and title links. Leave the title blank to browse popular titles in the selected region. Explore taglines, overviews, ratings, credits, and filmographies. Expand a cast or crew member’s other library titles inline in details, or follow links to Douban, IMDb, and TMDB.
- **Core List Coverage:** Includes tiers 1–3 by default. Select tiers or include and exclude individual lists, then save to update deduplicated statistics. The home page's total unique titles and in-library count still cover all lists. You can also choose which list opens from Home.

### Your Library and Playback

- **Home and Continue Watching:** Browse Emby libraries and resume the matching media version with your default player and route. Open the full view to see all entries.
- **Browse your library:** Explore Emby movies, TV shows, collections, seasons, episodes, and playable versions. Filter movies, TV shows, or short films, and manage watch states. In Settings → Privacy, hide watch history and progress, or independently hide Libraries or Continue Watching on Home.
- **Episode groups:** When groups are available, view the automatic recommendation or switch groups manually from the season menu in the series playback section. Episode titles and summaries follow the selected group; season and episode numbers and playback order stay the same.
- **Check availability and missing episodes:** Use synchronized Emby data to check library status and check missing seasons and episodes against the current season arrangement or episode group, including missing episode numbers. Unchecked seasons and unknown totals are identified separately. Checking missing episodes works without MoviePilot; subscribing requires it.
- **Multiple routes and external players:** Set separate synchronization and playback routes for the same Emby server, then choose a version to launch SenPlayer, Infuse, or VidHub with resume playback and progress callbacks. Matching parts share a version card and Continue Watching entry; select a `PART 1`, `DISC 2`, or other original file marker to resume, with the last-watched part selected by default and full filenames available on hover. Each part keeps its own progress; full-length versions still sync progress with one another.

### Subscriptions, Caches, and Backups

- **MoviePilot integration:** Subscribe to missing movies or incomplete seasons, skipping available movies, complete seasons, and existing subscriptions. Search and manage subscriptions individually or in batches. MoviePilot is optional and handles downloads and library imports.
- **Metadata and image caches:** List and library syncs automatically complete TMDB metadata in your selected language for country and genre filters and title details. Connecting Emby also enables caching of person and full-season episode metadata. Images load on demand. Inspect sync results, retry failures, manage caches, or rebuild the local search index.
- **Backup and restore:** Choose configuration, lists, caches, and preferences for encrypted export and selective restore.

## Languages and Display

Set interface, preset list, TMDB metadata, and poster languages independently under “Connections & Settings → Language.” The interface supports System, Simplified Chinese, Traditional Chinese, and English. List and metadata languages can follow the interface or use any of the three languages independently.

List synchronization reads and caches upstream names in all three languages, so switching between cached names needs no new download. Title and person metadata, episode details, and titles shown in sync history follow the **TMDB Metadata Language**, with separate caches for each language. Available Emby data is retained when corresponding metadata is missing. Refreshing metadata updates local data only, leaving server metadata unchanged.

Posters can use the original language, Chinese, or English. Cached images are reused; uncached images still require a connection. Library name mapping supports Chinese–English presets and custom display names. Blank mappings keep the original name, and changes apply only within this app.

Under “Connections & Settings → Appearance,” choose Automatic (the default, following the system), Light, or Dark mode, adjust poster size, and switch between Liquid Glass and the classic appearance on supported systems.

## Keyboard Shortcuts (macOS)

| Shortcut | Action |
| --- | --- |
| ⌘1 / ⌘2 / ⌘3 | Home / TMDB Search / Emby Library |
| ⌘4 | What to Watch |
| ⌘5 | Last list or studio visited in this session; opens the default list when none has been visited |
| ⌘6 | Subscriptions (requires MoviePilot configuration) |
| ⌘, / ⌘R / ⌘F | Settings / Refresh the current page / Search |
| ⌘[ | Go back; close the current details when open |
| ⌘] | Go forward in browsing history, when available |
| Arrow keys | Move between title and episode cards; switch titles while previewing |
| Space | Preview the hovered or keyboard-selected title; press again to close |
| Return | Open full details; activate the focused option in playback dialogs |
| Esc | Close the current preview, details, or playback dialog; clear selection when no overlay is open |
| Tab / Shift+Tab | Change playback-dialog options; arrows and hover also select, and clicking outside dismisses |

**Inside the full-screen poster wall:** P pauses or resumes drift, and D switches between light and dark. Press Esc on the wall, then press it again within three seconds to return.

On other browsing pages, Space works over both the poster and the text below it. Scrolling retains the selected card. If it leaves the viewport, or keyboard navigation restarts after switching to the mouse, navigation begins at the first fully visible card.

When a text field has focus, arrow keys, Space, Return, and Esc retain their normal text-field behavior. ⌘F selects all existing search text. Submitting a search releases text focus without selecting a result; press an arrow key to start selecting cards.

## Download and Get Started

Requires **macOS 14 or later**. Universal packages support **Apple Silicon and Intel**. Download the DMG from the [latest Release](https://github.com/ffinly/emby-companion/releases/latest) and drag **Emby Companion.app** to Applications. Quit the old version before replacing it.

### First Launch: macOS Security Prompts

The current package is locally signed and has no Apple Developer ID signature or notarization. After confirming it came from this repository's Releases, try opening it once. If blocked, go to **System Settings → Privacy & Security → Open Anyway** and follow the prompts. See [Apple's guidance](https://support.apple.com/en-us/102445).

<details>
<summary>Alternative: use Terminal to address first-launch restrictions</summary>

Use this only after confirming the package came from this repository's Releases and moving the app to Applications:

```bash
xattr -rd com.apple.quarantine "/Applications/Emby Companion.app"
```

If permission is denied, add `sudo` before the command.

This command removes the app's download quarantine attribute; it cannot repair genuinely damaged files. If macOS explicitly reports malware, stop opening the app and report the exact message.

</details>

Later packages' signing status is listed in their Release notes.

### First-Time Setup

On a fresh installation, Home shows “Quick Setup,” where you can configure the basics or restore a backup. Existing users can reopen it under “Connections & Settings → About → Quick Setup.”

1. **Configure TMDB API:** You can request your own API Key free for personal use. Expand “How to Get an API Key,” follow the steps to open [TMDB API settings](https://www.themoviedb.org/settings/api), read the [API terms](https://www.themoviedb.org/api-terms-of-use), enter the **32-character API Key (v3)**, and click “Test and Save.” Do not enter the longer API Read Access Token.
2. **Configure Emby Server (optional):** Enter the server address, username, and password, then click “Sign In & Sync Emby.” Your library syncs in the background; Emby Premiere is not required. You can skip Emby and still browse lists, search, and explore studios.
3. **Configure MoviePilot Subscriptions (optional):** Enter the service address and an API token of at least **16 characters**, then click “Test and Save.” Copy the token from MoviePilot's “Settings → System → Basic Settings.” Skip this step if you do not use subscriptions; skipping Emby also skips this step automatically.
4. Once TMDB is configured and the optional steps are configured or skipped, click “Get Started.” Lists and library data continue syncing in the background. To play media, separately install a supported external player listed below.

Keep the default TMDB API and image addresses unless you use your own reverse proxy. “TMDB Proxy” applies only to TMDB metadata, images, and lists; when disabled, TMDB follows the system proxy. Software updates, Emby, and MoviePilot always follow the system proxy.

TMDB and MoviePilot settings can be cleared separately. Sign out of Emby before clearing TMDB settings; proxy settings are kept. Signing out of Emby clears its address, account, token, routes, local library, dedicated images, and search index. TMDB lists, shared caches, MoviePilot settings, and app preferences are kept. Pending playback progress is retained separately and resumes syncing only after signing back in to the original server and account. Media and watch history on the server are not modified.

<a id="en-emby-routes-and-players"></a>

## Routes and Players

After signing in, add and manage routes under “Connections & Settings → Emby → Multiple Connections.” Routes for the same server and account share the library cache. Set the main synchronization route and default playback route separately, or preview and import settings through an `ecplayer://importserver` link. See “Emby Routes → Import Emby from a Link” in the app for its format.

| External Player | Versions Supporting Progress Callbacks When the Playback Window Closes |
| --- | --- |
| SenPlayer | 6.1.1 or later |
| Infuse | 8.4.7 or later |
| VidHub | 2.3.5 or later |

Playback progress syncs automatically, with no switch to enable. **Close the playback window to sync progress. Do not quit the player directly.** The app uses only the actual position returned by the player and never estimates progress without a valid callback. If a network error prevents synchronization, retry from the home page. Players must be installed separately.

Keep this app running during playback to maintain the Emby session and playback history. Closing this app’s window keeps heartbeats running; quitting this app or detecting that the player has exited stops them. Valid progress callbacks that arrive later can still be received.

Open “Connections & Settings → Playback → View Playback Logs” to inspect player launches, heartbeats, callbacks, and synchronization. Filter, search, view records by playback request, or export `.log` files. Records and expanded ping details load automatically as you scroll. Successful pings are hidden by default and grouped in the full view. Logs stay on this device for up to seven days and 20,000 entries, excluding playback links and credentials.

## Software Updates

Check manually or enable automatic checking and downloading under “Connections & Settings → Software Update.” Downloads show progress and can resume after interruption. After verification, you choose when to install and relaunch; failed verification stops installation. If an update fails, you can view and copy diagnostic details for that attempt.

Multilingual release notes follow the current interface language. Older notes available in only one language retain their original text.

## Caches and Backups

“Connections & Settings” provides cache cleanup, local search index rebuilding, and encrypted backups. Clearing local caches does not delete Emby server content. Connection and sign-in information remain, and you can synchronize again afterward. “TMDB Cache Cleanup” can clear search result caches separately while keeping lists, library metadata, and images.

| Backup Component | Included Data |
| --- | --- |
| TMDB API Settings | API address, image address, and API Key |
| MoviePilot API Settings | Service address and API token |
| TMDB Lists | List contents, custom lists, list settings, and core list selection |
| TMDB Cache | Title, episode, person, and episode group metadata and images |
| Emby Settings | Server, routes, current account, sign-in token, and watch history |
| Emby Cache | Library, collections, episodes, episode group selections, and Emby images |
| Preferences | Language, appearance, playback and privacy preferences |

Choose what to export, set a password of at least **eight characters**, and save the `.ecbackup` file. Components for unconfigured services cannot be selected. When importing, choose again from the components included in the backup: configuration, lists, and preferences replace corresponding data, while caches are merged. Core list selection is included with “TMDB Lists.” Watch history is included with “Emby Settings” for the current account only; restore checks the server and account and keeps newer records.

Backups may contain API keys and sign-in information. Keep the file and password secure.

## Privacy and Feedback

Connection information and caches are stored locally. Features send requests to your configured services, TMDB, and GitHub. GitHub list-definition and update requests do not include your TMDB API Key or Emby credentials.

Report bugs or suggest features through [GitHub Issues](https://github.com/ffinly/emby-companion/issues/new/choose), choosing the appropriate template.

When reporting issues, click “Export Diagnostics” under “Connections & Settings → About” and attach the generated `.txt` file, steps to reproduce, and an error screenshot. The file summarizes the version, configuration, cache and sync status, recent errors, update diagnostics, and logs from up to the **10 most recent playback sessions**, with consecutive successful pings summarized. Exporting makes no new network requests.

Diagnostics automatically hide server addresses, accounts, credentials, file paths, and title identifiers. Title names are replaced with consistent aliases within each file, and text follows the interface language at export time. The in-app playback logs and their separate export retain real titles; hide viewing content and private information before sharing those logs or screenshots.

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
