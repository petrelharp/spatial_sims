Tips for matking spatial density match up with theoretical expectation:

- Asynchronous life cycle: theoretical calculations might assume that birth and death
    refer to the same population size. But in SLiM they are offset by half a step!
    To make SLiM agree with the theoretical model,
    (a) make it so new offspring don't die their first year (this will be more efficient anyhow, as we don't produce offspring we never use), and
    (b) compute spatial density in `late( )` and save it as a property of the individual to use it in density calculations for birth.

- Boundary effects: individuals near the edge of the range might have lower neighbor density.
    Compute mean nearby density as number of indidivuals per *available* habitat instead.

Other points to make:

- Intro: the importance of being spatial (discrete pops pigeonholes us)

- Pain in the torus: why does it happen? The model is critical...


General-purpose considerations:

1. Let $\theta$ be proportional to the typical difference between
    birth (times establishment) and death
    for population densities between (say) 0 and twice the carrying capacity,
    Then it takes of order $\theta$ generations for the population density to change.

2. If dispersal distance, $\sigma$, is much greater than $1/\sqrt{\theta}$,
    then dispersal is faster than population change,
    and the population will be effectively nonspatial.
    If $\sigma$ is much less than $1/\sqrt{\theta}$,
    then each (singular!) location changes instantaneously,
    and so if the limit is stochastic at all it will be singular.

3. If the limit is stochastic depends on $\theta / N$.
    Since $N$ is the time scale of demographic noise,
    this is the ratio of two time scales.
    If demographic noise is slower than population change
    (i.e., if $\theta/N \approx 0$)
    then the limiting population is deterministic;
    otherwise, it is random (and superprocess-like).

4. The process being deterministic
    coincides with lack of coalescence, I think?
    I'm not sure about this, as $N$ is the *local* density;
    but in our proofs this is precisely when we get coalescence or not.

5. The width equilibrium fluctuations of population size
    depend on $\theta$ (are of width $\theta$?) and so a comparison
    of $\theta$ to $N$ (within the interaction distance?)
    determines whether local extinction/recolonization is likely
    (this is just point 3 again?).
