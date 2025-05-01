# Golden Gates Language (GGL) Design

Golden Gates is a new educational circuit simulaton tool and user inteface for constructing and simulated digital logic circuits.

The Golden Gates Language (GGL) is a restricted version of Python that can specify circuits and sub-circuits.

The capabilities of GGL are based on the native circuit elements and components in the Digital Education Circuit Simulation Application:

https://github.com/hneemann/Digital

The Docs are here in PDF:

https://github.com/hneemann/Digital/releases/download/v0.31/Doc_English.pdf

The circuit specification form should for the use of basic gates, wires, splitters, inputs, outputs, as well as higher level components like adders, muxes, decoders, etc.

Here is what we are thinking of an initial form:

```
from ggl import circuit

c = circuit.Circuit()

a1 = c.logic.and(bits=4, input=2)
i1 = c.logic.input(bits=4)
i2 = c.logic.input(bits=4)
o1 = c.logic.ouput(bits=4)
c.connect(i1, a1.input[0])
c.connect(i2, a1.input[0])
c.connect(a1.ouput, o1)

i1.value = 0b0001
i2.value = 0b1001
c.run()
print(o1)
# output should be 0b0001
```

Propose a full specification of GGL by analyzing the current Digital (https://github.com/hneemann/Digital/releases/download/v0.31/Doc_English.pdf) functionality and generalizing the example form above.