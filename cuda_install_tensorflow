# cuda, cudnn, nvidia driver install for tensorflow usage

- main info link:
[link](https://gist.github.com/alexlee-gk/76a409f62a53883971a18a11af93241b)

- check compatibility:
  - [link](https://github.com/tensorflow/tensorflow/releases)
  - do upgrades if needed

- good links for newest upgrades:
  - [link](https://github.com/mind/wheels/releases/tag/tf1.4-gpu-cuda9)
  - pip install --ignore-installed --upgrade \ https://github.com/mind/wheels/releases/download/tf1.4-gpu-cuda9/tensorflow-1.4.0-cp35-cp35m-linux_x86_64.whl

## install process

0 - uninistall previous things!:
- all:
    - ```sudo apt-get remove --purge nvidia-*```
- just cuda:
    - ```sudo /usr/local/cuda-9.1/bin/uninstall_cuda_9.1.pl```


1 - check devices: ```lspci | egrep 'VGA|3D'```

2 - Install the NVIDIA drivers
- runfiles [link](http://www.nvidia.com/Download/driverResults.aspx/112992/en-us)
- before login :

        ctrl + alt + f1
        sudo ./NVIDIA-Linux-x86_64-375.26.run --dkms --no-opengl-files 
- if stuck in login! :

        ctrl+alt+f1
        sudo apt-get remove --purge nvidia-*
        sudo apt-get autoremove
        echo "nouveau" | sudo tee -a /etc/modules

3 - install cuda:
- ```sudo ./cuda_8.0.44_linux.run ```
- (if does not u should change its permissions) -> ```chmod ...```

4- add these to bashrc:

        export PATH=$PATH:/usr/local/cuda/bin
        export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/usr/local/cuda/lib64:/usr/local/lib:/usr/local/cuda/extras/CUPTI/lib64

5 - then execute
- ```source .bashrc```

6 - check:

- driver test: ```nvidia-smi```
- cuda test: ```nvcc --version```

5 - install cudnn
- Nvidia cudnn instalation tutorial [link](https://docs.nvidia.com/deeplearning/sdk/cudnn-install/index.html)

6 - check driver and cuda capability:

        cd /usr/local/cuda/samples/1_Utilities/deviceQuery
        sudo make
        ./deviceQuery

7 - whole thing:

        python3 >>> import tensorflow as tf
        python3 >>> ...


