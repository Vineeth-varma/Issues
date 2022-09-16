## WSL DNS Stopping issue 
### For this issue you can see lot of failures from apt commands like update and upgrade 
**Workaround**
1. Create a file: /etc/wsl.conf.
2. Put the following lines in the file
  ```
  [network]
  generateResolvConf = false
  ```
3. In a powershell window, run wsl --shutdown
4. Restart WSL2  
    * Press ['windows' + r ] -> services.msc -> lxssManager -> rightclick -> restart
5. Create a file: /etc/resolv.conf. If it exists, replace existing one with this new file.
6. Put the following lines in the file
  ```
  nameserver 8.8.8.8
  ```
7. Repeat steps 3 and 4. You will see it working fine now.
