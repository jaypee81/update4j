
* **1.3.3**
  * Properly escape special chars in output XML. Allow control chars in properties.
  * Renamed `UpdateHandler::connect` to `UpdateHandler::openDownloadStream`
  * Added 2 more `Configuration.Builder::signer` overloads.
* **1.3.2** *— h/t [@ChristianCiach](https://github.com/ChristianCiach)*
  * Control how files are downloaded with `UpdateHandler::connect`.
  * Delete old files with `Configuration::deleteOldFiles`.
* **1.3.1**
  * `DefaultBootstrap` sync local now creates directories to write local config.
  * `DefaultBootstrap` remote signature failure would not fall back to local.
* **1.3.0**
  * Rewrite of `DefaultBootstrap`.
  * You can now sign the configuration itself to ensure integrity of non-file elements, as paths and properties.
  * `FileMetadata.getSignature()` now returns a `String` instead of `byte[]` to avoid modification.
  * Java 11 compatibility: Removed JavaFX modules.
  * Fixed single instance bug on Linux.
  * Connection/read timeouts at 10 seconds.
  * Safer file overriding by properly handling file locks.
  * `ConfigMapper` and `FileMapper` lists are now `final`, to prevent accidental `NPE`.
  * `FileMetadata::streamDirectory` now automatically presets `path` attribute to actual filename _relative to_ the streaming directory, instead of absolute source path.
* **1.2.2**
  * Removed `DefaultUpdateHandler` percentage output to avoid problems with Eclipse console.
  * Added `DefaultBootstrap` with a straightforward CLI, and `DefaultLauncher`.
  * Added `Configuration.sync()` methods.
  * Additional file validation on update and renaming `UpdateManager.verifyingFileSignature()` to `validatingFile()` to include all of them.
  * To avoid version inconsistencies, all downloads are now atomic; if one download fails all previous are rolled back. Updated `UpdateHandler.doneDownloadFile()` to add awareness of this.
  * Fixed bug when downloading automatic module with no `Automatic-Module-Name` in `META-INF/MANIFEST.MF`.
* **1.2.1**
  * _Retracted, didn't correctly set main class in module descriptor._  
* **1.2.0**
  * Bug fixes.
  * Major redo of Configuration builder API.
  * Reduced dependencies to zero.
  * Renamed `Library` to `FileMetadata` and `<library>` XML element to `<file>`.
  * Warnings if files were incorrectly added to the boot classpath.
  * Reject download if module name or package name conflicts with a module on the boot modulepath and additional `ignoreBootConflict` attribute to `<file>` to override it.
  * Directly pass instances of service providers instead of locating providers.
  * Removed deprecated methods.
* **1.1.3-beta**
  * `Library.Reference.Builder` no longer automatically sets `modulepath` to true.
  * Warn on `Configuration::launch` if there is no library that has set either `classpath` or `modulepath` to true.
* **1.1.2-beta**
  * Added `LaunchContext.getClassLoader()` method.
* **1.1.0-beta**
  * Added full support of loading jars into the classpath.
  * Added "add exports/opens/reads" support.
  * Renamed `ImplicationType` to `PlaceholderMatchType`.
* **1.0.0-beta.1**
  * Deprecated verification via a `Certificate`, use `PublicKey` instead. Will be removed completely once it graduates beta.
* **1.0.0-beta**
  * Initial release.

