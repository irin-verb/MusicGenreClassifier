# Music Genre Classifier

## About

> Исследовательская работа в вузе. PyQT-приложение для определения музыкального жанра записи одной из 4ех моделей нейросети + модули для их обучения
>
> Research work at a university. PyQT application for determining the musical genre of a recording of one of 4 neural network models + modules for training them

**Предмет / Subject** :  Научно-исследовательская работа / Research work

**Курс / Course** : 3ий курс / 3rd course

## Project structure

Код для модулей neural_network_builder, neural_network_trainer полностью (за исключением некоторых методов) и для модулей music_processor, neural_network_processor частично (около половины методов) взят из репозитория <https://github.com/musikalkemist/DeepLearningForAudioWithPython>

---
The code for the neural_network_builder and neural_network_trainer modules is completely (with the exception of some methods) and for the music_processor and neural_network_processor modules partially (about half of the methods) taken from the repository <https://github.com/musikalkemist/DeepLearningForAudioWithPython>

Название модуля / Module name  | Описание модуля / Module description
----------------|----------------------
music_processor | Обработка и преобразование аудиозаписей / Processing and converting audio recordings
neural_network_builder | Построение моделей нейросетей / Building neural network models
neural_network_processor | Нейросетевое распознавание музыкальных жанров / Neural network recognition of musical genres
neural_network_trainer | Обучение нейросетей / Training neural networks
application_processor | Главный модуль приложения, точка входа в программу / The main module of the application, the entry point to the program
application_interface | Интерфейс и логика взаимодействия с пользователем / Interface and user interaction logic

## Preparation for work

Для работы с приложением необходимы следующие библиотеки: PyQT5, librosa, tensorflow, keras, sklearn

Для изучения всех возможностей с самого начала необходимо запускать ячейки Jupyter Notebook по очереди, в порядке их расположения. 

Модуль music_processor подготавливает датасет с музыкой 10ти жанров и сохраняет спектрограммы мел-частотных кепстральных коэффициентов треков по жанрам в виде json-файла.
Датасет необходимо загрузить в папку проекта c .ipynb-файлом в созданную папку "DataSet". В качестве датасета для обучения использован датасет [GTZAN](https://www.kaggle.com/datasets/andradaolteanu/gtzan-dataset-music-genre-classification)

Модуль neural_network_builder просто содержит структуру 4ех моделей нейросетей: многослойный перцептрон, многослойный перцептрон с предотвращением переобучения, сверточная нейронная сеть и рекуррентная нейронная сеть с долгой краткосрочной памятью 

Модуль neural_network_processor содержит логику обработки созданного с помощью модуля music_processor файла data.json и его подготовки к работе для задач классификации, а также методы для распознавания жанра аудиозаписи (вернее ее спектрограммы мел-частотных кепстральных коэффициентов) на основе выбранной модели

Модуль neural_network_trainer с нуля обучает 4 модели нейросети и выгружает в .keras файлы (лежат в репозитории)

Модуль application_interface просто содержит интерфейс приложения, а модуль application_processor - запускает его.

Для работы только с самим приложением, без обаботки и подготовки датасета, без обучения нейросетей с нуля необоходимо скомпилировать все модули, но запустить на выполнение только модуль application_processor (для этого методы main всех остальных неосновных модулей вынесены в отдельные ячейки)

---

The following libraries are required to work with the application: PyQT5, librosa, tensorflow, keras, sklearn

To explore all the features from the very beginning, you need to run the Jupyter Notebook cells one by one, in the order in which they appear.

The music_processor module prepares a dataset with music from 10 genres and saves spectrograms of mel-frequency cepstral coefficients of tracks by genre as a json file.
The dataset must be uploaded to the project folder with the .ipynb file in the created "DataSet" folder. The [GTZAN](https://www.kaggle.com/datasets/andradaolteanu/gtzan-dataset-music-genre-classification) dataset was used as a training dataset.

The neural_network_builder module simply contains the structure of 4 neural network models: multilayer perceptron, multilayer perceptron with overfitting prevention, CNN and RNN-LSTM

The neural_network_processor module contains the logic for processing the data.json file created using the music_processor module and preparing it for work for classification tasks, as well as methods for recognizing the genre of an audio recording (or rather, its spectrogram of chalk-frequency cepstral coefficients) based on the selected model

The neural_network_trainer module trains 4 neural network models from scratch and uploads files to .keras (located in the repository)

The application_interface module simply contains the application interface, and the application_processor module runs it.

To work only with the application itself, without processing and preparing the dataset, without training neural networks from scratch, you need to compile all modules, but only run the application_processor module (for this, the main methods of all other non-main modules are placed in separate cells)
