# Commands to remember 

  https://www.environment.leeds.ac.uk/wiki/view/IT/LinuxRemote
  
```sh
sudo openconnect -u eeara --juniper vpn.leeds.ac.uk
```
  * connect using x2go

  * just connect via terminal 
```sh
ssh -A eeara@foe-linux-02.leeds.ac.uk
```
# arc systems and training:

  >http://arc.leeds.ac.uk/

# yum update: s

```sh
sudo yum update
```

# printing remotely 
 > lp -d myprint-staff -o ColorModel=Color -o KMDuplex=2Sided -o copies=1 FILENAME.pdf

# Tar based method to copy from monsoon 

## Transfer *from* institution to MONSooN:
```sh
$cd /path/to/localfiles

$tar cf - myfiles | ssh anran@lander.monsoon-metoffice.co.uk "ssh xcslc0 \" cd /path/to/destination/directory && tar xvf - \" "
```
~~/home/d04/anran/1850_emission_files/1850_greg~~

## Transfer *from* MONSooN to Institution:
```sh
$cd /path/to/destination
$ssh anran@lander.monsoon-metoffice.co.uk "ssh xcslc0 \" cd /path/to/source/directory && tar cf - myfiles \" " | tar xvf -

#An example Transfer from monsoon to institution

$ssh anran@lander.monsoon-metoffice.co.uk "ssh xcslc1 \" cd /home/d04/anran/cylc-run/u-bx512/share/data/History_Data && tar cf - *.pp \" " | tar xvf -
```

# convert model output to pp file
>/projects/um1/vn10.8/xc40/utilities/um-convpp ax337a.pm2013dec ax337a.pm2013dec.pp

~~/home/d04/anran/cylc-run/u-bb862/share/data/History_Data~~

~~ssh anran@lander.monsoon-metoffice.co.uk "ssh xcslc0 \" cd /home/d04/anran/cylc-run/u-bd918/share/data/History_Data && tar cf - *.pp \" " | tar xvf -~~

# MOOSE ACCESS
```sh
moo mkset -p --project-ukca --single-copy :/crum/u-ca123

moo put *.pp :crum/u-ca123/apm.pp/

moo get :/crum/u-ca123/apm.pp/*.pp .      # the full stop at the end extracts all files to the current directory 
```

# mark down image testing s

![alt text](images/indirect.png)

# vimrc for python indentation

Copy of following code block into your vimrc file and you're good to go. The `set mouse =a` command is only for enabling mouse click on vim. You can disregard that if you want. 


```sh
syntax enable 
set mouse=a
set tabstop=4
set shiftwidth=4
set expandtab
set softtabstop=4
syntax on
set number 
filetype indent on
set autoindent

```

# reading netcdf files using python
```python
from netCDF4 import Dataset
check1 = Dataset(files[0])
check2 = np.asarray(check1['model_data'])
```
# generating an ssh key pair 
```sh
ssh-keygen -t rsa -b 4096 -C "ARCHER access"
```

# open textedit 

```sh 
open -a TextEdit archer_rsa_jasmin.pub
````

# create a virtual environment 

```sh 
conda create --name env_name python=3.9

source activate env_name

```

