# LR1110 EVK demo application changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/), and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [v2.1.0] 2020-10-30

### Added

- Automatic assistance location update

### Changed

- Upgraded LoRa Basics Modem-E driver to v2.0.1

### Fixed

- Wrong default assistance location in NAV message

## [v2.0.0] 2020-10-15

### Added

- Support for Modem-E
  - GNSS and Wi-Fi location with the Modem-E
  - Send the location requests compatible with Node-Red LoRa Cloud utils example
  - Demo for radio testing of the Modem-E
  - Join procedure
  - Corresponding GUI pages

### Changed

- `AlmanacUpdate` can use GLS or DAS server
- Host code compatible with python 3.5
- Reset the chip at the boot of the application

### Fixed

- Fix `FieldTestPost` so it can handle result files that does not provide the version line
- Bug in ping-pong demo where the master was never receiving correctly the slave pong
- Bug with deadlock of Wi-Fi demo
- Compilation warnings due to wrong `printf` format and missing cases in `switch/case`

## [v1.4.0] 2020-10-09

### Changed

- Use GLS for solvers
- Fix warning in host code

## [v1.3.1] 2020-10-05

### Fixed

- RF switch configuration when the HP power amplifier is selected
- Serial communication error because of a badly handled value of Wi-Fi type when transmitting scan results
- FieldTestPost crashes when the result file does not contain the version information (not requested by the solver actually)

## [v1.3.0] 2020-06-06

### Added

- Radio interface class for radio test modes
- Device abstraction so that demonstrations do not rely on the device being only a transceiver
- Wi-Fi result type is now configurable
- Intermediary class between `GuiCommon` and `GuiMenu` classes
- `CommunicationInterface` and `CommunicationManager` classes to unify the way the application communicates with the outside world

### Changed

- Start and configure frames in HCI are merged - a start frame now selects a demo, configure it and start it in a row
- GNSS helper methods are now implemented in device specific class
- Cleaned Python standard output of demonstration
- Reformatted Python source code
- `Screen` member is now handled in `GuiCommon` class
- LR1110 driver is now v2.0.1

### Fixed

- Replaced switch / case with ternary operator for boolean values
- LR1110 driver version is not fetched properly

### Removed

- Automatic mode in demonstration runtime
- Usage of Unidecode library in Python host application

## [v1.2.0] 2020-04-28

### Added

- Initial version
