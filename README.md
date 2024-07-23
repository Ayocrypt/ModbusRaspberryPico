# ModbusRaspberryPico
## RS485 Network Setup with Raspberry Pi Pico

## Purpose
- **Separate TTL to RS485 Converters**: Each switch network requires its own converter for reliability and reduced interference.

## Configuration

### Relay Settings
- **Slave Address**: `2` (labeled on relay, code uses `2`)

### Switch Settings
- **Slave Address**: `8` (labeled on switch, code uses `1`)

## Connection Diagram

### Wiring with CAT6

#### RS485 Data Lines
- **Each Network**: Use a separate twisted pair for A and B lines.

#### Power Lines
- **12V Power**: Shared across all relays and switches.
- **5V Power**: Optionally shared, based on capacity.

### Components

#### Separate RS485 Networks
- **Individual TTL to RS485 Converters**: 
  - Connect each switch network to its own converter.
  - Ensure proper RX, TX connections to Pico.

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

This setup ensures efficient communication and power distribution.

