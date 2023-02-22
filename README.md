# This repo has been archived and the code is maintained in:
 - Repo: https://github.com/golles/ESPHome-Config
 - Documentation: https://github.com/golles/ESPHome-Config/blob/main/docs/PARTICULATE_MATTER.md
 - Configuration: https://github.com/golles/ESPHome-Config/blob/main/particulate_matter.yaml

---

# Particulate matter sensor moved

This is an [ESPHome](https://esphome.io/) particulate matter sensor. The shopping list (~30$) and build steps can be found on [sensor.community](https://sensor.community/en/sensors/airrohr/).

## APIS
- [api.sensor.community](https://github.com/opendata-stuttgart/meta/wiki/EN-APIs)
- [api-rrd.madavi.de](https://github.com/opendata-stuttgart/meta/wiki/EN-APIs)
- [OpenSenseMap](https://docs.opensensemap.org/#api-Measurements-postNewMeasurements)

## Device registration
For sensor.community and madavi you need to register your sensor on [devices.sensor.community](https://devices.sensor.community/). For OpenSenseMap you need to do that on [opensensemap.org](https://opensensemap.org/account).
In OpenSenseMap you can find your `Access Token` under the security options of the specific senseBoxes.

## miscellaneous
### SDS011 update interval
This sensor has a limited lifespan and shouldn't be activated too often. Setting the `update_interval` to `30min` is recommended. However, this doesn't seem to work out of the box resulting in the sensor being on continuously and pushing readings every second. This can be resolved by setting the value to `0min` first and then to `30min`. For me, I had to repeat this a few times to get this working. More info in this [ESPHome issue](https://github.com/esphome/issues/issues/1144)
