Smild integrator
=========

A ansible role for Integration testing.

Requirements
------------

* Ansible 2.0 or later
* Smild 3.0 or later

Role Variables
--------------

    project_root_dir: "{{playbook_dir}}/../"                                                # the root path of project
    project_integration_test_dir: "{{playbook_dir}}/../repositories"                        # the path will contains the projects to test the integration
    project_to_integrate: null                                                              # Git parameters of project in which test the integration                                                
    project: null                                                                           # Git parameters of project that you want to test                                               

Dependencies
------------

* [Ansible role - tierratelematics.smild-ansible](https://galaxy.ansible.com/tierratelematics/smild-ansible/)
* [Ansible library - json_file_replacer](https://github.com/tierratelematics/ansible-json-file-replacer)

Example Playbook
----------------

    - hosts: localhost
      connection: local

      roles:
        - { role: tierratelematics.smild-integrator,
            project_to_integrate: {
                                     "project_name": "project-name",
                                     "repo_url": "git-url",
                                     "branch": "git-branch"
                                  },
            project: {
                      "project_name": "project-name",
                      "repo_url": "git-url",
                      "branch": "git-branch"
                   }
          }


License
-------

Copyright 2017 Tierra SpA

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

[http://www.apache.org/licenses/LICENSE-2.0](http://www.apache.org/licenses/LICENSE-2.0)

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.