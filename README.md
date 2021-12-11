# Wav2Lip
#### Wav2Lip: Accurately Lip-syncing Videos In The Wild
 Wav2Lip wrapper pypi package code for this package is available at: https://github.com/mehdihosseinimoghadam/Wav2Lip
 also original code from writers of Wav2Lip is available at:
 https://github.com/Rudrabha/Wav2Lip

[![Build Status](https://travis-ci.org/joemccann/dillinger.svg?branch=master)](https://travis-ci.org/joemccann/dillinger)

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://github.com/mehdihosseinimoghadam/Wav2Lip/blob/master/Wav2Lip_wrapper_pypi_package.ipynb)

Prerequisites
-------------
- `Python 3.6` 
- ffmpeg: `sudo apt-get install ffmpeg`
- Face detection [pre-trained model](https://www.adrianbulat.com/downloads/python-fan/s3fd-619a316812.pth) should be downloaded to `face_detection/detection/sfd/s3fd.pth`. Alternative [link](https://iiitaphyd-my.sharepoint.com/:u:/g/personal/prajwal_k_research_iiit_ac_in/EZsy6qWuivtDnANIG73iHjIBjMSoojcIV0NULXV-yiuiIg?e=qTasa8) if the above does not work.



Getting the weights
----------
| Model  | Description |  Link to the model | 
| :-------------: | :---------------: | :---------------: |
| Wav2Lip  | Highly accurate lip-sync | [Link](https://iiitaphyd-my.sharepoint.com/:u:/g/personal/radrabha_m_research_iiit_ac_in/Eb3LEzbfuKlJiR600lQWRxgBIY27JZg80f7V9jtMfbNDaQ?e=TBFBVW)  |
| Wav2Lip + GAN  | Slightly inferior lip-sync, but better visual quality | [Link](https://iiitaphyd-my.sharepoint.com/:u:/g/personal/radrabha_m_research_iiit_ac_in/EdjI7bZlgApMqsVoEUUXpLsBxqXbn5z8VTmoxp55YNDcIA?e=n9ljGW) |
| Expert Discriminator  | Weights of the expert discriminator | [Link](https://iiitaphyd-my.sharepoint.com/:u:/g/personal/radrabha_m_research_iiit_ac_in/EQRvmiZg-HRAjvI6zqN9eTEBP74KefynCwPWVmF57l-AYA?e=ZRPHKP) |
| Visual Quality Discriminator  | Weights of the visual disc trained in a GAN setup | [Link](https://iiitaphyd-my.sharepoint.com/:u:/g/personal/radrabha_m_research_iiit_ac_in/EQVqH88dTm1HjlK11eNba5gBbn15WMS0B0EZbDBttqrqkg?e=ic0ljo) |


## Features

- Easy to use
- Fast
- Accurate

## Usage

First of all get the weights:


```sh
wget "https://www.adrianbulat.com/downloads/python-fan/s3fd-619a316812.pth" -O "/usr/local/lib/python3.7/dist-packages/Wav2Lip/face_detection/detection/sfd/gfs3fd.pth"
```

```sh
gdown https://drive.google.com/uc?id=1jQOJInh8cDj2mrbUgcQxhCc7rpAgyV1-
```

After pip installation add these directories:

```sh
mkdir /usr/local/lib/python3.7/dist-packages/Wav2Lip/results
mkdir /usr/local/lib/python3.7/dist-packages/Wav2Lip/temp
mkdir /usr/local/lib/python3.7/dist-packages/Wav2Lip/checkpoints
```

Then add weights:

```sh
mv /content/wav2lip_gan.pth /usr/local/lib/python3.7/dist-packages/Wav2Lip/checkpoints/
&&
cd /usr/local/lib/python3.7/dist-packages/Wav2Lip
```

Import Wav2Lip wrapper function:

```py
from Wav2Lip.wrapper_app import main
main("/path/to/wav/file","path/to/image")
```

The resulting video would be in
```sh
/usr/local/lib/python3.7/dist-packages/Wav2Lip/results/result_voice.mp4
```

If you run in colab you can use this script:

```py
from IPython.display import HTML
from base64 import b64encode
mp4 = open('/usr/local/lib/python3.7/dist-packages/Wav2Lip/results/result_voice.mp4','rb').read()
data_url = "data:video/mp4;base64," + b64encode(mp4).decode()
HTML("""
<video width=400 controls>
      <source src="%s" type="video/mp4">
</video>
""" % data_url)
```





## Authors

| Name | Github | Home Page |
| ------ | ------ | ------|
| Mehdi Hosseini Moghadam | https://github.com/mehdihosseinimoghadam |https://www.linkedin.com/in/mehdi-hosseini-moghadam-384912198/|
| Hanie Poursina |https://github.com/HaniePoursina | http://haniepoursina.ir/

## Github

Source is avaliable at
https://github.com/mehdihosseinimoghadam/Wav2Lip



## License

MIT

**Free Software, Hell Yeah!**


Acknowledgements
----------
This is only a wrapper package and the main code of Wav2Lip can be found in https://github.com/Rudrabha/Wav2Lip

