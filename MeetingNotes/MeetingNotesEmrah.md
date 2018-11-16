The samples for the different neutron models can be found here:

http://nusoft.fnal.gov/nova/production/production4/nd_geant_systs_v1.html

There is now a version of MCNP with a low energy cut off to distinguish between Geant and MCNP.

Emrah is going to start working on the single particle gen comparisons for the different models 
at a few energies and positions in the detector

Closure studies for MCNP first. Geant with Geant with library compared with default geant.
Need to find out the upper energy range of Chris's library. If possible Emrah should do a Gausian
variation on the initial energy

Comparison of MCNP with geant: we can set a minimum and maximum energy range for the MCNP libarary.
A few samples: MCNP on low energy only, MCNP on high energy only, MCNP on mid-range only

For setting the ranges to study MCNP, we should use the cutoffs suggested in Ryans talk.

Next Week - Emrah and Matt to use:
  * NeutronMCAna
  * CellHitTimeAna
  * NuMuNeutronAna
On the new MC samples
