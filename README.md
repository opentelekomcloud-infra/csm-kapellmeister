# CSM Kapellmeister
The only legit way to conduct test infrastructure

### Workflow 

1. **Setup Conductor**

    Your master machine is set up with `setup_local_conductor.yml` playbook.

    *Installs Terraform and required python packages, including Ansible v. 2.8.*

1. **Setup test host**

    Use `prepare_test_host.yml` playbook to set up VM for monitoring.

    *Sets up ECS from image `Debian_CSM_test_host` and clone
    [CSM](https://github.com/opentelekomcloud-infra/customer-service-monitoring).*

1. **Start monitoring**

    Use `scenario<N>` playbook, where `<N>` is `1..4` to set up exact monitoring scenarios.

    *Runs `./build.sh` and `./test.sh` for scenario from 
    [CSM](https://github.com/opentelekomcloud-infra/customer-service-monitoring).*
