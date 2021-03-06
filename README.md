log4j_detector_on_java
=========

A brief description of the role goes here.

Requirements
------------

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

Role Variables
--------------
example:
log4j_detector_on_java_openjdk:
   version: '8u292-b10'
   checksum: 'b51ef522d35b23ee2469bb2324b365ffdd9773420329ece675bdfcf1b9365ae4'
   install_from_files_directory: yes
   remove: no

log4j_detector_on_java_log4j:
   version: '2021.12.20'
   checksum: '5bfdb4d60809f363218f238496d0c591de0a2565b40edb9b10d586024d9533d5'
   nice: 0
   opts: '-Xmx1024m'
   install_from_files_directory: yes
   path_search: '/'
   argument: --exclude='["/home"]'
   remove: no

log4j_detector_on_java_file_result:
   path_report_on_controlled_node:
   create: yes
   filename:
   csv:

log4j_detector_on_java_dir_work: /opt/log4j_detector_on_java
log4j_detector_on_java_dir_openjdk: "{{ log4j_detector_on_java_dir_work }}/openlogic-openjdk-jre-{{ log4j_detector_on_java_openjdk.version }}-linux"
log4j_detector_on_java_path_java: "{{ log4j_detector_on_java_dir_openjdk }}/bin/java"

log4j_detector_on_java_dir_create:
  - "{{ log4j_detector_on_java_dir_work }}"
  - "{{ log4j_detector_on_java_dir_openjdk }}"

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: username.rolename, x: 42 }

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
