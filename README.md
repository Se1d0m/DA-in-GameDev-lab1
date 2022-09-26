# АНАЛИЗ ДАННЫХ И ИСКУССТВЕННЫЙ ИНТЕЛЛЕКТ [in GameDev]
Отчет по лабораторной работе #1 выполнил(а):
- Масленников Павел Алексеевич
Отметка о выполнении заданий (заполняется студентом):

| Задание | Выполнение | Баллы |
| ------ | ------ | ------ |
| Задание 1 | * | 60 |
| Задание 2 | * | 20 |
| Задание 3 | # | 20 |

знак "*" - задание выполнено; знак "#" - задание не выполнено;

Работу проверили:
- к.т.н., доцент Денисов Д.В.
- к.э.н., доцент Панов М.А.
- ст. преп., Фадеев В.О.

[![N|Solid](https://cldup.com/dTxpPi9lDf.thumb.png)](https://nodesource.com/products/nsolid)

[![Build Status](https://travis-ci.org/joemccann/dillinger.svg?branch=master)](https://travis-ci.org/joemccann/dillinger)

Структура отчета

- Данные о работе: название работы, фио, группа, выполненные задания.
- Цель работы.
- Задание 1.
- Код реализации выполнения задания. Визуализация результатов выполнения (если применимо).
- Задание 2.
- Код реализации выполнения задания. Визуализация результатов выполнения (если применимо).
- Задание 3.
- Код реализации выполнения задания. Визуализация результатов выполнения (если применимо).
- Выводы.
- ✨Magic ✨

## Цель работы
Ознакомиться с основными функциями Unity и взаимодействием с объектами внутри редактора.

## Задание 1
### Пошагово выполнить каждый пункт с описанием и примера реализации задач по теме видео самостоятельной работы.
Ход работы:
1)	Создать новый проект из шаблона 3D – Core;
2)	Проверить, что настроена интеграция редактора Unity и Visual Studio Code (пункты 8-10 введения);
3)	Создать объект Plane;
4)	Создать объект Cube;
5)	Создать объект Sphere;
6)	Установить компонент Sphere Collider для объекта Sphere;
7)	Настроить Sphere Collider в роли триггера;
8)	Объект куб перекрасить в красный цвет;
9)	Добавить кубу симуляцию физики, при это куб не должен проваливаться под Plane;
10) Написать скрипт, который будет выводить в консоль сообщение о том, что объект Sphere столкнулся с объектом Cube;
11) При столкновении Cube должен менять свой цвет на зелёный, а при завершении столкновения обратно на красный.


```py

using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class CheckCollider : MonoBehaviour
{
    // Start is called before the first frame update
    void Start()
    {
        
    }

    // Update is called once per frame
    void Update()
    {
        
    }

    private void OnTriggerEnter(Collider other) {
        Debug.Log("Произошло столкновение с " + other.gameObject.name);
        other.GetComponent<Renderer>().material.SetColor("_Color", Color.green);
    }

    private void OnTriggerExit(Collider other) {
        Debug.Log("Завершено столкновение с " + other.gameObject.name);
        other.GetComponent<Renderer>().material.SetColor("_Color", Color.red);
    }
}


```


![1](https://user-images.githubusercontent.com/57959955/192260786-ebee1bcd-e26b-4d66-bdc5-6d1dc78018f4.PNG)



## Задание 2
### Продемонстрируйте на сцене в Unity следующее:
- Что произойдёт с координатами объекта, если он перестанет быть дочерним?
- Создайте три различных примера работы компонента RigidBody?

Ход работы:
При создании дочернего объекта он принимает координаты своего родителя. То есть, при его создании координаты будут иметь значения 0,0,0, относительно его родителя.
При прерывания связи с родительским объектом, бывший дочерний объект принимает координаты относительно точки отсчета координат игрового мира.

Первичные координаты относительно родителя (координаты Cylinder):
![2](https://user-images.githubusercontent.com/57959955/192287229-9699eff1-6677-451e-919c-f8b463bbaa66.PNG)

Координаты в случае смены положения относительно родительского объекта:
![3](https://user-images.githubusercontent.com/57959955/192287237-933e53af-2968-4003-a88f-0ea13d52eab6.PNG)

Координаты при разрыве связи с родительским элементом:
![4](https://user-images.githubusercontent.com/57959955/192287248-3766f0ad-28d3-4805-b71f-7c0592c82da8.PNG)



Пример 1:
1) Создать два объекта Plane и выстроить наклонную поверхность
2) Создать объект Cube
3) Создать объект Sphere
4) Добавить компоненты Rigidbody для двух Cube и Sphere
5) Включить гравитацию для компонентов
6) Компоненты скатываются по наклонной плоскоти при запуске сцены


https://user-images.githubusercontent.com/57959955/192265740-7569c76f-f480-450f-ac39-ea5e789ecaaf.mp4



Пример 2: 
1) Создать объект Sphere и Plane
2) К объекту Sphere добавить компонент Rigidbody
3) Поднять объект Sphere над Plane
4) Установть значение 6 в строке Drag
5) Включить гравитацию для объекта Sphere
6) Строка Drag отвечает за замедление движения объекта в пространстве. Чем больше значение тем больше будет замедлен объект.
7) При изменении этого значения меняется скорость падения объекта Sphere на Plane


Пример 3:
1) Создать объект Sphere и Plane
2) К объекту Sphere и Plane добавить компонент Rigidbody
3) Поднять объект Sphere над Plane
4) Установить гравитаю для Sphere и кинематику для Plane
5) При прикосновении с объектов Sphere и Plane - Sphere будет уничтожаться



https://user-images.githubusercontent.com/57959955/192293267-56d8ffd9-9667-475c-a169-8335da9993e8.mp4



```py

using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class DestroyObject : MonoBehaviour
{
    // Start is called before the first frame update
    void Start()
    {
        
    }

    // Update is called once per frame
    void Update()
    {
        
    }


    private void OnCollisionEnter(Collision other) {
        if (other.gameObject.name == "Sphere"){
    Destroy(other.gameObject);
        
    }
}

}

```

## Задание 3
### Реализуйте на сцене генерацию n кубиков. Число n вводится пользователем после старта сцены.



## Выводы

Абзац умных слов о том, что было сделано и что было узнано.

| Plugin | README |
| ------ | ------ |
| Dropbox | [plugins/dropbox/README.md][PlDb] |
| GitHub | [plugins/github/README.md][PlGh] |
| Google Drive | [plugins/googledrive/README.md][PlGd] |
| OneDrive | [plugins/onedrive/README.md][PlOd] |
| Medium | [plugins/medium/README.md][PlMe] |
| Google Analytics | [plugins/googleanalytics/README.md][PlGa] |

## Powered by

**BigDigital Team: Denisov | Fadeev | Panov**
