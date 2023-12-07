MOCAT Monte Carlo single run example:

```Py linenums="1"

    addpath(genpath(pwd)); % just temporally include all subfolders

    ICfile = '2020.mat'

    seed = 1; % random number generation base

    disp('MC configuration starting...');
    cfgMC = setup_MCconfig(seed,ICfile);
    fprintf('Seed %i\n', seed);

    fprintf('Initial Population:  %i sats\n', size(cfgMC.mat_sats,1));
    fprintf('Launches per year: %i\n', size(cfgMC.repeatLaunches,1));
    disp('Starting main_mc...');

    [nS,nD,nN,nB]=main_mc(cfgMC,seed);

    % developing functionality
    LRCI(idx) = nS/(nS+nD+nN+nB);
``` 