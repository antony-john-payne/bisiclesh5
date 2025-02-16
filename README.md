# bisiclesh5
Python code to read hdf5 output from the BISICLES ice sheet model using h5py.

You will need install h5py which may be troublesome in condo but works using pip.

import bisiclesh5 as bh5
a = bh5.bisicles_hf5('plot.stable_shelves.500m.000000.2d.hdf5','thickness')

Read specified variable from file. This creates a bisicles_hd5 class that contains

   bisicles_hf5.fname - filename
   bisicles_hf5.time
   bisicles_hf5.variable_name
   bisicles_hf5.full_name
   bisicles_hf5.units
   bisicles_hf5.num_levels - number of levels
   bisicles_hf5.offset - grid offsets for each level [level]
   bisicles_hf5.num_boxes - list of number of boxes in each level [level]
   bisicles_hf5.dx - grid spacing for each level [level]
   bisicles_hf5.x - x, y for each level in global coordinate system
   bisicles_hf5.y - as list of 1-d arrays [level][box]
   bisicles_hf5.data - data for each level as list of 2-d arrays [level][box]

also methods

   bisicles_hf5.plot() - produces a nice plot with AMR boxes
   bisicles_hf5.mesh() - displays grid points (will be slow and need to zoom to see details)
   bisicles_hf5.flatten() - creates flattened version as flat class

b = a.flatten()

can control level that you want to flatten to (default is finest) and region to flatten
(default is entire extent of coarest level. These options have not be tested much.

    flat.fname
    flat.time
    flat.variable_name
    flat.full_name
    flat.units
    flat.dx
    flat.x
    flat.y
    flat.data

there is a guick plot method as well

b.plot()
