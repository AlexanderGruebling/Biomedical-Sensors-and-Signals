# Electric Biosignals 2
## Medium Impedance as biosignal origin
### Constant/direct electrical field
* Inhomogenous distribution of the restivity p (local static charactersitic)
* Resistance R (global) R = (p * l) / A
* Impedance of tissure decreases with increasing field frequency
### Alternative electrical field
* effective conductivity y_eff = 1 / p + delta y = y + delta y 
* local ohmic law:
	* vE = vI * 1 / y
	* v denotes vectors
	* vE ... electrical field 
	* vI ... current density
	* y ... conductivity
* U then follows as:
	* U = ∫vE dl
	* I = ∫vI dA
* Flux Density:
	* vD = e * vE 
* vJ = vJ_C + vJ_D = jw*e'*vE + y*vE + w*e''*vE
	* Out of phase dielectric current density vJ_D = jw * e' * vE
	* In phase total conductance current density J_C = y\*vE + w\*e''*vE
* Freqency is dependent on conductivity y_eff
* Frequency is dependent on conductivity e
* two electrodes, in between thighly packed cells:
	* low frequencies: current goes between cells, resulting in a high impedance and narrow cross sectional area A
	* High frequencies: current easily crosses cell membranes, cross sectional area thus is large, causing the impedance to go down
	* ![Beta dispersion]("beta dispersion.png") 
### Dispersion mechanisms
* atom consists of positively charged nucleus and negatively charged elctron hull
* per default, there is no polarization in an atom
* with displacement polarization f < 100000 GHz, an electric field can lead to polarized atoms
* gamma dispersion: orientation polarization, electric field with f < 30 GHz rearranges dipoles such that all charges face in the same direction, so for f_d = 15 GHz increased permettivity is achieved
* beta dispersion: cell membrane polarization f < 100 MHz
* permitvity of water: e_NF = 80

## Methodological issues
### Registration of impedance of human body
* measured through applied alternating electrical field
* 4 electrodes:
	* 2 apply electrical field from alternating current source
	* 2 measure impedance, after passing the signal through amplifier, bandpass, demuodulator and low pass --> result: Impedance
* Signal components:
	* Nearly constant component U_0 (nearly 90% of u) due to initial medium impedance 
	* Alternating component u_~ (< 10% of u) due to respiratory and cardiac activity, displacement of organs and liquids
### Physiological correlates
* Registration of volume and conductivity changes
#### Inhalation vs. Exhalation
* electrodes can be put anywhere on thoracic area
* Inhalation: more lung tissue (isolating), less heart tissue (conductive) --> higher voltage drop
* Exhalation: less lung tissue, more heart tissue --> lower voltage drop
#### Systole vs Diastole
* Equipotential line changes mainly around the heart --> electrodes must be put close to the heart
	* heart filled with blood --> lesser equipotential lines
	* empty heart --> more equipotential lines
### Forward vs Inverse Problem
* Forward: given physiological instance, calculate something
	* one clear solution
* Inverse: Given a single value, find sources for this value
	* e.g. which charges induced the electrical field?
	* many possible solutions
### Recording System
* frequency f
	1. 20-100 kHz
	2. > 20 kHz to avoid neural stimulation
	3. < 100 kHz due to dispersion (consider very large f for example, then permitivity y and e of tissue, lung and blood become identical, thus, cardiac/respiratory activity cannot be detected)
* current amplitude I 
	1. ~ 1mA
	2. probability of neural stimulation increases with increasing I and decreasing f
	3. Thermal effects increase with increasing effective value of I 
	4. Signal to noise ratio of alternating component u_~ increases with increasing I 
* Why 4 electrodes? why not 2?
	* connect two electrodes to tissue, we want to measure tissue Impedance
	* however, electrode impedance is not known; it depends on area of contact and changes with time as well
	* thus, it could be that tissue impedance is not even dominating the total measured Impedance
	* Solution: 4 electrodes
		* connect a third electrode between electrode 1 and tissue, and a fourth electrode between tissue and electrode 2
		* now connect electrodes 3 and 4 to a voltmeter 
		* the ideal voltmeter has a current of 0, therefore, the measured voltage drop is identical to the voltage drop along the tissue
		* this way, tissue impedance can be measured 
## Application issues
* some signals have region dependence
* signals may be composed of other signals (seperation with PCA, ICA necessary)