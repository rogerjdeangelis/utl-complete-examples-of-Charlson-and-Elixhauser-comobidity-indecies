# utl-complete-examples-of-Charlson-and-Elixhauser-comobidity-indecies
Complete examples of Charlson and Elixhauser comobidity indecies.

    Complete examples of Charlson and Elixhauser comobidity indecies

    see
    https://cran.r-project.org/web/packages/comorbidity/vignettes/comorbidityscores.html

    my macros
    https://tinyurl.com/y9nfugth
    https://github.com/rogerjdeangelis/utl-macros-used-in-many-of-rogerjdeangelis-repositories

    R package for Charlson Index

     medicalrisk
     comoRbidity
     comorbidity


    R has three packages to computes Charlson and Elixhauser comobidity indecies.
    They do both ICD9 and ICD10.


    CHARLSON INDEX

    Many variations of the Charlson comorbidity index have been presented,
    as outlined by Sharabiani et al. in their systematic review. comorbidity
    computes the Quan et al. version of the Charlson score for both ICD-9-CM
    and ICD-10 coding systems, as outlined in their paper from 2005; in the next
    subsections, we present the different ICD codes utilised by comorbidity. Categorisation of
    scores and weighted scores is based on work by Menendez et al.


    ELIXHAUSER INDEX

    The Elixhauser comorbidity index, analogously as the Charlson comorbidity
    index, is a method for measuring patient comorbidity based on ICD-9-CM
    and ICD-10 diagnosis codes found in administrative data developed by
    Elixhauser et al. in 1998. Over time, there have been changes to the
    Index based on different research. For instance:
    The original index was developed with 30 categories. Now there are
    variants with 31 categories (Garland et al., 2012);
    the list of specific ICD diagnosis codes that are used to identify
    different categories of comorbidity have been modified and updated
    from ICD-9-CM to work with ICD-10 coding (Quan et al., 2005);
    weighting algorithms were developed, based on the association between
    comorbidity and death, in order to produce an overall score for the
    Elixhauser index (van Walraven et al., 2009; Moore et al., 2016).
    comorbidity is using the coding definition of Quan et al. (2005) for
    both ICD-9-CM and ICD-10 coding systems. The weighting is based on work by
    Moore et al. (2016); however, as the AHRQ Elixhauser comorbidity score
    only includes 29 comorbidites and not 31 (as in the Quan et al. version),
    we included weights from van Walraven et al. for the missing comorbidities.
    The actual codes and weights utilised by comorbidity are introduced
    in the next subsections.
    Finally, the categorisation of scores and
    weighted scores is based on work by Menendez et al.

    *_                   _
    (_)_ __  _ __  _   _| |_
    | | '_ \| '_ \| | | | __|
    | | | | | |_) | |_| | |_
    |_|_| |_| .__/ \__,_|\__|
            |_|
    ;

    options validvarname=upcase;
    libname sd1 "d:/sd1";

    * Three patients and thier ICD-10 Codes;

    data sd1.have;
     input pat icd10$;
    cards4;
    1 M519
    1 T469
    1 K717
    1 T400
    1 Q308
    1 U016
    1 F653
    1 B677
    1 H930
    2 P11
    2 M79
    2 C577
    2 R864
    2 O047
    2 S934
    2 S032
    2 L538
    2 C436
    2 N180
    2 K611
    3 E161
    3 Q659
    3 T025
    3 S832
    3 N490
    3 A505
    3 M42
    3 Q990
    3 M430
    3 Q55
    ;;;;
    run;quit;

    *            _               _
      ___  _   _| |_ _ __  _   _| |_
     / _ \| | | | __| '_ \| | | | __|
    | (_) | |_| | |_| |_) | |_| | |_
     \___/ \__,_|\__| .__/ \__,_|\__|
                    |_|
    ;

    CHARLSON INDEX  (see below for documentation)
    --------------
                      PATIENTS
                      --------

    CONDITION      1     2     3

      AMI          0     0     0   Myocardial infarction
      CHF          0     0     0   Congestive heart failure
      PVD          0     0     0   Peripheral vascular disease
      CEVD         0     0     0   Cerebrovascular disease
      DEMENTIA     0     0     0   Dementia
      COPD         0     0     0   Chronic pulmonary disease
      RHEUMD       0     0     0   Rheumatic disease
      PUD          0     0     0   Pepticulcer disease
      MLD          1     0     0   Mild liver disease
      DIAB         0     0     0   Diabetes without complication
      DIABWC       0     0     0   Diabetes with chronic complication
      HP           0     0     0   Hemiplegia or paraplegia
      REND         0     1     0   Renal disease
      CANC         0     1     0   Any malignancy
      MSLD         0     0     0   Moderate or severe liver disease
      METACANC     0     0     0   Metastatic solid tumour
      AIDS         0     0     0   AIDS/HIV

      SCORE        1     2     0
      INDEX        2     2     1

      WSCORE       1     4     0   * WEIGHTED SCORE
      WINDEX       2     3     1   * WEIGHTED INDEX


    ELIXHAUSER INDEX
    ----------------
                      PATIENTS
                      --------

    CONDITION      1     2     3

      CHF          0     0     0
      CARIT        0     0     0
      VALV         0     0     0
      PCD          0     0     0
      PVD          0     0     0
      HYPUNC       0     0     0
      HYPC         0     0     0
      PARA         0     0     0
      OND          0     0     0
      CPD          0     0     0
      DIABUNC      0     0     0
      DIABC        0     0     0
      HYPOTHY      0     0     0
      RF           0     1     0
      LD           1     0     0
      PUD          0     0     0
      AIDS         0     0     0
      LYMPH        0     0     0
      METACANC     0     0     0
      SOLIDTUM     0     1     0
      RHEUMD       0     0     0
      COAG         0     0     0
      OBES         0     0     0
      WLOSS        0     0     0
      FED          0     0     0
      BLANE        0     0     0
      DANE         0     0     0
      ALCOHOL      0     0     0
      DRUG         0     0     0
      PSYCHO       0     0     0
      DEPRE        0     0     0

      SCORE        1     2     0
      INDEX        3     3     2

      WSCORE       4    13     0   * WEIGHTED SCORE
      WINDEX       3     4     2   * WEIGHTED INDEX


    *              _
      ___ ___   __| | ___
     / __/ _ \ / _` |/ _ \
    | (_| (_) | (_| |  __/
     \___\___/ \__,_|\___|

    ;

    %utl_submit_r64('
    library(comorbidity);
    library(haven);
    library(SASxport);
    have<-read_sas("d:/sd1/have.sas7bdat");
    head(have);
    c10 <- comorbidity(x = have, id = "PAT", code = "ICD10", score = "charlson_icd10");
    c10;
    write.xport(c10,file="d:/xpt/cci_charlson10.xpt");
    e10 <- comorbidity(x = have, id = "PAT", code = "ICD10", score = "elixhauser_icd10");
    write.xport(e10,file="d:/xpt/cci_elixhauser10.xpt");
    ');

    libname c10 xport "d:/xpt/cci_charlson10.xpt";
    libname e10 xport "d:/xpt/cci_elixhauser10.xpt";

    data c10;
      set c10.c10;
    run;quit;

    data e10;
      set e10.e10;
    run;quit;

    proc transpose data=c10 out=c10xpo;
     id pat;
    run;quit;

    proc transpose data=e10 out=e10xpo;
     id pat;
    run;quit;

    proc print data=e10xpo ;
    run;quit;


    * ____ _                _                   _         _  ___
     / ___| |__   __ _ _ __| |___  ___  _ __   (_) ___ __| |/ _ \
    | |   | '_ \ / _` | '__| / __|/ _ \| '_ \  | |/ __/ _` | (_) |
    | |___| | | | (_| | |  | \__ \ (_) | | | | | | (_| (_| |\__, |
     \____|_| |_|\__,_|_|  |_|___/\___/|_| |_| |_|\___\__,_|  /_/

    ;

    CD-9-CM codes
    The ICD-9-CM codes used by comorbidity to compute the Charlson comorbidity index are:

    Myocardial infarction: 410.x, 412.x

    Congestive heart failure: 398.91, 402.01, 402.11, 402.91, 404.01, 404.03,
    404.11, 404.13, 404.91, 404.93, 425.4 - 425.9, 428.x

    Peripheral vascular disease: 093.0, 437.3, 440.x, 441.x,
    443.1 - 443.9, 47.1, 557.1, 557.9, V43.4

    Cerebrovascular disease: 362.34, 430.x - 438.x

    Dementia: 290.x, 294.1, 331.2

    Chronic pulmonary disease: 416.8, 416.9, 490.x - 505.x, 506.4, 508.1, 508.8

    Rheumatic disease: 446.5, 710.0 - 710.4, 714.0 - 714.2, 714.8, 725.x

    Peptic ulcer disease: 531.x - 534.x

    Mild liver disease: 070.22, 070.23, 070.32, 070.33, 070.44, 070.54, 070.6,
    070.9, 570.x, 571.x, 573.3, 573.4, 573.8, 573.9, V42.7

    Diabetes without chronic complication: 250.0 - 250.3, 250.8, 250.9

    Diabetes with chronic complication: 250.4 - 250.7

    Hemiplegia or paraplegia: 334.1, 342.x, 343.x, 344.0 - 344.6, 344.9

    Renal disease: 403.01, 403.11, 403.91, 404.02, 404.03, 404.12, 404.13,
    404.92, 404.93, 582.x, 583.0 - 583.7, 585.x, 586.x, 588.0, V42.0, V45.1, V56.x

    Any malignancy, including lymphoma and leukemia, except malignant
    neoplasm of skin: 140.x - 172.x, 174.x - 195.8, 200.x - 208.x, 238.6

    Moderate or severe liver disease: 456.0 - 456.2, 572.2- 572.8

    Metastatic solid tumor: 196.x - 199.x

    AIDS/HIV: 042.x - 044.x


    * ____ _                _                   _         _ _  ___
     / ___| |__   __ _ _ __| |___  ___  _ __   (_) ___ __| / |/ _ \
    | |   | '_ \ / _` | '__| / __|/ _ \| '_ \  | |/ __/ _` | | | | |
    | |___| | | | (_| | |  | \__ \ (_) | | | | | | (_| (_| | | |_| |
     \____|_| |_|\__,_|_|  |_|___/\___/|_| |_| |_|\___\__,_|_|\___/

    ;

    The ICD-10 codes used by comorbidity to compute the Charlson comorbidity index are:

    Myocardial infarction: I21.x, I22.x, I25.2

    Congestive heart failure: I09.9, I11.0, I13.0, I13.2, I25.5,
       I42.0, I42.5 - I42.9, I43.x, I50.x, P29.0

    Peripheral vascular disease: I70.x, I71.x, I73.1, I73.8, I73.9,
    I77.1, I79.0, I79.2, K55.1, K55.8, K55.9, Z95.8, Z95.9

    Cerebrovascular disease: G45.x, G46.x, H34.0, I60.x - I69.x

    Dementia: F00.x - F03.x, F05.1, G30.x, G31.1

    Chronic pulmonary disease: I27.8, I27.9, J40.x - J47.x, J60.x - J67.x, J68.4, J70.1, J70.3

    Rheumatic disease: M05.x, M06.x, M31.5, M32.x - M34.x, M35.1, M35.3, M36.0

    Pepticulcer disease: K25.x - K28.x

    Mild liver disease: B18.x, K70.0 - K70.3, K70.9, K71.3 - K71.5,
    K71.7, K73.x, K74.x, K76.0, K76.2 - K76.4, K76.8, K76.9, Z94.4

    Diabetes without chronic complication: E10.0, E10.1, E10.6, E10.8,
    E10.9, E11.0, E11.1, E11.6, E11.8, E11.9, E12.0, E12.1, E12.6, E12.8,
    E12.9, E13.0, E13.1, E13.6, E13.8, E13.9, E14.0, E14.1, E14.6, E14.8, E14.9

    Diabetes with chronic complication: E10.2 - E10.5, E10.7, E11.2 - E11.5,
    E11.7, E12.2 - E12.5, E12.7, E13.2 - E13.5, E13.7, E14.2 - E14.5, E14.7

    Hemiplegia or paraplegia: G04.1, G11.4, G80.1, G80.2, G81.x, G82.x, G83.0 - G83.4, G83.9

    Renal disease: I12.0, I13.1, N03.2 - N03.7, N05.2 - N05.7, N18.x, N19.x,
    N25.0, Z49.0 - Z49.2, Z94.0, Z99.2

    Any malignancy, including lymphoma and leukemia, except malignant neoplasm of skin:
    C00.x - C26.x, C30.x - C34.x, C37.x - C41.x, C43.x, C45.x - C58.x,
    C60.x - C76.x, C81.x - C85.x, C88.x, C90.x - C97.x

    Moderate or severe liver disease: I85.0, I85.9, I86.4, I98.2,
    K70.4, K71.1, K72.1, K72.9, K76.5, K76.6, K76.7

    Metastatic solid tumour: C77.x - C80.x

    AIDS/HIV: B20.x - B22.x, B24.x

    *_____ _ _      _                                 _         _  ___
    | ____| (_)_  _| |__   __ _ _   _ ___  ___ _ __  (_) ___ __| |/ _ \
    |  _| | | \ \/ / '_ \ / _` | | | / __|/ _ \ '__| | |/ __/ _` | (_) |
    | |___| | |>  <| | | | (_| | |_| \__ \  __/ |    | | (_| (_| |\__, |
    |_____|_|_/_/\_\_| |_|\__,_|\__,_|___/\___|_|    |_|\___\__,_|  /_/

    ;


    CD-9-CM codes
    The ICD-9-CM codes used by comorbidity to compute the Elixhauser comorbidity index are:

    Congestive heart failure: 398.91, 402.01, 402.11, 402.91, 404.01, 404.03,
    404.11, 404.13, 404.91, 404.93, 425.4 - 425.9, 428.x

    Cardiac arrhythmias: 426.0, 426.13, 426.7, 426.9, 426.10, 426.12, 427.0 - 427.4,
    427.6 - 427.9, 785.0, 996.01, 996.04, V45.0, V53.3

    Valvular disease: 093.2, 394.x - 397.x, 424.x, 746.3 - 746.6, V42.2, V43.3

    Pulmonary circulation disorders: 415.0, 415.1, 416.x, 417.0, 417.8, 417.9

    Peripheral vascular disorders: 093.0, 437.3, 440.x, 441.x, 443.1 - 443.9,
    447.1, 557.1, 557.9, V43.4

    Hypertension, uncomplicated: 401.x

    Hypertension, complicated: 402.x - 405.x

    Paralysis: 334.1, 342.x, 343.x, 344.0 - 344.6, 344.9

    Other neurological disorders: 331.9, 332.0, 332.1, 333.4, 333.5, 333.92,
    334.x - 335.x, 336.2, 340.x, 341.x, 345.x, 348.1, 348.3, 780.3, 784.3

    Chronic pulmonary disease: 416.8, 416.9, 490.x - 505.x, 506.4, 508.1, 508.8

    Diabetes, uncomplicated: 250.0 - 250.3

    Diabetes, complicated: 250.4 - 250.9

    Hypothyroidism: 240.9, 243.x, 244.x, 246.1, 246.8

    Renal failure: 403.01, 403.11, 403.91, 404.02, 404.03, 404.12, 404.13,
    404.92, 404.93, 585.x, 586.x, 588.0, V42.0, V45.1, V56.x

    Liver disease: 070.22, 070.23, 070.32, 070.33, 070.44, 070.54, 070.6,
    070.9, 456.0 - 456.2, 570.x, 571.x, 572.2 - 572.8, 573.3, 573.4, 573.8, 573.9, V42.7

    Peptic ulcer disease, excluding bleeding: 531.7, 531.9, 532.7,
    532.9, 533.7, 533.9, 534.7, 534.9

    AIDS/HIV: 042.x - 044.x

    Lymphoma: 200.x - 202.x, 203.0, 238.6

    Metastatic cancer: 196.x - 199.x

    Solid tumor without metastasis: 140.x - 172.x, 174.x - 195.x

    Rheumatoid arthritis/collagen vascular diseases: 446.x, 701.0, 710.0 - 710.4,
    710.8, 710.9, 711.2, 714.x, 719.3, 720.x, 725.x, 728.5, 728.89, 729.30

    Coagulopathy: 286.x, 287.1, 287.3 - 287.5

    Obesity: 278.0

    Weight loss: 260.x - 263.x, 783.2, 799.4

    Fluid and electrolyte disorders: 253.6, 276.x

    Blood loss anemia: 280.0

    Deficiency anemia: 280.1 - 280.9, 281.x

    Alcohol abuse: 265.2, 291.1 - 291.3, 291.5 - 291.9, 303.0, 303.9, 305.0,
    357.5, 425.5, 535.3, 571.0 - 571.3, 980.x, V11.3

    Drug abuse: 292.x, 304.x, 305.2 - 305.9, V65.42

    Psychoses: 293.8, 295.x, 296.04, 296.14, 296.44, 296.54, 297.x, 298.x

    Depression: 296.2, 296.3, 296.5, 300.4, 309.x, 311


    *_____ _ _      _                                 _         _ _  ___
    | ____| (_)_  _| |__   __ _ _   _ ___  ___ _ __  (_) ___ __| / |/ _ \
    |  _| | | \ \/ / '_ \ / _` | | | / __|/ _ \ '__| | |/ __/ _` | | | | |
    | |___| | |>  <| | | | (_| | |_| \__ \  __/ |    | | (_| (_| | | |_| |
    |_____|_|_/_/\_\_| |_|\__,_|\__,_|___/\___|_|    |_|\___\__,_|_|\___/

    ;


    ICD-10 codes
    The ICD-10 codes used by comorbidity to compute the Elixhauser comorbidity index are:

    Congestive heart failure: I09.9, I11.0, I13.0, I13.2, I25.5, I42.0,
    I42.5 - I42.9, I43.x, I50.x, P29.0

    Cardiac arrhythmias: I44.1 - I44.3, I45.6, I45.9, I47.x - I49.x,
    R00.0, R00.1, R00.8, T82.1, Z45.0, Z95.0

    Valvular disease: A52.0, I05.x - I08.x, I09.1, I09.8, I34.x - I39.x,
    Q23.0 - Q23.3, Z95.2 - Z95.4

    Pulmonary circulation disorders: I26.x, I27.x, I28.0, I28.8, I28.9

    Peripheral vascular disorders: I70.x, I71.x, I73.1, I73.8, I73.9, I77.1,
    I79.0, I79.2, K55.1, K55.8, K55.9, Z95.8, Z95.9

    Hypertension, uncomplicated: I10.x

    Hypertension, complicated: I11.x - I13.x, I15.x

    Paralysis: G04.1, G11.4, G80.1, G80.2, G81.x, G82.x, G83.0 - G83.4, G83.9

    Other neurological disorders: G10.x - G13.x, G20.x - G22.x, G25.4, G25.5,
    G31.2, G31.8, G31.9, G32.x, G35.x - G37.x, G40.x, G41.x, G93.1, G93.4, R47.0, R56.x

    Chronic pulmonary disease: I27.8, I27.9, J40.x - J47.x, J60.x - J67.x, J68.4, J70.1, J70.3

    Diabetes, uncomplicated: E10.0, E10.1, E10.9, E11.0, E11.1, E11.9, E12.0,
    E12.1, E12.9, E13.0, E13.1, E13.9, E14.0, E14.1, E14.9

    Diabetes, complicated: E10.2 - E10.8, E11.2 - E11.8, E12.2 - E12.8, E13.2 - E13.8, E14.2 - E14.8

    Hypothyroidism: E00.x - E03.x, E89.0

    Renal failure: I12.0, I13.1, N18.x, N19.x, N25.0, Z49.0 - Z49.2, Z94.0, Z99.2

    Liver disease: B18.x, I85.x, I86.4, I98.2, K70.x, K71.1, K71.3 - K71.5,
    K71.7, K72.x - K74.x, K76.0, K76.2 - K76.9, Z94.4

    Peptic ulcer disease, excluding bleeding: K25.7, K25.9, K26.7, K26.9, K27.7, K27.9, K28.7, K28.9

    AIDS/HIV: B20.x - B22.x, B24.x

    Lymphoma: C81.x - C85.x, C88.x, C96.x, C90.0, C90.2

    Metastatic cancer: C77.x - C80.x

    Solid tumor without metastasis: C00.x - C26.x, C30.x - C34.x, C37.x - C41.x,
    C43.x, C45.x - C58.x, C60.x - C76.x, C97.x

    Rheumatoid arthritis/collagen vascular diseases: L94.0, L94.1, L94.3, M05.x,
    M06.x, M08.x, M12.0, M12.3, M30.x, M31.0 - M31.3, M32.x - M35.x, M45.x, M46.1, M46.8, M46.9

    Coagulopathy: D65 - D68.x, D69.1, D69.3 - D69.6

    Obesity: E66.x

    Weight loss: E40.x - E46.x, R63.4, R64

    Fluid and electrolyte disorders: E22.2, E86.x, E87.x

    Blood loss anemia: D50.0

    Deficiency anemia: D50.8, D50.9, D51.x - D53.x

    Alcohol abuse: F10, E52, G62.1, I42.6, K29.2, K70.0, K70.3, K70.9, T51.x, Z50.2, Z71.4, Z72.1

    Drug abuse: F11.x - F16.x, F18.x, F19.x, Z71.5, Z72.2

    Psychoses: F20.x, F22.x - F25.x, F28.x, F29.x, F30.2, F31.2, F31.5

    Depression: F20.4, F31.3 - F31.5, F32.x, F33.x, F34.1, F41.2, F43.2


