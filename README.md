# Machine-Learning-Security
Researched, analyzed, and developed ML algorithms to detect cybersecurity threats in computer networks.

# Introduction-
A program/code which is designed to penetrate the system without user authorization and takes inadmissible action is known as malicious software or malware . Malware is a term used for Trojan Horse, spyware, adware, worm, virus, ransomware, etc. Here we are detecting whether or not the portable executable files are harmful or non-harmful.
Portable Executables encapsulate the information necessary for a Windows operating system to manage the executable code. This includes dynamic library refer ences for linking, API export and import tables, Resource Management data and threat local storage data . A PE file consists of a numb of headers and sections that tell the dynamic linker how to map the file into memory. A Portable Executable file has various sections that contain the code and data of the executable including
•The. data section. This section is used to declare initialized data or constants that do not change at runtime.
•The. bss section. This section is used for declaring variables and contains uninitialized data.
•The. text section. This section keeps the actual code of the program.
•The. rsrc section. This section contains all the resources of the program.
•The. rdata section. This section holds the debug directory which stores the type, size and location of various types of debug information stored in the file.

# Dataset-
The dataset is available in various public domain and is provided by “Virusshare.com” – A repository of malware samples to provide security researchers, incident responders etc. access to sample of live malicious code. The dataset consists of 19611 data entries listing PE Information from Various sources. Out of these 4615 are malicious while 14996 are legitimate. The dataset consists of total 57 features for every File. File Extensions of PE Format Files
Taking all features into consideration may lead to overfitting and may produce poor results. In order to find which feature, contribute significantly towards building the model, we employed feature selection algorithm using Extra Tree Classifier. On executing the algorithm, we found that out of 76 features only 16 features were important. Hence only 16 these features were taken into consideration while building the model.

# Approach-
The important steps involved in implementing the machine learning model are described as follows: -
• Collecting and Importing Dataset: Dataset described above is imported using Pandas library.
• Data Pre-processing: The CSV files contain unimportant parameters like Name of the file, md5 of file that need to be removed before training the model from its features. So, the Independent variable consist of 16 features listed above while Dependent variable consist of Integer. The plot 1 show the all the portable executable files classified into benign(harmful) and Malware(harmful).
• Splitting the dataset: We have used the train_test_split function from Scikit Learn Library to split our dataset in the ratio 1:4 as Test set and Train Set respectively.
• Building the Training Model: Dataset is fit into 2 different machine learning models using Scikit Learn library functions. Classification done using K Nearest Neighbours . KNN is a super simple algorithm, which assumes that similar things are in close proximity of each other. So if a datapoint is near to another datapoint, it assumes that they both belong to similar classes. We have tested the knn algorithm for 1 to 40 nearest neighbours , from which we got the least error for 3rd nearest neighbour.
• We have also use Random forest classification for
the classification of the PE files.For the best result we tested the with different no of tree in the forest from 20 to 100 from which we got least error for 50 trees.The depth of the tree
is 16 and rest is default.

# Results-
For Simple Knn Model:
• By taking 3rd nearest feature we got the least error therefore we got best accuracy which is equal to 0.97.     
For Random Forest Model:
• We got the accuracy of 0.98.
