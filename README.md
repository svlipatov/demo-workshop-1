# Итоговый проект по дисциплине "Программная инженерия II"

## "Short Text Enjoy" (STE)

### Участники группы

| Участник      |            Почта               |                  Telegram |
|:--------------|:------------------------------:|--------------------------:|
| Домченко М.Н. |   <domaxnik@gmail.com>         |                    @DMaxr |
| Якунин А.Г.   |  <sanchezz.jakunin@rambler.ru> |              @YakuninAlex |
| Полозов А.П.  |     <artdd52669@gmail.com>     |                @appolozov |
| Бакланов И.Л. |         <nymra@mail.ru>        |             @ivanbaklanov |
| Архипов Д.А.  | <arkhipov.danil2015@gmail.com> |               @Arkhip2000 |
| Липатов С.В.  |    <svlipatov@bk.ru>           |               @SLipatov   |
| Мальцев А.Ю.  |        <malets86@mail.ru>      |        @AlexandrMaltsev86 |

## Цель проекта

- Создать систему, которая сможет автоматически анализировать и сокращать тексты, делая их более
читаемыми и удобными для восприятия, а также сможет давать краткие ответы на вопросы по тексту. Тем самым экономится время пользователей на изучение объемных материалов и поиск нужной информации.

## Анализ проблем

- Одной из проблем, которую может решить данный проект, является информационная перегрузка.
В современном мире мы ежедневно сталкиваемся с огромным количеством информации, которую нужно
обработать и усвоить. Сокращение текстов поможет пользователям быстрее получать основную идею и
суть материала, не тратя время на чтение всего текста полностью.
- Еще одной проблемой, которую решает данный проект, является дефицит времени. В условиях
постоянной занятости и нехватки времени, люди часто вынуждены отказываться от чтения
объемных текстов, чтобы сэкономить время. Сокращение текстов позволяет получить необходимую
информацию быстрее и без необходимости читать весь материал целиком.

## Описание решения

Решение представляет собой веб-интерфейс, который использует две готовых модели машинного
обучения. Первая модель для сокращения текста на русском языке. Вторая модель для поиска в тексте ответа на вопрос.

Web-интерфейс написан на [Streamlit](https://streamlit.io/)

- Модель для сокращения текста - [IlyaGusev/mbart_ru_sum_gazeta](https://huggingface.co/IlyaGusev/mbart_ru_sum_gazeta)
- Модель для ответа на вопрос - [timpal0l/mdeberta-v3-base-squad2](https://huggingface.co/timpal0l/mdeberta-v3-base-squad2)

## Практическая ценность

Решение предлагает веб-интерфейс, который позволяет пользователям вводить текст для сокращения.
Система автоматически анализирует и сокращает текст, отображая результат на экране.
Это позволяет пользователям быстро получить основную информацию и решить, стоит ли читать полный текст.

Кроме того, решение может быть интегрировано с другими системами и приложениями, что позволяет
использовать его в различных контекстах и задачах. Например, оно может быть полезно для создания
краткого содержания статей, новостных лент, блогов и других текстовых материалов.

## Команда и план действий

За поиск, адаптацию и тесты модели отвечают *(backend, model)*:

- Архипов Данил
- Домченко Максим
- Бакланов Иван
- Полозов Артем
- Мальцев Александр
- Липатов Сергей

За UI отвечает *(frontend)*:

- Якунин Александр

За развертку приложения отвечает *(CI/CD)*:

- Полозов Артем
- Домченко Максим

## Этапы разработки и задачи

1. Поиск и тестирование модели (ответственные: Архипов, Домченко, Бакланов, Полозов, Мальцев, Липатов)
    - поиск подходящей модели и ее анализ
    - тестирование выбранных моделей
    - выбор финальной модели исходя из системных требований и имеющихся ресурсов
    - создание backend с выбранной моделью и написание к ней тестов
2. Отрисовка front-части (ответственный: Якунин)
    - создание макета ui
    - добавление тестов
3. Написание скрипта деплоя сервиса на виртуальную машину (ответственный: Домченко)
    - аренда виртуальной машины (Я.Облако). Минимальные параметры: RAM - 16 Gb, CPU - 4 ядра, HDD - 30 Gb
    - написание скрипта для утилиты make, включающий клонирование репозитория, запуск тестов, запуск линтера, запуск сервиса
    - тестирование готового решения
4. Добавление github-actions (ответственный: Полозов)
    - добавление правил в github на дальнейшие доработки проекта (commit и pull request)
  
## Начало работы

1. Запуск:

   __Локальный запуск:__

   - Стянут проект `git clone git@github.com:kwazart/demo-workshop-1.git`
   - Перейти в проект `cd demo-workshop-1`
   - Если не установлена - установить утилиту `make` командой `sudo apt install make` ([пример установки для windows](https://stackoverflow.com/questions/32127524/how-to-install-and-use-make-in-windows))
   - Если не установлена - установить `venv` для `python`
   - Подготовить окружение (*виртуальная среда, установка пакетов*) командой `make deps`
   - Запустить командой `make run`

   __Запуск в облаке:__

   - Подключиться к ВМ в облаке по ssh
   - Стянут проект по https `git clone https://github.com/kwazart/demo-workshop-1.git`
   - Перейти в проект `cd demo-workshop-1`
   - Установить утилиту `make` командой `sudo apt install make`
   - Установить `venv` для `python` командой `sudo apt install python3.10-venv`
   - Подготовить окружение (*виртуальная среда, установка пакетов*) командой `make deps`
   - Запустить командой `make run`

2. Откройте браузер и перейдите по адресу `http://[ВАШ_IP_ADDRESS]:8080` (адрес можно взять из логов запуска проекта):
   - Если запускали локально - <http://localhost:8080/>
   - WEB приложение развёрнуто в яндекс облаке по адресу - <http://130.193.40.39:8080/>
3. Дождитесь загрузки модели (во время загрузки будет отображена строка *Running load_model()*) ![load-model](https://github.com/kwazart/demo-workshop-1/assets/46990077/416ab68a-16ea-448d-a1e7-60cd000b9fea)
4. После загрузки можете ввести свой текст в текстовое поле и далее нажмите кнопки __Применить__![using](https://github.com/kwazart/demo-workshop-1/assets/46990077/37401c25-9105-4022-8d2d-eb311c641f26)
5. После обработки вашего текста (время обработки зависит от аппаратных возможностей) будет выведен результат в зеленом блоке ![final](https://github.com/kwazart/demo-workshop-1/assets/46990077/f66f8bb0-5ba9-412f-97e1-d3158c1bb0c2)
6. Ввести вопрос по тексту и нажать на кнопку __Получить ответ__ ![Screenshot 2024-03-30 033251](https://github.com/kwazart/demo-workshop-1/assets/86611399/093d58e8-6b9a-4603-8e3e-fe1d7eca9a15)

## Заключение

Основные преимущества нашего проекта:

- Экономия времени пользователей на чтение объемных текстов.
- Повышение эффективности работы с информацией за счет быстрого доступа к основной идее и ключевым моментам текста.
- Возможность быстрого поиска ответа на интересуюшие пользователя вопросы.
- Возможность интеграции с другими системами и приложениями для расширения области применения решения.
- Создание удобного и полезного инструмента для работы с большими объемами информации.
