# Beginner's guide to Guanlab
Startup settings for new lab members

## Servers
* Host **zeeb**
  - Hostname: zeeb.dcmb.med.umich.edu

* Host **liberty**
  - Hostname: liberty.dcmb.med.umich.edu

* Host **bartonshore**
  - Hostname: bartonshore.dcmb.med.umich.edu

* Host **whitmore**
  - Hostname: whitmore.dcmb.med.umich.edu

* Host **corrie**
  - Hostname: corrie.dcmb.med.umich.edu


For **zeeb** and **liberty**, each server has 24 GB X 8 GPU, 504 GB available RAM, 40 available cores, and 8 local disks.

For **bartonshore** and **whitmore**, each server has 46 GB X 4 GPU, 377 GB available RAM, 64 available cores, and 4 local disks. 

**corrie** is the latest server available since 2024/08, with 46 GB X 10 GPU, 566 GB available RAM, 128 available cores, and 8 local disks

Typically, a student is given access to **zeeb/bartonshore/corrie** group, or **liberty/whitmore** group. 

## File system

#### /home/[your uniquename]
This is the home folder of your account, you will also see a "~" in the terminal, like: `dengkw@bartonshore:~$  `

**DO NOT** save data or run program in this folder. Since the /home partition is relatively small and shared by all of the users, we highly recommend to only save the installation and config files, as well as the cache in this folder. If you need to setup the virtual environemnt, install them in your working directories

#### /local/disk*
These are the disks for running the lab projects. They're SSDs with relatively large spaces. You can save the data and run the codes for your current project.  
     
By typing `df -h /local/disk*`, you will see (use bartonshore as the example):  
![figure](/images/bartonshore_df_cmd.png)

#### /nfs/disk*
These are the disks for backups. They have the largest spaces and connected to all servers through the network. Backup your data/code/intermediate results in these disks.  
Please NOTE:
- There is **NO** automate backup in all disks. Thus, please backup your projects regularly to these disks
- **DO NOT** run programs in these disks as they are likely to be stuck.

## Access the lab remote server for the first time

0. Before you begin, always connect your personal computer to **umich VPN** so you don't need to worry about the network issue when you find the connection failed. Instructions for installation can be found here: https://its.umich.edu/enterprise/wifi-networks/vpn/getting-started

1. Open the terminal, and use the following command:

    ```bash
    ssh [youruniquename]@[Hostname]
    ```

    For example:
    
    ```bash
    ssh dengkw@zeeb.dcmb.med.umich.edu
    ```

    The password is the same as your Wolverine account.

    For Mac and Linux users, the terminal can be found directly in your applications.
    
    And for Windows users, there are two recommended solutions:
   * Install the Anaconda, and then you will have a Anaconda Powershell Prompt, which can directly use the `ssh` command like the other two systems.
   * Use Visual Studio Code. It has a convenient extension called "Remote - SSH" and you can connect to the server and manage the files interactively.

2. Initial setup on the server:

    After login, you’re in the home directory of the remote server:
  
    ![figure](/images/home_dir.png)

    Check the space availability as we have shown in previous section, and select any disk you'd like to create your own working folder. We recommend to use your unique name to name the folder.

    Step-by-step example:
    * (optional) check the space: `df -h /local/disk*`
    * Go to the select disk (e.g., disk1): `cd /local/disk1/`
    * Create a working folder: `mkdir <your_uniquename>` (e.g., `mkdir dengkw`)
    * Go to your folder and start working: `cd <your_uniquename>` 
    * (optional) we recommend to create separate folder for your projects like: `mkdir project1`

    ![figure](/images/create_work_dir.png)
  
3. (Optional) You can also create a softlink in your home directory for easier access to your disk:

    For example: `ln -s /local/disk1/dengkw disk1`

    ![figure](/images/softlink.png)


## Running environment management with Anaconda

1. You can find the latest installation file from this site: https://www.anaconda.com/download/success. Find the first link of Linux, right click it, and choose "Copy Link Address"
   
    ![figure](/images/anaconda_download_website.png)

2. Open the terminal and ssh to the server. In the home directory, type `wget` followed by the link you just copied. The link may look like:

    `wget https://repo.anaconda.com/archive/Anaconda3-XXX-Linux-x86_64.sh`

3. Run the installation file by: `bash bash Anaconda3-XXX-Linux-x86_64.sh`

4. Simply follow its instruction, choose the default value and answer "yes" except this one asking the location:

    ![figure](/images/anaconda_install.png)

    We recommend **NOT** to install it in the home directory. Use your working folder instead

5. After completing the installation, logout and re-login, you will see a `(base)` at the beginning of the command lines, like what we have shown in the previous figures. 
    * If you don't see it, try `conda activate`

## Use GPU

* To check the status of the GPUs, like if they are occupied by the other programs, you can use `nvidia-smi` or `gpustat` from `pip install gpustat`    
    
    Nvidia-smi
    ![figure](/images/nvidia-smi.png)
    gpustat
    ![figure](/images/gpustat.png)

* We use the deep learning frameworks Tensorflow (Keras) and PyTorch to build the AI models. After installing them, we need to test if they can access the GPUs.
  * PyTorch. In most of the time, we don't need worry too much about it. The dependencies will be installed automatically with PyTorch. To check if it can detect the GPUs, try this [answer](https://stackoverflow.com/questions/48152674/how-do-i-check-if-pytorch-is-using-the-gpu).
  
  * Tensorflow (Keras). Things can be messy with this framework. Before installation, you may need to check this [table of compatible settings](https://www.tensorflow.org/install/source#gpu), and download specific cuDNN and cudatoolkit. This two packages can be downloaded via conda, for example: 
      ```bash
      conda install cudatoolkit=10.0.130
      conda install cudnn=7.6.5=cuda10.0_0
      ```
      To test if the GPUs are accessible, use this [guidance](https://www.geeksforgeeks.org/how-to-check-if-tensorflow-is-using-gpu/?ref=oin_asr3)


## Self study materials

### VI
https://www.openvim.com/

### Machine learning study materials
https://github.com/GuanLab/Traditional-Machine-learning-self-study-syllabus

### Guan Lab winning algorithm code
https://www.synapse.org/#!Synapse:syn6180942/wiki/401735

### C++ tutorial
https://www.w3schools.com/cpp/default.asp

