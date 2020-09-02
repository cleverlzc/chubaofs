你好！
很冒昧用这样的方式来和你沟通，如有打扰请忽略我的提交哈。我是光年实验室（gnlab.com）的HR，在招Golang开发工程师，我们是一个技术型团队，技术氛围非常好。全职和兼职都可以，不过最好是全职，工作地点杭州。
我们公司是做流量增长的，Golang负责开发SAAS平台的应用，我们做的很多应用是全新的，工作非常有挑战也很有意思，是国内很多大厂的顾问。
如果有兴趣的话加我微信：13515810775  ，也可以访问 https://gnlab.com/，联系客服转发给HR。
# ChubaoFS

[![Build Status](https://travis-ci.org/chubaofs/chubaofs.svg?branch=master)](https://travis-ci.org/chubaofs/chubaofs)
[![LICENSE](https://img.shields.io/github/license/chubaofs/chubaofs.svg)](https://github.com/chubaofs/chubaofs/blob/master/LICENSE)
[![Language](https://img.shields.io/badge/Language-Go-blue.svg)](https://golang.org/)
[![Go Report Card](https://goreportcard.com/badge/github.com/chubaofs/chubaofs)](https://goreportcard.com/report/github.com/chubaofs/chubaofs)
[![Docs](https://readthedocs.org/projects/chubaofs/badge/?version=latest)](https://chubaofs.readthedocs.io/en/latest/?badge=latest)
[![FOSSA Status](https://app.fossa.io/api/projects/git%2Bgithub.com%2Fchubaofs%2Fcfs.svg?type=shield)](https://app.fossa.io/projects/git%2Bgithub.com%2Fchubaofs%2Fcfs?ref=badge_shield)
[![CII Best Practices](https://bestpractices.coreinfrastructure.org/projects/2761/badge)](https://bestpractices.coreinfrastructure.org/projects/2761)

<img src="https://user-images.githubusercontent.com/47099843/55525970-bf53d880-56c5-11e9-8c28-55d208859824.png" width="400" height="293" />


## Overview

ChubaoFS (储宝文件系统) is a distributed file system for cloud native applications. It has the following features:

* scale-out metadata management

* strong replication consistency for both append and random write

* specific storage optimizations for large and small files

* multiple volumes

* POSIX-compatible

For more details, please refer to our SIGMOD 2019 paper "ChubaoFS: A Distributed File System for Large Scale Container Platforms".


## Document

https://chubaofs.readthedocs.io/en/latest/

https://chubaofs.readthedocs.io/zh_CN/latest/


## Build

Build latest version of chubaofs is simply as following:

```
$ git clone http://github.com/chubaofs/chubaofs.git
$ cd chubaofs
$ make
```

If the build is successful, `cfs-server` and `cfs-client` will be found in directory `build/bin`


## Docker

Under the docker directory, a helper tool called run_docker.sh is provided to run ChubaoFS with docker-compose.

To start a minimal ChubaoFS cluster from scratch, note that **/data/disk** is arbitrary, and make sure there are at least 30G available space.

```
$ docker/run_docker.sh -r -d /data/disk
```

If client starts successfully, use `mount` command in client docker shell to check mount status:

```
$ mount | grep chubaofs
```

Open http://127.0.0.1:3000 in browser, login with `admin/123456` to view grafana monitor metrics.

Or run server and client seperately by following commands:

```
$ docker/run_docker.sh -b
$ docker/run_docker.sh -s -d /data/disk
$ docker/run_docker.sh -c
$ docker/run_docker.sh -m
```

For more usage:

```
$ docker/run_docker.sh -h
```


## License

Licensed under the [Apache License, Version 2.0](http://www.apache.org/licenses/LICENSE-2.0).
For detail see [LICENSE](LICENSE) and [NOTICE](NOTICE).

[![FOSSA Status](https://app.fossa.io/api/projects/git%2Bgithub.com%2Fchubaofs%2Fcfs.svg?type=large)](https://app.fossa.io/projects/git%2Bgithub.com%2Fchubaofs%2Fcfs?ref=badge_large)


## Reference

Reference to cite when you use the system in a research paper or tech report: 

Haifeng Liu, et al., CFS: A Distributed File System for Large Scale Container Platforms. SIGMOD‘19, June 30-July 5, 2019, Amsterdam, Netherlands. https://dl.acm.org/citation.cfm?doid=3299869.3314046





