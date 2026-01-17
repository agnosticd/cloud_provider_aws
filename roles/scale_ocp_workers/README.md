# scale_ocp_workers

Scales OpenShift worker nodes on AWS by managing MachineSets.

## Usage

Scale to 3 workers using existing instance type:

```yaml
- name: Scale OCP workers
  ansible.builtin.include_role:
    name: agnosticd.cloud_provider_aws.scale_ocp_workers
  vars:
    worker_instance_count: 3
```

Scale to 5 workers with a different instance type:

```yaml
- name: Scale OCP workers with custom instance type
  ansible.builtin.include_role:
    name: agnosticd.cloud_provider_aws.scale_ocp_workers
  vars:
    worker_instance_count: 5
    worker_instance_type: m5.2xlarge
    worker_machineset_suffix: compute
```

## Variables

See [defaults/main.yml](defaults/main.yml) for all variables and their defaults.
