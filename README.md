# BiotDD
Repository containing deal.ii implementation of domain decomposition for Biot system of poroelasticity.
Also contains preprints of publications related to this project(to be added).
Biot DD with and without mortar.

Authors: Manu Jayadharan, Eldar Khattatov, University of Pittsburgh 2018-2019.

mortar_flag: 0=no_mortar, 1=mortar_without_mulstiscale_basis, 2=mortar_with_multiscale_basis.
split_flag: 0=monolithic, 1=draine_split(DS), 2=fixed_stress.

Biotparameters bparam(delta_t, num_of_time_steps,c_0,alpha).
