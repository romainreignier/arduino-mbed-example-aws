# Arduino version of [Mbed OS example for AWS cloud](https://github.com/ARMmbed/mbed-os-example-for-aws)

Basically, copy all the needed source files in the sketch folder and manually add all the needed `#define` in the [`arduino-cli`](https://github.com/arduino/arduino-cli) invocation.

For the [Arduino Portenta H7](https://docs.arduino.cc/hardware/portenta-h7/), build this with the following line:

```
arduino-cli compile --fqbn arduino:mbed_portenta:envie_m7 --build-property "build.extra_flags=-DMBED_CONF_APP_AWS_ENDPOINT=iot.amazon.com -DMBED_CONF_APP_AWS_CLIENT_IDENTIFIER=johndoe -DMBED_CONF_AWS_CLIENT_BUFFER_SIZE=1024 -DMBED_CONF_AWS_CLIENT_CLEAN_SESSION=true -DMBED_CONF_AWS_CLIENT_KEEPALIVE=60s -DMBED_CONF_AWS_CLIENT_SOCKET_TIMEOUT=5s -DMBED_CONF_AWS_CLIENT_PORT=8883 -DMBED_CONF_APP_AWS_MQTT_TOPIC=\"sdkTest/sub\"" .
```

Not tested, only implemented to answer [this question on the Arduino forum](https://forum.arduino.cc/t/freertos-with-portenta-h7/990973).

## License and contributions

The software is provided under Apache-2.0 license. Contributions to this project are accepted under the same license.

The following projects from Amazon (under MIT license) are included:
  * [coreMQTT](https://github.com/FreeRTOS/coreMQTT)
  * [coreJSON](https://github.com/FreeRTOS/coreJSON)
  * [AWS IoT Device Shadow library](https://github.com/aws/Device-Shadow-for-AWS-IoT-embedded-sdk)
