### Fundamentals
$q$, charge (electric charge / electrical charge / electrostatic charge)

Potential (Physics)
A currently unrealized ability.
Having the power of being capable of happening.

How many coulombs in 1 mole of electrons?

$\displaystyle \frac{6.02214 \times 10^{23}}{6.24151 \times 10^{18}} = \frac{x}{1}$

$\displaystyle x = 96485.30564$

96485 coulombs/mole (Faraday's Constant)

---

##### Conductors, Insulators and Semiconductors
**Conductor**
Made of atoms whose valence electrons have weak bonds to their nuclei. When a bunch of metal atoms are together, they gladly share their outer electrons with each other, creating a "swarm" of electrons not associated with a particular nucleus. A very small electric force can make the electron swarm move.

Cu, Al, Au and Ag (and saltwater) are good conductors.

Pure water is poor conductor but the water in tap contains many minerals that provide the ions for conduction of electricity. At very high voltages, however, water molecules become ionized and separate into $\ce{H+}$ and $\ce{OH-}$ ions which results in increased conductivity.

**Insulators**
Materials whose valence electrons are tightly bound to their nuclei.

**Semiconductor**
Act like insulators, act like conductors under certain conditions.
Silicon is the most well-known semiconductor material.

##### Current, $I$ / $ampere$
- A stream of charged particles, such as electrons or ions, moving through an electrical conductor or space.
- Electrons from the valence shell of metal atoms move in the current. In other words, the moving electrons are what makes up the current in metals.
- The flow of charge (precisely, the intensity of it) (Charge flows in current, not current who flows).
- The rate at which charge is transferred through an object (q/sec or charge/second).

	Average current, $\displaystyle \overline{I} = \frac{\Delta{q}}{\Delta{t}}$
	Instantaneous current, $I = \displaystyle \lim_{\Delta{t \to 0}} \frac{\Delta{q}}{\Delta{t}} = \frac{dq}{dt}$

**Conventional current direction**
Positive to negative
Positive charges moving

Current direction: out from the positive, back into the negative

**Electron current**
Negative to positive
Electrons moving

Current, by default, means conventional current direction. Even though electrons have a negative charge and do almost all the work in most electric circuits, we still define positive current as the direction a *positive* charge would move. This is a very old historical convention.

In some cases, where the conductor consists of ions, current can be carried by positive charges (the cations). For example, the saltwater, $\ce{NaCl}$.

##### Voltage, $V$ / $volt$
- The pressure from an electrical circuit's power source that pushes charged electrons (current) through a conducting loop.
- Difference in electric potential (The amount of work needed to move a unit charge between two points) between two points.
- The change of energy experienced by a charge.

	Voltage between two points, $\displaystyle V = \frac{\Delta{U}}{q}$

One volt is the potential difference between two points of a wire carrying a current of 1 ampere when the power dissipated in the wire is 1 watt.

$\displaystyle 1\ volt = \frac{1\ watt}{1\ ampere}$

$\displaystyle 1\ volt = \frac{1\ joule}{1\ coulomb}$

##### Power, $P$ / $watt$
Rate of energy, $U$ transformed or transferred over time.

Power, $\displaystyle P = \frac{dU}{dt}$

$\displaystyle 1\ watt = \frac{1\ joule}{1\ second}$

$\displaystyle P = \frac{dU}{dt} = \frac{dU}{dq} \times \frac{dq}{dt} = VI$

##### Charge, $Q$ / $coulomb$
$Q$ is the symbol for charge, $C$ is the symbol for coulomb, while coulomb is the unit of charge

Positive and negative charge.
Causes matter to experience a force. Like charges repel, unlike charges attract.

coulomb: SI unit of charge, derived from ampere.

Charge of one electron:
$q_e = e =−1.602176565 \times 10^{-19}\ coulomb$

Coulomb in terms of number of electron charges:
$1 \ coulomb = 6.241509343 \times 10^{18} \ electrons$

One coulomb is the amount of charge flowing past a point in a wire in one second when the current in the wire is one ampere.

$\displaystyle 1\ ampere = \frac{charge\ of\ 6.24 \times 10^{18}\  electrons}{1\ second}$

$\displaystyle 1\ ampere = \frac{1\ coulomb}{1\ second}$

$\displaystyle 1\ coulomb = 1\ ampere \times 1\ second$

$C = As$
$A$, amperes
$s$, seconds

##### Ohm, R / $\Omega$
One ohm is the resistance between two points of a conductor when 1 volt is applied and a current of 1 ampere is flowing.

$\displaystyle 1\ ohm = \frac{1\ volt}{1\ ampere}$

**Ohm's Law**
The voltage across a conductor (e.g. resistor) is directly proportional to the current flowing through it, provided that all physical conditions and temperatures remain constant.

### Circuit Elements
Circuit is made of **elements**. Elements consist of **sources** and **components**. 

**Sources** provide energy to a circuit. There are two basic types.
- Voltage source
- Current source

**Components** come in three basic types.
- Resistor
- Capacitor
- Inductor

These sources and components are 2-terminal elements. They all have two terminals or connection points (anode and cathode). 

#### Ideal circuit elements
##### Sources
Ideal sources are those imaginary electrical sources. They provide constant voltage or current to the circuit. They don't have any internal resistance, where it is impossible to build a source with zero internal resistance. 

|Ideal source|Note|Symbol|Note (Symbol)|
|---|---|---|---|
|Constant voltage source|Has a fixed output voltage, $v = V$|![](constant_voltage_source.svg)|Left for battery, right for other power sources, often a power supply|
|Variable voltage source|Source generates a known voltage as a function of time, $v = v(t)$|![](variable_voltage_source.svg)|The line in the circle represents the waveform of voltage (in this case, the sine wave)|
|Constant current source|Has a fixed output current, $i = I$|![](constant_current_source.svg)|Arrow indicates the direction of positive current| 

Variants of voltage versus time plot, $v = v(t)$

![](vt_one.png)
![](vt_two.png)

##### Resistor
The voltage across a **resistor** is directly proportional to the current flowing through it.

$v = Ri$ (Ohm's law)
$R$ is a constant of proportionality
![](ohms_law_graph.png)

Symbol for resistor:
![](resistor.svg)
Left: US and Japan
Right: UK, Europe and the others

**Power in a resistor**
Power is dissipated by a resistor when current flows through it. Energy in flowing electrons becomes bulk heat as electrons collide with atoms in the resistor material.

$$
\begin{aligned}
P &= \frac{dU}{dt} = \frac{dU}{dq} \times \frac{dq}{dt} = VI \\ \\ \\
(V &= IR) \\ \\ \\
P &= (IR)I = I^2R \\ \\ \\
P &= V(\frac{V}{R}) = \frac{V^2}{R}
\end{aligned}
$$

##### Capacitor
- A device that stores electrical energy in form of electrical charge in an electric field.

- Capacitance is the capacitor's storage potential, measured in farads, $F$.

- A 1 farad capacitor can store 1 coulomb of charge at 1 volt.

	$\displaystyle C = \frac{Q}{V}$
	$\displaystyle 1\ farad = \frac{1\ coulomb}{1\ volt}$

	$Q$, Charges stored in the capacitor
	$V$, The electric potential between the two pieces of metal. 
	
	Region of low electric potential (V): negative
	Region of high electric potential (V): positive

- If a capacitor is fully charged up by battery, the voltage across the capacitor will be the same as the voltage of the battery.

- Capacitance, $C$ is the constant of proportionality.

- $C$ does not increase with $Q$ because as the charge increases, the voltage across the capacitor also increases.

- Symbol of capacitor:
	![](capacitor.svg)
	
	The version with curved line indicates that the capacitor requires one terminal to have positive voltage with respect to the other terminal. The curved line indicates the terminal that needs to be kept at the more negative voltage.

- Capacitor equation:
$$
\begin{aligned}
Q &= CV \\ \\
\frac{dq}{dt} &= C\frac{dv}{dt} \\ \\
i &= C\frac{dv}{dt}\ \ (Capacitor\ equation)\\ \\
v &= \frac{1}{C} \int_{-\infty}^{T} i\ dt\ \ (Integral\ form)
\end{aligned}
$$

**Power and energy in a capacitor**

The instantaneous power in watts associated with a capacitor,

$\displaystyle p = vi$
$\displaystyle p = v\ C\frac{dv}{dt}$

The energy, $U$ stored in a capacitor is power integrated over time,

$\displaystyle U = \int p\ dt = \int v\ C\frac{dv}{dt}\ dt = C \int v\ dv$ 

 If we assume the capacitor voltage was 0 V at the beginning of the integration, then the integral evaluates to:

 $\displaystyle U = \frac{1}{2}Cv^2\ \ (Energy\ in\ capacitor)$
 
##### Inductor
- A passive electronic component that stores energy in a surrounding magnetic field when electric current flows through it. The stored magnetic energy can return to the circuit by generating an electric current.

- The voltage across an inductor is directly proportional to the time rate of change of current through the inductor.

	$\displaystyle v = L\frac{di}{dt}$
	
	$L$, inductance (Constant of proportionality). Measured in unit henry ($H$).

- Symbol for an inductor:
	![](inductor.svg)

- Integral form of inductor equation.

	$\displaystyle v = L\frac{di}{dt}\ \ (Inductor\ equation)$
	$\displaystyle i = \frac{1}{L} \int_{-\infty}^T v\ dt\ \ (Integral form)$

**Power and energy in an inductor**
The instantaneous power in watts associated with an inductor,

$\displaystyle p = iv$
$\displaystyle p = i\ L\frac{di}{dt}$

The energy, $U$ stored in the magnetic field of an inductor is power integrated over time,

$\displaystyle U = \int p\ dt = \int i\ L\frac{di}{dt}\ dt = C \int i\ di$ 

$\displaystyle U = \frac{1}{2}Li^2\ \ (Energy\ in\ inductor)$

<br>

#### Non-ideal circuit elements
Real-world circuit elements are imperfect, they never have exactly their specified values. Physical devices like resistors, inductors, capacitors have some level of tolerance around the ideal value. 
Tolerance is the deviation from the nominal value, expressed with $\pm\%$ measured at 25$\celsius$ with no load applied. The tighter the tolerance, the more to pay for the component.

**Resistors**
The resistance value depends on two things:
- Bulk material (Resistivity)
	Affects how difficult it is for electrons to flow through
	Resistivity: Physical property of a substance because of which it opposes the flow of current.
	Conductivity:  Inverse of resistivity, the measure of the ease at which current can flow through.
- Shape of resistor (Resistance)
	Longer resistor has higher resistance than a shorter resistor because the electrons suffer more collisions as they pass through the atoms in the material.
	Resistor with greater cross-sectional area has lower resistance because electrons have a greater number of available paths to follow.

- **Resistor** is a circuit element, a physical object
	**Resistivity** is a property of bulk material
	**Resistance** is a property of resistor, determined by the resistivity of the material and the shape of the resistor

Resistor color code:
![](resistor_color_code.svg)

### Terminology
#### Circuit
**Short circuit**
A *short* happens when a path of low resistance is connected to a component. This results in an excessive current flowing through the circuit.
![](short_circuit.svg)

**Make or Break**
![](make_break.svg)

#### Schematic
Schematic - The drawing of a circuit

**Elements**:
![](schematic_elements.svg)

**Dots**
Dots indicates that the lines are connected. If the connection is obvious, the dot is not needed.
![](dots.svg)

**Nodes**
A junction where 2 or more elements connect.
![](nodes.svg)

**Branches**
The connection between nodes. A branch is a element.

**Loops**
Any closed path going through circuit elements.
![](loops.svg)

**Meshes**
A loop that has no other loops inside it (Think of it as the hole in circuit)
![](meshes.svg)

**Reference node**
Common choices of reference node:
- The negative terminal of the voltage or current source
- The node connected to the greatest number of branches

Voltages at other nodes are measured relative to the reference node.

**Ground**
- The reference point from which voltages are measured.
- A return path for electric current back to its source.
- A direct physical connection to the Earth, which is important for safety.

![](ground.svg)

##### Schematic Equivalence
To be equivalent, two schematics must
- Represent every component and source
- Have the same number of nodes
- Each node must be connected to the same branches

Equivalence means the matching nodes will have the same voltage, and the matching branches will have the same current.

##### Drawing habits
-   Place inputs on the left, and outputs on the right.
-   Let information flow from left to right across the circuit.
-   Use up/down on the page to suggest voltage levels. That is, draw higher voltage wires closer to the top of the page, and lower voltages (like ground) near the bottom of the page.

##### Sign convention for passive components
Passive components are components that do not create power and amplify signal. Resistors, capacitors, inductors are passive components.

![](sign_convention.svg)

$V_R$: Voltage polarity (The signs and arrow mean the same thing, use either one)
$i_R$: Current direction