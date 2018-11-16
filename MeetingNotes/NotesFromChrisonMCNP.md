# Emrah Nov 5

Thanks, Chris. 

I'll get the SingleGen running with the new settings asap, but I may not have results by this Thursday. 
Sorry to say that but I'll be in transit (mostly off) this week from Wednesday to Friday afternoon. 

btw, I cc'ed Matt as well. 


# Dan Nov 5

Ryan et al.,

This raises a detail: whether we should be “interpolating" in energy or just finding a neutron that’s 
available in the MCNP event library having the “exact” energy requested. I believe it would be desirable 
for Chris’s code to find the nearest-energy neutron and (provided it’s "close enough" in energy) scale it 
to the energy requested. 

As I recall, when I proposed this before, Chris raised questions such as whether its 
decay distance (and those of its daughters) should also be scaled, which stalled the idea. 
Surely a first-order attempt is better than nothing, though. Do you-all agree?

# From Ryan Nov 5

Hi Emrah, all,

I'd be interested in the next tests actually putting larger spreads on everything: varied energy 
over, say, 10 MeV to 800 MeV; varied initial positions over tens of cm; varied directions of tens of degrees.  
We can then look at the behavior in bins of energy, etc.  (Given the discrete nature of the library and the 
geometry, we don't expect smooth behavior, so its hard to interpret possible anomalies if the input 
is discrete in any way.  Once things seem to be working, we can then try to "break" things with more pathological 
input distributions, and explore then whether the breakage is due to the odd input or the code itself.)

Ryan


# From Chris Nov 5

I just added the ability to set the energy range over which we will use 
MCNP. Outside of this range we will use geant instead. If you update 
g4nova in fact you'll find you can't run without setting these. 
Something like this:
 
physics.producers.geantgen.G4AlgPSet.NeutronSubstitutionMinKE: 20  # MeV
physics.producers.geantgen.G4AlgPSet.NeutronSubstitutionMaxKE: 600 # MeV

And you should find a corresponding printout in the startup information. 
Setting -1 causes that boundary to be ignored, in case you want to make 
some comparisons.
 
I'm also now no longer doing the replacement on neutrons outside of the 
detector.
 
If you'd like to repeat your studies with this included, that would be 
great. I'd also like to stress that you'll definitely want to give the 
input neutrons some energy spread (1%), otherwise we'll see repeated 
re-use of the same library event.
 
Chris
