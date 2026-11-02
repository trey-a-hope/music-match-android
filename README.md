# Music Match (Android)

An early Android prototype from 2015-2016, and a forerunner of [inTuned](https://github.com/trey-a-hope/intuned.android). It reads the music on your phone and lists every song with its title, artist and date modified, inside a Material-style app shell with a toolbar and navigation drawer.

## What it does

- `Services/MediaService.java` queries Android's `MediaStore` for audio files marked as music, sorted by title, and turns them into `DTO/Song` objects (ID, title, artist, album, date modified).
- `MainActivity.java` shows those songs in a RecyclerView (`Adapters/SongListAdapter.java`, `res/layout/song_item_view.xml`), with a navigation drawer whose header reads "Trey's Profile" (`Navigation/AppNavigator.java`).
- `Network/` holds Volley and JSON parsing setup (`AppController`, `ConnectionManager`, `JSONParser`) for a backend that wasn't wired up yet.

## Tech stack

- Java, min SDK 14, target SDK 23 (Android Support Library 22/23, Gradle `compile` dependencies)
- Volley, Gson, Joda-Time, CircleImageView, sticky-header RecyclerView, ObservableScrollView, Caldroid, DroidParts

## Getting started

Open the project in Android Studio and run it on a device or emulator that has music files. It was last built in 2016, so expect to update the Gradle wrapper and plugin, replace `compile` with `implementation` and move to AndroidX before it builds on current tools. Newer Android versions also need the app to request the audio/storage permission at runtime before `MediaStore` returns songs.
