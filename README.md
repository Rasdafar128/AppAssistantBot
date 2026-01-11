# QnA Bot for Working with the Application

# Customer

![photo_2024-10-27_03-10-27](https://github.com/user-attachments/assets/9de8ca00-f593-4853-9f7a-8529d03f7f20)

LLC "Sila", created as part of the hackathon **Digital Breakthrough, Season: Artificial Intelligence**

# Problem

> Long onboarding for new software reduces productivity and requires significant support resources. Studying documentation takes time, while users’ habit of searching for answers through a convenient interface remains unmet.

# How Our Solution Helps

- **Cost reduction:** Instant access to answers reduces the need for technical support and training.
- **Increased answer accuracy:** By applying ML algorithms, the bot selects the most relevant answers, minimizing misunderstanding and reducing repeated support requests.

# ML Solution

- Uses LLMs (Large Language Models) to generate answers — **YandexGPT**
- The model does not hallucinate or invent facts
- The **SentenceTransformer** model is used to create embeddings — `SentenceTransformer ('BAAI/bge-m3')`

# Our Advantages

- We retrieve only the most relevant sections of the documentation to provide high-quality answers and attach images when necessary
- We store asked questions and generated answers for future reuse
- Our solution supports updating the documentation describing the application

# Architecture

![image](https://github.com/user-attachments/assets/51ba690b-7d09-45e9-aa38-bd03cd68ac35)

# Project Structure

- `Clio_Yandex_GPT.ipynb` — notebook with YandexGPT usage, answer comparison, prompt tuning, and metric calculation
- `documentation` — folder containing `.docx` files and other documentation
- `img_data` — folder with images extracted from `.docx` files
- `documentation/data_quastions.json` — a set of frequently asked questions and answers, which can be manually created via `Clio_Yandex_GPT.ipynb`
- `config.py` — file storing all keys and URLs
- `model.py` — contains the model class, prompt generator via embeddings, and QnA database creation
- `preproc_text.py` — functions for preprocessing `.docx` documentation
- `db.py` — SQL database
- `bot.py` — bot implementation
- `initialization.py` — file with all initializations
- `keyboards.py` — bot keyboard class

# Project Launch

- The `.docx` file must be located in the `documentation` folder
- Specify your links and keys in the `config.py` file

## Launch with the Initial Provided docx File

Nothing complicated here:

- Install dependencies: `pip install -r requirements.txt`
- Run the bot: `python bot.py`

```python
TG_BOT_TOKEN = 'YOUR_TOKEN'
YANDEX_PASSPORT_O_AUTH_TOKEN = 'YOUR_TOKEN'
MODEL_URI = 'YOUR_URI'
```


## Launch with Your Own docx File

This requires a few additional steps:

- The `.docx` file must contain a **TABLE OF CONTENTS** section formatted similarly to the original document in the repository
- If the document contains figures/images/photos, they must be labeled as shown in the example, e.g. `(Figure 1)`
- Then, populate the `img_data` folder with images (if any), naming them as `img_data/imgs<figure_number>.jpg`
- Install dependencies: `pip install -r requirements.txt`
- Run the bot: `python bot.py`

# Team

- [Egor Andreasyan](https://github.com/EgorAndrik)
- [Mikhail Vershinin](https://github.com/Rasdafar128)
- [Alexander Rotachyov](https://github.com/Sasha2810)



# QnA-Bot для работы с приложением

# Заказчик

![photo_2024-10-27_03-10-27](https://github.com/user-attachments/assets/9de8ca00-f593-4853-9f7a-8529d03f7f20)

ООО "Сила" сделанно в рамках хакатона Цифровой Прорыв сезон: Искусственный Интеллект

# Проблема

> Долгое освоение нового софта снижает производительность и требует много ресурсов на поддержку. Погружение в документацию занимает время, а привычка пользователей искать ответы через удобный интерфейс остается неудовлетворенной.

# Как наше решение помогает

- Сокращение затрат: Мгновенная доступность ответов снижает необходимость в технической поддержке и обучении.
- Увеличение точности ответов: Применяя ML-алгоритмы, бот подбирает наиболее релевантные ответы, что минимизирует ошибки в восприятии и снижает вероятность необходимости повторного обращения за поддержкой.

# ML Решение

- Используются LLM - большие языковые модели - для создания ответов на вопросы, ```YandexGPT```
- Модель не выдумывает и не додумывает факты
- Модель SentenceTransformer используется для создания эмбеддингов, ```SentenceTransformer ('BAAI/bge-m3’)```

# Наши Плюсы
- Мы находим только самые релевантные пункты документа для качественного ответа на вопрос, а также прилагаем фото при необходимости
- Мы сохраняем заданные вопросы и полученные ответы для дальнейшего использования
- Наше решение имеет возможность обновления документа с описанием приложения


# Архитектура

![image](https://github.com/user-attachments/assets/51ba690b-7d09-45e9-aa38-bd03cd68ac35)

# Структура проекта

- ```Clio_Yandex_GPT.ipynb``` - ноутбук с применением модели YandexGPT и сравнением ответов, настройкой промпта, а также подсчётом метрики
- ```documentation``` - папка с файлами .docx и тд
- ```img_data``` - папка с изображениями из .docx файла
- ```documentation/data_quastions.json``` - набор частых вопросов и ответов, его можно саморучно составить через ```Clio_Yandex_GPT.ipynb```
- ```config.py``` - файл в котором храняться все ключи и ссылки
- ```model.py``` - файл с классом модели и классом генератора промпта через Embeddings, а также составлением базы QnA
- ```preproc_text.py``` - файл с функциями по предобработке документации формата .docx
- ```db.py``` - SQL база данных
- ```bot.py``` - код самого бота
- ```initialization.py``` - файл со всеми инициализациями
- ```keyboards.py``` - класс с кнопками бота

# Запуск проекта

- файл формата .docx должен находитьмя в папке ```documentation```
- в файле ```config.py``` указываем свои ссылки и ключи

```python
TG_BOT_TOKEN = 'YOUR_TOKEN'
YANDEX_PASSPORT_O_AUTH_TOKEN = 'YOUR_TOKEN'
MODEL_URI = 'YOUR_URI'
```

## Запуск с docx файлом, который дан изначально

Тут ничего сложного

- скачиваем библиотеки ```pip install -r requirements.txt```
- потом запускаем бота ```python bot.py```

## Запуск со своим docx файлом

Здесь чуть больше пунктов

- Для начала нужно, чтобы в файле docx было поле СОДЕРЖАНИЕ и оно было оформлено похожим образом, как и в изначальном docx, который находится в репозитории
- Так же если в файле есть рисунки/картинки/фото то оно должны помичаться как в примере а именно " (Рисунок 1) "
- После чего нужно заполнить папку ```img_data``` изображениями, если они есть, создавать файлы нужно как img_data/imgs<номер по счету рисунка>.jpg
- после скачиваем библиотеки ```pip install -r requirements.txt```
- и запускаем бота ```python bot.py```

# Команда 
- [Андреасян Егор](https://github.com/EgorAndrik)
- [Вершинин Михаил](https://github.com/Rasdafar128)
- [Ротачёв Александр](https://github.com/Sasha2810)
