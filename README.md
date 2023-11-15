# DEMO2024
|Имя устройства  |Интерфейс           |IPv4/IPv6       |Маска/Префикс   |Шлюз                  |                       
|  ------------- | -------------      | -------------  |  ------------- |  -------------       |                    
|ISP             |ens192              |10.12.24.10     |/24             |10.12.24.254          |      
|                |ens224              |192.168.0.162   |/30             |                      |
|                |ens256              |192.168.0.166   |/30             |                      |
|HQ-R            |ens192              |192.168.0.161   |/30             |192.168.0.162         |                                   
|                |ens224              |192.168.0.1     |/25             |                      |
|BR-R            |ens192              |192.168.0.165   |/30             |192.168.0.166         |                                  
|                |ens224              |192.168.0.129   |/27             |                      |
|HQ-SRV          |ens192              |192.168.0.126   |/25             |192.168.0.1           |                                   
|BR-SRV          |ens192              |192.168.0.158   |/27             |192.168.0.129         |                      

![image](https://github.com/Timurssa39/DEMO2024/assets/148869003/6adb776a-6e3c-4f4e-a433-1c9a1b77fdde)

# 1. Настройка интерфейсов
Посмотрел существующие интерфейсы с помощью команды 

``ip a``

Зашел в файл настройки интерфейсов ISP, с помощью команды

``nano /etc/network/interfaces``


Настроил IP на все интерфейсы исходя из таблицы адресации

# ISP

``auto ens192``

``iface ens192 inet static``

``address 10.12.24.10``

``netmask 255.255.255.0``

``gateway 10.12.24.254``


``auto ens224``

``iface ens224 inet static``

``address 192.168.0.162``

``netmask 255.255.255.252``


``auto ens256``

``iface ens256 inet static``

``address 192.168.0.166``

``netmask 255.255.255.252``


Сохранил конфигурацию комбинацией клавиш 

``ctrl+s``

Вышел из конфигурационно файлы комбинацией клавиш

``ctrl+x``

Перезагрузил сервис работы с сетью

``Systemctl restart networking.service``

# HQ-R

``auto ens192
iface ens192 inet static
address 192.168.0.161
netmask 255.255.255.252
gateway 192.168.0.162``

``auto ens224
iface ens224 inet static
address 192.168.0.1
netmask 255.255.255.128``

Сохранил конфигурацию комбинацией клавиш 

``ctrl+s``

Вышел из конфигурационно файлы комбинацией клавиш

``ctrl+x``

Перезагрузил сервис работы с сетью

``Systemctl restart networking.service``

# BR-R

``auto ens192
iface ens192 inet static
address 192.168.0.165
netmask 255.255.255.252
gateway 192.168.0.166``

``auto ens224
iface ens224 inet static
address 192.168.0.129
netmask 255.255.255.224``

Сохранил конфигурацию комбинацией клавиш 

``ctrl+s``

Вышел из конфигурационно файлы комбинацией клавиш

``ctrl+x``

Перезагрузил сервис работы с сетью

``Systemctl restart networking.service``

# HQ-SRV

``auto ens192
iface ens192 inet static
address 192.168.0.126
netmask 255.255.255.128
gateway 192.168.0.1``

Сохранил конфигурацию комбинацией клавиш 

``ctrl+s``

Вышел из конфигурационно файлы комбинацией клавиш

``ctrl+x``

Перезагрузил сервис работы с сетью

``Systemctl restart networking.service``












  
 

