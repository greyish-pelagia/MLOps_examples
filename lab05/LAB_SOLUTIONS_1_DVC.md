```bash
(mlops-course-agh-lab-05) marcinmalek@Marcins-MacBook-Air lab05 % uv run python ames_inspect_data.py --file-path data/ames_data_2006_2008.parquet
     Order        PID  MS.SubClass MS.Zoning  Lot.Frontage  Lot.Area Street Alley Lot.Shape Land.Contour  ... Pool.Area Pool.QC Fence Misc.Feature Misc.Val Mo.Sold Yr.Sold Sale.Type  Sale.Condition  SalePrice
989    990  526351030           20        RL          87.0     11029   Pave  None       IR1          Lvl  ...         0    None  None         None        0       5    2008       WD           Normal     176500
990    991  526353050           20        RL           NaN     12925   Pave  None       IR1          Lvl  ...         0    None  None         None        0       5    2008       WD           Normal     237500
991    992  526354070           60        RL          85.0     11075   Pave  None       Reg          Lvl  ...         0    None  None         None        0       6    2008       WD           Normal     206900
992    993  527105050           60        RL          72.0      8702   Pave  None       IR1          Lvl  ...         0    None  None         None        0       4    2008       WD           Normal     187500
993    994  527106050           60        RL          65.0      8139   Pave  None       Reg          Lvl  ...         0    None  None         None        0      10    2008       WD           Normal     165000

[5 rows x 82 columns]
```

```bash
(mlops-course-agh-lab-05) marcinmalek@Marcins-MacBook-Air lab05 % uv run python ames_data_cleaning.py --file-path data/ames_data_2006_2008.parquet
/Users/marcinmalek/Documents/Codes/Projects/1_AGH/MLOps_examples/lab05/ames_data_cleaning.py:181: FutureWarning: Downcasting behavior in `replace` is deprecated and will be removed in a future version. To retain the old behavior, explicitly call `result.infer_objects(copy=False)`. To opt-in to the future behavior, set `pd.set_option('future.no_silent_downcasting', True)`
  df = df.replace(
(mlops-course-agh-lab-05) marcinmalek@Marcins-MacBook-Air lab05 % uv run python ames_inspect_data.py --file-path data/ames_data_2006_2008.parquet
    MSSubClass MSZoning  LotFrontage  LotArea  Street  Alley  LotShape LandContour  Utilities LotConfig  ...  PoolArea PoolQC Fence MiscFeature MiscVal MoSold  YrSold  SaleType  SaleCondition  SalePrice
989       SC20       RL         87.0    11029       2      0         3         Lvl          4    Corner  ...         0      0    No          No       0    May    2008       WD          Normal     176500
990       SC20       RL          0.0    12925       2      0         3         Lvl          4    Corner  ...         0      0    No          No       0    May    2008       WD          Normal     237500
991       SC60       RL         85.0    11075       2      0         4         Lvl          4    Inside  ...         0      0    No          No       0    Jun    2008       WD          Normal     206900
992       SC60       RL         72.0     8702       2      0         3         Lvl          4    Inside  ...         0      0    No          No       0    Apr    2008       WD          Normal     187500
993       SC60       RL         65.0     8139       2      0         4         Lvl          4    Inside  ...         0      0    No          No       0    Oct    2008       WD          Normal     165000

[5 rows x 80 columns]
```

```bash
(mlops-course-agh-lab-05) marcinmalek@Marcins-MacBook-Air lab05 % dvc checkout
Building workspace index                                                                                                                                                                        |2.00 [00:00,  281entry/s]
Comparing indexes                                                                                                                                                                              |4.00 [00:00, 2.71kentry/s]
Applying changes                                                                                                                                                                                |1.00 [00:00, 1.72kfile/s]
A       data/ames_data_2006_2008.parquet
(mlops-course-agh-lab-05) marcinmalek@Marcins-MacBook-Air lab05 % git checkout HEAD~2
M       .gitignore
Note: switching to 'HEAD~2'.
HEAD is now at 758d647 dvc update
(mlops-course-agh-lab-05) marcinmalek@Marcins-MacBook-Air lab05 % dvc checkout
Building workspace index                                                                                                                                                                        |3.00 [00:00,  407entry/s]
Comparing indexes                                                                                                                                                                              |4.00 [00:00, 2.66kentry/s]
Applying changes                                                                                                                                                                                |1.00 [00:00, 1.53kfile/s]
M       data/ames_data_2006_2008.parquet
(mlops-course-agh-lab-05) marcinmalek@Marcins-MacBook-Air lab05 % uv run python ames_inspect_data.py --file-path data/ames_data_2006_2008.parquet
     Order        PID  MS.SubClass MS.Zoning  Lot.Frontage  Lot.Area Street Alley Lot.Shape Land.Contour  ... Pool.Area Pool.QC Fence Misc.Feature Misc.Val Mo.Sold Yr.Sold Sale.Type  Sale.Condition  SalePrice
989    990  526351030           20        RL          87.0     11029   Pave  None       IR1          Lvl  ...         0    None  None         None        0       5    2008       WD           Normal     176500
990    991  526353050           20        RL           NaN     12925   Pave  None       IR1          Lvl  ...         0    None  None         None        0       5    2008       WD           Normal     237500
991    992  526354070           60        RL          85.0     11075   Pave  None       Reg          Lvl  ...         0    None  None         None        0       6    2008       WD           Normal     206900
992    993  527105050           60        RL          72.0      8702   Pave  None       IR1          Lvl  ...         0    None  None         None        0       4    2008       WD           Normal     187500
993    994  527106050           60        RL          65.0      8139   Pave  None       Reg          Lvl  ...         0    None  None         None        0      10    2008       WD           Normal     165000

[5 rows x 82 columns]
```
