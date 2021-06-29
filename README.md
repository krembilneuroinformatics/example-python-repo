Open this repo in jupyter [![Binder](http://mybinder.org/badge_logo.svg)](http://mybinder.org/v2/gh/krembilneuroinformatics/example-python-repo/HEAD)

# Example Python environment with a requirements.txt

This is modified for a demo in the KCNI School from an example template at: https://github.com/binder-examples/requirements

It is referenced in the KCNI-school-lessons repository

## To open this repo on binder 

Click on the badge at the top, or open the link below (same link)

(http://mybinder.org/v2/gh/krembilneuroinformatics/example-python-repo/HEAD)

## There are two files in this repo that make it binder compatible

- `requirements.txt` : tells binder what python packages to install ([see more below](#notes-about-requirementstxt))
- `runtime.txt` : tells binder what version of python to install ([see more below](#notes-about))

## The binder web address

Beyond that you need to need something to point your audience to the binder URL. There's a useful page at https://mybinder.org/ that helps you contruct your binder URL and badge to add to your `README.md`.

The binder URL encodes directions for binder for what github repo (and branch) to work from and what to display to the user.

For example: the usuall case (will open jupyter with the file browser pointing to the base of your repo)

```
http://mybinder.org/v2/gh/<github-user>/<github-repo>/<branch>
```
For this repo this is: http://mybinder.org/v2/gh/krembilneuroinformatics/example-python-repo/HEAD

But if you wanted the user to be pointed directly to one particular python notebook. You could point your users to:

```
http://mybinder.org/v2/gh/<github-user>/<github-repo>/<branch>?filepath=<filepath>
```

https://mybinder.org/v2/gh/krembilneuroinformatics/example-python-repo.git/HEAD?filepath=example_notebook.ipynb

Note: that even though users are pointed to one notebook in this case - the entire repo is still available for them to naviage to inside the binder instance.

## Notes about `requirements.txt`

The `requirements.txt` file should list all Python libraries that your notebooks
depend on, and they will be installed using:

```
pip install -r requirements.txt
```

The base Binder image contains no extra dependencies, so be as
explicit as possible in defining the packages that you need. This includes
specifying explicit versions wherever possible.

In this example we include the library `seaborn` which will be installed in
the environment, and our notebook uses it to plot a figure.

## Notes about 

## Fancier what to built requirements.txt

If you do specify strict versions, it is important to do so for *all*
your dependencies, not just direct dependencies.
Strictly specifying only some dependencies is a recipe for environments
breaking over time.

[pip-compile](https://github.com/jazzband/pip-tools/) is a handy
tool for combining loosely specified dependencies with a fully frozen environment.
You write a requirements.in with just the dependencies you need
and pip-compile will generate a requirements.txt with all the strict packages and versions that would come from installing that package right now.
That way, you only need to specify what you actually know you need,
but you also get a snapshot of your environment.
