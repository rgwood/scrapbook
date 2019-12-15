## Raspberry Pi

### Temperature readings

GPU: `vcgencmd measure_temp`
CPU: `cat /sys/class/thermal/thermal_zone0/temp` (Celsius, divide by 1000)