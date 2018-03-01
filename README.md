<h1 align="center" style="font-family: 'Oswald', sans-serif;color: #f3b144;font-size: 90px;margin: 10px 0;margin-top: 30px;line-height: 100%;text-shadow: 4px 4px #eeeeee;">CLEVER</h1>

<p align="center" style="font-family: 'Oswald', sans-serif;margin-bottom: 20px;text-shadow: 2px 2px #eeeeee;">EDUCATIONAL DRONE KIT FOR HIGH SCHOOL STUDENTS</p>
<p align="center">
	<img align="center" src="http://clever.copterexpress.com/clever.jpg" />
</p>
<p align="center" style="font-family: 'Oswald', sans-serif;" align="center">
	<a style="margin-right: 40px;color: #548dbe;" href="CLEVER%20Assembly%20Manual%20v1.0.pdf">Assembly Manual</a>
	<a style="margin-right: 40px;color: #548dbe;" href="OpenPilot-RELEASE-15.02.02-win32.exe">OpenPilot GCS v15.02</a>
</p>

<link rel="stylesheet" type="text/css" href="http://clever.copterexpress.com/main.css">
<link href="https://fonts.googleapis.com/css?family=Oswald" rel="stylesheet">

style="text-align: center;font-family: 'Oswald', sans-serif;"
style="text-align: center;font-family: 'Oswald', sans-serif;color: #f3b144;font-size: 90px;margin: 10px 0;margin-top: 30px;line-height: 100%;text-shadow: 4px 4px #eeeeee;"
style="text-align: center;font-family: 'Oswald', sans-serif;margin-bottom: 20px;text-shadow: 2px 2px #eeeeee;"

Клевер
======

<img src="assets/clever.jpg" align="right" width="300px" alt="Клевер">

«Клевер» — это учебный конструктор программируемого квадрокоптера, состоящего из популярных открытых компонентов, а также набор необходимой документации и библиотек для работы с ним.

Набор включает в себя полетный контроллер PixHawk/PixRacer с полетным стеком PX4, Raspberry Pi 3 в качестве управлящего бортового компьютера, модуль камеры для реализации полетов с использованием компьютерного зрения, а также набор различных датчиков и другой периферии.

На базе точно такой же платформы были созданы многие «большие» проекты компании Copter Express, например, дроны для [пиар-акций по автономной доставке пиццы](https://www.youtube.com/watch?v=hmkAoZOtF58) (Самара, Казань); дрон-доставщик кофе в Сколково, мониторинговый дрон с зарядной станцией, дроны-победители на полевых испытаниях «[Робокросс-2016](https://www.youtube.com/watch?v=dGbDaz_VmYU)», «[Робокросс-2017](https://youtu.be/AQnd2CRczbQ)» и многие другие.

Для того, чтобы научиться собирать, настраивать, пилотировать и программировать автономный дрон «Клевер», воспользуйтесь этим учебником.

Основная документация
---------------------

https://copterexpress.gitbooks.io/clever/content/

**Готовый образ ОС** для RPi 3 с предустановленным и преднастроенным ПО можно скачать [здесь](https://copterexpress.gitbooks.io/clever/content/docs/microsd_images.html).

[Описание API](https://copterexpress.gitbooks.io/clever/content/docs/simple_offboard.html) для автономных полетов.

Ручная установка
---------

Склонировать репозиторий в папку `/home/pi/catkin_ws/src/clever` (**важно**):

```bash
cd ~/catkin_ws/src
git clone https://github.com/CopterExpress/clever_bundle.git clever
```

Пересобрать ROS-пакеты:

```bash
cd ~/catkin_ws
catkin_make -j1
```

Включить сервис roscore (если он не включен):

```bash
sudo systemctl enable /home/pi/catkin_ws/src/clever/deploy/roscore.service
sudo systemctl start roscore
```

Включить сервис clever:

```bash
sudo systemctl enable /home/pi/catkin_ws/src/clever/deploy/clever.service
sudo systemctl start clever
```

Зависимости
-----------

[ROS Kinetic](http://wiki.ros.org/kinetic).

Необходимые для работы ROS-пакеты:

* `opencv3`
* `mavros`
* `rosbridge_suite`
* `web_video_server`
* `cv_camera`
* `nodelet`
* `dynamic_reconfigure`
* `bondcpp`, ветка `master`
* `roslint`
* `rosserial`

TODO: внести в package.xml
