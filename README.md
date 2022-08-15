# A Gentle Introduction to Deep Learning with TensorFlow

## Michelle Fullwood
Slides in Reveal.js for the talk above, to be presented at PyCon 2017 in Portland, OR.

# Jupyter
Below are the *instructions* for running the **JupyterLab** notebook.

## Development
To deploy a simple *single user* environment (i.e. for *development*) simply
run the following *Docker* commands (**note**: this assumes you are already
in the `Deep-Learning-With-TensorFlow-PyCon2017` directory):
```
docker run -d \
           --rm \
           --name gidltf \
           -e JUPYTER_ENABLE_LAB=yes \
           -p 8888:8888 \
           -v $PWD/notebooks:/home/jovyan \
           jupyter/tensorflow-notebook:lab-3.4.5 && \
sleep 5 && \
docker logs gidltf 2>&1 | grep "http://127.0.0.1" | tail -n 1 | awk '{print $2}'
```
Click the link (should look similar to:
http://127.0.0.1:8888/lab?token=LONG_ALPHANUMERIC_STRING) which will
`automatically` log you in and allow you to start running the *notebooks*.
