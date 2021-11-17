Tips for matking spatial density match up with theoretical expectation:

- Asynchronous life cycle: theoretical calculations might assume that birth and death
    refer to the same population size. But in SLiM they are offset by half a step!
    To make SLiM agree with the theoretical model,
    (a) make it so new offspring don't die their first year (this will be more efficient anyhow, as we don't produce offspring we never use), and
    (b) compute spatial density in `late( )` and save it as a property of the individual to use it in density calculations for birth.

- Boundary effects: individuals near the edge of the range might have lower neighbor density.
    Compute mean nearby density as number of indidivuals per *available* habitat instead.
