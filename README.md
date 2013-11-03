puppet-cvmfs
======

Puppet module for managing CVMFS.

#### Table of Contents
1. [Overview - What is the cvmfs module?](#overview)

Overview
--------

This module is intended to be used to manage CVMFS customizations. CVMFS is an HTTP based filesystem,
part of the [CernVM](http://cernvm.cern.ch) project.
Currently only the client customizations are supported.

Usage
-----

### Example

This is a simple example to add the atlas and sft CERN repositories, using a quota limit of 10GB for the cache
size and a local squid proxy mysqui.example.com:3128. The module will use the current defaults:

* repositories = 'sft.cern.ch'
* quota_limit = 30000
* no http_proxy

**Defining a cvmfs client customization**

```cvmfs
class { 'cvmfs::client':
    repositories => 'atlas.cern.ch,sft.cern.ch',
    quota_limit  => 30000,
    http_proxy   => 'mysquid.example.com:3128'
}
```

Limitations
------------

* Only the client customizations are currently supported

Contributors
------------

* https://github.com/desalvo/puppet-cvmfs/graphs/contributors

Release Notes
-------------

**0.1.0**

* Initial version
