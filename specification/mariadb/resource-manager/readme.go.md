## Go

These settings apply only when `--go` is specified on the command line.

``` yaml $(go)
go:
  license-header: MICROSOFT_MIT_NO_VERSION
  namespace: mariadb
  clear-output-folder: true
```

### Go multi-api

``` yaml $(go) && $(multiapi)
batch:
  - tag: package-2020-01-01
  - tag: package-2018-06-01
```

### Tag: package-2020-01-01 and go 

These settings apply only when `--tag=package-2020-01-01 --go` is specified on the command line. 
Please also specify `--go-sdk-folder=<path to the root directory of your azure-sdk-for-go clone>`. 

``` yaml $(tag) == 'package-2020-01-01' && $(go) 
output-folder: $(go-sdk-folder)/services/$(namespace)/mgmt/2020-01-01/$(namespace)
```

### Tag: package-2018-06-01 and go 

These settings apply only when `--tag=package-2018-06-01 --go` is specified on the command line. 
Please also specify `--go-sdk-folder=<path to the root directory of your azure-sdk-for-go clone>`. 

``` yaml $(tag) == 'package-2018-06-01' && $(go) 
output-folder: $(go-sdk-folder)/services/$(namespace)/mgmt/2018-06-01/$(namespace)
```
