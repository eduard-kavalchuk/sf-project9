JFrog UI is available at [http://84.201.156.71:8082](http://84.201.156.71:8082). Setup of PyPi repository with Artifactory was done with the help of [this](https://jfrog.com/screencast/setting-up-pypi-repository-in-minutes-with-jfrog-artifactory/) video.  

To install a package from pypi to a local virtual environment use the following command:
```
pip install --trusted-host 84.201.156.71 <PACKAGE>
```
As a result the package will first be added to an Articactory repository and then installed to a local venv.  
Repository for publishing own packages is located [here](http://84.201.156.71:8082/ui/repos/tree/General/pypi-local). To deploy a python egg to Artifactory, run the following command:
```
python3 setup.py sdist upload -r local
```
To deploy a python wheel to Artifactory, run the following command:
```
python3 setup.py bdist_wheel upload -r local
```
where ```local``` is the index server defined in ```.pypirc```.

