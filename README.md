# pynq-z2-illegal-instruction
okay,I gonna to say something that i've encountered.
I boughta FPGA (or maybe SoC whatever)  PYNQ_Z2.And I've got to say "yeah,It's great".But the processor and the description of cpu is not that fascinating and I didn't make it to use tensorflow on armv7l and the compatible whl file that i've used with the exactly name i needed is not useful.(Since i doubt that the cpu doesn't support AVX command.)And I'm still trying.   

Here is what i'm doing.Hope it will work for you with the same problem.

###############################
compile the exact version of tensorflow on your arm you needed
###############################

(nice networking)

(and all of the following is done on your own computer in ubuntu)

1.
  sudo apt-get install docker.io
  
  then
  
  sudo systemctl start docker
  
  sudo systemctl enable docker
  
  check whether it's done correctly.
  
  docker -v
  
  docker run --rm hello-world
  
  
2.
  git clone https://github.com/tensorflow/tensorflow.git
  
3.
  sudo CI_DOCKER_EXTRA_PARAMS="-e CI_BUILD_PYTHON=python3 -e CROSSTOOL_PYTHON_INCLUDE_PATH=/usr/include/python3.6" the_downloaded_folder_named_tensorflow/tensorflow/tools/ci_build/ci_build.sh PI-PYTHON3 the_downloaded_folder_named_tensorflow/tensorflow/tools/ci_build/pi/build_raspberry_pi.sh
  
4.
  waiting...
  
5.
  when everything is done smoothly,find the whl you build by yourself.
  
Good luck.
