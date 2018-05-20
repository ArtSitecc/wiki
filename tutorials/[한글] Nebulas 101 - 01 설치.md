# Nebulas 101 - 01 �����ϰ� �׺淯�� ��ġ

[������ Ʃ�丮�� ��ũ](https://www.youtube.com/watch?v=qtjss2LzSI4&list=PLFipfN18ZQwsW1_dge4w7dfsVNdNZZ37R)

�׺淯���� ���� ������Ʈ �ڵ�(https://nebulas.io/)�� �������� �������� �����ǰ� �ְ� ���ÿ����� ������ ���� �׽�Ʈ�ϰ� �ֽ��ϴ�. �������� �����̺� ü���� ������ �ϱ����� �׺淯�� �ҽ� �ڵ带 �ٿ�ε� �� �� �ֽ��ϴ�.

�׺淯���� ���� �� �˰� �����ø� [Non-Technical White Paper]�� �о����.(https://nebulas.io/docs/NebulasWhitepaper.pdf).

���� �� �� ��������� �˾ƺ��� �����ôٸ� [Technical White Paper](https://nebulas.io/docs/NebulasTechnicalWhitepaper.pdf)�� �׺淯�� ����� �ڵ带 �о����. (https://github.com/nebulasio/go-nebulas)

>�׺淯���� ���������� �ư� ������������ �����մϴ�. �� ����������� ������ �����Դϴ�.

## Golang ȯ��

�׺淯���� Golang�� ���� ����ǰ� �ֽ��ϴ�.

| Components | Version | Description |
|----------|-------------|-------------|
|[Golang](https://golang.org) | >= 1.9.2| The Go Programming Language |

### �� OSX

�ƿ��� golang�� ��ġ�ϱ� ���� [Homebrew](https://brew.sh/)�� ��õ�մϴ�.

```bash
# install
go�� ��ġ�մϴ�.

# ȯ�� ����
export GOPATH=/path/to/workspace
```

> �˸�:GOPATH�� �������� ���� ���� �� �ִ� ���� golang ���丮�Դϴ�. GOPATH�� ������ ��, ����� go ������Ʈ�� �� GOPATH ���丮�� ����Ǿ�� �մϴ�.

### Linux

```bash
# �ٿ�ε�
wget https://dl.google.com/go/go1.9.3.linux-amd64.tar.gz

# ����
tar -C /usr/local -xzf go1.9.3.linux-amd64.tar.gz

# ȯ�溯��
export PATH=$PATH:/usr/local/go/bin
export GOPATH=/path/to/workspace
```

## �׺淯�� ������

### �ٿ�ε�

���� ��ɾ�� �ҽ� �ڵ带 �����մϴ�.

```bash
# �۾����� ����
mkdir -p $GOPATH/src/github.com/nebulasio
cd $GOPATH/src/github.com/nebulasio

# �ٿ�ε�
git clone https://github.com/nebulasio/go-nebulas.git

# ����� ����
cd go-nebulas

# ������ �귣ġ�� ���� �������Դϴ�
git checkout master
```

### RocksDB ��ġ�ϱ�

* **OS X**:
* Install rocksdb via [Homebrew](https://brew.sh/)
```bash
brew install rocksdb
```

* **Linux - Ubuntu**
* Install Dependencies
```bash
apt-get update
apt-get -y install build-essential libgflags-dev libsnappy-dev zlib1g-dev libbz2-dev liblz4-dev libzstd-dev
```
* Install rocksdb by source code:
```bash
git clone https://github.com/facebook/rocksdb.git
cd rocksdb && make shared_lib && make install-shared
```

* **Linux - Centos**
* Install Dependencies
```bash
yum -y install epel-release && yum -y update
yum -y install gflags-devel snappy-devel zlib-devel bzip2-devel gcc-c++  libstdc++-devel
```
* Install rocksdb by source code:
```bash
git clone https://github.com/facebook/rocksdb.git
cd rocksdb && make shared_lib && make install-shared
```

### Go ������� ��ġ�ϱ�

Go dependencies in Go-Nebulas is managed by [Dep](https://github.com/golang/dep).

| Components | Version | Description |
|----------|-------------|-------------|
[Dep](https://github.com/golang/dep) | >= 0.3.1 | Dep is a dependency management tool for Go. |

#### Dep ��ġ�ϱ�

* **Mac OSX**
* Install Dep via [Homebrew](https://brew.sh/)
```bash
brew install dep
brew upgrade dep
```

* **Linux**
* Install dep
```bash
cd /usr/local/bin/
wget https://github.com/golang/dep/releases/download/v0.3.2/dep-linux-amd64
ln -s dep-linux-amd64 dep
```

#### ������� �ٿ�ε��ϱ�

Go-Nebulas�� ���� ������ø� �ٿ�ε��ϱ� ���� ��Ʈ ���丮�� �����մϴ�.

```bash
cd $GOPATH/src/github.com/nebulasio/go-nebulas
make dep
```

> `make dep`�� �� ���� ������ø� �ٿ�ε��ϱ� ������ ó�� �ٿ�ε� �ϴ� ����� �ð��� �� �ɸ��� �ֽ��ϴ�. ��� ������ô� �ٿ�ε尡 �� �ɼ� �ִµ� �� ��쿡�� ������� ����������  (http://ory7cn4fx.bkt.clouddn.com/vendor.tar.gz)���� ���� �ٿ�ε��ϰ� �׺淯�� ��Ʈ ���丮�� ������ Ǯ�� �˴ϴ�.
> ```bash
> vendor.tar.gz
> MD5: c2c1ff9311332f90e11fb81b48ca0984
> ```

�׺淯���� NVM (�׺淯�� ���� �ӽ�)�� V8 �ڹٽ�ũ��Ʈ �������� �����˴ϴ�.
�츮�� ��/�������� v8 ������ø� �����ϰ� �ְ� ���� ��ɾ�� v8 ������ø� ��ġ�մϴ�.

```bash
cd $GOPATH/src/github.com/nebulasio/go-nebulas
make deploy-v8
```

### Neb �����ϱ�

Golang ������ÿ�  V8 ������ø� ��ġ �Ŀ� �׺淯���� ���� ���� ������ ���� �� �ֽ��ϴ�.

```bash
cd $GOPATH/src/github.com/nebulasio/go-nebulas
make build
```

������ ������ ���� ��Ʈ ���丮 ����  `neb` ���������� ���� ���Դϴ�.
![make build](resources/101-01-make-build.png)

## NEB �����ϱ�

### ���ʽý� ���

���ο� �׺淯�� ü���� �����ϱ� ����, ���� ���ʽý� ��Ͽ� ���� ������ �ؾ� �մϴ�.

#### ���ʽý� ��� ����

```protobuf
# Neb genesis text file. Scheme is defined in core/pb/genesis.proto.

meta {
# Chain identity
chain_id: 100
}

consensus {
dpos {
# Initial dynasty, including all initial miners
dynasty: [
[ miner address ],
...
]
}
}

# ù ��ū�� �����(Pre-allocation)
token_distribution [
{
address: [ allocation address ]
value: [ amount of allocation tokens ]
},
...
]
```

genesis.conf�� ���ô� `conf/default/genesis.conf`�� �ֽ��ϴ�.
