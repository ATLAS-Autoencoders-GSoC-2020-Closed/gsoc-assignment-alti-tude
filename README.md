<h1 align="center">ATLAS Task Autoencoders</h1>

Compression of [data](https://github.com/alti-tude/atlas_task/tree/master/datasets) from 4-D to 3-D using autoencoders. 

## Running the project

Clone the repo and run Jupyter Notebook. Open `Atlas Task.ipynb`.

## Directory structure

* `Atlas Task.ipynb` contains the main code for training and running the model.
* `datasets/` contains the data in pickled format.
* `models/` contains the latest model that will be used.
* `runs/` is used for logging metrics to TensorBoard.
* `graphs/` containss all the output graphs created.

## Method

### Architecture

![Architecture](assets/Architecture%20diagram.png)

### Data

The data is 4 dimensional. The features are `m`, `pt`, `phi`, `eta`.

The minimum value of each of the train and validation data features is as follows. The minimum value of each column is colored.

<table>
<thead>
<tr>
  <th></th>
  <th>m</th>
  <th>pt</th>
  <th>phi</th>
  <th>eta</th>
</tr>
</thead>
<tbody>
<tr>
  <td>Minimum (Train)</td>
  <td bgcolor="green">-0.045353058725595474</td>
  <td>20000.154296875</td>
  <td bgcolor="green">-3.141587257385254</td>
  <td>-4.745397567749023</td>
</tr>
<tr>
  <td>Minimum (Validation)</td>
  <td>-0.04531514644622803</td>
  <td bgcolor="green">20000.07421875</td>
  <td>-3.1414923667907715</td>
  <td bgcolor="green">-4.78280782699585</td>
</tr>
</tbody>
</table>


The maximum value of each of the train and validation data features is as follows. The maximum value of each column is colored.

<table>
<thead>
<tr>
  <th></th>
  <th>m</th>
  <th>pt</th>
  <th>phi</th>
  <th>eta</th>
</tr>
</thead>
<tbody>
<tr>
  <td>Maximum (Train)</td>
  <td bgcolor="green">128247.671875</td>
  <td>748795.9375</td>
  <td bgcolor="green">3.1415462493896484</td>
  <td bgcolor="green">4.747644424438477</td>
</tr>
<tr>
  <td>Maximum (Validation)</td>
  <td>114533.4296875</td>
  <td bgcolor="green">786146.9375</td>
  <td>3.141526937484741</td>
  <td>4.6587443351745605</td>
</tr>
</tbody>
</table>


It is unpickled and loaded into a Pandas dataframe and normalization is done. The mean and standard deviation of the features of the train data is as follows:

<table>
<thead>
<tr>
  <th></th>
  <th>m</th>
  <th>pt</th>
  <th>phi</th>
  <th>eta</th>
</tr>
</thead>
<tbody>
<tr>
  <td>Mean (Train)</td>
  <td>8941.356798574077</td>
  <td>64458.68347131494</td>
  <td>0.0016911698064246217</td>
  <td>0.043500007558950136</td>
</tr>
<tr>
  <td>Standard Deviation (Train)</td>
  <td>7421.270110526609</td>
  <td>69874.99302638602</td>
  <td>1.8031508801540208</td>
  <td>1.4484389818869485</td>
</tr>
</tbody>
</table>

### Model

The initial parameters are as follows.

<table>
<thead>
<tr>
	<th>Parameter</th>
	<th>Value</th>
	<th>Variable name</th>
</tr>
</thead>
<tbody>
<tr>
	<td>Batch size</td>
	<td>200000</td>
	<td>BATCH_SIZE</td>
</tr>
<tr>
	<td>Epochs</td>
	<td>10000</td>
	<td>EPOCHS</td>
</tr>
<tr>
	<td>Learning rate</td>
	<td>0.001</td>
	<td>LR</td>
</tr>
<tr>
	<td>Scheduler patience</td>
	<td>100</td>
	<td>SCHEDULER_PATIENCE</td>
</tr>
<tr>
	<td>Activation function</td>
	<td>Hyperbolic Tangent</td>
	<td>MODEL_ACTIVATION_FUNC</td>
</tr>
</tbody>
</table>



### Loss

### Metric



