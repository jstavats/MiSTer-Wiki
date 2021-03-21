When overriding gamepad settings inside a core it is possible to define button combinations (e.g. A+B) if you have enough physical buttons.

To allow for this, MiSTer will ask if you want to setup "alternate mappings" after defining a gamepad.

Alternate mappings are active in parallel and allow two kinds of abilities: map two physical button to the same core button (e.g. alternate button for Start), or map one physical button to two-button combo in the core (e.g. map physical X to thr core's A+B).

## Bind core button to two physical buttons

The simplest is to map an extra physical button. Only this additional button needs to be defined in the alternate map, as follows:

| **map** | **d-pad** | **A** | **B** |
|:--------|:---------|:------|:------|
|**main**|_define_|Btn 1|Btn 2|
|**alt**|_skip_|_skip_|Btn 3|

The result of using this setup ia that you will have physical buttons 2 and 3 mapped to the core button B.

This also works with gamepad directions. For example, for games that use Up as a jump button, it is possible to map a physical third button to jump.


## Bind physical button to core button combo

A more advanced setup is to use both mappings in parallel to make one physical button push two core buttons at the same time.

See the table below:

| **map** | **d-pad** | **A** | **B** 
|:--------|:---------|:------|:------|
|**main**|_define_|Btn 1|Btn 3|
|**alt**|_skip_|Btn 3|Btn 2|

The result of this is that Button 1 will be A, Button 2 will be B, and Button 3 will be A+B.

This is particularly useful for the Neogeo core where some fighting games use A+B and C+D as "strong hit".
