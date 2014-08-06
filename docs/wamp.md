# WAMP Specification

## General Information

 - `board`s are referenced by their part code, not the index.

## Definitions

### RPC org.srobo.hello(`client_version`)

Return `true` if the client should reload the page before continuing, otherwise return `false`.


### RPC org.srobo.zone

Return the current zone the robot is configured to be in.

### PUB/SUB org.srobo.zone(`zone`)

When the zone changes.

### RPC org.srobo.mode

Return the current mode the robot is configured as. Mode is one of `comp` or `dev`.

### PUB/SUB org.srobo.mode(`mode`)

When the mode changes.


### PUB/SUB org.srobo.logs.append(`log`, `entry`)

When a single entry in the log has been added.

### RPC org.srobo.logs.all

Return a list of log objects (`{'type': type, 'title': title, 'name': name, 'contents': ['...', ...]}`).

### RPC org.srobo.logs.get(`name`)

Return a single log object.


### RPC org.srobo.start

Start the robot.

### RPC org.srobo.stop

Stop the robot.

### RPC org.srobo.state

Return the state of the robot, which can be one of `booting`, `started`, `stopping`, `stopped`.

### PUB/SUB org.srobo.state(`state`)

When the state changes.


### RPC org.srobo.pyenv.version

Return the current pyenv version.


### RPC org.srobo.project.name

Return the current project name.

### RPC org.srobo.project.version

Return the current project version.


### PUB/SUB org.srobo.power.output_state(`index`, `state`)

When the state of a power output on the power board has changed.

### RPC org.srobo.power.get_output_state(`index`)

Return the state of a power output on the power board.


### PUB/SUB org.srobo.servos.servo_value(`board`, `index`, `value`)

When a value on a servo has changed.

### RPC org.srobo.servos.get_servo(`board`, `index`)

Return a servo object (`{'value': value}`) about the requested servo.

### RPC org.srobo.servos.get_board(`serial_number`)

Return a servo board object (`{'servos': [<servo_object>, ...]}`) about the requested board.

### RPC org.srobo.servos.all_boards

Return a dictionary of serial number to servo board objects.


### PUB/SUB org.srobo.motors.motor_value(`board`, `index`, `value`)

When a value on a motor has changed.

### RPC org.srobo.motors.get_motor(`board`, `index`)

Return a motor object (`{'value': value}`) about the requested motor.

### RPC org.srobo.motors.get_board(`serial_number`)

Return a motor board object (`{'motors': [<motor_object>, ...]}`) about the requested board.

### RPC org.srobo.motors.all_boards

Return a dictionary of serial number to motor board objects.


### PUB/SUB org.srobo.ruggeduinos.pin_mode(`board`, `index`, `mode`)

When a pin mode has changed. Mode is one of `input`, `output`, `input_pullup`.

### PUB/SUB org.srobo.ruggeduinos.pin_value(`board`, `index`, `mode`)

When a pin value has changed.

### RPC org.srobo.ruggeduinos.get_pin(`board`, `index`)

Return a pin object (`{'mode': mode, 'type': type, 'value': value}`) for the requested pin. Type is one of `digital` or `analogue`.

### RPC org.srobo.ruggeduinos.get_board(`serial_number`)

Return a ruggeduino board object (`{'pins': [<pin_object>, ...]}`) for the requested board.

### RPC org.srobo.ruggeduinos.all_boards

Return a dictionary mapping serial numbers to ruggeduino board objects.


### RPC org.srobo.battery

Return a battery object (`{'level': level}`) for the robot battery.

### RPC org.srobo.battery.level

Return the batter level.

### PUB/SUB org.srobo.battery.level

When the robot battery level changes.