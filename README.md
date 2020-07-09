## Install DHT11 sensor


git clone https://github.com/adafruit/Adafruit_Python_DHT.git
cd Adafruit_Python_DHT.git
sudo python setup.py install
cd Adafruit_Python_DHT/examples


run

python AdafruitDHT.py 11 4


### JAVA INstall


## 1.리포지토리의 GSP 키를 더하기

curl -sL https://repos.influxdate.com/influxdb.key | sudo apt-key add -

## 2. 리포지토리를 더하기

echo "deb http://repos.influxdate.com/dabian stretch stable "| sudo tee/etc/apt/sources.list.d/influxdb.list

## 3프로그램 설치

sudo apt install influxdb

## 4 프로그램의 실행

sudo service influxdv start

## 5. 데이터베이스 만들기


>create database <데이터베이스룸>

확인 : show databases

# Grafana Installation
## 1.Repository의 key를 더하기


curl https://bintray.com/user/downloadSubjectPublicKey?username=bintray | sudo apt-key add -


## 2.Repository를 더하기
echo "deb https://dl.bintray.com/fg2it/deb stretch main" | sudo tee -a/etc/apt/sources.list.d/grafana.list


## 3. 프로그램 설치


sudo apt update
sudo apt install grafana


## 4. 프로그램 실행


sudo service grafana-server start


## influxdb import with python



sudo pip install influxdb


## gpio pin map


cd/tmp

wget https://project-downloads.drogon.net/wiringpi-latest.deb
sudo dpkg -i wiringpi-latest.deb

## github use
 - Repository down load
git clone https://github.com/qkrtjwjd<user name>/jjvison<repository name>
 
##  vim설정하기
set nu(번호)
set cindent(c언어)
set ts=4(띄어쓰기를 4개 한것)
if has("syntax")(syntax on 색깔)
syntax on
endif
set bg=dark
set expandtab
let python_version_2 =1
let python_highlight_al1 =1
filetype indent plugin on

## 움직임 감지
 1 #!/user/bin/python
  2
  3 import time
  4 import RPI_GPIO as GPIO
  5
  6 print GPIO.VERSION
  7 GPIO.setmode(GPIO.BCM)
  8 GPIO.setup(4, GPIO_IN)
  9
 10 def interrupt_fired(channel):
 11     print("inerrupt Fired")
 12     print(channel)
 13
 14 GPIO.add_event_detect(4,GPIO.FALLING, callback=interrupt_fired)
 15
 16 while(True):
 17     time.sleep(1)
 18     print("timer fired")

cd jjvison
ls
cp/ home/pi/work
cp/ home/pi/work/pir.py .
ls
add .
git add .
git commit -m pirsoftware


 1 #!/user/bin/python
  2
  3 import time
  4 import RPi.GPIO as GPIO
  5 import requests, json
  6 from influxdb import InfluxDBClient as influxdb
  7
  8 GPIO.setmode(GPIO.BCM)
  9 GPIO.setup(4, GPIO.IN)
 10
 11 def interrupt_fired(channel):
 12     print("inerrupt Fired")
 13     a=5
 14     print(a)
 15
 16 GPIO.add_event_detect(4,GPIO.FALLING, callback=interrupt_fired)
 17
 18 while(True):
 19     time.sleep(1)
 20     a=1
 21     data = [{
 22         'measurement':'pir',
 23         'tags':{
 24             'VisionUni':'2410',
 25             },
 26         'fields':{
 27             'pir':a,
 28             }
 29         }]
 30     client = None
 31     try:
 32         client = influxdb('localhost',8086,'root','pir')
 33     except Exeption as e:
 34         print "Exception"+str(e)
 35         if client is not None:
 36             try:
 37                 client.write_points(data)
                                                
