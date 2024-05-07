# 3-storey-
wipe
model  BasicBuilder  -ndm  2  -ndf  3 
# NodeCoord.tcl 

# Node   tag       xCrd           yCrd       ndf 
node       1  +0.000000E+00  +0.000000E+00  -ndf 3 
node       2  +1.968500E+02  +0.000000E+00  -ndf 3 
node       3  +0.000000E+00  +1.181100E+02  -ndf 3 
node       4  +1.968500E+02  +1.181100E+02  -ndf 3 
node       5  +8.465000E+01  +1.181100E+02  -ndf 3 
node       6  +1.122000E+02  +1.181100E+02  -ndf 3 
node       7  +0.000000E+00  +2.362200E+02  -ndf 3 
node       8  +1.968500E+02  +2.362200E+02  -ndf 3 
node       9  +8.465000E+01  +2.362200E+02  -ndf 3 
node      10  +1.122000E+02  +2.362200E+02  -ndf 3 
node      11  +0.000000E+00  +3.543300E+02  -ndf 3 
node      12  +1.968500E+02  +3.543300E+02  -ndf 3 
node      13  +8.465000E+01  +3.543300E+02  -ndf 3 
node      14  +1.122000E+02  +3.543300E+02  -ndf 3 
node      15  +1.968500E+02  +1.181100E+02  -ndf 3 
node      16  +0.000000E+00  +1.181100E+02  -ndf 3 
node      17  +1.968500E+02  +2.362200E+02  -ndf 3 
node      18  +0.000000E+00  +2.362200E+02  -ndf 3 
node      19  +1.968500E+02  +3.543300E+02  -ndf 3 
node      20  +0.000000E+00  +3.543300E+02  -ndf 3 
# Materials.tcl 

# Material "BeamColumnBrace":    matTag    Fy    E    b    R0    cR1    cR2    <a1    a2    a3    a4>    <sig0> 
uniaxialMaterial  Steel02       1  +5.000000E+01  +2.900000E+04  +5.000000E-02  +1.850000E+01  +9.250000E-01  +1.500000E-01  +0.000000E+00  +1.000000E+00  +0.000000E+00  +1.000000E+00  +0.000000E+00 

# Material "Material01":    matTag    E    <eta>    <Eneg>  
uniaxialMaterial  Elastic       2  +5 +0.000000E+00 
# Material "Material01":    matTag    E    <eta>    <Eneg>  
uniaxialMaterial  Elastic       3  1000 +0.000000E+00 


# Sections.tcl 

# Section "Beam1":    secTag 
section  Fiber       1  { 
    # PatchAISC "Beam1":    matTag    NSIJ    NSJK    Iy    Iz    Jy    Jz    Ky    Kz    Ly    Lz 
    patch  quad       1     6     1  +5.710000E+00  +3.260000E+00  +5.710000E+00  -3.260000E+00  +6.150000E+00  -3.260000E+00  +6.150000E+00  +3.260000E+00 
    patch  quad       1     1     6  -5.710000E+00  +1.300000E-01  -5.710000E+00  -1.300000E-01  +5.710000E+00  -1.300000E-01  +5.710000E+00  +1.300000E-01 
    patch  quad       1     6     1  -6.150000E+00  +3.260000E+00  -6.150000E+00  -3.260000E+00  -5.710000E+00  -3.260000E+00  -5.710000E+00  +3.260000E+00 
} 

# Section "Beam2":    secTag 
section  Fiber       2  { 
    # PatchAISC "Beam2":    matTag    NSIJ    NSJK    Iy    Iz    Jy    Jz    Ky    Kz    Ly    Lz 
    patch  quad       1     6     1  +5.720000E+00  +3.245000E+00  +5.720000E+00  -3.245000E+00  +6.100000E+00  -3.245000E+00  +6.100000E+00  +3.245000E+00 
    patch  quad       1     1     6  -5.720000E+00  +1.150000E-01  -5.720000E+00  -1.150000E-01  +5.720000E+00  -1.150000E-01  +5.720000E+00  +1.150000E-01 
    patch  quad       1     6     1  -6.100000E+00  +3.245000E+00  -6.100000E+00  -3.245000E+00  -5.720000E+00  -3.245000E+00  -5.720000E+00  +3.245000E+00 
} 

# Section "Brace":    secTag 
section  Fiber       3  { 
    # PatchAISC "Brace":    matTag    NSIJ    NSJK    Iy    Iz    Jy    Jz    Ky    Kz    Ly    Lz 
    patch  quad       1     1     1  +2.035000E+00  +2.500000E+00  +2.035000E+00  -2.500000E+00  +2.500000E+00  -2.500000E+00  +2.500000E+00  +2.500000E+00 
    patch  quad       1     1     1  -2.035000E+00  +2.500000E+00  -2.035000E+00  +2.035000E+00  +2.035000E+00  +2.035000E+00  +2.035000E+00  +2.500000E+00 
    patch  quad       1     1     1  -2.035000E+00  -2.035000E+00  -2.035000E+00  -2.500000E+00  +2.035000E+00  -2.500000E+00  +2.035000E+00  -2.035000E+00 
    patch  quad       1     1     1  -2.500000E+00  +2.500000E+00  -2.500000E+00  -2.500000E+00  -2.035000E+00  -2.500000E+00  -2.035000E+00  +2.500000E+00 
} 

# Section "Column1":    secTag 
section  Fiber       4  { 
    # PatchAISC "Column1":    matTag    NSIJ    NSJK    Iy    Iz    Jy    Jz    Ky    Kz    Ly    Lz 
    patch  quad       1     6     1  +3.565000E+00  +4.000000E+00  +3.565000E+00  -4.000000E+00  +4.000000E+00  -4.000000E+00  +4.000000E+00  +4.000000E+00 
    patch  quad       1     1     6  -3.565000E+00  +1.425000E-01  -3.565000E+00  -1.425000E-01  +3.565000E+00  -1.425000E-01  +3.565000E+00  +1.425000E-01 
    patch  quad       1     6     1  -4.000000E+00  +4.000000E+00  -4.000000E+00  -4.000000E+00  -3.565000E+00  -4.000000E+00  -3.565000E+00  +4.000000E+00 
} 

# Section "Column3":    secTag 
section  Fiber       5  { 
    # PatchAISC "Column3":    matTag    NSIJ    NSJK    Iy    Iz    Jy    Jz    Ky    Kz    Ly    Lz 
    patch  quad       1     6     1  +2.735000E+00  +2.995000E+00  +2.735000E+00  -2.995000E+00  +2.995000E+00  -2.995000E+00  +2.995000E+00  +2.995000E+00 
    patch  quad       1     1     6  -2.735000E+00  +1.150000E-01  -2.735000E+00  -1.150000E-01  +2.735000E+00  -1.150000E-01  +2.735000E+00  +1.150000E-01 
    patch  quad       1     6     1  -2.995000E+00  +2.995000E+00  -2.995000E+00  -2.995000E+00  -2.735000E+00  -2.995000E+00  -2.735000E+00  +2.995000E+00 
} 

# Section "ElasticDefault":    secTag    E    A    Iz    <G>    <alpha> 
section  Elastic       6  +2.900000E+04  +1.800000E+02  +4.860000E+03  +1.115400E+04  +8.333333E-01 
# SPConstraint.tcl 

# SPC   tag    Dx    Dy    Rz 
fix       1     1     1     1 
fix       2     1     1     1 

# GeoTran.tcl 

# GeoTran    type    tag    vec_xz 
geomTransf  Corotational       1 
# Elements.tcl 

# Element "Column1":    eleTag    NodeI    NodeJ    NIP    secTag    geoTranTag    <-mass massDens>    <-iter maxIters tol> 
element  forceBeamColumn       1       1       3     5     4     1  -mass +0.000000E+00  -iter   10  +1.000000E-12  -integration Lobatto 

# Element "Beam1":    eleTag    NodeI    NodeJ    NIP    secTag    geoTranTag    <-mass massDens>    <-iter maxIters tol> 
element  forceBeamColumn       2      15      16     5     1     1  -mass +0.000000E+00  -iter   10  +1.000000E-12  -integration Lobatto 

# Element "Beam2":    eleTag    NodeI    NodeJ    NIP    secTag    geoTranTag    <-mass massDens>    <-iter maxIters tol> 
element  forceBeamColumn       3      17      18     5     2     1  -mass +0.000000E+00  -iter   10  +1.000000E-12  -integration Lobatto 

# Element "Beam2":    eleTag    NodeI    NodeJ    NIP    secTag    geoTranTag    <-mass massDens>    <-iter maxIters tol> 
element  forceBeamColumn       4      19      20     5     2     1  -mass +0.000000E+00  -iter   10  +1.000000E-12  -integration Lobatto 

# Element "Column1":    eleTag    NodeI    NodeJ    NIP    secTag    geoTranTag    <-mass massDens>    <-iter maxIters tol> 
element  forceBeamColumn       5       4       2     5     4     1  -mass +0.000000E+00  -iter   10  +1.000000E-12  -integration Lobatto 

# Element "Column1":    eleTag    NodeI    NodeJ    NIP    secTag    geoTranTag    <-mass massDens>    <-iter maxIters tol> 
element  forceBeamColumn       6       3       7     5     4     1  -mass +0.000000E+00  -iter   10  +1.000000E-12  -integration Lobatto 

# Element "Brace":    eleTag    NodeI    NodeJ    secTag    <-rho rho>    <-cMass flag>    <-doRayleigh flag> 
element  truss       7       1       5     3  -rho +0.000000E+00  -cMass 0  -doRayleigh 0 

# Element "Brace":    eleTag    NodeI    NodeJ    secTag    <-rho rho>    <-cMass flag>    <-doRayleigh flag> 
element  truss       8       6       2     3  -rho +0.000000E+00  -cMass 0  -doRayleigh 0 

# Element "Brace":    eleTag    NodeI    NodeJ    secTag    <-rho rho>    <-cMass flag>    <-doRayleigh flag> 
element  truss       9       3       9     3  -rho +0.000000E+00  -cMass 0  -doRayleigh 0 

# Element "Column1":    eleTag    NodeI    NodeJ    NIP    secTag    geoTranTag    <-mass massDens>    <-iter maxIters tol> 
element  forceBeamColumn      10       8       4     5     4     1  -mass +0.000000E+00  -iter   10  +1.000000E-12  -integration Lobatto 

# Element "Column3":    eleTag    NodeI    NodeJ    NIP    secTag    geoTranTag    <-mass massDens>    <-iter maxIters tol> 
element  forceBeamColumn      11       7      11     5     5     1  -mass +0.000000E+00  -iter   10  +1.000000E-12  -integration Lobatto 

# Element "Brace":    eleTag    NodeI    NodeJ    secTag    <-rho rho>    <-cMass flag>    <-doRayleigh flag> 
element  truss      12      10       4     3  -rho +0.000000E+00  -cMass 0  -doRayleigh 0 

# Element "Brace":    eleTag    NodeI    NodeJ    secTag    <-rho rho>    <-cMass flag>    <-doRayleigh flag> 
element  truss      13       7      13     3  -rho +0.000000E+00  -cMass 0  -doRayleigh 0 

# Element "Brace":    eleTag    NodeI    NodeJ    secTag    <-rho rho>    <-cMass flag>    <-doRayleigh flag> 
element  truss      14      14       8     3  -rho +0.000000E+00  -cMass 0  -doRayleigh 0 

# Element "Column3":    eleTag    NodeI    NodeJ    NIP    secTag    geoTranTag    <-mass massDens>    <-iter maxIters tol> 
element  forceBeamColumn      15      12       8     5     5     1  -mass +0.000000E+00  -iter   10  +1.000000E-12  -integration Lobatto 

# Element "Element01":    eleTag    NodeI    NodeJ    -mat matTag1 matTag2 ...    -dir dir1 dir2 ...    <-orient x1 x2 x3 y1 y2 y3>    <-doRayleigh flag> 
element  zeroLength      16       4      15  -mat 3  3  2  -dir 1  2  3 -orient -1.000000E+00 +0.000000E+00 +0.000000E+00  +0.000000E+00 -1.000000E+00 +0.000000E+00 

# Element "Element01":    eleTag    NodeI    NodeJ    -mat matTag1 matTag2 ...    -dir dir1 dir2 ...    <-orient x1 x2 x3 y1 y2 y3>    <-doRayleigh flag> 
element  zeroLength      17      16       3  -mat 3  3  2  -dir 1  2  3 -orient -1.000000E+00 +0.000000E+00 +0.000000E+00  +0.000000E+00 -1.000000E+00 +0.000000E+00 

# Element "Element01":    eleTag    NodeI    NodeJ    -mat matTag1 matTag2 ...    -dir dir1 dir2 ...    <-orient x1 x2 x3 y1 y2 y3>    <-doRayleigh flag> 
element  zeroLength      18       8      17  -mat 3  3  2  -dir 1  2  3 -orient -1.000000E+00 +0.000000E+00 +0.000000E+00  +0.000000E+00 -1.000000E+00 +0.000000E+00 

# Element "Element01":    eleTag    NodeI    NodeJ    -mat matTag1 matTag2 ...    -dir dir1 dir2 ...    <-orient x1 x2 x3 y1 y2 y3>    <-doRayleigh flag> 
element  zeroLength      19      18       7  -mat 3  3  2  -dir 1  2  3 -orient -1.000000E+00 +0.000000E+00 +0.000000E+00  +0.000000E+00 -1.000000E+00 +0.000000E+00 

# Element "Element01":    eleTag    NodeI    NodeJ    -mat matTag1 matTag2 ...    -dir dir1 dir2 ...    <-orient x1 x2 x3 y1 y2 y3>    <-doRayleigh flag> 
element  zeroLength      20      12      19  -mat 3  3  2  -dir 1  2  3 -orient -1.000000E+00 +0.000000E+00 +0.000000E+00  +0.000000E+00 -1.000000E+00 +0.000000E+00 

# Element "Element01":    eleTag    NodeI    NodeJ    -mat matTag1 matTag2 ...    -dir dir1 dir2 ...    <-orient x1 x2 x3 y1 y2 y3>    <-doRayleigh flag> 
element  zeroLength      21      20      11  -mat 3  3  2  -dir 1  2  3 -orient -1.000000E+00 +0.000000E+00 +0.000000E+00  +0.000000E+00 -1.000000E+00 +0.000000E+00 
# Recorder_3.tcl 

# Node Recorder "AllNode":    fileName    <nodeTag>    dof    respType 
recorder  Node  -file  trial1.out  -time  -node 1 2 3 4 5 6 -dof 1  2  3  disp

# LoadPattern_3.tcl 
#Define gravity loads
pattern Plain 1 Constant {
load       8  0  -100  0  

load       7  0  -100  0

 
    # eleLoad    eleTags    beamPoint    Py    xL    <Px> 
 
    # eleLoad    eleTags    selfWeight    xFactor    yFactor 
} 
# AnalysisOptn "StaticDefault": Type: Static 
# ------------------------------------------ 
constraints Transformation;     		# how it handles boundary conditions
numberer Plain;					# renumber dof's to minimize band-width (optimization), if you want to
system BandGeneral;				# how to store and solve the system of equations in the analysis
test NormDispIncr 1.0e-3 6 ; 			# determine if convergence has been achieved at the end of an iteration step
algorithm Newton;				# use Newton's solution algorithm: updates tangent stiffness at every iteration
integrator LoadControl 1;			# determine the next time step for an analysis, # apply gravity in 10 steps
analysis Static					# define type of analysis static or transient
analyze 10;					# perform gravity analysis
