# Beginner's guide to Guanlab
Startup settings for new lab members
## Access your remote server for the first time
1. Before you begin, connect to umich VPN first. instructions can be found there: https://its.umich.edu/enterprise/wifi-networks/vpn/getting-started
2. Use ssh to connect to remote server from your laptop terminal
  
  ![figure](/images/image1.png)

* For [MacOS example](https://osxdaily.com/2017/04/28/howto-ssh-client-mac/)
* For [Windows example](https://my.kualo.com/knowledgebase/?kbcat=0&article=890)

Open your terminal, type in the following command:

```
ssh youruniquename@zeeb.dcmb.med.umich.edu
```
Or 
```
ssh youruniquename@zeeb.dcmb.med.umich.edu
```
The password is the same one as your wolverine account. 

2. Initial setup on the server:

After login, you’re in the home directory of remote server:
  
  ![figure](/images/image2.png)

* Install all your prerequisites here, such as [anaconda](https://docs.anaconda.com/anaconda/install/index.html).
* **Don’t put your projects under the home directory because the space is limited.**
3. Create local disks to store your project:
  
  ![figure](/images/image3.png)

Select any disk you’d like to create your own local disk. Before that, you may check the availability of space for each of them. 
  
  ![figure](/images/image4.png)

4. Create your own directory under one of them. Here I select `disk4` for example. Name your own disk by your unique name.
  
  ![figure](/images/image5.png)

5. And here it is!
  
  ![figure](/images/image6.png)

6. Also you can create a softlink in your home directory for easier access to your disk:

  ![figure](/images/image7.png)

7. And you can access your disk directly in your home directory:

  ![figure](/images/image8.png)

