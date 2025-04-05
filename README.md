# Machine Learning Assessment Model for Drug Susceptibility
 
These codes are part of the supporting information of the article "Assessment of Drug Susceptibility for Patient-Derived Tumor Models through Lactate Biosensing and Machine Learning" (published in ACS Sens., with doi.org/10.1021/acssensors.2c02381)

## Data processing.
In order to compare the attribution values of different samples, the original data need to be standardized before analysis. The attribution of each sample is divided by the corresponding attribution of its negative control (NC).  
Note: SZ is the relative size of the cell cluster ($SZ_{D7}/SZ_{D0}$), CL is the chemiluminescence intensity value measured by Celltitle-glo reagent, and LA is the apparent 7-day lactate secretion of the sample ($LA_{D7}-LA_{D0}$), where $LA_{D0}$ is almost 0.

## Machine Learning Analysis 
Machine learning algorithms, including Stochastic Gradient Descent (SGD), Random Forest (RF), and Support Vector Machines (SVM), are implemented with Jupyter Notebook 6.4.8 (Python 3.7.6) using multiple open libraries, including Scikit-Learn, Panda, NumPy, Seaborn and Matplotlib. ML algorithms differentiate drug test results by outputting predicted probabilities and predicted categories through different combinations of three attributes ($LA+LA_{Err}/CL+CL_{Err}/SZ+SZ_{Err}$). Area under the curve values (AUCs) derived from the receiver operating characteristic (ROC) curves were calculated using the **pROC** package in R (version 4.2.2). All ROC curves presented in the results were represented along with 95% CIs. The CI values were calculated by 2000 bootstrap replicates. The performance (ROC & confusion matrix) of these machine learning algorithms are shown in fold **Result_Figures**.

## Instruction 指南

**Note: When using a relative path, this file must be placed in the current running directory of Jupyter; or use an absolute path instead. Otherwise a 'File Not Found Error' will appear.**

**ML_algorithm_directory**: '..\ML program', containing 2 Jupyter Notebook files ('ML_2type.ipynb' & 'ML_3type.ipynb') for binary (E/NE) / multi-class classifiers (SE/E/NE) respectively, and corresponding PDF & html flies (unable to run, just for those who have not installed Jupyter to view the code).

**raw_data_directory**: '..\ML_dataset.xlsx' containing 2 Excel_sheets for ML algorithms.

存放机器学习算法的原始数据的文件路径：原始数据存放在'import_data'文件夹中。

**export_data_directory**: '..\export_data', containing results of moving average dataset, accuracy scores and confusion matrices of RF, running history of DNN model.

'export_data'文件夹中是导出的数据和结果。含有t-SNE结果，RF、DNN运行结果和处理后的数据集。

In the **dataset_for_paper** you could find raw data of Fig.4 and Fig.5 of the article. In fact, these data are identical with those in the 'import_data' folder, only recorded separately in different sheets according to different EV types.

在'dataset_for_paper'文件夹中，您可以找到文章中图4和图5的原始数据。实际上这些数据与'import_data'文件夹中的数据完全一致，只是根据不同的EV类型分别写在不同的表格中。

(Updatad 2025-April-05)
