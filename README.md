# ML_company_audit_project
Итоговый проект курса "Машинное обучение в бизнесе"

Стек:

ML: sklearn, pandas, numpy
API: flask
Данные: https://archive.ics.uci.edu/ml/datasets/Audit+Data 

Задача: предсказать по результатм аудита, является ли организация мошеннической или нет (поле Risk). Бинарная классификация

Используемые признаки:

- Inherent_Risk (float64)
- CONTROL_RISK (float64)
- Detection_Risk (float64)
- Audit_Risk (float64)

Преобразования признаков: StandardScaler

Модель: Logistic Regression

### Клонируем репозиторий и создаем образ
```
$ git clone https://github.com/highgroll/ML_company_audit_project.git
$ cd ML_company_audit_project
$ docker build -t highgroll/ML_company_audit_project .
```

### Запускаем контейнер

Здесь Вам нужно создать каталог локально и сохранить туда предобученную модель (<your_local_path_to_pretrained_models> нужно заменить на полный путь к этому каталогу)
```
$ docker run -d -p 8180:8180 -p 8181:8181 -v <your_local_path_to_pretrained_models>:/app/app/models fimochka/gb_docker_flask_example
```

### Переходим на localhost:8181
