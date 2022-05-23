# Gopher

A simple task system using Docker SDK


## Getting Started

### Pre-requisite

- Go (Tested with 1.15.15)


### Step 1. Clone the repository

```
git clone https://github.com/gauravgahlot/gopher
```

### Project Directory Structure

```
$ tree
.
├── LICENSE
├── README.md
├── go.mod
├── go.sum
├── internal
│   ├── container-manager
│   │   └── container_manager.go
│   ├── task-runner
│   │   └── runner.go
│   └── types
│       └── task.go
├── main.go
└── task.yaml

4 directories, 9 files
```


### Step 2. Building Go binaries

```
cd gopher
go build
```

This command builds a gopher binary as shown in the project tree structure:

#### Project Directory Structure:

```
$ tree
.
├── LICENSE
├── README.md
├── go.mod
├── go.sum
├── gopher
├── internal
│   ├── container-manager
│   │   └── container_manager.go
│   ├── task-runner
│   │   └── runner.go
│   └── types
│       └── task.go
├── main.go
└── task.yaml

4 directories, 10 files
```


### Step 3. Compiling and running tasks

```
./gopher run task.yaml
preparing task -  gopher-loops
preparing task -  hello-gopher
starting task -  gopher-loops
starting task -  hello-gopher
completed task -  hello-gopher
completed task -  gopher-loops
```

Run `docker ps -a` to see what all containers ran and exit:

```
docker ps -a
CONTAINER ID   IMAGE     COMMAND                  CREATED          STATUS                      PORTS     NAMES
08f08e39cab9   busybox   "echo 'Hello, Gopher…"   13 minutes ago   Exited (0) 13 minutes ago             hello-gopher
```
