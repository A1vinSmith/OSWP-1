## Exam Roadmap
```bash
ssh <username>@<target_ip> -p<port>                        ## connecting to the target system with SSH information provided by @offsec
iw dev wlan0 scan | grep SSID                              ## wireless networks within the range of the wireless card (wlan0) are detected
airmon-ng start wlan0                                      ## setting the wireless card (wlan0) to monitor mode
airodump-ng mon0                                           ## detecting surrounding networks by listening to the network in monitor mode
iwconfig mon0 channel 3                                    ## change the channel where the wireless network card is located
iwlist mon0 channel                                        ## view the channel where the wireless network card is located
airodump-ng -c 3 --bssid <AP_MAC> -w <capture_file> mon0   ## listening to the target AP on the specified channel
  ```                                                                            
       
 
----------------------------------------------------------------------------------------------------------------------------------------------------------------



## Opening more than one screen with the "screen" tool;
```bash
  # screen -S test        ## creating a workspace
  # screen -l              ## list actively used screens
  # screen -a -r 13245    ## switch to a specifically selected screen
  # CTRL + a + n          ## connects to the next session
  # CTRL + a + p          ## go back to the previous session
```

#### Open a New Screen Session
You start by opening a new screen session by typing `screen` in the terminal and hitting Enter. This will create a new screen session and switch you to it.

#### Detach from the Session
To detach from the current screen session (leaving it running in the background), press `Ctrl + A` followed by `Ctrl + D`.

#### List Running Sessions
You can list all the running screen sessions by typing `screen -ls`.

#### Resume a Session
To resume a particular session, type `screen -r <session_id>` where `<session_id>` is the identifier of the session you want to reconnect to.

#### Open Multiple Sessions
To open multiple sessions simultaneously, you can repeat steps 1-4. Each time you create a new session, it will be assigned a unique session ID.

#### Switch Between Sessions
While inside a screen session, you can switch between multiple sessions by pressing `Ctrl + A` followed by `" (double quote)`. This will display a list of active sessions, and you can select the one you want to switch to.

#### Close a Session
To close a screen session, ensure you're not inside that session (you can detach if needed), then type `exit` and press Enter. This will close the current session.



----------------------------------------------------------------------------------------------------------------------------------------------------------------



### Attack Map WEP ###


WEP

> WEP;

  AUTH: OPN? or SKA?

  > AUTH: OPN;

    Any client connected to AP? YES? or NO?

    > YES;

      # ARP Request Replay Attack
      # Interactive Packet Replay Attack
      # Deauthentication Attack (can be used in both cases (yes or no))
  
    > NO;

      # Fake Authentication Attack (can be used in both cases (yes or no))
      # Fragmentation Attack
      # Korek ChopChop Attack


  > AUTH: SKA (Bypassing WEP Shared Key Authentication);

    ## There is a client connected to the AP. You can follow the steps below to attack;

     # Deauthentication Attack
     # Fake Shared Key Authentication Attack
     # ARP Request Replay Attack
     # Deauthentication Attack
     # Aircrack-ng

### Attack Map WPA/WPA2 ###


#### Attack;

Deauthentication Attack
  
#### Cracking the network key;

* with Aircrack-ng
* with JTR and Aircrack-ng
* with coWPAtty
* with Pyrit



