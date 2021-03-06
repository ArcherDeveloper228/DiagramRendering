# Требования к проекту
---
# Содержание

# 1 Введение

## 1.1 Назначение

 В этом документе описаны функциональные и нефункциональные требования к веб-приложению «DiagramRendering» для Google Chrome. Этот документ предназначен для команды, которая будет реализовывать и проверять корректность работы приложения.

## 1.2 Бизнес-требования


### 1.2.1 Исходные данные

В современном мире много людей работает с различного рода диаграммами и сервисами, которые предоставляют возможности работы с ними.
Однако, не все из них предосталяют информацию в нужном для пользователя виде. Это приводит к тому, что пользователи ищут сторонние сервисы для получение желаемого результата. 


### 1.2.2 Возможности бизнеса

Многие преподователи, архитекторы желают иметь приложение, которое позволит получать диаграммы в png формате. Подобное приложение позволит им тратить меньше времени на получение необходимого результата. Интерфейс, спроектированный с учётом того что он должен быть простым, чтобы была возможность работать людям с малой технической грамотностью.

## 1.3 Аналоги

Основное отличие от большинства аналогов -- способ предоставления сервиса. DiagramRendering является веб-приложением, это значительно упрощает процесс использования. 
Все перечисленные аналоги требуют предварительной установки и настройки.

- https://www.onlinecharts.ru/
  - Отсутсвие возможности генерировать диаграммы по уже существующему xml файлу.
- https://www.chartblocks.com/
  - Реклама
  - Отсутсвие возможности генерировать диаграммы по уже существующему xml файлу.

## Требования пользователя

### Программные интерфейсы

- Должна быть возможность отображения диаграммы в браузере.
- Должен быть реализован рендеринг диаграммы, которую генерирует библиотека mxGraph в изображение формата png.
- Должна быть возможность сохрание полученного результат на локальный диск компьютера. 

### Интерфейс пользователя

- Главный экран приложения
  ![Main](mockups/Main.png)
- Страница для управления пользователями
  ![PersonalPage](mockups/UsersTable.png)
- Страница для рендеринга
  ![RenderPage](mockups/RenderPage.png)
- Страница с диаграммой
  ![RenderPage](mockups/PageWithDiagram.png)

### Характеристики пользователей


### 2.3.1 Классы пользователей

| Класс пользователей | Описание |
|:---|:---|
| Анонимные пользователи | Пользователи, которые не хотят регистрироваться в приложении. Не имеют доступ к функционалу |
| Зарегистрированные пользователи | Пользователи, которые вошли в приложение под своим именем (псевдонимом), желающие рендерить диаграммы, выбранные ими. Имеют доступ к частичному функционалу |
| Администраторы | Пользователи, которые вошли в приложение под своим именем (псевдонимом) и имеющие, возможность не только рендерить диаграммы,но и активировать пользователей. Имеют доступ к полному функционалу |

### 2.3.2 Аудитория приложения


#### 2.3.2.1 Целевая аудитория

 Люди со средним или выше среднего уровнем образования,например, архитекторы, преподаватели, менеджеры, обладающие минимальной технической грамотностью.


#### 2.3.2.2 Побочная аудитория
Все остальные люди, обладающие вышеперечисленными качествами.


## 2.4 Предположения и зависимости
1. Приложение будет работать независимо от подключения к Интернету;
2. Приложение не обрабатывает файлы xml не сгенерированные библиотекой mxGraph.


# 3 Системные требования


## 3.1 Функциональные требования


### 3.1.1 Основные функции

#### 3.1.1.1 Вход пользователя в приложение
**Описание.** Пользователь имеет возможность использовать приложение без создания собственного профиля либо войдя в свою учётную запись.

| Функция | Требования | 
|:---|:---|
| Вход в приложение без создания собственного профиля | Приложение должно предоставить пользователю возможность войти в приложение|
| <a name="registration_requirements"/>Регистрация нового пользователя | Приложение должно запросить у пользователя ввести имя для создания учётной записи. Пользователь должен либо ввести имя, либо отменить действие |
| *Пользователь с таким именем существует* | *Приложение должно известить пользователя об ошибке регистрации и запросить ввод 


#### 3.1.1.2 Активация аккаунта
**Описание.** Администратор имеет возможность активировать/деактивировать аккаунт.

| Функция | Требования | 
|:---|:---|
| <a name="registration_requirements"/>Администратор должен активировать/деактивировать аккаунт | Пользователь должен зарегистрироваться и дождаться, пока администратор активирует аккаунт |


#### 3.1.1.3 Рендеринг диаграммы
**Описание.** Зарегистрированный пользователь имеет возможность рендерить диаграммы.

| Функция | Требования | 
|:---|:---|
| Рендеринг диаграммы | Пользователь имеет возможность выбрать файл из локального хранилища | Приложение должно отрендерить диграмму и отобразить ее в окне браузера |


#### 3.1.1.4 Сохранение изображения
**Описание.** Пользователь имеет возможность сохранить изображение на локальный диск.

| Функция | Требования | 
|:---|:---|
| Сохранение изображения | Пользователь должен иметь возможность сохранить полученную диаграмму в выбранную им дерикторию |


#### 3.1.1.5 Выход зарегистрированного пользователя из учётной записи
**Описание.** Зарегистрированный пользователь имеет возможность выйти из учётной записи.

**Требование.** Приложение должно предоставить зарегистрированному пользователю возможность выйти из учётной записи с возвратом к окну входа в приложение.

#### 3.1.1.6 Регистрация нового пользователя после входа в приложение
**Описание.** Анонимный пользователь имеет возможность зарегистрироваться в приложении.

**Требование.** Приложение должно предоставить анонимному пользователю возможность зарегистрироваться в приложении. 


### 3.1.2 Ограничения и исключения
1. Приложение работает независимо от подключения к Интернету;
2. Рендеринг осуществляется при наличии подходящего xml файла, сгенерированного при помощи библиотеки mxGraph.


## 3.2 Нефункциональные требования


### 3.2.1 Атрибуты качества


#### 3.2.1.1 Требования к удобству использования
1. Все элементы должны быть светлыми;
2. Все функциональные элементы пользовательского интерфейса имеют названия, описывающие действие, которое произойдет при выборе элемента;


#### 3.2.1.2 Требования к безопасности
Приложение предоставляет возможность рендеринга и сохранения диаграммы только после активации администратором данного аккуаунта.


### 3.2.2 Внешние интерфейсы
Окна приложения удобны для использования пользователями с плохим зрением :
  * размер шрифта не менее 14пт;
  * функциональные элементы контрастны фону окна.


### 3.2.3 Ограничения
1. Приложение реализовано на платформе .NET Framework 4.7.2;
2. Профиль пользователя хранится в базе данных.