# Two Trees Sapphire-S Profile
This purpose of this project is to create a proper machine profile for Cura for the Two Trees Sapphire-S printer. Cura uses this profile to guide it when slicing models to create G-code for you.

## How it was built.
This profile was built off of the settings Excel file in the Two Trees Facebook group and my efforts to tune my printer. It is by no means perfect and I have additional settings I will likely add as I find time to tinker and test. Additionally I expect you may find issues, please feel free to submit issues or suggestions.

The goal is to create a solid profile and add it to Cura properly. But I've started this to allow the community to collaborate.

## How to install.
1. Copy the two folders from this repo into your `resources` folder under the Cura install.
2. If you have adjusted your steps for X,Y,Z or E you will need to do one of the following:
   A. Adjust the appropriate setting in the file to match your settings on your machine. 
    ```
    "machine_steps_per_mm_x":
    {
        "default_value": 640                 
    },
    "machine_steps_per_mm_y":
    {                    
        "default_value": 640
    },
    "machine_steps_per_mm_z":
    {
        "default_value": 400
    },
    "machine_steps_per_mm_e":
    {
        "default_value": 400
    }
    ```
   B. Create a derivative of this profile as outlined in the Cura documentation and save it to your `resources/definitions`
    ```
    {
        "name": "TwoTrees Sapphire S - Custom",
        "version": 2,    
        "inherits": "twotrees_sapphire_s",
        "metadata": {
            "visible": true,
            "author": "<--YOUR NAME HERE-->",
            "manufacturer": "TwoTrees",
            "file_formats": "text/x-gcode",
            "machine_extruder_trains": {
                "0": "twotrees_sapphire_s_extruder_0"
            },
            "supports_usb_connection": false
        },
        "overrides":
        {
            "machine_steps_per_mm_x":
            {
                "default_value": 640                 
            },
            "machine_steps_per_mm_y":
            {                    
                "default_value": 640
            },
            "machine_steps_per_mm_z":
            {
                "default_value": 400
            },
            "machine_steps_per_mm_e":
            {
                "default_value": 400
            }
        }
    }
    ```       

## How to participate.

1. Start by reading the Cura documentation on creating machine profiles [here](https://github.com/Ultimaker/Cura/wiki/Adding-new-machine-profiles-to-Cura).
2. Clone this repo and send me a pull request with your changes.

### Areas that need work.
* Multi-extruder support
* Print head geometry & offset (this is used to prevent collisions)
* Gantry height (I have no idea how this is supposed to work on a printer with a bed that moves down the Z-axis)
* Material and quality profiles
* Better start/end G-code
* Making it look nicer
  * Models of the print bed
  * Models of the hot-end