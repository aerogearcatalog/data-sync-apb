# Data Sync APB

[![](https://img.shields.io/docker/automated/jrottenberg/ffmpeg.svg)](https://hub.docker.com/r/aerogearcatalog/data-sync-apb/)
[![Docker Stars](https://img.shields.io/docker/stars/aerogearcatalog/data-sync-apb.svg)](https://registry.hub.docker.com/v2/repositories/aerogearcatalog/data-sync-apb/stars/count/)
[![Docker pulls](https://img.shields.io/docker/pulls/aerogearcatalog/data-sync-apb.svg)](https://registry.hub.docker.com/v2/repositories/aerogearcatalog/data-sync-apb/)
[![License](https://img.shields.io/:license-Apache2-blue.svg)](http://www.apache.org/licenses/LICENSE-2.0)

## Testing

If you want to test the changes made to this repo, you can do it by simply running `apb test`
The test does the following:
1. Builds the APB 
1. Creates the project in currently targeted OpenShift instance
1. Runs the `provision` role
1. Runs the `test-provision` role which checks that
    * Grafana and Prometheus routes are accessible
    * we're getting successful response from OpenShift auth proxy server
1. Runs `deprovision` role
1. Runs `deprovision-test` role which checks that all objects (routes, pods, services) were deprovisioned successfully

If the test ends successfully, you should see the message `Pod phase Succeeded without returning test results` in your console output.

For more information about testing of APBs, check [ansible-playbook-bundle documentation](https://github.com/ansibleplaybookbundle/ansible-playbook-bundle/blob/master/docs/getting_started.md#test).
