## Visualizing wages and labor force patterns

### Installing and Building the project

First clone the repo and install dependencies
```shell
git clone https://github.com/UI-Research/RockefellerWages.git
cd RockefellerWages/
npm install
sudo npm install -g grunt-cli
sudo npm install -g bower
bower install
```

Change back to the project root directory...
```shell
cd ../ 
```

Get the current data from bacchus...
```shell
grunt get-data
```

`grunt` to start a watch server
```shell
grunt
```

### Minifying code and deploying to Bacchus

Once the code is in a state you feel is good for production, run the following command:
```shell
grunt deploy
```
This will minify all the javascript and css and copy over the code to bacchus (currently the folder `/bsouthga/rfdata/`). If you wish to change the deployment folder, edit the path at the top of `Gruntfile.js`.

### Updating the data

In order to be able to serve the large amount of data to the browser, the data must be compressed. Additioanlly, once the new data is encoded, a json file containing the list of acceptable industry codes must be generated. 

Once new raw data has been placed in `app/data/raw` run the task...
```shell
grunt update-data
```
This will compress the data into base 86 and generate the industry code json

To deploy the data to the server, run the following task...
```shell
grunt deploy-data
```
