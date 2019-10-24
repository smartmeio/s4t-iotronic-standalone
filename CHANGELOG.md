Iotronic-standalone v2.3.7

- Device Manager:
    - Added 'maintenance' state for device
    - Fixed bug: "extra info field: when it is not in JSON format"
    - Added "state_time" attribute in "boards" DB table
    - Added APIs:
      - change device state (single and batch)
      - force device connection status
    - Improved update device info: Iotronic will inject all settings.json updated file
    
- Plugin Manager:
    - Added attributes in "plugins" DB table:
      - packaging
      - iotronic_dep
    - Added attributes in "plugins_injected" DB table:
      - autostart
      - on_maintenance
    - Fixed bug in getChecksum() function
    - Added APIs:
      - Inject plugins.json into device (single and batch)
      - Get plugins.json for the device



```
alter table `boards` add column `state_time` TIMESTAMP NULL DEFAULT CURRENT_TIMESTAMP;
alter table `plugins_injected` add column `autostart` VARCHAR(45) NULL DEFAULT 'false';
alter table `plugins_injected` add column `on_maintenance` VARCHAR(45) NULL DEFAULT 'false';
alter table `plugins` add column `iotronic_dep` VARCHAR(45) NULL DEFAULT 'false';
alter table `plugins` add column `packaging` VARCHAR(45) NULL DEFAULT 'single';
```
