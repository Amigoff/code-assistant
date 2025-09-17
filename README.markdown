# Инструкция по запуску симуляции в webots.
## Открываем 3 терминала
1. Запуск самой симуляции webots
```console
ros2 launch drone_webots sim_launch.py
```
2. Переходим в директорию ardupilot и запускаем файл SITL_launch
```concole
 cd ardupilot
./SITL_launch.sh
```
3. Запускаем rqt
```console
rqt & ros2 launch drone_launch components.launch.py
```
После этих шагов симуляция полностью запущена

## Билд проекта после изменений
Переходим в папку ros2_ws и собираем проект заново
```console
cd ros2_ws
MAKEFLAGS=-j5 colcon build --parallel-workers=2
```
Если хотите пересобрать отдельные пакеты
```console
MAKEFLAGS=-j5 colcon build --packages-select object_tracker drone_move --parallel-workers=2
```

## Изменение конфигурации управления 
```console
nano /opt/sky/config.yaml
```
## Запуск дрона и проведение тестового полета
### Зайти в webots и выбрать в таблице объектов предполагаемую цель (ЛКМ)
<img width="526" height="543" alt="image" src="https://github.com/user-attachments/assets/f4297b87-3c1a-4549-8e3b-7d2ef6960452" />

### С помощью появившихся координатных линий отдалить цель об Бражника на ~80-100 метров 
<img width="457" height="331" alt="image" src="https://github.com/user-attachments/assets/54e59ec2-285f-4aaa-9e9b-d2e2c51fe42e" />

### Переходим в окно qrt
Нужно перезагрузить список сервисов, чтобы отображался полный их список

<img width="171" height="64" alt="image" src="https://github.com/user-attachments/assets/f97c9651-8eb8-469a-880e-73a1989142aa" />

По умолчанию цель будет двигаться. Чтобы изменить её траекторию или остановить, нужно выбрать сервис /webots/switch_target_trajectory и активировать несколько раз кнопкой call

<img width="875" height="65" alt="image" src="https://github.com/user-attachments/assets/2d3fb147-55b0-4620-a444-e84c08387287" />

Для восстановления изначального положения цели используется сервис /webots/reset_target

Чтобы активировать выбор цели вручную, нужно в левом окне сервисов выбрать /drone/object_tracker/overlayed

Далее под ним в окне команды указать
```console
/drone/object_tracker/click
```
и нажать enter

<img width="805" height="139" alt="image" src="https://github.com/user-attachments/assets/16f7546c-707b-495a-81a0-692e89931134" />

далее можно нажатием ЛКМ выбирать цель для Бражника

### Открываем Qgroundcontrol 
Переходим в главное окно и, есали горит надпись disconnected, нажимаем на неё и выбираем SITL

<img width="1211" height="605" alt="image" src="https://github.com/user-attachments/assets/dd9a48bf-064e-467d-9854-db90623951c9" />

Чтобы взлететь нажимаем кнопку takeoff и проводим слайдером вправо

### Возвращаемся в окно rqt
После того как Бражник взлетел и цель выбрана, чтобы начать преследование цели нужно выбрать сервис /drone/move/start_interception и нажать call

<img width="883" height="74" alt="image" src="https://github.com/user-attachments/assets/7c3cbc78-012a-4656-b527-ab28c22eabc2" />

После этого начнет работать скрипт наведения и дрон полетит за целью. Текущие векторы ошибки полета выводятся в 3й терминал, где запущен rqt

