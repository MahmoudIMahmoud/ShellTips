#How to kill a process that captures apecific port on windows?
1-Open windows cmd in admin mode.<br>
2-Type <br>
```Shell
  netstate -anbo | findstr <port-number>
 ```
3-Use the pid from the previous, then
  ```Shell
  taskkill /F /PID <PID><br>
  ```
  
  ##A sample:
  
  ```Shell
  netstate -anbo | findstr 444
  
  Out:
  TCP    0.0.0.0:4444           0.0.0.0:0              LISTENING       13872
  TCP    [::]:4444              [::]:0                 LISTENING       13872
  
  Then:
  taskkill /F /PID 13872
  
  Out:
  SUCCESS: The process with PID 13872 has been terminated.
  ```
