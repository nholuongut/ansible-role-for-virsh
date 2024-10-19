# Ansible Role - virsh
![](https://i.imgur.com/waxVImv.png)
### [View all Roadmaps](https://github.com/nholuongut/all-roadmaps) &nbsp;&middot;&nbsp; [Best Practices](https://github.com/nholuongut/all-roadmaps/blob/main/public/best-practices/) &nbsp;&middot;&nbsp; [Questions](https://www.linkedin.com/in/nholuong/)
<br/>

## Variables

```yaml
deploy_dir: Required for where the base path lives
```

## Tags

```YAML
tags:
- install
- rename
- create
- storage
```

## Examples

### Example to install the packages

```YAML
- hosts: all

  vars:
    flags:      ['install']

  roles:
    - { role: nho.luong }
```

### Example to create a vm

```YAML
- hosts: all

  vars:
    flags:          ['create']
    vm_name: 'vm_name'
    vm_cfg:
      storage:
        primary:
          size: 320G
          type: xfs
          name: vda
        secondary:
          size: 3T
          type: xfs
          name: vdb
      vcpus: 4
      memory:
        size: 4096
      graphics:
        vnc:
          port: 5900
      network:
        do_proxy: true            # Enable proxy settings for the new VM. Ensure proxy config is included.
        dchp: true                # Whether to use DHCP
        # Required when not using DHCP
        ip: xx.xx.xx.xx           # IP Address to use
        mask: x                   # Network Mask Value
        gateway: xx.xx.xx.xx      # Network Gateway
        netmask: xx.xx.xx.xx      # Netmask
        broadcast: xx.xx.xx.xx    # Broadcast address
        mac: xxx.xxx.xxx.xxx      # MAC Address
    proxy:
      addr: "address.com"
      port: "3128"


  roles:
    - { role: nho.luong }
```

### Example to rename a vm

```YAML
- hosts: all

  vars:
    flags:  ['rename']
    vm_name: 'vm_name'
    vm_old: 'old_vm'

  roles:
    - { role: nho.luong }
```

### Example add secondary storage

```YAML
- hosts: all

  vars:
    flags:              ['secondary_storage']
    vm_name: 'vm_name'
    vm_cfg:
      storage:
        primary:
          size: 320G
          type: xfs
          name: vda
        secondary:
          size: 3T
          type: xfs
          name: vdb
    base_image_path:   '/mnt/storage/'

  roles:
    - { role: nho.luong }
```

## Linting

```bash
yamllint -c yamllint.yaml .
ansible-lint .
```

# 🚀 I'm are always open to your feedback.  Please contact as bellow information:
### [Contact ]
* [Name: nho Luong]
* [Skype](luongutnho_skype)
* [Github](https://github.com/nholuongut/)
* [Linkedin](https://www.linkedin.com/in/nholuong/)
* [Email Address](luongutnho@hotmail.com)

![](https://i.imgur.com/waxVImv.png)
![](Donate.png)
[![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/nholuong)

# License
* Nho Luong (c). All Rights Reserved.🌟
