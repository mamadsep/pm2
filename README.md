![PM2](https://github.com/unitech/pm2/raw/master/pres/pm2.20d3ef.png)

PM2 is a process manager for Node.JS application with a built-in load balancer. It will allows you to keep an application alive forever, to reload them without downtime and will facilitate common admin system work.

PM2 is constantly assailed by [more than 300 test](https://travis-ci.org/Unitech/PM2)

Compatible with CoffeeScript.
Works on Linux & MacOS.

[![NPM version](https://badge.fury.io/js/pm2.png)](http://badge.fury.io/js/pm2) [![Build Status](https://api.travis-ci.org/Unitech/PM2.png?branch=master)](https://travis-ci.org/Unitech/PM2)

[![NPM](https://nodei.co/npm/pm2.png?downloads=true&downloadRank=true)](https://nodei.co/npm/pm2/)

## Install PM2

```bash
$ npm install pm2 -g
```

## Start an application

```bash
$ pm2 start app.js
$ pm2 start app.js -i max  # Enable load-balancer and cluster features
```

## Main features

### Process management

Once app are started you can list them and manage them:

![Process listing](https://github.com/unitech/pm2/raw/master/pres/pm2-list.png)

To list all running processes:

```bash
$ pm2 list
```

To manage your process it's straightforward:

```bash
$ pm2 stop     <app_name|id|all>
$ pm2 restart  <app_name|id|all>
$ pm2 delete   <app_name|id|all>
```

To get more details about a specific process:

```bash
$ pm2 describe 0
```

### Monitoring

![Monit](https://github.com/unitech/pm2/raw/master/pres/pm2-monit.png)

Monitor all processes launched:

```bash
$ pm2 monit
```

### Log facilities

![Monit](https://github.com/unitech/pm2/raw/master/pres/pm2-logs.png)

Displaying logs of specified process or all processes in realtime:

```bash
$ pm2 logs
$ pm2 logs big-api
$ pm2 flush          # Clear all the logs
```

### Load balancing / 0s reload downtime

When an app is started with the -i <worker number> option, the cluster mode is enabled.

With the cluster mode, PM2 enable load balancing between each worker.
Each HTTP/TCP/UDP request will be forwarded to a specific process at a time.

```bash
$ pm2 start app.js -i max  # Enable load-balancer and cluster features

$ pm2 reload all           # Reload all apps in 0s manner
```

### Startup script generation

PM2 can generate and configure a startup script to keep PM2 and your processes alive at every server restart.

```bash
$ pm2 startup <ubuntu|centos|gentoo|systemd>
```

To save a process list just do:

```bash
$ pm2 save
```

## Monitoring dashboard

![Dashboard](http://leapfrogui.com/controlfrog/img/cf-layout-1.png)

We're going to release a very nice product, a dashboard to monitor every part of your Node.js applications. Here are some links:

- [Pitch + Survey](https://docs.google.com/forms/d/1FuCjIhrGg-ItxInq2nLreoe9GS-gZWJNkNWE0JJajw8/viewform) People who fill the survey will be eligible for free license

Thanks in advance and we hope that you like PM2!

## Other PM2 features

- [Watch & Restart](https://github.com/Unitech/PM2/blob/development/ADVANCED_README.md#a890)
- [JSON application declaration](https://github.com/Unitech/PM2/blob/development/ADVANCED_README.md#a10)
- [Using PM2 in your code](https://github.com/Unitech/PM2/blob/development/ADVANCED_README.md#programmatic-example)
- [Deployment workflow](https://github.com/Unitech/PM2/blob/development/ADVANCED_README.md#deployment)
- [Startup script generation (SystemV/Ubuntu/Gentoo/AWS)](https://github.com/Unitech/PM2/blob/development/ADVANCED_README.md#a8)
- [Advanced log management (flush, reload, ilogs)](https://github.com/Unitech/PM2/blob/development/ADVANCED_README.md#9)
- [GracefullReload](https://github.com/Unitech/PM2/blob/development/ADVANCED_README.md#a690)

## Know more about PM2

[Advanced README.md](https://github.com/Unitech/PM2/blob/development/ADVANCED_README.md)

## Contributors

[Contributors](https://github.com/Unitech/PM2/graphs/contributors)

## License

Files in `lib/` are made available under the terms of the GNU Affero General Public License 3.0 (AGPL 3.0).
Except the file `lib/CLI.js` who is made under the terms of the Apache V2 license.
