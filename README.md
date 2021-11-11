
# Apache TVM v0.8dev for Google Colab

This is a zip of Apache TVM v0.8dev built for Google Colab. You can use it in your colab notebook by running


```
# from https://colab.research.google.com/github/uwsampl/tutorial/blob/master/notebook/02_TVM_Tutorial_Relay.ipynb#scrollTo=bdiA6WVx0Nuc
try:
  import google.colab
  IN_COLAB = True
except:
  IN_COLAB = False

if IN_COLAB:
    # Installing Dependencies
    ! echo "deb https://dl.bintray.com/sbt/debian /" | sudo tee -a /etc/apt/sources.list.d/sbt.list
    ! sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 2EE0EA64E40A89B84B2DF73499E82A75642AC823
    ! sudo apt-get update
    ! sudo apt-get install -y -q llvm-6.0 libtinfo-dev libffi-dev zlib1g-dev clinfo tree
    ! pip install intel-openmp mkl-static
    ! wget -O /tmp/tvm.zip https://github.com/sebinthomas/TVM_colab/raw/master/build/apache_tvm_colab_v1.zip
    ! mkdir -p /tvm
    ! unzip "/tmp/tvm.zip" -d /tmp/ && cp -r /tmp/apache_tvm_colab/* /tvm
    ! ls -la /tvm
    ! pip install onnx
    ! sudo apt install clang-format
    # Add TVM to the Python path.
    import sys
    import os
    sys.path.append('/tvm/python')
    sys.path.append('/tvm/topi/python')
    sys.path.append('/tvm/vta/python')
    os.environ['TVM_HOME'] = '/tvm'
else:
    print("Notebook executing locally, skipping Colab setup ...")
```

Notebook to compile, coming soon.