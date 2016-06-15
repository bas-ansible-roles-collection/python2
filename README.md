# Python 2 (`python2`)

Master: [![Build Status](https://semaphoreci.com/api/v1/bas-ansible-roles-collection/python2/branches/master/badge.svg)](https://semaphoreci.com/bas-ansible-roles-collection/python2)
Develop: [![Build Status](https://semaphoreci.com/api/v1/bas-ansible-roles-collection/python2/branches/develop/badge.svg)](https://semaphoreci.com/bas-ansible-roles-collection/python2)

Installs Python 2 language runtime/development packages and PIP package manager

**Part of the BAS Ansible Role Collection (BARC)**

**This role uses version 0.3.1 of the BARC flavour of the BAS Base Project - Pristine**.

## Overview

* Installs Python 2 runtime package
* Installs Python 2 development package
* Installs PIP package manager

## Quality Assurance

This role uses manual and automated testing to ensure its features work as advertised.
See [here](tests/README.md) for more information.

## Ansible compatibility

* this role supports Ansible 1.8 or higher in the 1.x series
* this role supports Ansible 2.x

**Note:** Support for Ansible 1.x is deprecated by this role, future versions will support Ansible 2.x only.

More information on Ansible compatibility is available in the
[BARC General Documentation](https://antarctica.hackpad.com/BARC-Overview-and-Policies-SzcHzHvitkt#:h=Ansible-compatbility).

## Dependencies

* none

More information on role dependencies is available in the
[BARC General Documentation](https://antarctica.hackpad.com/BARC-Overview-and-Policies-SzcHzHvitkt#:h=Role-dependencies)

## Requirements

* none

More information on role requirements is available in the
[BARC General Documentation](https://antarctica.hackpad.com/BARC-Overview-and-Policies-SzcHzHvitkt#:h=Role-requirements)

## Limitations

* The Python version varies depending on which operating system is used

As the package policy varies between operating systems, the version of Python installed is variable between supported 
operating systems.

For Python 2, only the minor version of Python differs between supported operating systems.

_This limitation is **NOT** considered to be significant. Solutions will **NOT** be actively pursued._ 
_Pull requests addressing this limitation will be considered.*_

See [BARC-127](https://jira.ceh.ac.uk/browse/BARC-127) for further details.

* The Python PIP version varies depending on which operating system is used

As the package policy varies between operating systems, the version of Python installed is variable between supported 
operating systems.

_This limitation is **NOT** considered to be significant. Solutions will **NOT** be actively pursued._ 
_Pull requests addressing this limitation will be considered.*_

See [BARC-128](https://jira.ceh.ac.uk/browse/BARC-128) for further details.

More information on role limitations is available in the 
[BARC General Documentation](https://antarctica.hackpad.com/BARC-Overview-and-Policies-SzcHzHvitkt#:h=Role-limitations)
 
## Usage

### BARC Manifest

By default, BARC roles will record that they have been applied to a system, this is termed the BAS Manifest.
The specific local facts set for this role are:

* `ansible_local.barc_python2.general.role_applied` - (boolean) records whether a role has been applied
* `ansible_local.barc_python2.general.role_version` - (string) records the version of the role that was applied

**Note:** You **SHOULD** use this feature to determine whether this role has been applied to a system.
If you do not want these facts to be set by this role, you **MUST** skip the **BARC_SET_MANIFEST** tag.

More information is available in the
[BARC General Documentation](https://antarctica.hackpad.com/BARC-Overview-and-Policies-SzcHzHvitkt#:h=Role-Manifest)

### Python version

Depending on the operating system used, the version of Python and PIP installed will differ, though it will be at least 
Python *2.7*. The table below hopes to clarify the versions you can expect:

| Operating System | Python Version | PIP Version | Notes  |
| ---------------- | -------------- | ----------- | ------ |
| Ubuntu           | *2.7.6*        | *1.5*       | -      |
| CentOS           | *2.7.5*        | *7.1*       | -      |

Because the exact version installed cannot be guaranteed by this role, you should be careful if using depending on this 
role in another role or a project that relies on Python. If any version of Python 2.7 is acceptable this role is 
suitable, however where you depend on some feature added to minor releases (e.g. *2.1*) this role is unsuitable.

This ambiguity, and the differences in the version of PIP available are both considered limitations.
See the *limitations* section for more information.

### Development packages

Unusually for a BARC role this role will install development libraries as well as run-time libraries for Python. This 
is to allow modules which build native extensions to be installed.

### Typical playbook

```yaml
---

- name: ...
  hosts: all
  become: yes
  vars: []
  roles:
    - bas-ansible-roles-collection.python2
```

### Tags

BARC roles use standardised tags to control which aspects of an environment are changed by roles.
Tasks in this role will 'tag' themselves with these tags as appropriate, typically in `tasks/main.yml`.

More information is available in the
[BARC General Documentation](https://antarctica.hackpad.com/BARC-Overview-and-Policies-SzcHzHvitkt#:h=Appendix-B---BARC-Standardised)

### Variables

#### *python2_barc_role_name*

* **MUST NOT** be specified
* specifies the name of this role within the BAS Ansible Roles Collection (BARC) used for setting local facts
* see the *BARC roles manifest* section for more information
* example: `python2`

#### *python2_barc_role_version*

* **MUST NOT** be specified
* specifies the name of this role within the BAS Ansible Roles Collection (BARC) used for setting local facts
* see the *BARC roles manifest* section for more information
* example: `2.0.0`

## Developing

### Issue tracking

Issues, bugs, improvements, questions, suggestions and other tasks related to this package are managed through the
[BAS Ansible Roles Collection](https://jira.ceh.ac.uk/projects/BARC) (BARC) project on Jira.

This service is currently only available to BAS or NERC staff, although external collaborators can be added on request.
See our contributing policy for more information.

More information is also available in the
[BARC General Documentation](https://antarctica.hackpad.com/BARC-Overview-and-Policies-SzcHzHvitkt#:h=Issue-Tracking)

### Source code

All changes should be committed, via pull request, to the canonical repository:

`ssh://git@stash.ceh.ac.uk:7999/barc/python2.git`

A read-only mirror of this repository is maintained on GitHub:

`git@github.com:bas-ansible-roles-collection/python2.git`

More information is available in the
[BARC General Documentation](https://antarctica.hackpad.com/BARC-Overview-and-Policies-SzcHzHvitkt#:h=Source-Code)

### Contributing policy

This role welcomes contributions, see `CONTRIBUTING.md` for our general policy.

### Release procedure

The general release procedure for BARC roles is available in the
[BARC General Documentation](https://antarctica.hackpad.com/BARC-Overview-and-Policies-SzcHzHvitkt#:h=Release-procedures)

## Licence

Copyright 2016 NERC BAS.

Unless stated otherwise, all documentation is licensed under the Open Government License - version 3.
All code is licensed under the MIT license.

Copies of these licenses are included within this role.
