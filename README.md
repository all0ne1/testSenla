# Симуляция экосистемы

## Описание
Симуляция, которая моделирует взаимодействие между живыми существами, такими как хищники, травоядные и растения. Она учитывает фактор температуры и влажности, определяя условия для живых существ. В каждой клетке содержится 1 животное, n количество растений и m воды. 
Программа поддерживает загрузку уже существующих симуляци и создание новых. Подключено логгирование большинство действий происходящих во время симуляции. 
Климат изменяется в симуляции, плавно смещаясь в сторону подсчетов на основе процентного общего соотношения параметров (животных, растений и воды) к их максимально возможному.
На карте содержатся источники воды, которые пополняются. Вода растекается по всем возможным соседним клеткам и потребляются растениями

# Симуляция происходит пошагово:
- Распространение воды в соседние клетки
- Рост растений
- Ход травоядных
- Ход хищников
- Пополнение источников воды
- Старение
- Обновление климатических условий

## Особенности
- Моделирование взаимодействия между хищниками и травоядными.
- Настройка климатических условий (влажность и температура).
- Динамический климат
- Возможность сохранения и загрузки состояния симуляции.
- Графическое представление симуляции в виде двухмерного массива.
- Пошаговая механика

## Структура
- climate/Climate -- класс климата
- climate/Conditions -- enum для условий климата
- map/Cell -- класс клетки
- map/EcosystemMap -- клас карты для обработки взаимодействий с ней
- species/Animal -- интерфейс животных
- species/Plant -- интерфейс растений
- species/Flora -- общий класс для растений
- species/Herbivore -- общий класс для травоядных, описывает стандартное поведение
- species/Predator -- общий класс для хищников, описывает стандартное поведение
- species/Species -- абстрактный класс для всех возможных видов в экосистеме
- utils/Colors -- вспомогательный класс с глобальными переменными для придания цвета вывода в консоль
- utils/Utils -- вспомогательные класс для загрузки существующих и инициализации создания новых симуляций
- Config -- класс конфигурации симуляции
- Ecosystem -- содержит инициализацию логгирования и метод симуляции
- Main -- точка входа

## Пример вывода
```
[P] - Хищник
[HE] - Травоядное
[T] - Растение
[P,nT] - Хищник и n растений
[H,nT] - Травоядное и n растений
Ход 1
+--------------------------------------------------------------------------------+
| [*3T*] [*1T*] [*2T*] [*1T*] [*1T*] [*3T*] [H,1T] [*2T*] [*2T*] [*2T*]|
| [*1T*] [*3T*] [*1T*] [*2T*] [****] [****] [*HE*] [****] [****] [*1T*]|
| [****] [****] [****] [*1T*] [*1T*] [*1T*] [*2T*] [*1T*] [H,1T] [*1T*]|
| [*3T*] [****] [*1T*] [*2T*] [****] [*1T*] [*1T*] [*1T*] [*1T*] [*HE*]|
| [*2T*] [*1T*] [*1T*] [*2T*] [*1T*] [****] [H,1T] [*1T*] [*2T*] [*2T*]|
| [****] [*2T*] [*3T*] [****] [*1T*] [*2T*] [*2T*] [*3T*] [*2T*] [****]|
| [****] [*3T*] [P,2T] [*2T*] [****] [*2T*] [*2T*] [*2T*] [*2T*] [*2T*]|
| [*1T*] [*2T*] [*1T*] [*3T*] [****] [*2T*] [*2T*] [*1T*] [*HE*] [*2T*]|
| [*2T*] [****] [*2T*] [*HE*] [P,2T] [*HE*] [****] [****] [*1T*] [*2T*]|
| [*1T*] [*1T*] [****] [*2T*] [*1T*] [*2T*] [*2T*] [****] [*1T*] [*1T*]|
+--------------------------------------------------------------------------------+
```
![image](https://github.com/user-attachments/assets/084ce4a3-5f46-457e-9c8c-6fa56fc4992c)

