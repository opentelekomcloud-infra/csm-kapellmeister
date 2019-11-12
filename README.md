# CSM Kapellmeister
The only legit way to conduct test infrastructure

### Workflow 

1. **Setup Conductor** \
    Your master machine is setup with `setup_local_conductor.yml` playbook
    Install Terraform and required python packages, including Ansible v. 2.8

1. **Setup test host** \
    Set up ECS from image `Debian_CSM_test_host` and clone
    [CSM](https://github.com/opentelekomcloud-infra/customer-service-monitoring)

1. **Build target infrastructure** \
    Run `./build.sh` for each used scenario of 
    [CSM](https://github.com/opentelekomcloud-infra/customer-service-monitoring).
    This will create infrastructure used in tests and apply playbooks defined for each scenario

1. **Start monitoring** \
    Run `./test.sh` for each used scenario.
    Will start service-like background monitoring of created infrastructure and
    report to designated InfluxDB instance
