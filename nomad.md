## Nomad learning
> Just small notes about some parts of nomad and workflow with it. 

Nomad has great documentation, most of the time it is everything you need when interacting with Nomad

Intro https://www.nomadproject.io/intro/index.html

Documentation https://www.nomadproject.io/docs/index.html

#### About
`Nomad` is a tool built by `HashiCorp` for efficient cluster management, jobs sheduling and other types of infrastructure operations.

#### Install

Installing process is pretty obvious, as it built in `Golang` the easiest way will be just to to grub single executable binary from https://github.com/hashicorp/nomad/releases

You should add `Nomad` ex. binary to your $PATH in your preffered shell. 


### Jobs

As described in docs primary configuration structure, most of the time when using Nomad you interacts with them. Job are written in DSL language built by Hashi team called `HCL`.

Docs about HCL can be found [here](https://github.com/hashicorp/hcl)

Job syntax validation can be done by 

```sh
$ nomad validate <path_to_job>
```


Each job consists of `Tasks` and `TaskGroups`

`Task` is a single action that should be performed. It can be starting `nginx`, or building your `API` docker image etc.

`TaskGroup` is a set of tasks that should work together.

Sample task group can be called `web` where you start your `api` and `mongo` for example.

#### API

`Nomad` provided REST API for fetching, creating jobs, their statuses etc.

There are some packages with wrapper around API. Main official package in `Golang` as it a core of nomad and third party in Java, Ruby etc.

Can be used by cluster monitoring solutions.
