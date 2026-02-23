# gothic_ctsm
tools and plotting for CTSM simulations at Gothic, CO

1) Clone CTSM
   - Follow steps on [CTSM-wiki](https://github.com/ESCOMP/CTSM/wiki/Quick-start-to-CTSM-development-with-git)
   - run ./py_env_create
2) Run subset data for single point (see `tools/site_and_regional`)
   ```
   ./subset_data point --lat 38.9375 --lon 253.0625 \
   --create-surface \
   --uniform-snowpack \
   --outdir /glade/derecho/scratch/$USER/nldas/gothic/ \
   --site Gothic_aspen \
   --dompft 8 \
   --create-user-mods \
   --overwrite
   ```        
3) Modify usermods to customize your settings
   - see `/glade/campaign/cgd/tss/people/wwieder/gothic/user_mods_BGC`
4) Create and run new case
   ```
   ./create_newcase --case /glade/work/$USER/gothic/aspen_sp_test0 \
   --res CLM_USRDAT \
   --compset HIST_DATM%1PT_CLM60%SP_SICE_SOCN_SROF_SGLC_SWAV_SESP \
   --output-root /glade/derecho/scratch/$USER/gothic \
   --run-unsupported \
   --user-mods-dir /glade/derecho/scratch/$USER/nldas/gothic/user_mods
   ```
   - See also this [tutorial example](https://github.com/wwieder/CTSM-Tutorial/blob/NEON_Tutorial_2023/notebooks/ProjectExamples/CTSMsp_NEON_fromScratch.ipynb)
