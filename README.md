[![Donate](https://img.shields.io/badge/donate-Pizza-yellow.svg)](https://www.buymeacoffee.com/ntguest)
[![Donate](https://img.shields.io/badge/donate-Yandex-blueviolet.svg)](https://yoomoney.ru/to/410011383527168)
# SolaMon
### Monitor and control a hybrid solar inverter with Esphome and Home Assistant

### Wiring

If your device doesn't have an RS485 interface, you need to buy a conversion module.

![image](https://github.com/user-attachments/assets/3af6374a-4025-4d2a-9892-c483ee2821ac)


[I buy it here](https://www.aliexpress.com/item/1005005977004769.html)


![image](https://github.com/user-attachments/assets/e97e4c5b-83d4-4d09-9261-57851b7ace93)


### Software installation

In your own yaml file:
* Specify the Substitution section with pins used for communication;
* Add link to remote package;
* Create new project subdirectory within your ESPHome configuration directory (let it be solamon, for example)
* Copy the helpers folder to a newly created project directory
* Enjoy.

  
```
substitutions:
  inverter_tx_pin: GPIO17
  inverter_rx_pin: GPIO16
  update_interval: 12s
  inverter_voltage_offset: "0"
  select_skip_updates: "2"
  device_name: solamon

packages:
  remote_package:
    url: https://github.com/ntguest/SolaMon
    ref: main
    files:
      - solamon.yaml
```
