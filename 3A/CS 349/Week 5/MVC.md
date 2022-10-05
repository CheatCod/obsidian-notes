# MVC

MVC seperate "business" logic and the UI logic

- View and controller can be changed without changing the underlying model
- Useful when
	- Adding support for new input device
	- Adding support for new output device

## MVC Implementation

MVC is typically implemented using the Observer design pattern

Interface architecture is decomposed into three parts:

- Model: manages system state and its modification
- View: manages interface to provide feedback
- Controller: manages interaction to request system state modification

