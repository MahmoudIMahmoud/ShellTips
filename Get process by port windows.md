#How to kill a process that captures apecific port on windows?
1-Open windows cmd in admin mode.<br>
2-Type <br>
```sh
  netstate -anbo | findstr <port-number>
 ```
3-Use the pid from the previous, then
  ```sh
  taskkill /F /PID <PID><br>
  ```
  
  ##A sample:
  
  ```sh
  netstate -anbo | findstr 4444
  
  Out:
  TCP    0.0.0.0:4444           0.0.0.0:0              LISTENING       13872
  TCP    [::]:4444              [::]:0                 LISTENING       13872
  
  Then:
  taskkill /F /PID 13872
  
  Out:
  SUCCESS: The process with PID 13872 has been terminated.
  ```
