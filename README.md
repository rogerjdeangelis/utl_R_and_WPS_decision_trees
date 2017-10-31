# utl_R_and-WPS_decision_trees
Simple example targeting Spanish speakers for a brochure written in Spanish. Decision trees. Big Data Analytics. Machine Learning.  Identify groups wit a higher likelihood of responding to a marketing campaign.

    ```  R and SAS/WPS Decision trees: Tageting Spanish speaking responders (because the brocure is in Spanish)                                                       ```
    ```                                                                                                                                                               ```
    ```  The sweet spots for a marketing campaign requires a high number of spanish speaking                                                                       ```
    ```    Model Results                                                                                                                                             ```
    ```     1. Score > 38                                                                                                                                             ```
    ```     2. Score between 31 and 38 with age decade <=6                                                                                                            ```
    ```                                                                                                                                                               ```
    ```                                                                                                                                                               ```
    ```    WORKING CODE  (prety much all the code)                                                                                                                    ```
    ```    ============                                                                                                                                               ```
    ```    SAS/IML/R or WPS/PROC-R                                                                                                                                    ```
    ```                                                                                                                                                               ```
    ```        output.tree <- ctree(                                                                                                                                  ```
    ```            nativeSpeaker ~ age + shoeSize + score,data = input.dat);                                                                                          ```
    ```                                                                                                                                                               ```
    ```  see                                                                                                                                                          ```
    ```  https://goo.gl/3UDE81                                                                                                                                        ```
    ```  https://dzone.com/articles/3-machine-learning-algorithms-you-need-to-know?                                                                                   ```
    ```  edition=329540&utm_source=Weekly%20Digest&utm_medium=email&utm_campaign=Weekly%20Digest%202017-10-11                                                         ```
    ```                                                                                                                                                               ```
    ```                                                                                                                                                               ```
    ```                                                                                                                                                               ```
    ```  HAVE                                                                                                                                                         ```
    ```  ====                                                                                                                                                         ```
    ```                                                                                                                                                               ```
    ```  SD1.READINGSKILLS total obs=105                                                                                                                              ```
    ```                                                                                                                                                               ```
    ```  Obs    NATIVESPEAKER    AGE    SHOESIZE    SCORE                                                                                                             ```
    ```                                                                                                                                                               ```
    ```    1         yes           5      24.83     32.29                                                                                                             ```
    ```    2         yes           6      25.95     36.63                                                                                                             ```
    ```    3         no           11      30.42     49.61                                                                                                             ```
    ```    4         yes           7      28.66     40.28                                                                                                             ```
    ```    5         yes          11      31.88     55.46                                                                                                             ```
    ```   ....                                                                                                                                                        ```
    ```                                                                                                                                                               ```
    ```                                                                                                                                                               ```
    ```                                                                                                                                                               ```
    ```  WANT                                                                                                                                                         ```
    ```  ====                                                                                                                                                         ```
    ```                                                                                                                                                               ```
    ```                                   Is the adult a Spanish speaker?                                                                                             ```
    ```                                                                                                                                                               ```
    ```                                   Shoesize was not useful so it is not part of the tree.                                                                      ```
    ```                                   Eliminating variables is useful.                                                                                            ```
    ```                                                                                                                                                               ```
    ```                                                                                                                                                               ```
    ```                                                                                                                                                               ```
    ```                                            Score                                                                                                              ```
    ```                                             ___                                                                                                               ```
    ```                                            / _ \                                                                                                              ```
    ```                                           | | | |                                                                                                             ```
    ```                                           | |_| |                                                                                                             ```
    ```                                            \___/                                                                                                              ```
    ```                                           /     \                                                                                                             ```
    ```                                          / p<.01 \                                                                                                            ```
    ```                                  <=38   /         \                                                                                                           ```
    ```                                        /           \  >38                                                                                                     ```
    ```                                   2   /             \                                                                                                         ```
    ```                                  Age /               \                                                                                                        ```
    ```                                   __/                 \ 7                                                                                                     ```
    ```                                  / _ \       +*******************+                                                                                            ```
    ```                                 | | | |      *      yes          *                                                                                            ```
    ```                                 | |_| |      *  n=62   err=30%   *  19 were no ~30% error                                                                     ```
    ```                                  \___/       +*******************+                                                                                            ```
    ```                                 /      \                                                                                                                      ```
    ```                                /  p<.07 \                                                                                                                     ```
    ```                         <=6   /          \  >6                                                                                                                ```
    ```                              /            \                                                                                                                   ```
    ```                             /              \                                                                                                                  ```
    ```                        3   /                \                                                                                                                 ```
    ```                      Score/                  \   6                                                                                                            ```
    ```                       ___/            +*******************+                                                                                                   ```
    ```                      / _ \            *      no           *  0% error                                                                                         ```
    ```                     | | | |           * n=21   err=0%     *  all 21 are no                                                                                    ```
    ```                     | |_| |           +*******************+  perfect prediction (nice)                                                                        ```
    ```                      \___/                                                                                                                                    ```
    ```                      /     \                                                                                                                                  ```
    ```                     / p<.01 \                                                                                                                                 ```
    ```              <=31  /         \  >31                                                                                                                           ```
    ```                   /           \                                                                                                                               ```
    ```               4  /             \  5                                                                                                                           ```
    ```                 /               \                                                                                                                             ```
    ```                /                \                                                                                                                             ```
    ```      +*******************+  +*******************+   83 already taken care of above                                                                            ```
    ```      *       no          *  *     yes           *                                                                                                             ```
    ```      *  n=13   err=0%    *  *  n=9  err 0%      *                                                                                                             ```
    ```      +*******************+  +*******************+                                                                                                             ```
    ```                                                                                                                                                               ```
    ```          Perfect prediction                                                                                                                                   ```
    ```         all not Native Speakers                                                                                                                               ```
    ```                                                                                                                                                               ```
    ```      NATIVESPEAKER  AGE    Cnt        NATIVESPEAKER AGE   Cnt                                                                                                 ```
    ```      ---------------------------      --------------------------                                                                                              ```
    ```      no              5      6         yes           5      5                                                                                                  ```
    ```      no              6      7         yes           6      4                                                                                                  ```
    ```                                                                                                                                                               ```
    ```                                                                                                                                                               ```
    ```  Checking the Tree                                                                                                                                            ```
    ```                                                                                                                                                               ```
    ```  proc freq data=sd1.readingSkills(where=(score>38.31));                                                                                                       ```
    ```  tables nativespeaker*age /list;                                                                                                                              ```
    ```  run;quit;                                                                                                                                                    ```
    ```                                                                                                                                                               ```
    ```  proc freq data=sd1.readingSkills(where=(score<=38.31 and age>6));                                                                                            ```
    ```  tables nativespeaker*age /list;                                                                                                                              ```
    ```  run;quit;                                                                                                                                                    ```
    ```                                                                                                                                                               ```
    ```  proc freq data=sd1.readingSkills(where=(score<=38.31 and age<=6 and score <=30.77));                                                                         ```
    ```  tables nativespeaker*age /list;                                                                                                                              ```
    ```  run;quit;                                                                                                                                                    ```
    ```                                                                                                                                                               ```
    ```  proc freq data=sd1.readingSkills(where=(score<=38.31 and age<=6 and score >30.77));                                                                          ```
    ```  tables nativespeaker*age /list;                                                                                                                              ```
    ```  run;quit;                                                                                                                                                    ```
    ```                                                                                                                                                               ```
    ```  *                _               _       _                                                                                                                   ```
    ```   _ __ ___   __ _| | _____     __| | __ _| |_ __ _                                                                                                            ```
    ```  | '_ ` _ \ / _` | |/ / _ \   / _` |/ _` | __/ _` |                                                                                                           ```
    ```  | | | | | | (_| |   <  __/  | (_| | (_| | || (_| |                                                                                                           ```
    ```  |_| |_| |_|\__,_|_|\_\___|   \__,_|\__,_|\__\__,_|                                                                                                           ```
    ```                                                                                                                                                               ```
    ```  ;                                                                                                                                                            ```
    ```                                                                                                                                                               ```
    ```  * column score could be the result of regresssion (logistic)                                                                                                 ```
    ```  options validvarname=upcase;                                                                                                                                 ```
    ```  libname sd1 "d:/sd1";                                                                                                                                        ```
    ```  data sd1.readingSkills;                                                                                                                                      ```
    ```    input NATIVESPEAKER$    AGE    SHOESIZE 5.2    SCORE 5.2 @@;                                                                                               ```
    ```  cards4;                                                                                                                                                      ```
    ```  yes 5 24.8332.29  yes 6 25.9536.63  no 11 30.4249.61  yes 7 28.6640.28  yes 11 31.8855.46                                                                    ```
    ```  yes 10 30.0852.83  no 7 27.2634.40  yes 11 30.7255.53  yes 5 25.6432.50  no 7 26.7033.93                                                                     ```
    ```  yes 11 31.8755.47  yes 10 29.1651.34  no 9 29.1341.77  no 6 26.8730.03  no 5 24.2325.62                                                                      ```
    ```  yes 6 25.6835.30  no 5 24.8625.63  no 6 26.1530.77  no 9 27.8241.94  yes 5 24.8731.70                                                                        ```
    ```  no 6 25.2130.37  no 6 27.3629.30  no 8 28.6638.09  yes 9 29.9848.63  yes 10 30.8452.41                                                                       ```
    ```  no 7 26.8134.19  yes 6 26.8935.35  yes 8 28.4343.72  no 11 31.7148.68  yes 8 27.7844.15                                                                      ```
    ```  yes 9 28.8848.70  yes 7 26.6739.66  no 9 28.9141.80  no 9 27.8842.42  yes 7 25.4739.70                                                                       ```
    ```  yes 8 27.7244.06  no 7 25.1934.28  yes 11 30.7955.98  yes 11 30.7655.86  yes 11 30.5156.61                                                                   ```
    ```  no 5 26.2426.18  no 5 24.3625.36  no 7 27.6132.88  no 10 29.6545.76  yes 8 29.4943.49                                                                        ```
    ```  yes 7 26.9238.91  yes 8 28.3644.99  no 6 26.1029.35  yes 8 29.6443.67  yes 8 27.2543.68                                                                      ```
    ```  no 8 26.2237.74  yes 6 26.1336.26  no 9 30.4642.50  no 7 27.8134.34  yes 10 29.3752.84                                                                       ```
    ```  yes 10 29.3451.95  yes 7 25.4639.52  no 10 28.7745.86  no 11 30.3550.02  no 8 29.3337.52                                                                     ```
    ```  yes 10 28.8751.54  no 7 26.6233.97  no 7 28.1133.40  no 11 30.9950.28  yes 10 29.2550.81                                                                     ```
    ```  yes 5 24.5431.96  no 8 26.9937.62  no 11 30.2750.22  no 7 27.8634.21  yes 10 30.1752.17                                                                      ```
    ```  yes 7 25.5340.25  no 7 26.7634.72  yes 10 29.6351.48  no 5 24.4125.33  no 9 30.6442.88                                                                       ```
    ```  yes 7 26.7839.37  yes 8 28.5143.69  yes 5 23.6832.33  no 7 26.7633.13  no 10 29.6547.09                                                                      ```
    ```  no 9 29.3341.30  no 6 26.4829.52  no 9 28.3641.93  no 8 27.1538.31  no 10 30.5845.20                                                                         ```
    ```  yes 9 30.0848.72  no 9 28.3442.43  yes 11 29.2555.99  yes 9 28.2248.19  no 8 28.1137.39                                                                      ```
    ```  no 8 26.7937.40  yes 10 31.0951.96  no 5 24.2926.38  no 7 27.0433.53  yes 7 24.9240.20                                                                       ```
    ```  no 6 27.2329.54  yes 7 25.6141.15  yes 10 28.4552.58  yes 7 27.6040.01  yes 11 31.9756.71                                                                    ```
    ```  yes 8 28.8544.41  yes 8 25.4044.37  no 7 27.1233.92  no 8 27.7537.98  no 10 28.6446.21                                                                       ```
    ```  ;;;;                                                                                                                                                         ```
    ```  run;quit;                                                                                                                                                    ```
    ```                                                                                                                                                               ```
    ```  *          _       _   _                                                                                                                                     ```
    ```   ___  ___ | |_   _| |_(_) ___  _ __                                                                                                                          ```
    ```  / __|/ _ \| | | | | __| |/ _ \| '_ \                                                                                                                         ```
    ```  \__ \ (_) | | |_| | |_| | (_) | | | |                                                                                                                        ```
    ```  |___/\___/|_|\__,_|\__|_|\___/|_| |_|                                                                                                                        ```
    ```                                                                                                                                                               ```
    ```  ;                                                                                                                                                            ```
    ```                                                                                                                                                               ```
    ```  %utl_submit_wps64('                                                                                                                                          ```
    ```  libname sd1 "d:/sd1";                                                                                                                                        ```
    ```  options set=R_HOME "C:/Program Files/R/R-3.4.0";                                                                                                             ```
    ```  libname wrk "%sysfunc(pathname(work))";                                                                                                                      ```
    ```  proc r;                                                                                                                                                      ```
    ```  submit;                                                                                                                                                      ```
    ```  source("c:/Program Files/R/R-3.4.0/etc/Rprofile.site",echo=T);                                                                                               ```
    ```  library(party);                                                                                                                                              ```
    ```  library(partykit);                                                                                                                                           ```
    ```  library(haven);                                                                                                                                              ```
    ```   input.dat<-read_sas("d:/sd1/readingSkills.sas7bdat");                                                                                                       ```
    ```   input.dat$NATIVESPEAKER<-as.factor(input.dat$NATIVESPEAKER);                                                                                                ```
    ```   output.tree <- ctree(                                                                                                                                       ```
    ```     NATIVESPEAKER ~ AGE + SHOESIZE + SCORE,data = input.dat);                                                                                                 ```
    ```   pdf("d:/pdf/tree.pdf");                                                                                                                                     ```
    ```   plot(as.simpleparty(output.tree));                                                                                                                          ```
    ```   endsubmit;                                                                                                                                                  ```
    ```  run;quit;                                                                                                                                                    ```
    ```  ');                                                                                                                                                          ```
    ```                                                                                                                                                               ```
    ```  *_     ___   ____                                                                                                                                            ```
    ```  | |   / _ \ / ___|                                                                                                                                           ```
    ```  | |  | | | | |  _                                                                                                                                            ```
    ```  | |__| |_| | |_| |                                                                                                                                           ```
    ```  |_____\___/ \____|                                                                                                                                           ```
    ```                                                                                                                                                               ```
    ```  ;                                                                                                                                                            ```
    ```                                                                                                                                                               ```
    ```  4         proc r;                                                                                                                                            ```
    ```  5         submit;                                                                                                                                            ```
    ```  6         source("c:/Program Files/R/R-3.4.0/etc/Rprofile.site",echo=T);                                                                                     ```
    ```  7         library(party);                                                                                                                                    ```
    ```  8         library(partykit);                                                                                                                                 ```
    ```  9         library(haven);                                                                                                                                    ```
    ```  10        input.dat<-read_sas("d:/sd1/readingSkills.sas7bdat");                                                                                              ```
    ```  11        input.dat$NATIVESPEAKER<-as.factor(input.dat$NATIVESPEAKER);                                                                                       ```
    ```  12        output.tree <- ctree(   NATIVESPEAKER ~ AGE + SHOESIZE + SCORE,data = input.dat);                                                                  ```
    ```  13        pdf("d:/pdf/tree.pdf");                                                                                                                            ```
    ```  14        plot(as.simpleparty(output.tree));                                                                                                                 ```
    ```  15        endsubmit;                                                                                                                                         ```
    ```  NOTE: Using R version 3.4.0 (2017-04-21) from C:/Program Files/R/R-3.4.0                                                                                     ```
    ```                                                                                                                                                               ```
    ```  NOTE: Submitting statements to R:                                                                                                                            ```
    ```                                                                                                                                                               ```
    ```  > source("c:/Program Files/R/R-3.4.0/etc/Rprofile.site",echo=T);                                                                                             ```
    ```  > options(help_type = "html")                                                                                                                                ```
    ```  > .libPaths("D:/R/library")                                                                                                                                  ```
    ```  > library(party);                                                                                                                                            ```
    ```  Loading required package: grid                                                                                                                               ```
    ```  Loading required package: mvtnorm                                                                                                                            ```
    ```  Loading required package: modeltools                                                                                                                         ```
    ```  Loading required package: stats4                                                                                                                             ```
    ```  Loading required package: strucchange                                                                                                                        ```
    ```  Loading required package: zoo                                                                                                                                ```
    ```  Attaching package: 'zoo'                                                                                                                                     ```
    ```  The following objects are masked from 'package:base':                                                                                                        ```
    ```                                                                                                                                                               ```
    ```
