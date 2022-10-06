# АНАЛИЗ ДАННЫХ И ИСКУССТВЕННЫЙ ИНТЕЛЛЕКТ [in GameDev]
Отчет по лабораторной работе #1 выполнил(а):
- Масленников Павел Алексеевич
Отметка о выполнении заданий (заполняется студентом):

| Задание | Выполнение | Баллы |
| ------ | ------ | ------ |
| Задание 1 | # | 60 |
| Задание 2 | # | 20 |
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
По теме видео практических работ 1-5 повторить реализацию игры на Unity. Привести описание выполненных действий.

## Задание 1
### Пошагово выполнить каждый пункт с описанием и примера реализации задач по теме видео самостоятельной работы.
Ход работы:
1)	


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
### В проект, выполненный в предыдущем задании, добавить систему проверки того, что SDK подключен (доступен в режиме онлайн и отвечает на запросы);

Ход работы:
При создании дочернего объекта он принимает координаты своего родителя. То есть, при его создании координаты будут иметь значения 0,0,0, относительно его родителя.
При прерывания связи с родительским объектом, бывший дочерний объект принимает координаты относительно точки отсчета координат игрового мира.



## Задание 3
### 1.	Произвести сравнительный анализ игровых сервисов Яндекс Игры и VK Game;
2.	Дать сравнительную характеристику сервисов, описать функционал;
3.	Описать их методы интеграции с Unity;
4.	Произвести сравнение, сделать выводы;
5.	Подготовить реферат по результатам выполнения пунктов 1-4 .




## Выводы



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

