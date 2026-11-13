# Table → notebook map

All main and supplementary tables are produced by five notebooks in `notebooks/`. Output files are written to `/kaggle/working/nssp_main_results/` (main notebook) or `/kaggle/working/` (addon notebooks).

| Table | Notebook, cell | Output file |
|---|---|---|
| Table 1, S1a, S1b | nssp_main_tables_kaggle, cell 5 | T1_S1ab_graph_spectrum.csv |
| S2a, S2b | main, cells 4–5 | S2ab_econ_overlap.csv, S2b_econ_variants_graph.csv |
| Table 2, S3a | main, cell 6 | T2_S3a_variance.csv |
| S3b | main, cell 6 | S3b_identification.csv |
| S4 | main, cell 7 | S4_profile_rho.csv |
| S5 | nssp_addon8_kaggle, cell 6 | S5_MC_rho_year_shocks.csv |
| S6 | main, cell 7 | S6_model_fit.csv |
| Table 4, S7a–f, S8a–f | main, cell 7 | T4_queen_SDM_*.csv, S7_coefficients.csv, S8_impacts.csv |
| Table 5, S14, S15 | main, cell 7 | T5_sanit_indirect_robustness.csv, S8_impacts.csv (sample = full+HDI; idw_*) |
| S9, S10 | main, cell 7 | S9_indirect_share_sanit.csv, S10_rho0_substitution_vs_SLX.csv |
| S16, S17, S18a, S19 | main, cell 7 | S16_LR_tests.csv, S17_LM_tests.csv, S18a_hausman.csv, S19_pairwise_AIC.csv |
| S20–S22 | main, cell 7 | S20_S22_econ_variants.csv |
| S23a, S23b | main, cell 7 | S23ab_VIF_demeaned_design.csv |
| Table 3, S11, S11b, S11c | nssp_precise_tables_kaggle, cell 6 | T3_S11_elpd_comparison.csv, S11b_exact_refits_totals.csv, S11c_exact_refits_pointwise.csv, MCSE_elpd_between_chains.csv |
| S12, S13a | nssp_precise_tables_kaggle, cell 6 | S12_S13a_model_weights.csv |
| Table 6, S13b | nssp_precise_tables_kaggle, cell 6 | T6_S13b_model_averaged_impacts.csv |
| Table 7, S27–S29, Table 8 | nssp_precise_tables_kaggle, cell 7 | T7_S27_dynamic_bc.csv, S28_dynamic_coefficients.csv, S29_dynamic_impacts.csv, T8_dynamic_sanit_queen.csv, MCSE_dynamic_blocks.csv |
| S26 | main, cell 10 | S26_dynamic_sample.csv |
| S30, S31a–c | nssp_addon8_kaggle, cell 8 | S30_bayes_dynamic_full.csv, S31abc_bayes_dynamic_coefficients.csv |
| S32 | nssp_addon8_kaggle, cell 6 | S32_MC_W_recovery.csv |
| S33 | main, cell 11 | S33_degree_vs_node_impacts.csv |
| S24, S24b | nssp_addon6_kaggle, cell 8 | ADD_E8_power_curve_econ.csv |
| S35, S36 | nssp_addon6_kaggle, cells 6–7 | ADD_E7a_*.csv, ADD_E7b_*.csv |
| S34 | nssp_addon7_kaggle, cells 6–8 | ADD_E9_*.csv |
| S18b | nssp_addon8_kaggle, cell 7 | S18b_spatial_hausman.csv |
| S25 | nssp_addon8_kaggle, cell 9 | S25_original_estimates_spectral_radius.csv |
| Moran's I, Getis–Ord Gi*, LISA (Section 3.1), Fig. 2 | nssp_addon8_kaggle, cell 5 | moran_I_by_year.csv, lisa_getis_2024.csv, Fig2_LISA_2024.png |
| Fig. 1 | conceptual workflow diagram (no data) | — |

The main notebook ends with `CHECK_vs_manuscript_and_addon5.csv`, comparing recomputed values with the manuscript and with `results/addon5`.

Tables that depend on random draws (Bayesian elpd, stacking, bootstrap bias correction) are taken from `nssp_precise_tables_kaggle.ipynb`, which uses two independent chains of 8,000 draws and three blocks of 1,999 bootstrap replications and reports the Monte Carlo error between them. The main notebook computes the same quantities with fewer draws as a check.
