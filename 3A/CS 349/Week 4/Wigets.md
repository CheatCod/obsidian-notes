# UI Widgets

Widgets are parts of an interface that have their own behaviour.

E.g., buttons, drop-down menus, spinners

They are also called components or controls or UI elements

Perform 4 essential functions:
- capture user input
- generate events
- provide user feedback
- maintain state
	- They may have state, or data that they control


## Logical Input Devices

A logical input device is a collection of widgets that share common functionality.

E.g., logical button devices generate “pushed” events when activated.

A specific widget is an *instance* of a particuar logical device.

### Button, Menu

Support simple interaction, with a single fixed action. Broadcast an event when activated by an user.

### Slider, Spinner

Capture a real number from a specific range. Support validation(e.g. positive number only), and representation of the selected value. 

### Checkbox, RadioButton

Represents a boolean value and displays the current state
