# Simple Google Distance Matrix
## What's this?
Basically a quick and dirty distance matrix retriever. A by product from one of my research.

## How to use it?
Enter Origin and Destination then VUALA. Separate location with "|", note that destination is limited to 25 locations max due to implementation, however origin has no limitation.

Eligible choice of location can be:
*    Lat long separated by comma
*    Google map readable location name
*    Address

For example:
*    Taipei 101|Fifth Avenue
*    36,-75|34.222,-100.444

Also Google Distance Matrix has "Elements per second" limitation, the matrix will update approximately 100 elements every 10 seconds to avoid over query.

However for unknown reason Google often still responds with over query error, thus borns incremental delay (By default extra 0.1 seconds per request). This will decrease the chance of over query error, but will still occur occasionally.

Also note that Google can only accept update to 2500 elements per day, so good luck with that. If you have Google cloud platform api, you can use it for up to 100,000 elemts per day.

## Notes on error
Due to no error handler, any sorts of error will halt the retrieving process. You can lookup in console log to see what's happening and try to solve it.

## To do list
* Error handler for over query limitation, perform query again instead of skipping it
* Error handler for location unable to be identified by Google, maybe just skip instead of getting stuck
* Option to switch between traveling time and distance.

Hope I ever get to fix any of these, probably won't.
