---
layout: page
title: Usage
sidebar_link: true
---

Machiavelli gives a robust GUI that primarily acts as a URL-mangler: buttons, dropdowns and toggles allow for changing of URL parameters, which is then used on page load to create the visualization shown. 

Although the GUI can assist in creating the URLs, they can also be generated manually, using the below specification. 
Machiavelli aggregates backends in the Rails server end, and serves the collected versions in it's own endpoints. This allows the front end to query one place, and for any external authentication to happen server-side. 

Endpoints
--------

### GET `/` - Visualizations

All GUI, all the time. 

**Optional parameters**

 * `metric` - as listed by `/source/` - multiple allowed
 * `time` - "relative" (default) or "absolute"
 * `start` - seconds since epoch (if `time=absolute`) or nice-time format (if `time=relative`)
 * `stop` - seconds since epoch (if `time=absolute`) or nice-time format (if `time=relative`), or "now"
 * `step` - seconds interval between points. default dynamically redefined. 
 * `graph` - "standard" (default), "stacked", "horizon"
 * `play` - "true", or "false". Only compatible when `stop=now` 

Nice-time format is defined as: `int[w|d|h|min]` (weeks, days, hours, minutes)/ Example: `3h` = 3 hours, `2d` = 2 days, `14d=2w`  

**Sample Request**

`http://machiavelli/?metric=Simple~Clizia&metric=Simple~The_Mandrake&graph=stacked&start=1d`

**Response Properties**

Shiny, Bootstrap-y. 

**Sample response**

Pretty graphs. 

### GET `/search/`
Used for the listing of sources from backends. 

**Optional Parameters**

 *  `backend` - specify a particular backend to list

**Sample Request**

`curl "http://machiavelli/search/?backend=Simple"`

**Response Properties**

JSON array of tilde-delimited metrics. Format: `backend~metric`

**Sample response**

`["Simple~The_Prince","Simple~Clizia","Simple~The_Mandrake"]`

### GET `/metric/`
Used for the retrieving of data from a particular backend metrics, as sourced from `/source`/

**Required parameters**
 * `metric` - the metric name, as supplied by `/source/`
 * `start` - seconds since epoch 
 * `stop` - seconds since epoch 
 * `step` - seconds interval between points

**Sample Request**

`curl "http://machiavelli/metric/?metric=Simple~Clizia&start=100&stop=300&step=50"`

**Response Properties**

JSON array of x,y hashes. Array size = `(stop - start) / step`

**Sample response**

`[{"x":100,"y":35.35},{"x":150,"y":35.92},{"x":200,"y":35.82},{"x":250,"y":35.03}]`


