# IntDT: A Large-scale Roadside Dual-Lidar Dataset


This is the official implementation of the IntDT dataset, a large-scale roadside dual-lidar dataset.

## Overview
- [Data Download](#Data-Download)
- [Benchmark](#Benchmark)
  - [3D Object Detection](#3D-Object-Detection)
  - [3D Object Tracking](#3D-Object-Tracking)
- [Acknowledgment](#Acknowledgment)

## Data Download
Our dataset is freely available to researchers. Please download and sign our [agreement](https://docs.google.com/document/d/14ufBczTjLYnxm5bWkFROsz9FYEugZ2QL/edit?usp=sharing&ouid=110390481963822269546&rtpof=true&sd=true) and send it to the provided email address (wen.xiao@cug.edu.cn). You will receive the download link within one week.
After downloading the data, please put the data in the following structure:
```shell
├── IntDT-S-dataset
│   ├── 0011
|      |── label
|      |── lidar
|      |── metadata.json
│   ├── 0012
│   ├── 0021
│   ├── 0022
│   ├── ...
├── IntDT-D-dataset
│   ├── 001
|      |── Lidar1
|         |── label
|         |── lidar
|         |── metadata.json
|      |── Lidar2
|         |── label
|         |── lidar
|         |── metadata.json
|      |── metadata.json
│   ├── 002
│   ├── 003
│   ├── ...
```


## Benchmark

### 3D Object Detection

#### Results of detection models on the IntDT-D validation set.
<table>
  <tr>
    <th rowspan="2">Method</th>
    <th colspan="4">Vehicle (AP@50)(%)</th>
    <th colspan="4">Pedestrian (AP@50)(%)</th>
    <th colspan="4">Cyclist (AP@50)(%)</th>
    <th rowspan="2">mAP(%)</th>
  </tr>
  <tr>
    <th></th>
    <th>Overall</th>
    <th>0–30 m</th>
    <th>30–50 m</th>
    <th>50–100 m</th>
    <th>Overall</th>
    <th>0–30 m</th>
    <th>30–50 m</th>
    <th>50–100 m</th>
    <th>Overall</th>
    <th>0–30 m</th>
    <th>30–50 m</th>
    <th>50–100 m</th>
    <th></th>
  </tr>
  <tr>
    <td>IA-SSD</td>
    <td>34.38</td>
    <td>80.95</td>
    <td>39.43</td>
    <td>16.59</td>
    <td>14.66</td>
    <td>27.28</td>
    <td>15.43</td>
    <td>4.66</td>
    <td>24.82</td>
    <td>39.62</td>
    <td>23.31</td>
    <td>11.83</td>
    <td>24.62</td>
  </tr>
  <tr>
    <td>PV-RCNN</td>
    <td>31.17</td>
    <td>74.18</td>
    <td>34.77</td>
    <td>15.77</td>
    <td>8.92</td>
    <td>13.88</td>
    <td>10.72</td>
    <td>4.73</td>
    <td>24.84</td>
    <td>42.30</td>
    <td>20.91</td>
    <td>11.76</td>
    <td>21.64</td>
  </tr>
  <tr>
    <td>CenterPoint</td>
    <td>26.93</td>
    <td>70.16</td>
    <td>20.62</td>
    <td>17.86</td>
    <td>12.36</td>
    <td>23.03</td>
    <td>11.85</td>
    <td>4.29</td>
    <td>25.31</td>
    <td>41.80</td>
    <td>22.64</td>
    <td>12.34</td>
    <td>21.54</td>
  </tr>
</table>

#### Results of detection models on the IntDT-D test set.
<table>
  <tr>
    <th rowspan="2">Method</th>
    <th colspan="4">Vehicle (AP@50)(%)</th>
    <th colspan="4">Pedestrian (AP@50)(%)</th>
    <th colspan="4">Cyclist (AP@50)(%)</th>
    <th rowspan="2">mAP(%)</th>
  </tr>
  <tr>
    <th></th>
    <th>Overall</th>
    <th>0–30 m</th>
    <th>30–50 m</th>
    <th>50–100 m</th>
    <th>Overall</th>
    <th>0–30 m</th>
    <th>30–50 m</th>
    <th>50–100 m</th>
    <th>Overall</th>
    <th>0–30 m</th>
    <th>30–50 m</th>
    <th>50–100 m</th>
    <th></th>
  </tr>
  <tr>
    <td>IA-SSD</td>
    <td>28.34</td>
    <td>78.22</td>
    <td>31.61</td>
    <td>14.67</td>
    <td>17.94</td>
    <td>24.53</td>
    <td>13.90</td>
    <td>11.66</td>
    <td>20.11</td>
    <td>31.30</td>
    <td>11.30</td>
    <td>13.33</td>
    <td>22.13</td>
  </tr>
  <tr>
    <td>PV-RCNN</td>
    <td>26.84</td>
    <td>75.64</td>
    <td>30.12</td>
    <td>13.40</td>
    <td>16.07</td>
    <td>32.38</td>
    <td>8.15</td>
    <td>10.94</td>
    <td>21.84</td>
    <td>50.89</td>
    <td>15.40</td>
    <td>2.91</td>
    <td>21.58</td>
  </tr>
  <tr>
    <td>CenterPoint</td>
    <td>22.05</td>
    <td>67.23</td>
    <td>21.58</td>
    <td>12.29</td>
    <td>27.84</td>
    <td>44.38</td>
    <td>13.91</td>
    <td>25.64</td>
    <td>14.45</td>
    <td>30.11</td>
    <td>14.34</td>
    <td>2.32</td>
    <td>21.45</td>
  </tr>
</table>



### 3D Object Tracking

#### Results of 3D Object Tracking models on the IntDT-S validation set.

<table>
    <tr>
        <th>Tracking</th>
        <th>Detection</th>
        <th>AMOTA (%)</th>
        <th>AMOTP (m)</th>
    </tr>
    <tr>
        <td rowspan="3">PC-TCNN</td>
        <td>IA-SSD</td>
        <td>56.4</td>
        <td>0.825</td>
    </tr>
    <tr>
        <td>PV-RCNN</td>
        <td>50.9</td>
        <td>0.801</td>
    </tr>
    <tr>
        <td>CenterPoint</td>
        <td>41.3</td>
        <td>0.900</td>
    </tr>
</table>

#### Results of 3D Object Tracking models on the IntDT-S test set.

<table>
    <tr>
        <th>Tracking</th>
        <th>Detection</th>
        <th>AMOTA (%)</th>
        <th>AMOTP (m)</th>
    </tr>
    <tr>
        <td rowspan="3">PC-TCNN</td>
        <td>IA-SSD</td>
        <td>65.6</td>
        <td>0.661</td>
    </tr>
    <tr>
        <td>PV-RCNN</td>
        <td>54.7</td>
        <td>0.714</td>
    </tr>
    <tr>
        <td>CenterPoint</td>
        <td>43.8</td>
        <td>0.797</td>
    </tr>
</table>



## Acknowledgment
- [OpenPCDet](https://github.com/open-mmlab/OpenPCDet)
- [SUSTechPOINTS](https://github.com/naurril/SUSTechPOINTS)

Sincere appreciation for their great contributions.
