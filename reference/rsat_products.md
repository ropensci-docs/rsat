# Show the products accepted by the services

Show the products accepted by the services

## Usage

``` r
rsat_products(...)

# S4 method for class 'ANY'
rsat_products()
```

## Arguments

- ...:

  additional arguments.

## Value

prints a list of products

## Examples

``` r
rsat_products()
#> [1] "-------------------------------------------------------------------------"
#> [1] "    rsat supported products"
#> [1] "-------------------------------------------------------------------------"
#> [1] "MODIS_Aqua: MYD09A1, MYD09CMG, MYD09GA, MYD09GQ, MYD09Q1, MYD11A1, MYD11A2 , MYD11B1, MYD11B2, MYD11B3, MYD11C1, MYD11C2, MYD11C3, MYD11_L2, MYD13A1, MYD13A2 , MYD13A3, MYD13C1, MYD13C2, MYD13Q1, MYD14, MYD14A1, MYD14A2, MYD15A2H, MYD16A2, MYD16A2GF, MYD16A3GF, MYD17A2H, MYD17A2HGF, MYD17A3HGF, MYD21, MYD21A1D, MYD21A1N, MYD21A2, MYD21C1, MYD21C2, MYD21C3, MYD28C2, MYD28C3"
#> [1] "MODIS_Terra: MOD09A1, MOD09CMG, MOD09GA, MOD09GQ, MOD09Q1, MOD11A1, MOD11A2 , MOD11B1, MOD11B2, MOD11B3, MOD11C1, MOD11C2, MOD11C3, MOD11_L2, MOD13A1, MOD13A2 , MOD13A3, MOD13C1, MOD13C2, MOD13Q1, MOD14, MOD14A1, MOD14A2, MOD15A2H, MOD16A2, MOD16A2GF, MOD16A3GF, MOD17A2H, MOD17A2HGF, MOD17A3HGF, MOD21, MOD21A1D, MOD21A1N, MOD21A2, MOD21C1, MOD21C2, MOD21C3, MOD28C2, MOD28C3"
#> [1] "-------------------------------------------------------------------------"
#> [1] "Landsat-8: landsat_ot_c2_l2, landsat_ot_c2_l1, lsr_landsat_8_c1, landsat_8_c1"
#> [1] "Landsat-7: landsat_etm_c2_l2, landsat_etm_c2_l1, lsr_landsat_etm_c1, landsat_etm_c1"
#> [1] "Landsat_1-5: landsat_tm_c2_l2, landsat_tm_c2_l1, landsat_mss_c2_l1, lsr_landsat_tm_c1, landsat_tm_c1, landsat_mss_c1"
#> [1] "-------------------------------------------------------------------------"
#> [1] "Sentinel-1: SLC, GRD, OCN"
#> [1] "Sentinel-2: S2MSI2A, S2MSI1C, S2MS2Ap"
#> [1] "Sentinel-3: SR_1_SRA___, SR_1_SRA_A, SR_1_SRA_BS, SR_2_LAN___, OL_1_EFR___, OL_1_ERR___, OL_2_LFR___, OL_2_LRR___, SL_1_RBT___, SL_2_LST___, SY_2_SYN___, SY_2_V10___, SY_2_VG1___, SY_2_VGP___"
#> [1] "Sentinel-5: L1B_IR_SIR, L1B_IR_UVN, L1B_RA_BD1, L1B_RA_BD2, L1B_RA_BD3, L1B_RA_BD4, L1B_RA_BD5, L1B_RA_BD6, L1B_RA_BD7, L1B_RA_BD8, L2__AER_AI, L2__AER_LH, L2__CH4, L2__CLOUD_, L2__CO____, L2__HCHO__, L2__NO2___, L2__NP_BD3, L2__NP_BD6, L2__NP_BD7, L2__O3_TCL, L2__O3____, L2__SO2___"
#> [1] "-------------------------------------------------------------------------"
```
