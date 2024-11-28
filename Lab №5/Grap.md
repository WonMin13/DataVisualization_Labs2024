# Графики из L5-1-Simple-Charts

## Упражнение: Исследование данных
Попробуйте нарисовать новые или повторить старые графики с использованием Altair!

В частности, попробуйте разные (по желанию) комбинации следующих свойств:

Marks: mark_point(), mark_line(), mark_bar(), mark_text(), mark_rect()...
Data Columns: 'Acceleration', 'Cylinders', 'Displacement', 'Horsepower', 'Miles_per_Gallon', 'Name', 'Origin', 'Weight_in_lbs', 'Year'
Encodings: x, y, color, shape, row, column, opacity, text, tooltip...

### График с mark_bar()
![image](https://github.com/user-attachments/assets/6d0fab82-e94a-4bd6-ba23-94b2bf6b3c3d)

![image](https://github.com/user-attachments/assets/ab14d729-5a1e-484a-ad5a-38a6632fb92c)


### График с mark_line()
![image](https://github.com/user-attachments/assets/561ed5d9-c353-4bf6-abea-1b88248b7731)

![image](https://github.com/user-attachments/assets/295dd615-21ca-4f3c-9d27-c10c18797823)


### График с mark_point()
![image](https://github.com/user-attachments/assets/09132f0b-3850-4cd2-b785-f66490e7b734)

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
![image](https://github.com/user-attachments/assets/ad0a7eed-597b-46c9-94b2-9759dac1aa13)

![image](https://github.com/user-attachments/assets/e96f8cae-2a0f-4ad0-9db1-7f07ffcb5ec9)


### Линейный график
![image](https://github.com/user-attachments/assets/2d599dfb-3c15-4375-8e3d-1b0082e1de2d)

![image](https://github.com/user-attachments/assets/a8e4bd6c-198d-40f4-8332-6988074284f8)


### Гистограмма цилиндров
![image](https://github.com/user-attachments/assets/46acae20-d6fb-4020-8d96-6683bdf69ffb)

![image](https://github.com/user-attachments/assets/130f1014-0112-4b13-a000-1792ac0b89d6)


### Тепловая карта
![image](https://github.com/user-attachments/assets/26fc1f45-efbf-4004-ac1f-f20709986f36)

![image](https://github.com/user-attachments/assets/f06d941c-e1a7-496b-a0c1-5fe8d11ffeca)


### Добавьте график, который будет выглядеть лучше с другими типами данных
![image](https://github.com/user-attachments/assets/49b515b6-1c68-4196-a274-a248bac6ed46)

![image](https://github.com/user-attachments/assets/ef905563-ce97-410f-8eec-6170267b4ac5)

---------------------------------------------------------------------------------------------

# Графики из L5-5-Selections

## Упражения: выбор
1) Используя данные cars, создайте диаграмму рассеяния, где размер точек становится больше при наведении.

2) Используя данные cars, создайте двухпанельный график с гистограммами (например, миль на галлон на одной панели, мощность (horsepower) – на другой), в котором выделение данных на одной гистограмме фильтрует данные на второй.

### Диаграмма рассеяния с изменением размера точек при наведении:
![image](https://github.com/user-attachments/assets/8e10bff5-0668-4eb9-90ec-1950fe3db4d2)

![image](https://github.com/user-attachments/assets/cfb539ab-1675-45a6-b094-68798567bca5)

hover = alt.selection_single(on='mouseover', nearest=True) - Создаёт интерактивный объект, реагирующий на наведение курсора (mouseover) и выделяющий ближайшую точку (nearest=True).

size=alt.condition(hover, alt.value(200), alt.value(50)) - Увеличивает размер точки до 200 при наведении и уменьшает до 50, если точка не выбрана.

### Двухпанельный график с фильтрацией:
![image](https://github.com/user-attachments/assets/75b66f53-9382-4df5-9d88-4c8249ac7ce2)

![image](https://github.com/user-attachments/assets/e364850b-5a53-408a-a266-4d31aa7fdac8)

interval = alt.selection_interval() - Добавляет возможность выделять диапазон (например, на одной панели)

.transform_filter(inte - al)

Фильтрует данные на второй панели, отображая только выделенные на первой панели.


# Графики из L5-6-Transformations

## Упражение
![image](https://github.com/user-attachments/assets/c888567a-fb30-440f-a594-30e40f5ea7ec)

Создать график, основанные на этих данных и сформировать график синуса и косинуса с помощью функции Altair transform_calculate.
Использовать transform_filter на этом графике, и удалить области графика, где значение косинуса меньше значения синуса.

### График синуса и косинуса:
![image](https://github.com/user-attachments/assets/bb295e71-5864-4667-8575-051139072df6)


transform_calculate( sin='sin(datum.x)', cos='cos(datum.x)' ) - Вычисляет значения синуса (sin) и косинуса (cos) для каждого x с помощью выражения Als меньше sin.

### Фильтрация областей:
![image](https://github.com/user-attachments/assets/42c72e88-1bf2-4fa4-9d41-dfe53a63618e)

![image](https://github.com/user-attachments/assets/706bc7f7-9bf1-4429-86b8-712bbfdb051b)

transform_filter( 'datum.cos >= datum.sin' ) - Фильтрует данные, исключая те области, где cos меньше sin.
