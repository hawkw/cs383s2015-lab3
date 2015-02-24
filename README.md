cs383f2015-lab3
================

El Farol Bar multi-agent simulations in Repast Simphony.
 - For plots and data analysis, check out our [IPython notebook](http://nbviewer.ipython.org/github/hawkw/cs383f2015-lab3/blob/master/analysis.ipynb)
 - For documentation of implemented strategies, check out the [JavaDoc](http://hawkweisman.me/cs383f2015-lab3/) for our agent classes.

Implementation
--------------

We have added three additional agent types:
 - `AgentRan`, which makes a random prediction between the maximum and minimum attendance levels.
 - `AgentAverage`, which makes a prediction based on the average of all the remembered attendence levels.
 - `AgentMarkov`, which uses a Markov chain predictive model to predict the next attendance.

These new agent types were implemented by extracting an interface `Agent` from the public methods in the provided `Agent` class (renamed to `AgentWeighted`). New agent classes were written to extend this interface, and the `ElFarolContextBuilder` class was modified to create agents of the correct type depending on the parameters passed to the model. Additional parameters were added to the Repast model for controlling the distribution of agents, the maximum run time, and other characteristics.

For documentation on the functionality of each agent type, please check out the [JavaDoc](http://hawkweisman.me/cs383f2015-lab3/) for their respective Java classes.

We had intended to use Repast's batch mode for running all of the required parameters configurations in the laboratory handout, but this was determined to be impossible due to memory leak bug in Repast. Therefore, each parameters configuration was run by hand, instead.
