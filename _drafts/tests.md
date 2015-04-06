Initial test
1. Activate motor for 100ms at the first step in boot procedure.
1. Blink led twice.
SPI memory testing.
2. Test flash memory.
3. Test FRAM memory.
SPI sensor testing.
4. Test ADXL362 sensor.
5. Test MPU9250 sensor.
6. Test connected barometers.
Manual tests
1. Press the button cause led to flash.
2. Long press the button activate the motor.

Blink led after each passed test. If error detect leave led on for 5s after boot. If test are finished blink led five times.

Test for ADXL362
1. Read SPI deviceId
2. Read & Write & Read & Write ACTIVITY TIME REGISTER
3. Read temperature
4. Self Test
Test for MPU9250
1. Read WHO_AM_I register.
2. Read & Write & Read & Write Wake-on Motion Threshold
