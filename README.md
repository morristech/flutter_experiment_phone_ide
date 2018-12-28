# flutter_experiment_phone_ide

## Set up

Has only been tested on Windows + Android (other platforms should work with little code adjustments)

The PC and the device must be in the same private network.

No root, what so ever required.

*Estimated set up time: 8 minutes*

#### 1. Download Dart (Flutter has dart, but it is not a full version of it)
```
https://www.dartlang.org/tools/sdk#install
```
#### 2. Make sure dart is in your path. Type `dart` into the command line and see if it is there. 

If it is not, put it into the path (https://docs.alfresco.com/4.2/tasks/fot-addpath.html)

#### 3. Clone this repositry 
```git
git clone https://github.com/Norbert515/flutter_experiment_phone_ide.git
```
#### 4. Include the code into your Flutter project
Copy the "ide" folder under "https://github.com/Norbert515/flutter_experiment_phone_ide/tree/master/flutter_experiment_phone_ide/lib" into your project

#### 5. Add dependecies
Add these three dependencies into your pubspec.yaml and run `packages get`
```
  rpc: ^0.6.0
  http: ^0.11.0
  path: ^1.6.2
```

#### 5. Navigate to the server
```
flutter_experiment_phone_ide/flutter_experiment_phone_ide_server/bin/
```

#### 6. Open the command line here (or navigate to this place)


#### 7. Get the deviceId of the device you want to run it on

Emulator/ Desktop embedder/ connected phone :
Run 
```
flutter devices
```
or 
```
adb devices
```
to get a list of possible targets.

Wireless phones :
It still goes through adb, but wirelessly. Here is a very quick set up for that https://futurestud.io/tutorials/how-to-debug-your-android-app-over-wifi-without-root

#### 8. Start the server
It takes 2 arguments
```
--projectPath=<path_to_the_project_you_want_to_develop_on_your_phone>
--deviceId=<adb_device_id_to_run_this_on>
```
This is how it could look like:
```
dart server.dart --projectPath="C:\Users\Norbert\workspace\flutter_experiment_phone_ide\flutter_experiment_phone_ide" --deviceId="172.23.218.234:5555"
```

#### 9. Open the link which the server prints out to the console on your phone.
The link is: 
```
<server_local_ip>:<port>/test/v1/coldStart
```

#### 10. VPN (Not tested) 
if you want to develop apps anywhere you go, you will have to set up a VPN to connect the phone and the PC.
