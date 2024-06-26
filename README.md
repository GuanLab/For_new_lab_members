# Beginner's guide to Guanlab
Startup settings for new lab members

## Servers
* Host **zeeb**
  - Hostname: zeeb.dcmb.med.umich.edu

* Host **liberty**
  - Hostname: liberty.dcmb.med.umich.edu

* Host **bartonshore**
  - Hostname: 10.224.85.11

* Host **whitmore**
  - Hostname: 10.224.85.12


For **zeeb** and **liberty**, each server has 24GX8 GPU, 512 GB memory (128 cores), and 8 local disks.

For **bartonshore** and **whitmore**, each server has 12X4 GPU, 256 memory, and 4 local disks. 

Typically, a student is given access to **zeeb/bartonshore** pair, or **liberty/whitmore** pair. 

### The /home partition is extremely small, please only install programs here, definitely no data/computation here/

The /local/disk[1-8] are for your current projects, each is 4TB.
The /nfs/disk[1-12] are backup storages, connected to all servers. Each disk is 12TB.

### Please note there is absolutely no back up in all disks. Thus, please backup to backup storages. 

## Access the lab remote server for the first time
1. Before you begin, connect your personal computer to **umich VPN**. Instructions for installation can be found here: https://its.umich.edu/enterprise/wifi-networks/vpn/getting-started
2. 
3. Use ssh to connect to the remote server from your laptop terminal
  
  ![figure](/images/image1.png)

* For [MacOS example](https://osxdaily.com/2017/04/28/howto-ssh-client-mac/)
* For [Windows example](https://my.kualo.com/knowledgebase/?kbcat=0&article=890)

Open your terminal, use the following command:

```
ssh [youruniquename]@[Hostname]
```

for example:
```
ssh janedoe@zeeb.dcmb.med.umich.edu
```
The password is the same one as your Wolverine account. 


2. Initial setup on the server:

After login, you’re in the home directory of the remote server:
  
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


## Self study materials

### VI
https://www.openvim.com/

### Machine learning study materials
https://github.com/GuanLab/Traditional-Machine-learning-self-study-syllabus

### Guan Lab winning algorithm code
https://www.synapse.org/#!Synapse:syn6180942/wiki/401735

### C++ tutorial
https://www.w3schools.com/cpp/default.asp

