# Adsorption Information File
This repository contains the details of an universal file format for gas adsorption experiments.

## Core dictionary
The current dictionary of data items used by adsorption information files can be found below:

| data name | description |
| --- | --- |
| _exptl_operator | name of the person who ran the experiment (string) |
| _exptl_date | date of the experiment (string in ISO 8601 format)|
| _exptl_instrument | instrument id used for the experiment (string)    | 
| _exptl_location | location of the experiment (string)    | 
| _exptl_adsorptive |  name of the adsorptive (string)    | 
| _exptl_temperature | temperature of the experiment (float)    | 
| _exptl_sample_mass | mass of the sample (float)   | 
| _exptl_sample_density | density of the sample (float)   | 
| _exptl_notes | notes of the adsorption experiment (string)   | 
| _exptl_run_number | run number for cycle experiments (integer)   | 
| _exptl_p0 | saturation pressure of the experiment at the temperature of the experiment (float) |
| _exptl_method | method of measuring adsorption (volumetric, chromatographic, gravimetric, simulation) |
| _sample_id | unique identifying code used by the operator (string)  | 
| _sample_material_id | designated name for the material (string)   | 
| _sample_notes | notes of sample preparation (string)   | 
| _units_temperature | units of temperature (string)  | 
| _units_pressure | units of pressure (string)   | 
| _units_mass | units of mass (string)  | 
| _units_loading | units of amount adsorbed (string)   |
| _units_loading_type | adsorption definition (net, excess, absolute)   | 
| _units_density | units of density (string)   |  
| _adsorp_pressure | equilibrium pressure of the adsorption measurement (float)  | 
| _adsorp_p0 |  saturation pressure of the adsorption measurement at the temperature of the experiment (float)   | 
| _adsorp_amount  | amount adsorbed during the adsorption measurement (float)   | 
| _desorp_pressure | equilibrium  pressure of the desorption measurement at the temperature of the experiment (float)   | 
| _desorp_p0 | saturation pressure of the desorption measurement at the temperature of the experiment (float)   | 
| _desorp_amount |  amount adsorbed during the desorption measurement (float)   |
| _audit_aifversion | version number of AIF dicitionary (integer) |

## Mixture adsorption
Mixture adsorption can be defined using the same terms as the core dictionary where the suffix *_n*, where n=1,2,3 can be added to data names to refer to different adsorptives. For example:

| data name | description |
| --- | --- |
| _exptl_adsorptive_n |  name of the adsorptive for mixture adsorption n=1,2,3 (string) |
| _exptl_adsorptive_n_molfraction | mole fraction of adsorptive n (float) | 
| _adsorp_pressure_n | equilibrium pressure of the adsorptive n  (float)  | 
| _adsorp_amount_n  | amount adsorbed of species n  (float)   | 

Please note, in this case *_adsorp_pressure* is used to refer to the total pressure.

## Cycle experiments
Adsorption cycle experiments can be defined using multi data blocks within the same AIF. data_blocks should be labeled with the number of the run (*data_run1*) and the *_exptl_run_number* data name used.


## raw2aif converter
A simple program was produced for windows computers to facilitate the production of adsorption information files from raw analysis text files exported by Quantachrome software (*.txt*) and the Belsorb software raw data files (*.DAT*) and xls files exported by Micromeritics software (*.xls*).

The current versions of this program can be found on the [release page](https://github.com/jackevansadl/adsorptioninformationformat/releases),
of this repository.

## Citation
Jack D. Evans, Volodymyr Bon, Irena Senkovska, and Stefan Kaskel, *preprint*, **2021**, preprint.
  DOI: [10.26434/chemrxiv.13562798](https://dx.doi.org/10.26434/chemrxiv.13562798)
  
