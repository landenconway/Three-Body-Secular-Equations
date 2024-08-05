# Secular equations of motion for a hierarchical three body system.
Listed in this github repository are the secular equations of motion of a hierarchical three body system calculated using the methods laid out in paper 2. Within the *equations* folder are 10 subfolders organized by effect. These subfolders contain the corresponding contribution to each orbital element's secular evolution coming from said effect. The meaning of each subfolder is as follows:
- *quadrupole* = effects coming from 1st-order perturbation theory applied to the quadrupole equations of motion.
- *octupole* = effects coming from 1st-order perturbation theory applied to the octupole equations of motion.
- *hexadecapole* = effects coming from 1st-order perturbation theory applied to the hexadecapole equations of motion.
- *dotriacontapole* = effects coming from 1st-order perturbation theory applied to the dotriacontapole equations of motion.
- *dom Q^2* = effects coming from the dominant term in 2nd-order perturbation theory using quadrupole equations of motion twice.
- *dom Qoct* = effects coming from the dominant term in 2nd-order perturbation theory using quadrupole and octupole equations of motion.
- *subdom Q^2* = effects coming from the subdominant term in 2nd-order perturbation theory using quadrupole equations of motion twice.
- *Q^2 dtdF* = effects coming from higher order corrections to dt/dF using quadrupole equations of motion twice.
- *Q^2 dtdu* = effects coming from higher order corrections to dt/du using quadrupole equations of motion twice.
- *Qoct dtdF* = effects coming from higher order corrections to dt/dF using quadrupole and octupole equations of motion.  


For each effect there are at most 8 text files that correspond to 8 different orbital elements' secular evolutions for that given effect. The text files are the raw equations in the **Mathematica** language. One should be able to paste or import these text files directly into **Mathematica** to use them. Alternatively, if one is using **Maple**, there is a function, ***FromMMA(input)*** , that converts **Mathematica** text into **Maple**. As an example, in the *dom Q^2* folder, each text file represents:

- *domQ2CapitalA* = The contribution to dA/dt coming from this effect ( the dominant quadupole squared). Where A is the outer orbit's semi-major axis.
- *domQ2CapitalE* = The contribution to dE/dt coming from this effect. Where E is the outer orbit's eccentricity.
- *domQ2e* = The contribution to de/dt coming from this effect. Where e is the inner orbit's eccentricity.
- *domQ2Ohm* = The contribution to dΩ/dt coming from this effect. Where Ω is the inner orbit's line of nodes.
- *domQ2w* = The contribution to dω/dt coming from this effect. Where ω is the inner orbit's pericenter angle.
- *domQ2w3* = The contribution to dω3/dt coming from this effect. Where ω3 is the outer orbit's pericenter angle.
- *domQ2z* = The contribution to dz/dt coming from this effect. Where z is the relative inclintion between inner and outer orbit.

The inner orbit's semi major axis is missing from this list because its contribution from this effect is zero. Any missing element for a given effect signifies its contribution being zero. Additionally, in our chosen coordinate system dΩ/dt = dΩ3/dt. The absence of Ohm3 is due to this equivalence. Some other comments about the syntax and notation:
- Capital Epsilon is used in *Mathematica* to represent the outer orbit's eccentricity as E is used for the exponential in *Mathematica*
- w and w3 are used to represent the pericenter angles instead of the usual ω
- Only the relative inclination is given. To use the individual inclinations one can either extract them from the raw equations of motion for each effect, or dynamically determine them using angular momentum relations.
- The only place where the individual inclinations occur is in the dΩ/dt equations. Here *l* is used instead of the usual *i* to avoid confusion within *Mathematica* relating to the imaginary unit

