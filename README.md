# Indego
Home Assistant Custom Component for Bosch Indego Lawn Mower

Place the files in custom-component in your Home Assistant folder for custom-componentes

    config/custom_components
    
Add the platform to your configuration.yaml

    sensor:
      - platform: indego
        name: Mower name
        username: !secret indego_username
        password: !secret indego_password
        id: !secret indego_id

Add your account (usually mail address), password and serial number to secrets.yaml: 

    indego_username: name@mail.com
    indego_password: mysecretpw
    indego_id: 123456789

Usage

There are two sensor entities:

|sensor | description|
|-------|------------|
|<name>_mower_state | This is the current state of the mower. Updated every 30 seconds.|
|<name>_lawn_mowed | This is the current percentage of the lawn that is mowed.|
|<name>_alerts | Number of alerts on the mower|
|<name>_mowing_mode | The mowing mode set for the mower|
|<name>_next_predicitve_session | Next predicted mowing session (currently not working)|


Debugging:

    logger:
      default: error
      logs:
        custom_components.indego: debug


Credits:

Fork from iMarkus/Indego (thanks for the inspiration and all your work with the basics!)

Inspiration from http://grauonline.de/wordpress/?page_id=219

Inspiration from https://github.com/jofleck/iot-device-bosch-indego-controller
