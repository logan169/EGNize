# EGNize
## EGN web server for Network analysis and visualisation

EGNize is a fullstack web application (Python2/AngularJS) based on an encapsulated modified version of
[EGN](https://bmcevolbiol.biomedcentral.com/articles/10.1186/1471-2148-13-146) (Perl). It allows users to create networks (based on gene and genome similarity) and visualize them through an
interactive visualization tool (SigmaJS).

As analysing some data could take some times (depending on dataset size), a mail server was implemented to keep user
informed of analysis status and send output files directly to user mail when done.
Output files produced by EGNize could then either be visualized directly using EGNize's interactive visualization tool or any
other network analysis software (Cytoscape or Gephi).

The visualisation tools are highly customizable to anyone that would like for example to associate keyboard/mouse inputs in order to display
any kind of metrics over a color gradient.

#### Actual available interaction are :
- Mouse wheel           => zoom in and zoom out
- Click and hold        => slide throught the network
- Right click on a node => display his gene/genomics similarity with neighbours nodes represented with a color gradient
- Left click on a node  => display only nodes that share a similarity with it
- Double click anywhere => reset to default display where node are colored according to the biological group they belongs

For more information about EGNize, please read appDescription.pdf or send a mail to <logan1691987@gmail.com>

#### Dependancies
- Python 2
- Flask
- Flask mail
- Blast (should be callable through terminal)

### Initialization

#### To launch the server (Back-end)
After installing dependencies, and editing mail account information in config.py, type the following commands from 'egn_server' folder:

        $ chmod +x launch_srvr.py
        $ ./launch_srvr.py

#### How to use it (Front-end)

Once the server is up, type in your browser's URL bar the URL displayed in the terminal after executing last command.
Per default, it should be <http://localhost:8084> but may change depending on your flask configuration.

##### Create a network

Once connected, click on 'new analysis' in the top right corner and fill up inputs form and upload your .faa input file.
Please refer to EGN documentation for input value.
- Don't forget to enter your mail adress to get back your zip archive (containing all outputs files) when analysis is done.
- Be aware that starting several runs (with different parameters) on the same input file will return a zip archive that also contains all previous outputs analysis for this input file.


##### Visualize a network

After receiving zip archive, reconnect to EGNize page, click on "load a network" button and upload a json or gexf file.
After clicking on ok, modal should close and visualization tool should display your network.
Report to the 'Actual available interaction' section above for possible interactions.


