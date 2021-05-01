# Welcome to GitHub Desktop!

This is your README. READMEs are where you can communicate what your project is and how to use it.

Write your name on line 6, save it, and then head back to GitHub Desktop.
- hosts: mikrotik-test
   connection: network_cli
   gather_facts: true
   ignore_errors: yes

   vars:
     name1: 'ops1'
     name2: 'y.yudin'

   tasks:
     - name: disable user name1
       routeros_command:
        commands: '/user set disabled=yes [find where name={{ name1 }}]'
     - name: disable user (name2)
       routeros_command:
        commands: '/user set disabled=yes [find where name={{ name2 }}]'
     - name: disable ppp-secret name1
       routeros_command:
        commands: '/ppp secret set disabled=yes [find where name={{ name1 }}]'
     - name: disable ppp-secret name2
       routeros_command:
        commands: '/ppp secret set disabled=yes [find where name={{ name2 }}]'
#    - name: show disabled users/ppp
#      routeros_command:
#        commands: '/user print where [find disabled=[yes]]'
#        register: cmdout
#     - debug:
#         var: cmdout.stdout_lines
#        commands: '/ppp secret print [find where disabled=[yes]]'
#        register: cmdout
 #    - debug:
 #        var: cmdout.stdout_lines