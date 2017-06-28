# Class_ify_Audio
A Raspberry Pi based audio classification algorithm. Code forked from http://www.aicbt.com/raspberry-pi-sleep-monitor/ 


#make sure everything is up to date
sudo apt-get update
sudo apt-get upgrade
 
#get pip (for installing python libraries)
curl --silent --show-error --retry 5 https://bootstrap.pypa.io/get-pip.py | sudo python2.7
 
#install python libraries
sudo apt-get install python-numpy
sudo apt-get install python-scipy
sudo pip install tornado
 
#install pyaudio
sudo apt-get install libportaudio0 libportaudio2 libportaudiocpp0 portaudio19-dev
git clone http://people.csail.mit.edu/hubert/git/pyaudio.git
cd pyaudio
sudo python setup.py install
cd ..
 
#install the LittleSleeper code
git clone https://github.com/DrewWham/Class_ify_Audio.git

#Reboot Raspberry Pi
cd LittleSleeper
nohup python audio_server.py &
nohup python web_server.py &
