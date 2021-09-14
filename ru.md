# Мигаем светодиодами

```package
core
radio
microphone
```
```template
basic.forever(function () {
	
})
```

## Step 0 @showDialog
Привет! Сегодня мы узнаем, как мигать подключенными к Micro:bit светодиодами!
## Step 1 @showDialog
Перед тем, как начать, проверьте, что светодиоды подключены к Micro:bit так же, как на схеме:
![](https://raw.githubusercontent.com/CraftAndCode/mood-badge/master/mood%20badge%20schematic.gif)


## Step 2 @showHint
### Зажигаем светодиод
Для начала, найдём блок кода ``||pins.цифровой: записать контакт||`` и поместим его внутрь блока ``||basic.постоянно||``.
```hint
Этот блок выглядит вот так:
```
```block
pins.digitalWritePin(DigitalPin.P0, 0)
```
## Step 3 @showDialog
На Micro:bit есть 25 металлических контактов для подключения внешних устройств.
  
Пять из них соединены с отверстиями в плате: 0, 1, 2, 3V, and GND. Блок ``||pins.цифровой: записать контакт||`` может включать и выключать светодиоды, соединённые с этими отверстиями.

## Step 4 @showHint
### Зажигаем светодиод
Давайте зажжём зелёный светодиод! Поменяйте цифру в блоке ``||pins.цифровой: записать контакт||`` с 0 на 1. Цифра 1 означает, что выбранный контакт теперь включен.

```blocks
basic.forever(function () {
    pins.digitalWritePin(DigitalPin.P0, 1)
})
```

## Step 5 @showHint
### Зажигаем светодиод
Симулятор не знает о том, что к Micro:bit подключены светодиоды. Чтобы проверить работу нашей программы, нам нужно скачать её в Micro:bit. Давайте сделаем это!
```hint
В окне симулятора контакт 0 подсвечен оранжевым.
Это означает, что он включён.
```
![](https://raw.githubusercontent.com/CraftAndCode/mood-badge/master/LED0.png)

## Step 6 @showHint
### Мигаем светодиодом
А теперь, заставим светодиод мигать! Соберите по образцу программу, которая будет поочерёдно включать и выключать светодиод, а затем загрузите её в Micro:bit.
```blocks
basic.forever(function () {
    pins.digitalWritePin(DigitalPin.P0, 1)
    basic.pause(500)
    pins.digitalWritePin(DigitalPin.P0, 0)
    basic.pause(500)
})
```
## Step 7
### Задание:
Дополните написанную программу так, чтобы одновременно мигали два светодиода.
```hint
Последовательность команд: 
```
* Включить контакт 0,
* Включить контакт 1,
* Подождать,
* Выключить контакт 0,
* Выключить контакт 1,
* Подождать.

## Step 8
### Сделай сам!
Используя команды, о которых мы сегодня узнали, запрограммируйте светофор. Пусть светофор переключается с зелёного на красный и обратно с помощью двух кнопок.

## Answers @showDialog

### Ответ: Задание
```blocks
basic.forever(function () {
    pins.digitalWritePin(DigitalPin.P0, 1)
    pins.digitalWritePin(DigitalPin.P1, 1)
    basic.pause(500)
    pins.digitalWritePin(DigitalPin.P0, 0)
    pins.digitalWritePin(DigitalPin.P1, 0)
    basic.pause(500)
})
```

### Ответ: Сделай сам!
Программа может выглядеть так:
```blocks
pins.digitalWritePin(DigitalPin.P1, 1)
input.onButtonPressed(Button.A, function () {
    pins.digitalWritePin(DigitalPin.P1, 0)
    pins.digitalWritePin(DigitalPin.P0, 1)
})
input.onButtonPressed(Button.B, function () {
    pins.digitalWritePin(DigitalPin.P0, 0)
    pins.digitalWritePin(DigitalPin.P1, 1)
})
```

