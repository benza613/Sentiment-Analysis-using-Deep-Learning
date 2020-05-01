1. To Demo a review of your own to see the predicted sentiment classification you can run the notebook
notebooks_finals/DEMO.ipynb

In this notebook you can choose which one of the provided models & dataset you want to load & in the end of the notebook you can add your own review.

Example : 
data_corpus = {
    'MODEL AAA' : {
        'model_path' : 'ModelResults/v3_767c02af219c4133946edcaf89e67387/model.h5',
        'train_data_path' : 'amz_all_electronics/Data_Balanced_2000_Apr-03-2020_06-46/Train_2000_Apr-03-2020_06-46.zip',
        'test_data_path' : 'amz_all_electronics/Data_Balanced_2000_Apr-03-2020_06-46/Test_2000_Apr-03-2020_06-46.zip',
    },
    'MODEL BBB' : {
        'model_path' : 'ModelResults/v3_lstm_1f9ff1c3924d4bac8894dda0fc3bf5bf/model.h5',
        'train_data_path' : 'amz_all_electronics/Data_Balanced_20000_Apr-03-2020_06-52/Train_20000_Apr-03-2020_06-52.zip',
        'test_data_path' : 'amz_all_electronics/Data_Balanced_20000_Apr-03-2020_06-52/Test_20000_Apr-03-2020_06-52.zip',
    },
...
...
...
...
}

--> JUST CHOOSE THE MODEL NAME 
CHOOSE_VARIABLE = 'MODEL BBB'

2. To compile models for yourself, you can use the provided small or medium train-test datasets and any of the following notebooks
notebooks_finals/model_lstm
notebooks_finals/model_CNN
notebooks_finals/model_cnn_gru
notebooks_finals/GloVe_biLstm   (to run and create this model you will need the 200 dimension glove file that I can send you the drive shared link for)



3. I have already provided 1 example for embedding visualization (2 files - embedding weights & word dict )
vecs_elec_small_lstm.tsv
meta_elec_small_lstm.tsv
you can load these files on http://projector.tensorflow.org and verify that they are working 

OR ALTERNATIVELY if you wish to create these files on your own, you cann run 
notebooks_finals/embedding_visualisation.ipynb and generate the files for the combination of model-datasets. 
(I have already provided u the object, you have to just choose the model u want, same like above)



4. To check/run ensemble notebook, you can run 
notebooks_finals/EnsembleMajorityModel 
basically the file can take an array of models and make majority/mode predictions for each test input point.
( If there are even number of models & same number of modes conflict, it will default to the lower mode value, in this case 0 )


5. The remaining notebooks in 
notebooks/
data_cleaning2  ==> Takes the raw n-GB data set and preprocesses it & outputs a cleant csv/zip file.
test_train_splitter  ==> Takes the cleant csv/zip file and given a parameter, IT generates two files of 90-10% train test split.   
LexicalAnalysis, naive_bayes  ==> These two notebooks are our baseline models that we ran as a comparison to evaluate our neural models

To run these two notebooks specifically u will need the bag of words and other dependencies that are too big to attach to this, but we can share it with you via drive or something