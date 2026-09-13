# Frontend-разработчик

# Рамазанова Гузаллия

## Контактная иноформация

|Страна|Город|email|GitHub|discord|
|------|-----|-----|------|-------|
|Россия|Екатеринбург|ramazanova_guzalliia@mail.ru|GuzalliiaR|ramazanova_guzalliia_49468|

## О себе
Привет! Меня зовут Гузаллия. Я — Frontend-разработчик с бэкграундом в инженерной сфере.

**Образование и прошлый опыт:**

* **Образование:** Окончила бакалавриат и магистратуру в Физико-технологическом институте УрФУ  по специальности «Электроника и наноэлектроника».

* **Опыт в инженерии:** Работала конструктором в АО «Эйрбург» и АО «Группа СВЭЛ». В процессе работы поняла, что у меня есть интерес к web-разработке. 

**Опыт разработки:** <br>
Последние 6 месяцев совмещала основную работу с инициативной разработкой внутреннего корпоративного сервиса для АО «Группа СВЭЛ». Я спроектировала и написала web-приложение, которое автоматизирует расчёт параметров электрооборудования по ТЗ заказчика (стек React, Vite, JavaScript).

## Навыки
* **Web-development:** `HTML5`, `CSS3`, `JavaScript (ES6+)`
* **Frameworks/Libraries:** `React`, `Redux Toolkit`
* **Methodologies:** `Feature-Sliced Design (FSD)`, `БЭМ`
* **Development tools:** `VS Code`, `Vite`
* **Version-control:** `GIT`, `GitHub`

## Примеры кода
Пример декларативного UI-компонента из проекта для **АО «Группа СВЭЛ»**. 

**Особенности реализации:** Бизнес-логика подбора оборудования полностью инкапсулирована в кастомные хуки, UI-компонент отвечает только за отображение и оптимизирован с помощью `React.memo`.
```
import { memo } from "react";
import { useSelector } from "react-redux";
import useSelectedReactorFSD from "../../lib/useSelectedReactorFSD";
import useSelectedCapacitorFCD from "../../lib/useSelectedCapacitorFCD";
import { selectInputtedValues } from '../../model/firstFormSlice';
import {
    selectParametersReactorFCD,
    selectParametersCapacitorFCD
} from '../../model/parametersSlice';
import { selectorInputtedValueCB } from '../../model/secondFormSlice';
import styles from './FieldsetSelectDeviceFCD.module.css';


const FieldsetSelectDeviceFCD = () => {

    const inputtedValues = useSelector(selectInputtedValues);
    const parametersReactorFCD = useSelector(selectParametersReactorFCD);
    const parametersCapacitorFCD = useSelector(selectParametersCapacitorFCD);
    const inputtedValueCapacitorBank = useSelector(selectorInputtedValueCB);

    const { selectedReactorTable } = useSelectedReactorFSD(inputtedValues, parametersReactorFCD);

    const { selectedCapacitorTable } = useSelectedCapacitorFCD(
        inputtedValues,
        inputtedValueCapacitorBank,
        parametersCapacitorFCD
    );

    return (
        <fieldset className={styles.fieldsetOfSelectedDevices}>
            <legend>
                <h3 className={styles.legend}>
                    Характеристики выбранного оборудования в ФКУ
                </h3>
            </legend>

            <div className={`${styles.containerInFieldset} ${styles.innerColumns}`}>
                <div className={styles.columnOfTable}>
                    <table className={`${styles.tableSelectedCapacitor} tableToExport_CapacitorBank`} >
                        <caption>
                            Выбранный конденсатор
                        </caption>
                        <thead>
                            <tr>
                                <th className="th_color-violet">Характеристика</th>
                                <th className="th_color-violet">Значение</th>
                            </tr>
                        </thead>
                        <tbody id="tableSelectedCapacitor">
                            {
                                selectedCapacitorTable.map((row) => (
                                    <tr key={row.id}>
                                        <td>{row.name}</td>
                                        <td>{ row.value }</td>
                                    </tr>
                                ))
                            }
                        </tbody>
                    </table>
                </div>

                <div className={styles.columnOfTable}>
                    <table className={`${styles.tableSelectedReactor} tableToExport_CurrentsFCD`}>
                        <caption>
                            Выбранный реактор
                        </caption>
                        <thead>
                            <tr>
                                <th className="th_color-violet">Характеристика</th>
                                <th className="th_color-violet">Значение</th>
                            </tr>
                        </thead>
                        <tbody id="tableSelectedReactor">
                            {
                                selectedReactorTable.map(row => (
                                    <tr key={row.id}>
                                        <td>{row.name}</td>
                                        <td>{row.value}</td>
                                    </tr>
                                ))
                            }
                        </tbody>
                    </table>
                </div>
            </div>
        </fieldset>
    )
};

export default memo(FieldsetSelectDeviceFCD);
```

## Проекты и опыт разработки

### 1. Web-приложение для расчета электрооборудования | АО «Группа СВЭЛ»
* **Описание:** Инженерный калькулятор для подбора фильтрокомпенсирующих устройств (ФКУ) или реактора для СТАТКОМ на основе пользовательского ввода.
* **Стек:** React, Redux Toolkit, Vite, FSD, CSS Modules.
* **Ссылки:** *находится в приватном доступе*

### 2. Todo-List
* **Описание:** Классический таск-менеджер для отработки базовых концепций реактивности и управления состоянием.
* **Стек:** React, Vite, JavaScript, CSS Modules.
* **Ссылки:** [Демо (GitHub Pages)](https://guzalliiar.github.io/Todo-List/)

### 3. FromBoard-Delivery
* **Описание:** Сервис доставки, разработанный для глубокой отработки отзывчивой верстки по исходному макету.
* **Стек:** HTML5, CSS3 (БЭМ), JavaScript.
* **Ссылки:** [Дизайн-макет в Figma](https://www.figma.com/design/lXrQSo0hqpH42GsL22vRd9/FromBoard-Delivery--For-Devs---Copy-?node-id=217-0&t=af0Y5eSmzRJSwQbt-1) | [Демо (GitHub Pages)](https://guzalliiar.github.io/FromBoard-Delivery/)

## Образование
* **Уральский федеральный университет (УрФУ)**, Екатеринбург
    * Физико-технологический институт | Электроника и наноэлектроника
    * Уровень образования: 
        * **Магистр** (выпуск 2022 г.)
        * **Бакалавр** (выпуск 2020 г.)

## Языки

**Английский** — уровень B1.
