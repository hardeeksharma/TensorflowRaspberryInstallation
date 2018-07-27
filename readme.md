#  Raspberry Pi - Tensorflow Setup

#### Some prerequisite before actual tensorflow installtion.

First check default python version on the raspberry pi. There are sometime two version installed in the raspberry pi version 2.n and 3.5.n.

`python -V`

`python3 -V`

This will display the version 2.n.m and 3.n.m of default python.

Now check the default pip version for python 2.n

    pip -V
    pip3 -V

If output turns out not 18.n then you have to upgrade. To upgrade the pip version run the below command.

This command update the pip for python version 2.n.m

    sudo pip install --upgrade pip

This command update the pip for python version 3.n.m

    sudo pip3 install --upgrade pip

## Step to download and install python 3.6.3
    #make a folder on desktop
    mkdir python3.6
    cd python3.6
    
    wget https://www.python.org/ftp/python/3.6.3/Python-3.6.3.tar.xz
    tar -xvf Python-3.6.3.tgz
     cd Python-3.6.3
    ./configure #take 3-5 minutes
     make # take 5 minutes
    make install #take 5-10 minutes on Rpi

Now you have successfully installed python 3.6.3 on your raspberry pi. Now as we have 3 python versions installed on our pi. To run 3.6.3 specifically we run command.
####Successfully installed python 3.6.3
Check the installation by command

`python3.6 -V`

This will print the Python 3.6.3 on the console.
To work on version 3.6.3 specifically type `python3.6` this will open up 3.6.3 console.

------------

# Tensorflow installation steps

    sudo apt install libatlas-base-dev 
	# Prerequsite as per tensorflow docs
	[Tensorflow docs](https://www.tensorflow.org/install/install_raspbian "Tensorflow docs")
	#take 1-2 minutes
	 
	 sudo pip3.6 install tensorflow 
	 # take 10-15 minutes as per pi clock speed if overclocked 8-10 minutes
	 
	 sudo apt-get update
	 sudo apt-get upgrade
   

######To verify the installation run sample tensorflow code by making a python file

    vim tftest.py

Enter the following code in the python file

    # Python
    import tensorflow as tf
    hello = tf.constant('Hello, TensorFlow!')
    sess = tf.Session()
    print(sess.run(hello))
	

To run the sample code run following command on the terminal

    sudo python3.6 tftest.py
    
    #Output
    Hello, Tensorflow.
	

