# Change Log

All notable changes to "Visualkube for JetBrains IDE" will be documented in this file.
> This changelog also covers updates related to the following IDEs:  
> Android Studio, IntelliJ IDEA, PyCharm, JetBrains Gateway, DataGrip, RubyMine, GoLand, WebStorm, PhpStorm, RustRover, CLion, Rider, DataSpell, MPS

- [Change Log](#change-log)
  - [2.1.0](#210-251101)
  - [2.0.0](#200-251016)
  - [1.5.2](#152-251008)
  - [1.5.1](#151-251007)
  - [1.5.0](#150-250929)
  - [1.4.0](#140-250928)
  - [1.3.0](#130-250925)
  - [1.2.1](#121-250923)
  - [1.2.0](#120-250922)
  - [1.1.0](#110-250920)
  - [1.0.1](#101-250919)
  - [1.0.0](#100-250918)

## 2.1.0 (25.11.01)
### Improvements
- Gradle Plugin Upgrade (#1)  
  Upgraded IntelliJ Platform Gradle Plugin from 2.9.0 to 2.10.3  
  (ensures compatibility with the latest IntelliJ Platform and improves build stability)

### Security Fixes
- **Apache Commons Lang Vulnerability** (#2)  
  Fixed an uncontrolled recursion vulnerability in Apache Commons Lang (commons-lang3 v3.16.0).  
  This issue could trigger a StackOverflowError when processing very long inputs, potentially causing the application to crash.  
  The dependency has been updated to a secure version to prevent this behavior.

## 2.0.0 (25.10.16)
### Added
- Reload View: Restarts the plugin to refresh content, update caches, or reload the UI.
- Toggle Console Output: Toggles the Run/Debug console. When enabled, logs are displayed; when disabled, the console is hidden and logging is silenced.
- Clear the Instance Cache: Clears the JCEF instance cache for the current IDE. Fast to execute and useful for starting fresh without reinstalling. Required once per IDE when uninstalling.
- Clear the JCEF Cache: Clears the global JCEF cache. Helps resolve issues or return to a clean state, and is required once per device when uninstalling. The operation itself is quick, but the cache will be re-downloaded on IDE restart, which may be slow in regions with limited internet speed. This mechanism is currently being improved, and once completed, the re-download process will be significantly faster.

## 1.5.2 (25.10.08)
### Improved
- JCEF cache isolation for JetBrains IDEs (#DEV-197)  
  JCEF cache is now isolated per IDE instance, ensuring one‑to‑one alignment with each IDE.  
  This allows multiple IDEs (e.g., Android Studio, IntelliJ IDEA, PyCharm) to run side by side without cache interference, enabling smooth scaling across different versions or editions.

## 1.5.1 (25.10.07)
### Fixed
- IllegalStateException: Can't crate client in state INITIALIZATION_FAILED (#DEV-195, #196)  
  Caused by an issue where the plugin view did not appear

### Changed
- Compatibility updated: the maximum supported build number for JetBrains IDEs is now 253 (previously 252).

## 1.5.0 (25.09.29)
### Added
- Added console log output to track plugin startup progress.

### Fixed
- PluginException: Cannot init toolwindow (#DEV-173)  
  Caused by an unused indicator value being accessed outside the Event Dispatch Thread (EDT) scope.
- Background Process Indicator warning (#DEV-183)  
  Resolved the issue that could lead to visual inconsistencies.

### Improved
- Enhanced stability by resolving related warning messages in the JetBrains IDE log.

### Changed
- Updated ToolWindow icon size to 13x13 in accordance with JetBrains guidelines.
- Updated URL paths in Changelog to match the latest route changes

## 1.4.0 (25.09.28)
### Added
- Progress bar in the plugin view and an indicator in the bottom-right corner of the IDE to show loading status with messages and percentage.

### Fixed
- UI Freeze on First Run After Installation (#DEV-172)  
  Resolved an issue where the IDE could appear frozen for about 5-10 seconds when opening a project and clicking the plugin icon immediately after the first run. 
  (This resolves the Known Issue reported in version 1.3.0.)

### Improved
- View creation task to run in the background for better performance.

## 1.3.0 (25.09.25)
### Fixed
- Project Reopen Exception (#DEV-168)  
  Resolved an issue where reopening a project caused the error "*Must be called before CefApp is initialized*" and displayed "*Nothing to show*" in the plugin view.

### Known Issues
- UI Freeze on First Run After Installation  
  - Immediately after first run the plugin, opening a project and then clicking the plugin icon right now may cause the IDE UI to appear frozen for about 5-10 seconds while the plugin loads. After the plugin is loaded successfully, the IDE may display the message "*Plugin 'Visualkube' might be slowing things down.*"
  - This occurs only once after the initial run and does not reappear after reopening the project, restarting the IDE, or updating the plugin. 
    We are investigating this issue to improve startup performance in a future release.

## 1.2.1 (25.09.23)
### Improved
- Startup performance: the plugin now loads without waiting for project indexing 
  (previously showed "*This view is not available until indexes are built*").

## 1.2.0 (25.09.22)
### Added
- Integrated a self-contained JCEF into the plugin package.

### Fixed
- JCEF initialization and detection issues
  - Plugin failed to detect or initialize JCEF intermittently when using the Boot runtime switcher with a JCEF‑supported JBR. 
  - Error "*JCEF is not supported in this env or failed to initialize*" no longer appears. (This resolves the Known Issue reported in version 1.1.0.)

### Improved
- Plugin compatibility in JetBrains IDEs without requiring a JCEF-supported JBR boot runtime
- Official support for Android Studio (stabilized and verified)

### Changed
- Minimum required versions for backward compatibility:
  - IntelliJ IDEA: 2023.1.1
  - Android Studio: Hedgehog 2023.1.1 Canary 7

### Removed
- JBR boot runtime dependency with JCEF
- Boot runtime switcher for the IDE

## 1.1.0 (25.09.20)
### Added
- Introduced Boot runtime switcher for the IDE, allowing users to select a boot runtime (including JCEF-supported JBR).

### Fixed
- Resolved JCEF initialization error ("*JCEF is not supported in this env or failed to initialize*") when running the plugin in Android Studio.

### Known Issues
- JCEF initialization and detection issues  
  When using the Boot runtime switcher with a JCEF‑supported JBR, the plugin may fail to detect or initialize JCEF correctly, showing the error "*JCEF is not supported in this env or failed to initialize*".

## 1.0.1 (25.09.19)
### Added
- Initial (experimental) support for Android Studio

## 1.0.0 (25.09.18)
### Added
- Initial release with support for IntelliJ IDEA
- Core functionality of Visualkube plugin
- JBR boot runtime dependency with JCEF
