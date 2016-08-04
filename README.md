localcloud-vboxguest
=========

This role is designed for installing VirtualBox guest additions into VMs. This is mostly needed when doing local development with vagrant, but may be also useful otherwise. It will download guest additions iso image from oracle and perform required instalation steps.

Requirements
------------

This role has been tested on Ubuntu 14.04 LTS, but since it only uses generic linux commands it should work fine on other distributions. The installed guest additions are intended for all distributions. The only requirement is that **Guest additions must match your VirtualBox version** 

Role Variables
--------------

`vboxguest_version ` Specifies what version of guest additions you wish to install. We try to maintain this to be mostly recent, but you better set this up yourself to what your VirtualBox version is.

Dependencies
------------

This role has no external dependencies.

Example Playbook
----------------

Please note that this role does force install, because there's currently no way to find out what version of guest additions is installed. For that reason you probably don't want to run this role every time, but only on initial box setup (or later if you need to upgrade)

    - hosts: servers
      roles:
         - dmitrybelyakov.localcloud-vboxguest
      vars: 
      		vboxguest_version: '5.0.16'

License
-------

The MIT License (MIT) Copyright (c) 2016 Dmitry Belyakov

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.


