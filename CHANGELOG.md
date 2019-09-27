Iotronic-standalone v2.3.7

- Device Manager:
    - Added 'maintenance' state for device
    - Fixed bug: "extra info field: when it is not in JSON format"
    - Added "state_time" attribute in "boards" DB table
    - New API to force device connection status
    
- Plugin Manager:
    - Added "autostart" attribute in "plugins_injected" DB table
    - Fixed bug in getChecksum()



```
alter table `boards` add column `state_time` TIMESTAMP NULL DEFAULT CURRENT_TIMESTAMP;
alter table `plugins_injected` add column `autostart` VARCHAR(45) NULL DEFAULT 'false';
alter table `plugins_injected` add column `on_maintenance` VARCHAR(45) NULL DEFAULT 'false';
alter table `plugins` add column `iotronic_dep` VARCHAR(45) NULL DEFAULT 'false';
```
