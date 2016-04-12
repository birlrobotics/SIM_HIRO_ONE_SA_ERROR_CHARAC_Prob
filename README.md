# data_004_SIM_HIRO_SA_ErrorCharac_Prob
Data from snap assembly work in simulation with the HIRO Robot. In particular this package is focusing on the analysis of failure trials, where different trials have been set to include a deviation in 1-3 directions and with different magnitudes. A probabilistic scheme is used to classify the failure type. Location: Guangzhou. Date: 2014.

There are two sets of data that capture failure: exp##_sereis and the FC###_series. The exp series was used for ICRA 2014 and the FC series was used in humanoids. Each folder name has a sequence number followed by the deviation direction and amount. For example, "exp1+x0.0080-z0.005" indicates the 1st experiment, with a deviation of 0.008m in the x-direction and -0.005m in the z-direction. Note: the z-direction is not considered in the experimentation, it is modified to ensure we can still make contact between parts. The deviations we analyize are combinations of the following: delx, dely, delYall. 
Note: Humanoids uses the (appropriate) term Yall. In the ICRA data, we used the  erroneous term Roll. 

Also in the exp series there is an "R" term in the folder name, this is a parameter used in the OpenHRP DyanmicsSimulator that modifies contact/penetration dynamics between objects. 

Each folder contains data for: (i) Manipulator data and (ii) RCBHT state estimation files related to the RCBHT. Also note that the experimental data is grouped into different under different coordination schemes. So far: MPFH and MHFP.

(i) ManipulatorData

Angles: Current Joint Angles (7 DoF) Format: time th1 th2 ... th7

CartPos: EndEffector Cartesian Position Format: time x y z r p y

Torques: Wrench data wrt the tool. No gravity compensation. Format: time Fx Fy Fz Mx My Mz

State: State Transition Time Vector. Format: time

(ii) RCBHT Information (Left and Right Arms)

Segments: contains information about how the original FT data is segmented by a regression fit for all 6 FT axes. Data include: iteration, average magnitude value, maximum magnitude value, minimum magnitude value, start time, finish time, gradient value, and gradient lable.

Composites: contains information of how neighboring segments are combined (though affected by MC filtering rules) for all 6 FT axes. Data include iteration, MC label, avg val across segments, root-mean-square value across segments, amplitude value across segments, gradient labels for both segments, start, end, avg time for both segments.

llBehaviors:

contains information of how neighboring actions are combined (though affected by LLB filtering rules) for all 6 FT axes. Data is kept in file (.txt) format and also in matlab format (.mat) and include the following info: iteration, llb label, avg. val for mc1 & mc2, avg val for combination of mc1&2, same for rms value and amplitude value, mc label 1 and 2, time they start and finish respectively, and the average time for both of them.