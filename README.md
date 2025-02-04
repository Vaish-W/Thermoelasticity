# Thermoelasticity
This repository contains a setup for the heat solver that gives an isothermal solution to test coupled thermoelasticity solver implemented in SU2. Refer [PR#2404](https://github.com/su2code/SU2/pull/2404) and [Discussion#2402](https://github.com/su2code/SU2/discussions/2402).
The config_therm.cfg implements this setup by modifying a tutorial on Linear elasticity already present in the 'SU2 tutorials' section ([Tutorial on linear elasticity](https://su2code.github.io/tutorials/Linear_Elasticity/)). The modifications are as follows:

### **Steps for Setup**
1. Modify the configuration file to enable thermal coupling and heat solver (```WEAKLY_COUPLED_HEAT_EQUATION = YES```).
2. Duplicating the marker definition inside the SU2 mesh file, and then using one copy for heat boundary conditions and another for FEA.
   ```MARKER_ISOTHERMAL = ( left_thermal, 300.0, right_thermal, 300.0 )```
3. Set ```FREESTREAM_TEMPERATURE = 310.0```
4. Add temperature output ```SCREEN_OUTPUT = (INNER_ITER, RMS_DISP_X, RMS_DISP_Y, RMS_TEMPERATURE, VMS)```
5. Run the solver and visualize the results using ParaView.

