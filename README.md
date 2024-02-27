# deep-learning-challenge
## Deep Learning Module 21 Challenge
This script contains two Google Colab notebooks

### Preprocessing the Data
The first notebook first reads in the charity_data.csv to a Pandas DataFrame and drops the identification columns: "EIN" and "NAME." Then counts the number of unique values for each column, and counts the values for the "APPLICATION_TYPE" column. It then replaces every value with a count of less than 500 to a single value simply called, "Other." Next, does the same for the "CLASSIFICATION column, but chooses a cutoff value of 1,000, so every value that appears less than 1,00 times is grouped into "Other." Next, uses pd.get_dummies() to encode categorical variables and split the preprocessed data into a features array, X, and a target array, y. These arrays are then used to split the data into training and testing datasets. The datasets are then scaled by creating a StandardScaler instance, fitting it to the training data, and using the transform function.

### Compiling, Training, and Evaluating the Model
The code then creates a binary classification model using TensorFLow that can predict if an Alphabet Soup-funded organization will be successful based on the features in the dataset, with two hidden layers and an output layer. The hidden layers use the ReLU activation function while the output layer uses Sigmoid. Afterwards the model is then complied and fitted, using 100 epochs to train it. Once the model is fitted, it is then evaluated using the test data to get the loss and accuracy, and receives an accuracy of 73%. Lastly, the model then exported to an HDF5 file.

### Optimizing the Model
The second notebook is very similar to the first one, just aiming to optimize the model to receive an accuracy of 75% or higher. To achieve this target accuracy, the only change made to the notebook is that the "NAME" column is kept in the orginal dataframe, instead of being dropped along with the "EIN" column. The "NAME" column is kept and the values with less than 100 counts are replaced with "Other." With just this change, the model is able to obtain an accuracy of 75%. The second notebook also includes and analysis report on the model's performance at the end.
