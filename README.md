# Omnik Statistics
=====
Omnikstats will search for your (WIFI connected) Omnik or Trannergy solar inverter and then download its statistics. 
Statistics can be logged to a CSV data file and/or uploaded to PVoutput.org

With a 5 minute interval cronjob, this program can upload statistics to PVoutput.org

Or you can (up to a 1-second precision) create log the monitoring data to a CSV file.

You only have to edit omnik.conf with your APIkey and System ID, to be provided by PVoutput.org

## Installation and Setup

* You may have to update first:
	sudo apt-get update
* The curl development must be installed:
	sudo apt-get install libcurl4-openssl-dev
* Clone the source with `git clone https://github.com/kevinvandervlist/omnikstats.git`
* Edit omnik.conf with your API key and SystemID
* do a make clean
* do a make all
* run: ./omnikstats -? for the usage.

### cronjob
The following cronjob command starts omnikstats every 5 minutes between 5 AM and 12 PM
(no use to get statistics during night time)

*/5 5-23 * * * /\<path to omnikstats>/omnikstats

## REMARKS

* If no key and/or systemID is provided the program will still run (with an error from PVoutput). You can also skip PVOutput integration completely.
* This program might not work for all Omnik inverters. 
* If you have more than 1 string in your solar system, it will get the statistics and -if desired- will
	log this to CSV. However, only the first string will be uploaded to PVoutput.org (for now)

