# Графики из L5-1-Simple-Charts

## Упражнение: Исследование данных
Попробуйте нарисовать новые или повторить старые графики с использованием Altair!

В частности, попробуйте разные (по желанию) комбинации следующих свойств:

Marks: mark_point(), mark_line(), mark_bar(), mark_text(), mark_rect()...
Data Columns: 'Acceleration', 'Cylinders', 'Displacement', 'Horsepower', 'Miles_per_Gallon', 'Name', 'Origin', 'Weight_in_lbs', 'Year'
Encodings: x, y, color, shape, row, column, opacity, text, tooltip...

### График с mark_bar()
alt.Chart(cars).mark_bar().encode(
    x='Origin:N',
    y='mean(Horsepower):Q',
    color='Origin:N'
)
![image](https://github.com/user-attachments/assets/ab14d729-5a1e-484a-ad5a-38a6632fb92c)


### График с mark_line()
alt.Chart(cars).mark_line().encode(
    x='Year:T',
    y='mean(Miles_per_Gallon):Q',
    color='Origin:N'
)
![image](https://github.com/user-attachments/assets/295dd615-21ca-4f3c-9d27-c10c18797823)


### График с mark_point()
alt.Chart(cars).mark_point().encode(
    x='Horsepower:Q',
    y='Miles_per_Gallon:Q',
    color='Cylinders:O',
    tooltip='Name:N'
)
![image](https://github.com/user-attachments/assets/122f138f-72e9-4ccf-86c7-757f34d2e5c0)

### Вопросы:
какой тип данных лучше подойдёт для Miles_per_Gallon?
какой тип данных лучше подойдёт для Origin?
какой тип данных лучше подойдёт для Cylinders?

* Miles_per_Gallon: Количественный (Q), так как это число, подходящее для вычислений (среднее, сумма и т.д.).
* Origin: Номинальный (N), так как это категория (страна).
* Cylinders: Упорядоченный (O), так как значения (4, 6, 8) имеют естественный порядок. рядок.

## Упражнение: Добавление явных типов
Следующие графики получены с использованием набора данных cars. Для каждого попробуйте задать типы данных так, чтобы графики не изменились.

Если среди этих графиков есть те, которые будут выглядеть лучше с другими типами данных, нарисуйте их отдельно.

### Бар-график
alt.Chart(cars).mark_bar().encode(
    y='Origin:N',
    x='mean(Horsepower):Q'
)
![image](https://github.com/user-attachments/assets/e96f8cae-2a0f-4ad0-9db1-7f07ffcb5ec9)


### Линейный график
alt.Chart(cars).mark_line().encode(
    x='Year:T',
    y='mean(Miles_per_Gallon):Q',
    color='Origin:N'
)
![image](https://github.com/user-attachments/assets/a8e4bd6c-198d-40f4-8332-6988074284f8)


### Гистограмма цилиндров
alt.Chart(cars).mark_bar().encode(
    y='Cylinders:O',
    x='count():Q',
    color='Origin:N'
)
![image](https://github.com/user-attachments/assets/130f1014-0112-4b13-a000-1792ac0b89d6)


### Тепловая карта
alt.Chart(cars).mark_rect().encode(
    x='Cylinders:O',
    y='Origin:N',
    color='count():Q'
)
![image](https://github.com/user-attachments/assets/f06d941c-e1a7-496b-a0c1-5fe8d11ffeca)


### Добавьте график, который будет выглядеть лучше с другими типами данных
alt.Chart(cars).mark_bar().encode(
    y='Cylinders:O',
    x='mean(Acceleration):Q',
    color='Origin:N'
)
![image](https://github.com/user-attachments/assets/ef905563-ce97-410f-8eec-6170267b4ac5)


