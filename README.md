![Imgur](https://i.imgur.com/iEWAtkS.gif?1)

# ads4mo - Added Download Services for Mercator-Ocean

[![Build Status](https://travis-ci.com/carmelosammarco/ads4mo.png)](https://travis-ci.com/carmelosammarco/ads4mo)


Python module containing added downloads services for download the netCDF files from the CMEMS's catalogue and especially usefull for big data requests. It is possible download data by MONTH, DEPTH or DAY until a maximum of three selected variables(Planning to increase this number thought).
It brings in a very intuitive scripting way what was already proposed with [MerOC](https://github.com/carmelosammarco/MerOC).

## Be aware that:

The tool is in development so it can be possible find bugs, errors and imprecisions. Please to report them if you find one.

## Dependencies:

The dependencies required which are not installed by default are listed below:

- [x] motuclient>=1.8.1
- [x] ftputil>=3.4

## Installation and module usage

```
pip install ads4mo
```
we can import the module as:

```
from ads4mo import download
```
Once the module is imported we can call the interactive download process typing;

```
download()
```

At this point the system is going to ask;

- **Type of the download** which can be set typing one of the following:

     - **MONTH**: The entire period selected will be downloaded by months
     - **DEPTH**: The entire period selected will be downloaded by depths levels.
     - **DAY**: The entire period selected will download in a daily base. 

- **Motu client script** which is generated by the CMEMS web portal. Please to copy and paste (or if you prefer typing by hand) just from the "--user" to the "--variable" parameters and replace <USERNAME> and <PASSWORD> with your CMEMS credentials. 

Following an example of the full script generted by the Web-portal:

```
python <PATH_TO_MOTUCLIENT_DIR>/motu-client.py --user <USERNAME> --pwd <PASSWORD> --motu http://nrt.cmems-du.eu/motu-web/Motu --service-id GLOBAL_ANALYSIS_FORECAST_PHY_001_024-TDS --product-id global-analysis-forecast-phy-001-024 --longitude-min -180 --longitude-max 179.9166717529297 --latitude-min -80 --latitude-max 90 --date-min "2019-04-19 12:00:00" --date-max "2019-04-19 12:00:00" --depth-min 0.493 --depth-max 0.4942 --variable thetao --variable bottomT  --out-dir <OUTPUT_DIR> --out-name <OUTPUT_FILENAME>
```

What you need to input:

```
--user <USERNAME> --pwd <PASSWORD> --motu http://nrt.cmems-du.eu/motu-web/Motu --service-id GLOBAL_ANALYSIS_FORECAST_PHY_001_024-TDS --product-id global-analysis-forecast-phy-001-024 --longitude-min -180 --longitude-max 179.9166717529297 --latitude-min -80 --latitude-max 90 --date-min "2019-04-19 12:00:00" --date-max "2019-04-19 12:00:00" --depth-min 0.493 --depth-max 0.4942 --variable thetao --variable bottomT
```






