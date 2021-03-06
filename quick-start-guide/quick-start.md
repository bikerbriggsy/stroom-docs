# Stroom Quick-Start Tutorial
In this quick-start guide you will learn how to use Stroom to get from [this CSV](resources/mock_stroom_data.csv), which looks like this:

```
id,guid,from_ip,to_ip,application
1,10990cde-1084-4006-aaf3-7fe52b62ce06,159.161.108.105,217.151.32.69,Tres-Zap
2,633aa1a8-04ff-442d-ad9a-03ce9166a63a,210.14.34.58,133.136.48.23,Sub-Ex
...
```
To this XML:

```xml
<?xml version="1.1" encoding="UTF-8"?>
<Events xmlns:stroom="stroom" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
   <Event>
      <Id>1</Id>
      <Guid>10990cde-1084-4006-aaf3-7fe52b62ce06</Guid>
      <FromIp>159.161.108.105</FromIp>
      <ToIp>217.151.32.69</ToIp>
      <Application>Tres-Zap</Application>
   </Event>
   <Event>
      <Id>2</Id>
      <Guid>633aa1a8-04ff-442d-ad9a-03ce9166a63a</Guid>
      <FromIp>210.14.34.58</FromIp>
      <ToIp>133.136.48.23</ToIp>
      <Application>Sub-Ex</Application>
   </Event>
  ...
```

You will go from a clean vanilla Stroom to having a simple [pipeline](/user-guide/pipelines/README.md) that takes in CSV data and outputs that data transformed into XML. Stroom is a generic and powerful tool for ingesting and processing data: it's flexible because it's generic so if you do want to start processing data we would recommend you follow this tutorial otherwise you'll find yourself struggling.

We're going to do the following:

1. Get and run Stroom
2. Do some quick and easy but necessary config
3. [Get some data into Stroom](feed/feed.md)
4. [Set up a pipeline to process the data](process/process.md)
5. [Index the data](index/index.md)
6. [Show the data on a dashboard](dashboard/dashboard.md)

All the things we create here are available as a [content pack](https://github.com/gchq/stroom-content/releases/tag/stroom-101-v1.0), so if you just wanted to see it running you could get there quite easily.

> **Note:** The CSV data used in _mock_stroom_data.csv_ (linked to above) is randomly generated and any association with any real world IP address or name is entirely coincidental.

## Getting and Running Stroom

There are several options to get Stroom running and by far the quickest and easiest is to use Docker. If you're new to [Docker](https://www.docker.com/what-docker) then you might want to follow their [getting started guide](https://www.docker.com/products/docker) first. Otherwise you can follow our [quick guide](/dev-guide/docker-running.md).

If you're really interested here are your full options for running Stroom:

* [Run using a Docker Hub image (recommended)](/dev-guide/docker-running.md#using-a-pre-built-docker-hub-image)
* [Run using a release](/install-guide/stroom-app-install.md)
* From source you can:
  * [Build and run from IntelliJ](/dev-guide/stroom-in-an-ide.md)
  * [Build and run using Docker](/dev-guide/docker-building.md)

## Basic configuration

### Enable processing of data streams

Automatic processing isn't enabled by default: you might first want to check other settings (for example  nodes, properties, and volumes). So we need to enable Stream Processing. This is in Tools -> Jobs menu::
![Opening the jobs ment](images/go-jobs.png)

Next we need to enable Stream Processor jobs:

![Enabling stream processing](images/configure-jobs.png)

Below the list of jobs is the properties pane. The Stream Processor's properties show the list of nodes. You should have one. You'll need to enable it by scrolling right:

![Enabling the nodes for the stream processor](images/configure-jobs-stream.png)

So now we've done that lets [get data into stroom](feed/feed.md).
