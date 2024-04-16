# Investigating-the-Performance-of-PCNN-and-BERT-Models-in-Relation-Extraction-Tasks

Relation Extraction(RE) is a relationship extraction coursework project developed based on OpenNRE, which directly provides trained models that users can directly use to perform relationship extraction on text directly.

## Overview
This project builds upon and extends the OpenNRE framework, an open-source project developed by the Natural Language Processing Group at Tsinghua University (THUNLP). OpenNRE is a versatile toolkit designed for neural relation extraction, providing a wide array of pre-trained models and the flexibility to train on custom datasets. 
We have modified parts of the toolkit, combining our ideas to optimise the following points:
 1.  Resolved an issue where the new version of the package was incompatible with the original code.
 2. One-click configuration, no longer need to do special efforts to learn how to install and configure the environment.
 3. Users can now easily use the model for relationship extraction.
## Reference
If you have more interest in the original project, for more details on the original OpenNRE framework, please visit its GitHub repository: OpenNRE GitHub repository ([OpenNRE](https://github.com/thunlp/OpenNRE)).

paper：

    @inproceedings{han-etal-2019-opennre,
    title = "{O}pen{NRE}: An Open and Extensible Toolkit for Neural Relation Extraction",
    author = "Han, Xu and Gao, Tianyu and Yao, Yuan and Ye, Deming and Liu, Zhiyuan and Sun, Maosong",
    booktitle = "Proceedings of EMNLP-IJCNLP: System Demonstrations",
    year = "2019",
    url = "https://www.aclweb.org/anthology/D19-3029",
    doi = "10.18653/v1/D19-3029",
    pages = "169--174"
    }

## Quick Start
Here are the guidelines for running in google colab. Special code modules will be given to users using jupyter to help modify the code in ipynb to run smoothly.

First of all, please follow our link to download the zip archive([re.zip](https://drive.google.com/file/d/1VOLHK9rKEGsBOhlDi-KjB6ZETBCLoBG1/view?usp=drive_link)). If it doesn't work, manually copy the URL below:
https://drive.google.com/file/d/1VOLHK9rKEGsBOhlDi-KjB6ZETBCLoBG1/view?usp=drive_link

You can also re-download the ipynb file [RE.ipynb](https://drive.google.com/file/d/1314b9U8D4VXdlkYXarZy3zCL4BwUugNR/view?usp=drive_link) on your own if you did not receive it in the coursework submitted.

***Files Management***
After getting the zip and ipynb files, if you are using colab, save the zip file in google drive's "mydrive" directory to make it easier to run the cp command in ipynb.
(Uploading directly to colab's virtual machine will take a lot of time, please upload it in drive and make sure you have enough space because the zip file is big and contains models)
In Jupyter just upload directly.

If done properly, you can just open ipynb and run it on the colab without having to read the following guide.

***Path and Code***
If you follow the tips, path won't need any extra effort from you. But if you don't, you should pay attention to the path.

    !cp "./drive/MyDrive/re.zip"  "./"
    # It works well if you put the zip file right in mydrive
    # If not, change it to your own path
    !cp "your re.zip file_path in drive" "./"
*In Jupyter：*
In case you have uploaded the zip to Jupyter, replace the first two code cells with the following.

    #Same as above './re.zip' should be the path of your zip file
    import zipfile
    with zipfile.ZipFile('./re.zip', 'r') as zip_ref:
	    zip_ref.extractall('.')
and

    # In jupyter you should also find the right path of unzip file re
    !pip install ./re/open_nre-0.1.1-py3-none-any.whl
Note the root directory in the fourth code cell：

    enter code herebase_config = {
    "dataset": "semeval",
    "train_file": "",
    "val_file": "",
    "test_file": "",
    "rel2id_file": "",
    "root_path": "./re",
    "only_test": True,
    }
    # The root directory should be "./re", please find the correct path to re.

## Model and Infer
***Train Models***
We no longer provide methods to train models, the project is already trained cnn and bert models. If you need to train the models yourself, please consult the project OpenNRE mentioned above.
The trained model can be manually imported into ckpt, and make sure the name and format is correct.

***Infer Models***
Examples of inferred relationships have been provided in the code, two for each model. Please note that the format of the input sentences must be the same as in the examples, and if in doubt refer to the semeval dataset in re/benchmark.
## Notice
This project requires gpu when running, please find your own suitable running environment carefully!

Transformers version 4.38 or higher are required for both training and inferring bert models.


  




