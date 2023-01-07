# Simple-SEIR-Model-for-Infectious-Diseases
The SEIR (Susceptible-Exposed-Infectious-Recovered) model is a mathematical model used to understand the spread of infectious diseases. It divides a population into four compartments: susceptible, exposed, infectious, and recovered.

Susceptible individuals are those who are at risk of becoming infected with the disease.

Exposed individuals are those who have been infected with the disease, but are not yet infectious. They are in the incubation period of the disease, and may not show any symptoms yet.

Infectious individuals are those who are actively infected with the disease and can transmit it to others. They may show symptoms of the disease.

Recovered individuals are those who have recovered from the disease and are no longer infectious. They may have immunity to the disease, or they may be able to become infected again.

The SEIR model tracks the movement of individuals between these compartments over time, using a set of differential equations. It can be used to predict the spread of the disease, evaluate the effectiveness of interventions (such as vaccination), and understand the dynamics of the disease.
The code uses two libraries (sets of pre-written code) called "deSolve" and "ggplot2". These libraries contain tools that we can use to model the spread of an infectious disease and make a graph to visualize the results.

Next, we define some model parameters. "pop_size" is the size of the population, which we set to 1 million. "incubation_period" is the number of days that it takes for a person to become sick after they are infected, which we set to 17 days. "beta" is a value that represents how easily the disease spreads, and "gamma" is a value that represents how quickly people recover from the disease.

Then, we define a function called "seir_model". This function takes in three arguments: "time", "state", and "parameters". These arguments are used to tell the function what values to use when calculating the spread of the disease. We use the "with" function to make it easier to refer to these values.

Inside the function, we use the "S", "E", "I", and "R" values from the "state" argument to calculate the rates of change for each compartment (susceptible, exposed, infectious, and recovered). We use the "beta" and "gamma" values from the "parameters" argument to help with these calculations.

Then, we return a list of the rates of change for each compartment.

After defining the function, we set the initial conditions for the model. This means we specify the number of people in each compartment at the start of the simulation. We set the number of susceptible people to the population size minus 1 (since 1 person is already exposed), the number of exposed people to 1, the number of infectious people to 0, and the number of recovered people to 0.

We then create a sequence of time points to use for the solution, starting at 0 and ending at 365 (days) with a step size of 1 day.

Next, we use the "ode" function to solve the model. This function takes in the initial state, the time points, the function we defined earlier (seir_model), and some additional parameters. It returns the output of the model as an object.

We convert the output object to a data frame using the "as.data.frame" function. This makes it easier to work with the output.

Finally, we use the "ggplot" function from the "ggplot2" library to create a graph of the results. We use the "geom_line" function to add lines for each compartment (susceptible, exposed, infectious, and recovered), and we use the "labs" and "scale_color_manual" functions to add labels and colors to the graph.

