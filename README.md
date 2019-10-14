# pin_controller

## Notes

The idea behind this module is to create a more OO design for controlling individual pins that doen't require different library for each port that is neede in the project. Since some of the pics can have up do port G, it can become a little bit messy with each of the ports having its own files. Also, it in a bit of a pain keeping all the files upto date when something is changed in one of them.

### Potential opions for the struct:

#### 1 - Functions pointers in struct

typedef struct 
{
	// Variables
	uint16_t port_address;
	uint8_t pin;
	uint8_t state;
	
	// Functions
	uint8_t create(uint8_t pin);

	uint8_t set_tris(uint8_t tris_value);
	uint8_t get_tris();
	void set_pin_to_output();
	void set_pin_to_input();
	bool is_pin_an_output();
	bool is_pin_an_input();

	uint8_t set_lat(uint8_t port_value);
	uint8_t set_output_high();
	uint8_t set_output_low();	

	uint8_t get_port();
	bool is_input_high();
	bool is_input_low();
}

#### 2 - Only state data. All functions are external

struct
{
	uint16_t port_address;
	uint8_t pin;
	uint8_t output_state;
	uint8_t input_state;
	uint8_t error;
}




