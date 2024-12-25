# Введение

В рамках дисциплины «Анализ данных и моделирование в урбанистике» командой №9 – студентами 2 курса Института Дизайна и Урбанистики Университета ИТМО – были подготовлены три сценария развития проектной территории – бывшего военного аэродрома в Ленинградской области, – прилегающей к г. Лодейное поле.

Лодейное Поле — город в Ленинградской области, административный центр Лодейнопольского муниципального района и Лодейнопольского городского поселения. Находится примерно в 193 км и 2,5 часах езды на автомобиле от Санкт-Петербурга. Город стоит на Волго-Балтийском водном пути, рядом проходит автодорога Р21 «Кола» (Санкт-Петербург – Мурманск).

Стратегией социально-экономического развития Лодейнопольского муниципального района определена проектная инициатива «Комфортные поселения», которая реализуется на всей территории области: населенные пункты должны стать комфортными для проживания и доступными в качестве места работы, удовлетворяющими современные потребности жителей в удобном жилье, коммунальных, бытовых, финансовых, социальных услугах, услугах сферы торговли, культуры, спорта и досуга, экологии, связи.

Отвечая инициативе, положенной в СЭР, командой проекта предлагается неиспользуемый на данный момент военный аэродром отдать под жилую застройку, однако, ключевой вопрос в том – какого характера, чтобы это не только воспрепятствовало развитию Лодейного Поля но и частично сбалансировало его актуальные проблемы.

# Постановка цели:
Цель курсовой работы заключается в определении вектора развития проектной территории, расположенной в границах Лодейнопольского городского поселения, а также её влияния в перспективе на г. Лодейное Поле, к которому она прилегает. Достижение поставленной цели сопряжено с формированием трёх сценариев развития жилой застройки, апробация которых посредством применения методов анализа данных и моделирования позволит выявить оптимальный.

# Команда проекта:

1.	Кураксина Варвара (аробация гипотез, анализ результатов, формирование гипотез и выводов, оформление репозитория) 
2.	Губина Алина (подготовка данных, расчёт ТЭП, формирование гипотез и выводов)
3.	Липовская Дарья (подготовка данных, визуализация результатов, сбор презентации)
4.	Басова Маргарита (предпроектное исследование)
5.	Сорокин Константин (апробация гипотез, анализ результатов)

# Предпроектный анализ
## Scenario 0

Прежде чем начать формировать сценарии развития, требовалось понимание контекста ситуации и оценки г. Лодейного Поля предложенными библиотекой BlocksNet методами и метриками.

В рамках дисциплины «Цифровое моделирование урбанизированных территорий» были собраны и подготовлены геослои с дорогами, железными дорогами и зданиями (с проставленными атрибутами population, building:levels, is_living). Эти данные, в частности, легли в основу предпроектного анализа, который включил в себя следующие шаги.

1.	Отрисовку геометрии границ города Лодейное Поле с включением в них территории проектирования (бывший военный аэродром).
2.	Генерацию городских кварталов с помощью BlocksGenerator на основе имеющихся геослоев автомобильных и железных дорог.
3.	Получение графа улично-дорожной сети в границах территории с помощью библиотеки IduEdu.
4.	Произведение на основе графа расчёта матрицы доступности и матрицы связности. 
5.	Произведение расчета обеспеченности территории школами, детскими садами, торговыми центрами, аптеками, МФЦ, супермаркетами, барами, кафе, отделениями почтовой связи, булочными.
6.	Реализация методов и метрик по подсчету разнообразия сервисов, центральности (населения, сервисов), определению типа землепользования и морфотипа застройки (SpaceMatrix).
   
# Гипотезы развития
Ни для одного сценария **не были взяты за основу результаты применения инструмента rTeam** - платформы автоматизированного проектирования развития территории: команда осталась неудовлетворена сгенерированной квартальной сеткой, расположением домов, которые в большинстве случаев занимали целый квартал подобно жилому комплексу, распределением сервисов и неэффективным землепользованием, оставляющим значительные незаполненные пустыри.  В связи с этим, для каждого сценария развития были отрисованы улично-дорожная сеть, рассчитаны технико-экономические показатели (включая население), расставлены сервисы (как нормативно, так и ненормативно в зависимости от сценария) _вручную_. Произведены те же расчеты, что и для **Scenario 0**.

## Scenario 1. Малоэтажная застройка.
Первый сценарий развития предлагает акцентироваться на сохранении природной составляющей, реализовать рекреационный потенциал через формирование лесопарковой зоны. Жилые кварталы представлены ИЖЗ (1-2 этажа), которая дает возможность жить в собственном доме и/или иметь участок земли в индивидуальном пользовании. Застройка соразмерна прилегающей к территории проектирования южной части города. Сервисы определены нормативно.

**Сильные стороны сценария**:
1. _Рекреационные возможности_: создание лесопарковой зоны обеспечивает жителям условия для активного отдыха, спорта и времяпрепровождения на природе.
2. _Гармония застройки_: застройка, соответствующая местно сложившимся морфотипам, способствует созданию комфортной городской среды и снижает нагрузку на инфраструктуру.
   
**Слабые стороны сценария**: 
1.	_Нерешенная проблема необеспеченности сервисами_: прирост населения не увеличит значительно нагрузку на существующие сервисы, она распределится на новые, однако вопрос актуальной необеспеченности ключевыми сервисами не будет урегулирован.
2.	_Зависимость от личного автомобиля_: низкоплотная и разреженная территория, застроенная ИЖС, требует для лучшей мобильности наличие личного автомобиля, что, вероятно, увеличит автомобильный поток и создаст нежелательную нагрузку на транспортную инфраструктуру, в частности, спровоцировал пробки на выезде с проектной территории.
   
Ожидаемым результатом после реализации методов и метрик является достаточно низкий уровень обеспеченности населения ключевыми сервисами (школами, детскими садами, аптеками, почтовыми отделениями, супермаркетами): проектируемая численность населения – 1.2 тыс человек, соответственно, количество закладываемых в сценарий сервисов незначительно. В среднем, **результаты обеспеченности** для первого сценария предполагаются **не выше 0.5**. **Доступность (accessibility)** при обеспечении проектной территории УДС должна остаться в пределах **10-15 минут** от одного квартала ко многим и от многих кварталов к одному, **связность (connectivity)** новых кварталов с существующими - в диапазоне от 1.5 до 3. Предполагается, что Landuse Prediction определит территорию проектирования категорией **residential**, **SpaceMatrix** - **малоэтажной низкоплотной жилой застройкой**.

### Результаты Scenario 1.
- Сгенерированные кварталы на основе дорог и железных дорог.
- Дорожный граф.
- Матрица доступности и матрица связности.
- Обеспеченность населения (подготовленный слой с домами) сервисами: булочные, бары, кафе, детские сады, торговые центры, МФЦ, аптеки, почтовые отделения, школы, супермаркеты.
- Разнообразие сервисов.
- Центральность (сервисов, населения).
- Landuse Prediction.
- SpaceMatrix.

**Scenario 2. Среднеэтажная застройка.**
Приоритетом второго сценария является увеличение численности и плотности населения, обеспечение его большим количеством доступного жилья. Застройка главным образом средне- и многоэтажная, повторяющая характер северной части города. Сервисы определены нормативно.

**Сильные стороны сценария:**
1. _Увеличение доступного жилья:_ рост числа жилых объектов позволяет большему количеству людей найти жильё по приемлемым ценам, что улучшает социальные условия.
2. _Плотность застройки:_ средне- и многоэтажная застройка позволяет максимально эффективно использовать доступные земельные ресурсы, что может снизить давление на инфраструктуру в других районах.
   
**Слабые стороны сценария:**
1. _Перегрузка инфраструктуры:_ резкое увеличение плотности населения может привести к перегрузке существующих социальных и коммунальных служб.
2. _Снижение качества жизни:_ увеличение числа жителей может ухудшить условия проживания, например, повысив уровень шума и загрязнения.

В связи с высокой проектируемой численностью населения - 12,2 тыс. человек - предполагается несколько большее размещение сервисов, однако это не гарантирует достижение желаемого уровня обеспеченности. Самый густонаселенный сценарий имеет риск получить самые низкие показатели обеспечнности. В среднем, **результаты обеспеченности** для второго сценария предполагаются **не выше 0.4**. **Доступность (accessibility)** при обеспечении проектной территории УДС должна остаться в пределах **10-15 минут** от одного квартала ко многим и от многих кварталов к одному, **связность (connectivity)** новых кварталов с существующими - в диапазоне от 1.5 до 3. Предполагается, что Landuse Prediction определит территорию проектирования категорией **residential**, **SpaceMatrix** - **среднеэтажной жилой застройкой**.

### Результаты Scenario 2.
- Сгенерированные кварталы на основе дорог и железных дорог.
- Дорожный граф.
- Матрица доступности и матрица связности.
- Обеспеченность населения (подготовленный слой с домами) сервисами: булочные, бары, кафе, детские сады, торговые центры, МФЦ, аптеки, почтовые отделения, школы, супермаркеты.
- Разнообразие сервисов.
- Центральность (сервисов, населения).
- Landuse Prediction.
- SpaceMatrix.


### Scenario 3. Совмещение малоэтажной и среднеэтажной застройки.

Сбалансированный сценарий развития посредством формирования комфортных районов среднеэтажной жилой застройки + БЖД. Создание сомасштабных человеку пространств, интеграция зелёных структур в городскую среду. Сервисы определены **НЕнормативно**.

Интерес третьего сценария заключается в том, что изначально нормативно расставленные сервисы при средней спроектированной численнности населения в 7,9 тыс. человек вполне вероятно тоже не обеспечат территорию в полной мере ключевыми сервисами, в связи с чем для третьего сценария было сформировано две городских модели: с нормативно и ненормативно расставленными сервисами. За эталонную мы принимаем **версию 3.2**.

**Сильные стороны сценария:**

1. _Комфортные районы:_ формирование среднеэтажной жилой застройки способствует созданию удобных и доступных для жизни пространств, что повышает качество жизни жителей.
2. _Интеграция зелёных структур:_ включение зелёных зон в городскую среду способствует улучшению экологии, повышает уровень комфорта и способствует здоровому образу жизни.
3. _Гибкость в определении сервисов:_ ненормативное определение сервисов позволяет гибко адаптироваться к меняющимся запросам и потребностям сообщества.

Слабые стороны:
1. _Зависимость от финансирования:_ Реализация такого сценария часто требует значительных финансовых вложений как со стороны государства, так и частных инвесторов. В условиях экономической нестабильности это может стать серьезным ограничением
В свящи со средней численностью населения количество запланированных сервисов невелико, поэтому уровень обеспеченности также остается недостаточным. При добавлении сервисов, обеспеченность некоторыми сервисами улучшится

В качестве ожиданий допускается, что при соблюдении нормативов градостроительного проектирования количество сервисов будет соотвествовать численности населения (территория будет обеспечена сервисами). Районы малоэтажной застройки оказываются в зоне риска. При уточнении количества сервисов, обеспеченность улучшится. В среднем, **результаты обеспеченности** для третьего сценария предполагаются **выше 0.4**. **Доступность (accessibility)** при обеспечении проектной территории УДС должна остаться в пределах **10-15 минут** от одного квартала ко многим и от многих кварталов к одному, **связность (connectivity)** новых кварталов с существующими - в диапазоне от 1.5 до 3. Предполагается, что Landuse Prediction определит территорию проектирования категорией **residential**, **SpaceMatrix** - **среднеэтажной жилой застройкой**.

