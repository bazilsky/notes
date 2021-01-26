# Remote access notes:

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

# yum update:

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

moo put bc047a.pm2014apr.pp :crum/u-ca123/apm.pp/bc047a.pm2014apr.pp

moo get moo:crum/u-bb283/apm.pp/bc047a.pm2014apr.pp .      # the full stop at the end extracts all files to the current directory 
```

# mark down image testing 

![alt text](https://github.com/bazilsky/no_sulphur_new/blob/master/images/dir_effect_nosulphur.png)
