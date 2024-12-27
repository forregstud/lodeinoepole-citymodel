# Введение

В рамках дисциплины «Анализ данных и моделирование в урбанистике» командой №9 – студентами 2 курса Института Дизайна и Урбанистики Университета ИТМО – были подготовлены три сценария развития проектной территории – бывшего военного аэродрома в Ленинградской области, – прилегающей к г. Лодейное поле.

Лодейное Поле — город в Ленинградской области, административный центр Лодейнопольского муниципального района и Лодейнопольского городского поселения. Находится примерно в 193 км и 2,5 часах езды на автомобиле от Санкт-Петербурга. Город стоит на Волго-Балтийском водном пути, рядом проходит автодорога Р21 «Кола» (Санкт-Петербург – Мурманск).

Стратегией социально-экономического развития Лодейнопольского муниципального района определена проектная инициатива «Комфортные поселения», которая реализуется на всей территории области: населенные пункты должны стать комфортными для проживания и доступными в качестве места работы, удовлетворяющими современные потребности жителей в удобном жилье, коммунальных, бытовых, финансовых, социальных услугах, услугах сферы торговли, культуры, спорта и досуга, экологии, связи.

Отвечая инициативе, положенной в СЭР, командой проекта предлагается неиспользуемый на данный момент военный аэродром отдать под жилую застройку, однако, ключевой вопрос в том – какого характера, чтобы это не только воспрепятствовало развитию Лодейного Поля но и частично сбалансировало его актуальные проблемы.

# Постановка цели:
Цель курсовой работы заключается в определении вектора развития проектной территории, расположенной в границах Лодейнопольского городского поселения, а также её влияния в перспективе на г. Лодейное Поле, к которому она прилегает. Достижение поставленной цели сопряжено с формированием трёх сценариев развития жилой застройки, апробация которых посредством применения методов анализа данных и моделирования позволит выявить оптимальный.

# Команда проекта:

1.	Кураксина Варвара (апробация гипотез, анализ результатов, формирование гипотез и выводов, оформление репозитория) 
2.	Губина Алина (подготовка данных, расчёт ТЭП, формирование гипотез и выводов)
3.	Липовская Дарья (подготовка данных, визуализация результатов, сбор презентации)
4.	Басова Маргарита (предпроектное исследование)
5.	Сорокин Константин (апробация гипотез, анализ результатов)

# Предпроектный анализ
## Scenario 0

Прежде чем начать формировать сценарии развития, требовалось понимание контекста ситуации и оценки г. Лодейного Поля предложенными библиотекой BlocksNet методами и метриками.

> Перед запуском [скрипта](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/pipeline.py) необходимо установить библиотеки.

В рамках дисциплины «Цифровое моделирование урбанизированных территорий» были собраны и подготовлены геослои с [дорогами](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_0/geojson%20files/railway.geojson), [железными дорогами](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_0/geojson%20files/railway.geojson) и [зданиями](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_0/geojson%20files/building.geojson) (с проставленными атрибутами population, building:levels, is_living). Эти данные, в частности, легли в основу предпроектного анализа, который включил в себя следующие шаги.

1.	Отрисовку [геометрии границ города](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_0/geojson%20files/boundaries.geojson) Лодейное Поле с включением в них территории проектирования (бывший военный аэродром).
2.	Генерацию [городских кварталов](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_0/geojson%20files/blocks/blocks.geojson) с помощью BlocksGenerator на основе имеющихся геослоев [автомобильных](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_0/geojson%20files/railway.geojson) и [железных дорог.](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_0/geojson%20files/railway.geojson)
3.	Получение [графа улично-дорожной сети](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_0/graph/graph.png) в границах территории с помощью библиотеки IduEdu.
4.	Произведение на основе графа расчёта [матрицы доступности](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_0/methods/accessibility.png) и [матрицы связности](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_0/methods/connectivity.png). 
5.	Произведение расчета обеспеченности территории [школами](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_0/provision/school_provision.png), [детскими садами](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_0/provision/kindergarten_provision.png), [торговыми центрами](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_0/provision/mall_provision.png), [аптеками](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_0/provision/pharmacy_provision.png), [МФЦ](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_0/provision/multifunctional_center_provision.png), [супермаркетами](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_0/provision/supermarket_provision.png), [барами](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_0/provision/bar_provision.png), [кафе](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_0/provision/cafe_provision.png), [отделениями почтовой связи](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_0/provision/post_provision.png), [булочными](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_0/provision/bakery_provision.png).
6.	Реализация методов и метрик по подсчету [разнообразия сервисов](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_0/methods/services_diversity.png), центральности ([населения](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_0/methods/population_centrality.png), [сервисов](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_0/methods/centrality.png)), [определению типа землепользования](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_0/methods/landuseprediction.png) и морфотипа застройки ([SpaceMatrix](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_0/methods/spacematrix.png)).

Оценка Scenario 0 позволила результировать следующий контекст:

### Обеспеченность сервисами
- **Школы**: обеспеченность школами в южной части недостаточна. Размещение дополнительной школы в проектном квартале должно улучшить обеспеченность школьными местами в южной части города.
- **Детские сады**: обеспеченность детскими садами в южной части недостаточна. Размещение дополнительного детского сада в проектном квартале должно улучшить обеспеченность местами в южной части города.
- **Супермаркет**: в целом весь город недостаточно обеспечен торговыми площадями исходя из показателя индекса Provision, поэтому необходимо размещение супермаркета на проектной территории.

### Разнообразие сервисов
Высокий индекс только в северной части города вдали от проектной территории. Размещение жилой застройки предполагает улучшение индекса в южной части города.

### Spacematrix
Город разделен на две части. С юга преобладает малоэтажная низкоплотная застройка. С севера примерно в равных пропорциях малоэтажная низкоплотная и среднеэтажная низкоплотная. Таким образом, в городе отсутствует высотная жилая застройка.

### Оценка центральности по сервисам
Сервисы сконцентрированы в северной части города. Размещение жилой застройки предполагает улучшение индекса в южной части города.

### Оценка центральности населения
Центр города тяготеет к железнодорожной станции, которая разделяет город на две части - южную и северную. Размещение проектной территории должно расширить условный центр города по показателю размещению населения.

### Вывод 
Выбранное место для размещения новой жилой застройки должно улучшить обеспеченность сервисами как в южной части города, так и в городе в целом, так как южная часть города развита хуже чем северная, соотвественно, требуется размещение дополнительных сервисов и общественных центров для улучшения показателей обеспеченности сервисами и разнообразия в кварталах.
   
# Гипотезы развития
Ни для одного сценария **[не были взяты за основу результаты применения инструмента rTeam](https://github.com/forregstud/lodeinoepole-citymodel/tree/main/scenario_rtim%20(denied))** - платформы автоматизированного проектирования развития территории: команда осталась неудовлетворена сгенерированной квартальной сеткой, расположением домов, которые в большинстве случаев занимали целый квартал подобно жилому комплексу, распределением сервисов и неэффективным землепользованием, оставляющим значительные незаполненные пустыри.  В связи с этим, для каждого сценария развития были отрисованы улично-дорожная сеть, рассчитаны технико-экономические показатели (включая население), расставлены сервисы (как нормативно, так и ненормативно в зависимости от сценария) _вручную_. Произведены те же расчеты, что и для **Scenario 0**.

## Scenario 1. Малоэтажная застройка.
Первый сценарий развития предлагает акцентироваться на сохранении природной составляющей, реализовать рекреационный потенциал через формирование лесопарковой зоны. Жилые кварталы представлены ИЖЗ (1-2 этажа), которая дает возможность жить в собственном доме и/или иметь участок земли в индивидуальном пользовании. Застройка соразмерна прилегающей к территории проектирования южной части города. Сервисы определены нормативно. 

![Визуализация первого сценария](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_1/scenario_1_viz.png)

**Сильные стороны сценария**:
1. _Рекреационные возможности_: создание лесопарковой зоны обеспечивает жителям условия для активного отдыха, спорта и времяпрепровождения на природе.
2. _Гармония застройки_: застройка, соответствующая местно сложившимся морфотипам, способствует созданию комфортной городской среды и снижает нагрузку на инфраструктуру.
   
**Слабые стороны сценария**: 
1.	_Нерешенная проблема необеспеченности сервисами_: прирост населения не увеличит значительно нагрузку на существующие сервисы, она распределится на новые, однако вопрос актуальной необеспеченности ключевыми сервисами не будет урегулирован.
2.	_Зависимость от личного автомобиля_: низкоплотная и разреженная территория, застроенная ИЖС, требует для лучшей мобильности наличие личного автомобиля, что, вероятно, увеличит автомобильный поток и создаст нежелательную нагрузку на транспортную инфраструктуру, в частности, спровоцировал пробки на выезде с проектной территории.
   
Ожидаемым результатом после реализации методов и метрик является достаточно низкий уровень обеспеченности населения ключевыми сервисами (школами, детскими садами, аптеками, почтовыми отделениями, супермаркетами): проектируемая численность населения – 1.2 тыс человек, соответственно, количество закладываемых в сценарий сервисов незначительно. В среднем, **результаты обеспеченности** для первого сценария предполагаются **не выше 0.5**. **Доступность (accessibility)** при обеспечении проектной территории УДС должна остаться в пределах **10-15 минут** от одного квартала ко многим и от многих кварталов к одному, **связность (connectivity)** новых кварталов с существующими - в диапазоне от 1.5 до 3. Предполагается, что Landuse Prediction определит территорию проектирования категорией **residential**, **SpaceMatrix** - **малоэтажной низкоплотной жилой застройкой**.

### Результаты Scenario 1.
- Сгенерированные [кварталы](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_1/geojson%20files/blocks/blocks_1.geojson) на основе [дорог](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_1/geojson%20files/road_1.geojson) и [железных дорог](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_0/geojson%20files/railway.geojson).
- [Дорожный граф](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_1/graph_1/graph_1.png).
- Матрица [доступности](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_1/methods_1/accessibility_1.png) и матрица [связности](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_1/methods_1/connectivity_1.png).
- Обеспеченность населения (подготовленный слой с домами) сервисами: [булочные](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_1/provision_1/bakery_provision_1.png), [бары](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_1/provision_1/bar_provision_1.png), [кафе](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_1/provision_1/cafe_provision_1.png), [детские сады](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_1/provision_1/kindergarten_provision_1.png), [торговые центры](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_1/provision_1/mall_provision_1.png), [МФЦ](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_1/provision_1/multifunctional_center_provision_1.png), [аптеки](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_1/provision_1/pharmacy_provision_1.png), [почтовые отделения](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_1/provision_1/post_provision_1.png), [школы](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_1/provision_1/school_provision_1.png), [супермаркеты](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_1/provision_1/supermarket_provision_1.png).
- [Разнообразие сервисов](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_1/methods_1/services_diversity_1.png).
- Центральность ([сервисов](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_1/methods_1/blocks_centrality_1.png), [населения](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_1/methods_1/population_centrality_1.png)).
- [Landuse Prediction](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_1/methods_1/landuse_prediction_1.png).
- [SpaceMatrix](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_1/methods_1/spacematrix_1.png).

Полученная [городская модель](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_1/city_model_1/city_model_1.pkl).

### Обеспеченность:

_Школы_: обеспеченность школами в южной части города была недостаточная. Размещение дополнительной школы в проектном квартале улучшило ситуацию в целом в южной части города. Территория новой застройки также является обеспеченной согласно показателям индекса.
_Детские сады_: обеспеченность детскими садами в южной части недостаточная. Размещение дополнительного детского сада в проектном квартале улучшило ситуацию в целом в южной части города. Однако нормативное размещение детского сада на проектируемой территории не полностью охватывает новую застройки и остаются необеспеченные кварталы согласно методу.
_Супермаркеты_: в целом весь город был недостаточно обеспечен торговыми площадями. Требуется размещение дополнительных торговых площадей на проектируемой территории.

### Разнообразие сервисов:
Размещение новой застройки привело к улучшению индекса в южной части города в целом.

### Оценка центральности по сервисам
Центральность размещения сервисов сместилась на территорию новой застройки. Таким образом, новый квартал может стать новым локальным городским центром для южной части города.

### Оценка центральности по населения
Отмечается смещение локального центра в южной части города в сторону новой застройки.

### Вывод:
Размещение новой застройки согласно выбранному сценарию 1 улучшает показатели качества городской среды в целом для Лодейного поля (южной части), за счет улучшения показателей обеспеченности местами в школах. Однако требуется размещение дополнительных торговых площадей и мест в детских садах.

## **Scenario 2. Среднеэтажная застройка.**
Приоритетом второго сценария является увеличение численности и плотности населения, обеспечение его большим количеством доступного жилья. Застройка главным образом средне- и многоэтажная (максимум - 7 этажей), повторяющая характер северной части города. Сервисы определены нормативно.

![Визуализация второго сценария](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_2/scenario_2_viz.png)

**Сильные стороны сценария:**
1. _Увеличение доступного жилья:_ рост числа жилых объектов позволяет большему количеству людей найти жильё по приемлемым ценам, что улучшает социальные условия.
2. _Плотность застройки:_ средне- и многоэтажная застройка позволяет максимально эффективно использовать доступные земельные ресурсы, что может снизить давление на инфраструктуру в других районах.
   
**Слабые стороны сценария:**
1. _Перегрузка инфраструктуры:_ резкое увеличение плотности населения может привести к перегрузке существующих социальных и коммунальных служб.
2. _Снижение качества жизни:_ увеличение числа жителей может ухудшить условия проживания, например, повысив уровень шума и загрязнения.

В связи с высокой проектируемой численностью населения - 12,2 тыс. человек - предполагается несколько большее размещение сервисов, однако это не гарантирует достижение желаемого уровня обеспеченности. Самый густонаселенный сценарий имеет риск получить самые низкие показатели обеспечнности. В среднем, **результаты обеспеченности** для второго сценария предполагаются **не выше 0.4**. **Доступность (accessibility)** при обеспечении проектной территории УДС должна остаться в пределах **10-15 минут** от одного квартала ко многим и от многих кварталов к одному, **связность (connectivity)** новых кварталов с существующими - в диапазоне от 1.5 до 3. Предполагается, что Landuse Prediction определит территорию проектирования категорией **residential**, **SpaceMatrix** - **среднеэтажной жилой застройкой**.

### Результаты Scenario 2.
- Сгенерированные [кварталы](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_2/geojson%20files_2/blocks/blocks_2.geojson) на основе [дорог](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_2/geojson%20files_2/road_2.geojson) и [железных дорог](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_0/geojson%20files/railway.geojson).
- Дорожный [граф](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_2/graph_2/graph_2.png).
- Матрица [доступности](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_2/methods_2/accessibility_provision_.png) и матрица [связности](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_2/methods_2/connectivity_2.png).
- Обеспеченность населения (подготовленный слой с домами) сервисами: [булочные](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_2/provision_2/bakery_provision_2.png), [бары](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_2/provision_2/bar_provision_2.png), [кафе](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_2/provision_2/cafe_provision_2.png), [детские сады](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_2/provision_2/kindergarten_provision_2.png), [торговые центры](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_2/provision_2/mall_provision_2.png), [МФЦ](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_2/provision_2/multifunctional_center_provision_22.png), [аптеки](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_2/provision_2/pharmacy_provision_2.png), [почтовые отделения](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_2/provision_2/post_provision_2.png), [школы](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_2/provision_2/school_provision_2.png), [супермаркеты](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_2/provision_2/supermarket_provision_2.png).
- [Разнообразие сервисов](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_2/methods_2/services_diversity_2.png).
- Центральность ([сервисов](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_2/methods_2/services_diversity_2.png), [населения](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_2/methods_2/population_centrality_2.png)).
- [Landuse Prediction](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_2/methods_2/landuse_prediction_2.png).
- [SpaceMatrix](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_2/methods_2/spacematrix_2.png).

Полученная [городская модель](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_2/city_model_2/city_model_2.pkl).

### Обеспеченность:

_Школы_: обеспеченность школами в южной части города была недостаточная. Размещение дополнительной школы в проектном квартале улучшило ситуацию в целом в южной части города. Однако, территория новой застройки будет не полностью обеспечена согласно показателям индекса.
_Детские сады_: обеспеченность детскими садами в южной части недостаточная. Размещение дополнительного детского сада в проектном квартале улучшило ситуацию в целом в южной части города. Однако нормативное размещение детского сада на проектируемой территории не полностью охватывает новую застройки и остаются необеспеченные кварталы согласно методу.
_Супермаркеты_: в целом весь город был недостаточно обеспечен торговыми площадями. Требуется размещение дополнительных торговых площадей на проектируемой территории.

### Разнообразие сервисов:
Размещение новой застройки не привело к улучшению индекса в южной части города в целом и на проектной территории в частности.

### Оценка центральности по сервисам
Центральность размещения сервисов сместилась на территорию новой застройки. Таким образом, новый квартал может стать новым локальным городским центром для южной части города.

### Оценка центральности по населения
Смещение локального центра в южной части города в сторону новой застройки. Возможно появление нового локального центра города.

### Вывод:
Размещение новой застройки согласно выбранному сценарию 2 улучшает показатели качества городской среды в целом для Лодейного поля (южной части) за счет улучшения разнообразия сервисов и возможного появления нового локального центра. Однако требуется размещение дополнительных торговых площадей, более оптимальное размещение детских садов и школ на проектируемой территории.

### Scenario 3. Совмещение малоэтажной и среднеэтажной застройки.

Сбалансированный сценарий развития посредством формирования комфортных районов среднеэтажной жилой застройки + БЖД (максимаьная высота зданий - 4 этажа). Создание сомасштабных человеку пространств, интеграция зелёных структур в городскую среду. Сервисы определены **НЕнормативно**.

Интерес третьего сценария заключается в том, что изначально нормативно расставленные сервисы при средней спроектированной численнности населения в 7,9 тыс. человек вполне вероятно тоже не обеспечат территорию в полной мере ключевыми сервисами, в связи с чем для третьего сценария было сформировано две городских модели: с нормативно и ненормативно расставленными сервисами. За эталонную мы принимаем **версию 3.2**.

![Визуализация третьего сценария](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_3/scenario_3_viz.png)

**Сильные стороны сценария:**

1. _Комфортные районы:_ формирование среднеэтажной жилой застройки способствует созданию удобных и доступных для жизни пространств, что повышает качество жизни жителей.
2. _Интеграция зелёных структур:_ включение зелёных зон в городскую среду способствует улучшению экологии, повышает уровень комфорта и способствует здоровому образу жизни.
3. _Гибкость в определении сервисов:_ ненормативное определение сервисов позволяет гибко адаптироваться к меняющимся запросам и потребностям сообщества.

**Слабые стороны**:
1. _Зависимость от финансирования:_ Реализация такого сценария часто требует значительных финансовых вложений как со стороны государства, так и частных инвесторов. В условиях экономической нестабильности это может стать серьезным ограничением

В качестве ожиданий допускается, что при соблюдении нормативов градостроительного проектирования количество сервисов будет соотвествовать численности населения (территория будет обеспечена сервисами). Районы малоэтажной застройки оказываются в зоне риска. При уточнении количества сервисов, обеспеченность улучшится. В среднем, **результаты обеспеченности** для третьего сценария предполагаются **выше 0.4**. **Доступность (accessibility)** при обеспечении проектной территории УДС должна остаться в пределах **10-15 минут** от одного квартала ко многим и от многих кварталов к одному, **связность (connectivity)** новых кварталов с существующими - в диапазоне от 1.5 до 3. Предполагается, что Landuse Prediction определит территорию проектирования категорией **residential**, **SpaceMatrix** - **среднеэтажной жилой застройкой**.

### Результаты Scenario 3 (нормативное внедрение новых сервисов).
- Сгенерированные [кварталы](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_3/geojson%20files_3/blocks/blocks_3.geojson) на основе [дорог](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_3/geojson%20files_3/road_3.geojson) и [железных дорог](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_0/geojson%20files/railway.geojson).
- Дорожный [граф](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_3/graph_3/graph_3.png).
- Матрица [доступности](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_3/methods_3/accessibility_3.png) и матрица [связности](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_3/methods_3/connectivity_3.png).
- Обеспеченность населения (подготовленный слой с домами) сервисами: [булочные](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_3/provision_3/bakery_provision_3.png), [бары](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_3/provision_3/bar_provision_3.png), [кафе](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_3/provision_3/cafe_provision_3.png), [детские сады](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_3/provision_3/kindergarten_provision_3.png), [торговые центры](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_3/provision_3/mall_provision_3.png), [МФЦ](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_3/provision_3/multifunctional_center_provision_3.png), [аптеки](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_3/provision_3/pharmacy_provision_3.png), [почтовые отделения](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_3/provision_3/post_provision_3.png), [школы](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_3/provision_3/school_provision_3.png), [супермаркеты](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_3/provision_3/supermarket_provision_3.png).
- [Разнообразие сервисов](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_3/methods_3/service_diversity_3.png).
- Центральность ([сервисов](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_3/methods_3/blocks_centrality_3.png), [населения](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_3/methods_3/population_diversity_3.png)).
- [Landuse Prediction](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_3/methods_3/landuse_prediction_3.png).
- [SpaceMatrix](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_3/methods_3/spacematrix_3.png).

Полученная [городская модель](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_3/city_model_3/city_model_3.pkl) для нормативно внедренных сервисов.

### Результаты Scenario 3.2 (ненормативное внедрение новых сервисов).
- Обеспеченность населения (подготовленный слой с домами) сервисами: [булочные](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_3/provision_3.2/bakery_provision_3.2.png), [бары](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_3/provision_3.2/bar_provision_3.2.png), [кафе](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_3/provision_3.2/cafe_provision_3.2.png), [детские сады](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_3/provision_3.2/kindergarden_provision_3.2.png), [торговые центры](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_3/provision_3.2/mall_provision_3.2.png), [МФЦ](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_3/provision_3.2/multifunctional_center_provision_3.2.png), [аптеки](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_3/provision_3.2/pharmacy_provision_3.2.png), [почтовые отделения](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_3/provision_3.2/post_provision_3.2.png), [школы](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_3/provision_3.2/school_provision_3.2.png), [супермаркеты](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_3/provision_3.2/supermarket_provision_3.2.png).
- [Разнообразие сервисов](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_3/methods_3.2/services_diversity_3.2.png).
- Центральность ([сервисов](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_3/methods_3.2/blocks_centrality_3.2.png), [населения](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_3/methods_3.2/blocks_centrality_3.2.png)).
- [Landuse Prediction](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_3/methods_3.2/landuse_prediction_3.2.png).
- [SpaceMatrix](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_3/methods_3.2/spacematrix_3.2.png).

- Полученная [городская модель](https://github.com/forregstud/lodeinoepole-citymodel/blob/main/scenario_3/city_model_3/city_model_3.2.pkl) для ненормативно внедренных сервисов.

Оценка Scenario 3.2 позволила результировать следующий контекст:

### Обеспеченность сервисами
- **Школы**: обеспеченность школами в южной части города была недостаточная. Размещение дополнительной школы в проектном квартале улучшило ситуацию в целом в южной части города. Территория новой застройки также является обеспеченной согласно показателям индекса.
- **Детские сады**: обеспеченность детскими садами в южной части недостаточная. Размещение дополнительного детского сада в проектном квартале улучшило ситуацию в целом в южной части города. Для территория новой застройки возможно потребуется размещение дополнительных мест в детских садах во встроенных помещениях на перифериях нового микрорайона.
- **Супермаркет**: в целом весь город был недостаточно обеспечен торговыми площадями исходя из показателя Provision, поэтому было необходимо размещение супермаркета на проектной территории. После размещения супермаркета на проектной территории обеспеченность улучшилась.

### Разнообразие сервисов
Как и предполагалось, размещение новой застройки привело к улучшению показателя в южной части города в целом.

### Spacematrix
Размещение новой застройки не изменяет высотный ландшафт застройки города. Город остается малоэтажным.

### Оценка центральности по сервисам
Центральность размещения сервисов сместилась на территорию новой застройки. Таким образом, новый квартал может стать новым локальным городским центром для южной части города.

### Оценка центральности по населению
Появление нового локального центра на территории новой застройки по показателю центральности населения.

# Сравнение показателя Provision для всех Сценариев

| Категории              | Сценарий 0 | Сценарий 1 | Сценарий 2 | Сценарий 3 | Сценарий 3.2 |
|------------------------|-------------|-------------|-------------|-------------|---------------|
| Булочные               | 1           | 1           | 1           | 1           | 1             |
| Бары                   | 0,095       | 0,176       | 0,119       | 0,134       | 0,271         |
| Кафе                   | 1           | 1           | 1           | 1           | 1             |
| Детские сады          | 0,408       | 0,509       | 0,331       | 0,376       | 0,43          |
| Торговые центры      | 1           | 1           | 1           | 1           | 1             |
| МФЦ                   | 0,011       | 0,020       | 0,013       | 0,015       | 0,023         |
| Аптеки                | 0,694       | 0,904       | 0,626       | 0,700       | 0,835         |
| Почтовые отделения    | 0,095       | 0,112       | 0,099       | 0,114       | 0,132         |
| Школы                 | 0,561       | 0,631       | 0,404       | 0,539       | 0,627         |
| Супермаркеты          | 0,203       | 0,278       | 0,220       | 0,240       | 0,399         |

# Анализ результатов

На основе проведенных расчетов, эталонным сценарием признан Scenario 3.2:

Размещение новой застройки в южной части Лодейного Поля согласно сценарию 3.2 представляет собой значимый шаг в улучшении качества городской среды. Этот сценарий способствует созданию нового локального центра, что, в свою очередь, положительно сказывается на доступности образовательных учреждений, таких как школы и детские сады, а также на обеспеченности торговыми площадями.
Улучшение показателей обеспеченности местами в школах и детских садах является одним из ключевых аспектов данного сценария. Это не только отвечает потребностям растущего населения, но и способствует созданию более комфортной и привлекательной городской среды для семей с детьми. Увеличение доступности торговых площадей также играет важную роль в формировании благоприятной экономической обстановки и повышении жизненного уровня жителей.
Снижение пространственного неравенства — еще один важный результат реализации сценария 3.2. Появление нового локального центра позволяет более равномерно распределить ресурсы и услуги по территории, что способствует улучшению общего качества жизни горожан. Это особенно актуально для Лодейного Поля, где исторически наблюдается концентрация услуг в определенных районах.
Кроме того, выбранный тип застройки соответствует концепции малоэтажной застройки, что обеспечивает гармоничное вписывание новых объектов в существующую городскую структуру и сохранение характерного облика города.
Таким образом, сценарий 3.2 выбран приоритетным, так как он не только отвечает современным требованиям к городской инфраструктуре, но и способствует устойчивому развитию Лодейного Поля как комфортного и привлекательного места для жизни.






