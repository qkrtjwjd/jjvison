## Install DHT11 sensor

"
git clone https://github.com/adafruit/Adafruit_Python_DHT.git
cd Adafruit_Python_DHT.git
sudo python setup.py install
cd Adafruit_Python_DHT/examples

"
'run
"
python AdafruitDHT.py 11 4
"

### JAVA INstall

## 1.리포지토리의 GSP 키를 더하기
curl -sL https://repos.influxdate.com/influxdb.key | sudo apt-key add -

## 2. 리포지토리를 더하기
echo "deb http://repos.influxdate.com/dabian stretch stable "| sudo tee/etc/apt/sources.list.d/influxdb.list
## 3프로그램 설치
sudo apt install influxdb

## 4 프로그램의 실행
sudo service influxdv start
