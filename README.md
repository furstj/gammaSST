# gammaSST transition and turbulence model
A three-equation transition and turbulence model for OpenFOAM proposed by [Menter, Smirnov, et al.](#Menter2015).

The model is based on the intermittency transport equation with empirical correlations for the transition onset and the intermittency production terms. The main difference with the original four-equation $\gamma-Re_\theta$ model is the equation for $Re_\theta$ is avoided.

The model reads as follows:
$$
\begin{align*}
\frac{\partial (\rho k)}{\partial t} + \frac{\partial (\rho U_j k)}{\partial x_j} &= \gamma P_k + P_k^{lim} - 
\tilde{D}_k + 
\frac{\partial}{\partial x_j} \left[ \left( \mu + \mu_t\sigma_k \right) \frac{\partial k}{\partial x_j} \right], 
\\
\frac{\partial (\rho \omega)}{\partial t} + \frac{\partial (\rho U_j \omega)}{\partial x_j} &= \alpha\frac{P_k}{\nu_t} - 
D_\omega + Cd_\omega +
\frac{\partial}{\partial x_j} \left[ \left( \mu + \mu_t\sigma_\omega \right) \frac{\partial \omega}{\partial x_j} \right], 
\\
\frac{\partial (\rho \gamma)}{\partial t} + \frac{\partial (\rho U_j \gamma)}{\partial x_j} &= P_\gamma - E_\gamma +
\frac{\partial}{\partial x_j} \left[ \left( \mu + \frac{\mu_t}{\sigma_\gamma} \right) \frac{\partial \gamma}{\partial x_j} \right].
\end{align*}
$$

For details on the model, please refer to the original publication by [Menter, Smirnov, et al.](#Menter2015).

Boundary conditions for intermittency $\gamma$ are zero normal flux (i.e. *zeroGradient*) at the wall and $\gamma=1$ at the inlet.

## Installation
1. Download the source code from the repository using git:

    git clone git://github.com/furstj/gammaSST.git

2. Enter the directory where the source code has been extracted, and compile it by typing:

    ./Allwmake
    
3. Add the following line to the *controlDict* of your case:

    libs ( "libIncompressibleGammaSSTModel.so" ) ;

  or

    libs ( "libCompressibleGammaSSTModel.so" ) ;
    
4. Add the following lines to the *turbulenceProperties* dictionary of your case:

    RAS
    {
        RASModel        gammaSST;
        turbulence      on;
        printCoeffs     on;
    }



## References
1. <a id="Menter2015"></a>MENTER, Florian R., SMIRNOV, Pavel E., LIU, Tao and AVANCHA, Ravikanth, 2015. A one-equation local correlation-based transition model. Flow, Turbulence and Combustion. 5 December 2015. Vol. 95, no. 4, p. 583–619. [doi:10.1007/s10494-015-9622-4](https://doi.org/10.1007/s10494-015-9622-4).


