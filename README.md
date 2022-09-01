# Rapid Axial Turbine Design algorithm (RATD)

This project contains a working, but not final, version of the FORTRAN code and related articles in the docs folder. This is a hobby repository and no major feature enhancements are planned.

In the source code most of the REAL variables are implicitly declared. The original author (L. J. PRITCHARD) worked and ran the code on a Harris 800 computer that had a 48-bit data bus and floating point numbers with 39-bit signed mantissas and 8-bit signed exponents. You can observe vintage catalogs in folder ./docs/Harris.

## Similar repository with implementation on Python
The Python implementation of 'Rapid Axial Turbine Design algorithm (RATD), the original author (L. J. PRITCHARD)' can be obtained from the David Poves repository.

https://github.com/DavidPoves/11-Parameters-Turbine-Blade-Generator

## FORTRAN сompilation
I compile 'ratd.f' with option -fdefault-real-8: set the default real type to an 8 byte wide type. This option also affects the kind of non-double real constants like 1.0. This option promotes the default width of DOUBLE PRECISION and double real constants like 1.d0 to 16 bytes if possible. If -fdefault-double-8 is given along with fdefault-real-8, DOUBLE PRECISION and double real constants are not promoted. Unlike -freal-4-real-8, fdefault-real-8 does not promote variables with explicit kind declarations.

https://gcc.gnu.org/onlinedocs/gfortran/Fortran-Dialect-Options.html

## An Eleven Parameter Axial Turbine Airfoil Geometry Model. Turbomachinery Airfoil Geometry Model. ASME Paper No. 85-GT-219.
Please, read the article in the ./docs folder or from https://asmedigitalcollection.asme.org/GT/proceedings/GT1985/79382/V001T03A058/235951

L. J. PRITCHARD - original author, Senior Aerodynamicist

The author would like to thank Gerry Large, Jim McKenna, and Ron Pampreen whose assistance made this geometry model possible.

...The mathematical derivation, and FORTRAN code, of a comprehensive but easy to use geometry model for axial flow turbine nozzles and rotors is presented. To uniquely define an airfoil on a cylinder the acrodynamicist need only specify the number of blades, and at each radius of interest: the axial and tangential chord, throat, ucovered turning, leading and trailing edge radii, inlet and exit blade angles, and inlet wedge angle. Default values exist for six of these geometric variables, which proves useful when starting a design. Both the suction and the pressure surfaces are described entirely by analytical functions. Sample airfoils are included that demonstrate the effect of each parameter upon blade shape...

## TODO and FIXME
Pull requests are welcome.

1. FIXME: 'SUBROUTINE TITLES'.

Unfortunately, optical character recognition (OCR) of FORTRAN code in article's pdf file is bad. Simple copy-paste not possible. Visual comparison and manual editing is needed.

2. TODO: Implement emulate output to CalComp plotter.

For example, can be used:

CALCOMP - PostScript Emulation of some CALCOMP Plotting Commands.

https://people.sc.fsu.edu/~jburkardt/f77_src/calcomp/calcomp.html

M_calcomp - This is an old Calcomp-compatible graphics library that requires fpm(Fortran Package Manager) to build properly. If you were not specifically looking for a Calcomp look-alike this is not recommended for general use.

https://github.com/urbanjost/M_calcomp

3. TODO: Output coordinates to dat file or others formats.
