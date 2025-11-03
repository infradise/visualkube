# Change Log

All notable changes to "Visualkube for VS Code" will be documented in this file.  
> This changelog also includes updates related to the following IDEs:  
> Visual Studio Code, VSCodium, Eclipse Theia IDE, WindSurf IDE, Trae IDE, Cursor IDE

- [Change Log](#change-log)
  - [1.1.0](#110-251103)
  - [1.0.7](#107-251004)
  - [1.0.6](#106-250926)
  - [1.0.5](#105-250908)
  - [1.0.4](#104-250904)
  - [1.0.3](#103-250903)
  - [1.0.2](#102-250902)
  - [1.0.1](#101-250901)
  - [1.0.0](#100-250901)

## 1.1.0 (25.11.03)
- Bumped Visualkube engine 5.9.1 (Build 2426) to **5.10.31 (Build 2428)**.

## 1.0.7 (25.10.04)
### Universal
- Fixed broken "Reset State for Testing" functionality  
  (triggering the command resulted in "command 'visualkube.resetState' not found")

### Universal / Web
- Added the "RUNTIME CONTEXT" section to indicate whether the runtime is Universal or Web
- Renamed the section "DASHBOARD" to "CONTROLLER"
- Renamed the menu item "Reset State for Testing" to "Reset State"
- Removed the All Platforms Guide
- Removed the Help and Feedback section

## 1.0.6 (25.09.26)
- Fixed issue where the error "'configuration.icons.description' must be defined and can not be empty" appeared (#DEV-171)
- Updated URL path links to reflect changed routes
- Removed "What's New" section items

## 1.0.5 (25.09.08)
- Added support for Visual Studio Code for the Web (vscode.dev)
- Made the extension available on vscode.dev
- Introduced an Activation Bar in Visual Studio Code
- Reduced minimum required VS Code version to 1.85.0 for backward compatibility

## 1.0.4 (25.09.04)
- Reduced minimum required VS Code version to 1.95.0 for backward compatibility

## 1.0.3 (25.09.03)
- Bumped Visualkube engine 5.8.22 (Build 2426) to **5.9.1 (Build 2426)**.
- Removed unnecessary fonts, reducing .vsix package size by 70M

## 1.0.2 (25.09.02)
- Bumped Visualkube engine 5.8.16 (Build 2425) to **5.8.22 (Build 2426)**.
- Added license

## 1.0.1 (25.09.01)
- Fixed broken links in README (Getting stared, Changelog sections)
- Fixed app icon is missing

## 1.0.0 (25.09.01)
- Powered by Visualkube engine **5.8.16 (Build 2425)**.
- Initial release