# ModbusRaspberryPico

## RS485 Network Setup with Raspberry Pi Pico

## Switch address tree
```
8- 1
7- 2
6- 4
5-  8
4-  16
3 - 32
2 - 64
1 - 128
```

## Requirements

- Raspberry Pi Pico
  - ![Pico Board](https://github.com/Ayocrypt/ModbusRaspberryPico/blob/main/RPI_pico.jpg)
- TTL to RS485 Converters (one per switch network)
  - ![RS485 TTL](https://github.com/Ayocrypt/ModbusRaspberryPico/blob/main/RS485_ttll.jpg)
- Modbus Eight Switches and Eight Relay Channels
- CAT6 Cable
- 12V Power Supply (Ensure sufficient current for all)
- 5V Power Supply (use separate supplies based on capacity)
- Resistors for Line Termination (not needed)

## Purpose

- **Separate TTL to RS485 Converters**: Each switch network requires its own converter for reliability and reduced interference.

## Configuration

### Network Details

1. **Network 1:**
   - **Switch Slave Address**: `129`
     - Switch Panel: Turn on button 1 and button 8
   - **Relay Slave Address**: `1`
     - Relay Panel: Turn on button 1 
   - **Python**: `(switch slave address = 129, relay slave address = 1)`

2. **Network 2:**
   - **Switch Slave Address**: `65`
     - Switch Panel: Turn on button 2 and button 8
   - **Relay Slave Address**: `6`
     - Relay Panel: Turn on button 2 and button 3
   - **Python**: `(switch slave address = 65, relay slave address = 6)`

3. **Network 3:**
   - **Switch Slave Address**: `33`
     - Switch Panel: Turn on button 3 and button 8
   - **Relay Slave Address**: `10`
     - Relay Panel: Turn on button 2 and button 4
   - **Python**: `(switch slave address = 33, relay slave address = 10)`

4. **Network 4:**
   - **Switch Slave Address**: `17`
     - Switch Panel: Turn on button 4 and button 8
   - **Relay Slave Address**: `18`
     - Relay Panel: Turn on button 2 and button 5
   - **Python**: `(switch slave address = 17, relay slave address = 18)`

5. **Network 5:**
   - **Switch Slave Address**: `9`
     - Switch Panel: Turn on button 5 and button 8
   - **Relay Slave Address**: `20`
     - Relay Panel: Turn on button 3 and button 5
   - **Python**: `(switch slave address = 9, relay slave address = 20)`

6. **Network 6:**
   - **Switch Slave Address**: `5`
     - Switch Panel: Turn on button 6 and button 8
   - **Relay Slave Address**: `34`
     - Relay Panel: Turn on button 2 and button 6
   - **Python**: `(switch slave address = 5, relay slave address = 34)`

7. **Network 7:**
   - **Switch Slave Address**: `3`
     - Switch Panel: Turn on button 7 and button 8
   - **Relay Slave Address**: `12`
     - Relay Panel: Turn on button 3 and button 4
   - **Python**: `(switch slave address = 3, relay slave address = 12)`

8. **Network 8:**
   - **Switch Slave Address**: `4`
     - Switch Panel: Turn on button 6 only
   - **Relay Slave Address**: `48`
     - Relay Panel: Turn on button 5 and button 6
   - **Python**: `(switch slave address = 4, relay slave address = 48)`

## Connection Diagram

### Wiring with CAT6

#### RS485 Data Lines
- **Shared Network**: Use a single twisted pair for A and B lines.

#### Power Lines
- **12V Power**: Shared across all relays and switches.
- **5V Power**: Optionally shared, based on capacity.

### Components

#### Separate RS485 Networks
- **Individual TTL to RS485 Converters**: 
  - Connect each switch network to its own converter.
  - Ensure proper RX, TX connections to Pico.
  - ![Sample Connections](https://github.com/Ayocrypt/ModbusRaspberryPico/blob/main/sample_connections.jpg)

## Power Supply

### 12V Power
- **Shared**: Connect 12V and GND in parallel for all relays and switches.

### 5V Power
- **Current Capacity**: Ensure power supply can handle total current for all Picos.
- **Alternative**: Use separate 5V supplies if needed.

## Steps

1. **Connect Each RS485 Network:**
   - Use CAT6 to run A and B lines for each network.
   - Connect each network's TTL to RS485 converter to switches.

2. **Connect Power:**
   - Parallel 12V and GND for all devices.
   - Use shared or separate 5V for Picos.

## Considerations

- **Current Capacity**: Verify the 5V supply can handle the load. If not:
  - Use additional 5V supplies.
  - Ensure all grounds are common.

- **Isolation**: Separate networks minimize interference and allow independent operation.

- [Working Single Network Video](https://github.com/Ayocrypt/ModbusRaspberryPico/blob/main/working_single_network_video.mp4)

This setup ensures efficient communication and power distribution.
