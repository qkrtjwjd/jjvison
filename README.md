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
