# Differences between Bluetooth LE and classic Bluetooth
There are two types of Bluetooth devices: one is referred to as Bluetooth Classic (BR/EDR) and the other is Bluetooth Low Energy (BLE).
Generally speaking, classic Bluetooth is mainly used for audio such as wireless telephone connections, wireless headphones and wireless speakers. Bluetooth Low Energy is more often seen in wearable devices, smart IoT devices, fitness monitoring equipment, and battery-powered accessories such as a keyboard.

Actually, the term ‘classic Bluetooth’ isn’t completely accurate. In the Bluetooth 4.0 specification, the SIG defined the four Bluetooth controller technologies: BR, EDR, AMP and LE.Since LE was proposed in 2010 and is relatively new, people call the former BR/EDR/AMP technology ‘classic Bluetooth’ technology for convenience.

Choose BLE or Bluetooth Classic depends on what you’re trying to accomplish. They are used for different purposes.Bluetooth cost a lot more than BLE and can handle a lot of data, as a result it consumes battery life quickly.
BLE is used for application that don't need to exchange a lot of data therefore it consume a lot less battery power and cost cheaper than Bluetooth.

When developing Bluetooth applications, you must be clear which version to use as they work differently. Each one has different physical layer modulation and demodulation methods. This means that Bluetooth LE and classic Bluetooth devices cannot communicate with each other. If the master device is a Bluetooth LE device, the slave device must also be a Bluetooth LE device.
There is a dual-mode Bluetooth device in the market, which supports both Bluetooth LE and classic Bluetooth. Cell phones are the most common example. Most modern smartphones can communicate with both classic and LE devices.

To conclude, thereʼs a big difference between Bluetooth Classic and Bluetooth Low Energy in terms of technical specification, implementation, and the types of applications to which theyʼre each suited. This is in addition to the fact that they are incompatible with each other.