
    NEURON TUTORIAL FOR IMPLEMENTING SIMULATIONS OF THALAMIC OSCILLATIONS

                          Alain Destexhe
		Laboratory for Computational Neuroscience
	Unité de Neurosciences Intégratives et Computationnelles (UNIC)
	Centre National de la Recherche Scientifique (CNRS)
			91198 Gif-sur-Yvette, France 

	    Formerly from (when this work was created):
            Department of Physiology, Laval University,
                      Quebec G1K 7P4, Canada

                       Destexhe@iaf.cnrs-gif.fr
                     http://cns.iaf.cnrs-gif.fr/Main.html


This package is running with the NEURON simulation program written by Michael
Hines and available on internet at:
  http://www.neuron.yale.edu/neuron/
  http://neuron.duke.edu/

The package contains mechanisms (.mod files) and programs (.oc files) needed 
to simulate interconnected thalamocortical (TC) and thalamic reticular (RE) 
cells, relative to the paper:

  Destexhe, A., Bal, T., McCormick, D.A. and Sejnowski, T.J.
  Ionic mechanisms underlying synchronized oscillations and propagating
  waves in a model of ferret thalamic slices. Journal of Neurophysiology
  76: 2049-2070, 1996. 

A postscript version of this paper, including figures, is available on
internet at 
  http://cns.iaf.cnrs-gif.fr/Main.html
  
PROGRAMS
  ========
- Fspin.oc	: spindle oscillations (short run)
			  see Fig. 7 of the paper
- FspinL.oc	: spindle oscillations (long run)
			  see Fig. 7 of the paper
- Fbic.oc	: bicuculline-induced oscillations (short run)
			  see Fig. 8 of the paper
- FbicL.oc	: bicuculline-induced oscillations (long run)
			  see Fig. 8 of the paper
- Fdelta.oc	: delta oscillations (short run)
- FdeltaL.oc	: delta oscillations (long run)



MECHANISMS
  ==========
- HH2.mod		: fast sodium spikes (Na and K currents)
- IT.mod			: T-current for TC cell
- IT2.mod		: T-current for RE cell (different kinetics and v-dep)
- Ih.mod			: h-current for TC cell, including upregulation
			  by intracellular calcium
- cadecay.mod		: intracellular calcium dynamics
- kleak.mod		: leak K+ current (TC cell)

- ampa.mod		: AMPA-mediated synaptic currents
- gabaa.mod		: GABA_A-mediated synaptic currents
- gabab.mod		: GABA_B-mediated synaptic currents


HOW TO RUN
  ==========
- Use autolaunch on modeldb or:
- unix platform:
  
  To compile the demo, NEURON and INTERVIEWS must be installed and working on
the machine you are using.  Just type ``` nrnivmodl ``` to compile the mechanisms
given in the mod files.

  Then, execute the main demo program by typing: ``` nrngui mosinit.hoc ```
- mswin platform:

  Compile the mechanism (mod) files by using mknrndll.  Then start the simulation
  by clicking on mosinit.hoc in windows explorer.
- back to any platform:
  
  Once the menu and graphics interface has appeared, select a simulation from the
"Simulations of thalamic oscillations" window.  Then click on "Init and Run"
button to start the simulation...

\
For more information about how to get NEURON and how to install it, please
refer to the following sites:
  http://neuron.duke.edu/
  http://www.neuron.yale.edu/

\
For further information, please contact:

Alain Destexhe
Laboratory for Computational Neuroscience
Unité de Neurosciences Intégratives et Computationnelles (UNIC)
Centre National de la Recherche Scientifique (CNRS)
91198 Gif-sur-Yvette, France 

Destexhe@iaf.cnrs-gif.fr
http://cns.iaf.cnrs-gif.fr/Main.html

\
7/11/2005 Additional modifications to restart by first closing other simulation
windows and also updating README contact information.

2/14/2001 Michael Hines trivially modified some of the hoc files
to use the more flexible load_file in place of certain xopen statements,
ensure that the current version of the standard gui library comes
up first, and arrange graphs on the screen.

Not yet:
He also updated the mod files to be compatible with cvode and
make use of internal compuations of ionic reversal potential. This
version is quantitatively identical to the original.

10-2007: AD, better synaptic mechanisms using counters; added delta
oscillations.
20120106 updated mod files IT.mod IT2.mod cadecay.mod gabab.mod SOLVE 
methods as suggested in web page
http://www.neuron.yale.edu/phpbb/viewtopic.php?f=28&t=592
