# Setup

## Install

- [python2](https://www.python.org/download/releases/2.0/)
- [pip](https://pip.pypa.io/en/stable/installation/)
- virtualenv with `pip install virtualenv`

## Create a Virtual Environment

Run `virtualenv -p path/to/python2 env`.
This will create a virtual environment where -p is the `target interpreter for which to create a virtual (either absolute path or identifier string) (default: /usr/bin/python3)` and will be saved to the `env` folder.

Activate the virtualenv with `source env/bin/activate`.
The terminal should have `(env)` at the beginning. This indicates that the
virtual enviroment is active.

Install dependencies with `pip install -r requirements.txt`

Add `"image_dim_ordering": "th"`and `"backend": "theano"` in your `keras.json`.
This file should be in `~/.keras/` folder. This should look like:

```json
{
    ...,
    "image_dim_ordering": "th",
    "backend": "theano"
}
```

Create a folder `weights` then download available pretrained models listed on
README.md and save them in `weights`, the default is
[sam-resnet_salicon2017_weights.pkl](https://github.com/marcellacornia/sam/releases/download/1.0/sam-resnet_salicon2017_weights.pkl).
Make sure that line `109` is pointing to the correct `.pkl` file. Default should
look like:

```py
    m.load_weights('weights/sam-resnet_salicon2017_weights.pkl')
```

When done installing, the dev environment should be ready.
Try running the command in README.md `python main.py test path/to/images/folder/`. The output should be in the `predictions/` folder.

## Exit the Virtual Environment

When done working on the project, deactivate the virtual environment by running
`deactivate` on the terminal. To work on it again, just activate the virtual
environment and skip all other steps.
