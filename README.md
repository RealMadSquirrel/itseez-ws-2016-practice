# Оптимизация производительности

[![Build Status](https://travis-ci.com/UNN-VMK-Software/itseez-ws-2016-practice.svg?token=74q9ezwHWyMjEnVK8mzs&branch=master)][travis]
[![Gitter](https://badges.gitter.im/Join%20Chat.svg)][gitter]

Данный репозиторий представляет собой проект, на базе которого будут выполняться
практические упражнения из курса по __Оптимизации приложений компьютерного
зрения__ в рамках зимней школы 2016 года, совместно проводимой компанией Itseez
и ННГУ им. Лобачевского.

Проект реализует относительно простой алгоритм — скелетонизация символов. Данный
алгоритм включает в себя несколько базовых операций из области обработки
изображений: конвертация из одного цветового пространства в другое,
масштабирование изображения, морфологические операции и некоторые другие. Однако
несмотря на кажущуюся простоту операций, можно убедиться, что первоначальная
версия может работать несколько секунд, что крайне медленно. Поэтому в рамках
практических занятий реализация должна будет оптимизироваться с использованием
различных приёмов, позволяющих сократить время работы алгоритма.

## Структура репозитория

Проект реализован на языке С++ и имеет распространенную в настоящее время
структуру. Он содержит статическую библиотеку, реализующую основной алгоритм,
небольшое демо-приложение, и две сборки с автоматическими тестами (регресионные
и на производительность). Для построения проекта используется инструмент CMake,
тесты реализованы при помощи фреймворка Google Test, также для удобства
используется библиотека OpenCV, предоставляющая структуры данных и некоторые
полезные функции для работы с изображениями.

Далее, рассмотрим назначение каждой из директорий:

  - `3rdparty` — директория, содержащая сторонние коды, необходимые для
    реализации автоматических тестов. В целом её можно игнорировать.
  - `include`, `src` — директории, содержащие реализацию фильтра скелетонизации.
    Они компилируются в статическую библиотеку `skeleton_filter`.
  - `sample` — директория с консольным приложением, загружающим изображение и
    производящим его скелетонизацию.
  - `test`, `perf` — директории, содержащие реализации регрессионных тестов и
    тестов на производительность.
  - `testdata` — директория с тестовыми изображениями, которые можно подавать на
    вход демо-придожению.
  - `.gitignore` — служебный файл Git, перечисляющий файлы, которые следует
    игнорировать.
  - `.travis.yml` — конфигурационный файл для системы автоматического
     тестирования [Travis-CI][travis].
  - `CMakeLists.txt` — корневой файл для сборки проекта с помощью CMake.
  - `README.md` — информация о проекте, которую вы сейчас читаете.

## Практические задания

Описание практических заданий можно найти в следующих документах:

  1. [Инструменты разработки][practice1]
  1. [Профилирование и бенчмаркинг][practice2]
  1. [Оптимизация работы с памятью][practice3]
  1. [Компилятор и оптимизация][practice4]
  1. [Переход на целочисленную арифметику][practice5]
  1. [Использование векторных инструкций][practice6]

<!-- LINKS -->

[gitter]:    https://gitter.im/UNN-VMK-Software/mp2-lab1-set
[travis]:    https://travis-ci.com/UNN-VMK-Software/itseez-ws-2016-practice
[practice1]: https://github.com/UNN-VMK-Software/itseez-ws-2016-practice/blob/master/doc/practice1-development-tools.md
[practice2]: https://github.com/UNN-VMK-Software/itseez-ws-2016-practice/blob/master/doc/practice2-profiling-and-benchmarking.md
[practice3]: https://github.com/UNN-VMK-Software/itseez-ws-2016-practice/blob/master/doc/practice3-memory.md
[practice4]: https://github.com/UNN-VMK-Software/itseez-ws-2016-practice/blob/master/doc/practice4-compiler.md
[practice5]: https://github.com/UNN-VMK-Software/itseez-ws-2016-practice/blob/master/doc/practice5-fixed-point.md
[practice6]: https://github.com/UNN-VMK-Software/itseez-ws-2016-practice/blob/master/doc/practice6-simd.md
