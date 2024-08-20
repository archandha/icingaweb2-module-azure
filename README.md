Microsoft Azure director importer module for Icinga Web 2
=========================================================

This is a simple Azure module for Icinga Web 2. Currently implented is an
Import Source provider for [Icinga Director](https://github.com/Icinga/icingaweb2-module-director).
It can import either virtual machines, load blanacers or application gateways
from all, one or multiple resource groups availsable to the given api
credentials.

This data can be used to be deployed immediately as new (virtual) hosts to your
[Icinga](https://www.icinga.org/) monitoring system.


Documentation
-------------

### Basics
 * [Installation](doc/01-Installation.md)
 * [ImportSource](doc/02-ImportSource.md)
 * [Fields queried](doc/05-FieldsQueried.md)
 * [Troubleshooting](doc/99-Troubleshooting.md)

Furthermore, there is a [ChangeLog](ChangeLog) file.

Please note, the project is work in progress. The **MASTER** will not
necessarily reflect a working copy of this software. Anything tested and
working will be tagged with a version number. Usually these tags are gpg
signed, too.

This module is released under the MIT License.

https://github.com/credativ/icingaweb2-module-azure/blob/master/LICENSE

Even if the releases are tagged and signed, there can no additional
warranty or liability be derived from this. MIT license applies.

For your convinience, you will find these tagged versions under the
[releases tab here on GitHub](https://github.com/credativ/icingaweb2-module-azure/releases).

Implemented features
--------------------

Currently, we have some resources implemented in this importer module:

* Application Gateways
* Container Registries
* Express Route Circuits
  * Peerings for Express Route Circuits
  * Authorizations for Express Route Circuits
* Load balancers
* Microsoft.DBforPostgreSQL servers (SAAS)
  * PostgreSQL Databases
  * PostgreSQL Configurations
  * PostgreSQL Firewall rules
  * PostgreSQL Security Alert Policies *)
  * PostgreSQL Virtual network rules
  * PostgreSQL Location based performance tiers
* Resource Groups
* Subscriptions
* Virtual machines
  * Disks for virtual machines
  * Network Interfaces for virtual machines

While the majority of the classes are tested and should be working smoothly,
the Container Registries as well as the PostgreSQL subtypes are considered
not intensively tested currently.

*) PostgreSQL Security Alert Policies are untested by the time of writing.
Please note for PostgreSQL Security Alert Policies that there is no "list"
function in the Azure API implemented. So the importer has to be set up with
a white space separated list of names for the policies to query.


The list of implemented features will be enhanced with any release step by step.
If you miss something, we would appreciate an open issue on this here on GitHub.
The same applies for missing fields on the import types. If you like to support
the development, you are very welcome to send pull requests. As a non
programmer, you can support this module to. For this, please contact our sales
department. (cf. "Support" down this page)


![Query types](/doc/screenshot/azure_object_types.png)

The importer can deal with multiple resource groups in a subscription. You can
either query any of these or select one or more while configuring it.

Troubleshooting should be easy as the **Azure Importer** does send log
information through the IcingaWeb2 logging pipeline. Just have your IcingaWeb2
logging configured and make sure that you get INFO level messages as well.


Dependencies
------------

This module has no dependencies on any SDK or other external files except
for the php-curl extension, which must be enabled.


Credits
-------

This module makes use of

https://github.com/tcdent/php-restclient

published under the MIT license. The REST client code was slightly modified to
fit into namespaces and uses valid exception classes suitable for IcingaWeb2

The code was inspired by the
[Icinga Web 2 module for vSphere](https://github.com/Icinga/icingaweb2-module-vsphere)
as well as by the
[AWS module for Icinga Web 2](https://github.com/Icinga/icingaweb2-module-aws).


Support
-------

The *icingaweb2-module-azure* is an open source project developed by
credativ. credativ offers technical support as well as installation
and integration support for this. If you are interested or need additional
features, please feel free to contact us.

* **Web** [credativ.de](https://credativ.de)
* **E-Mail:** [info@credativ.de](mailto:info@credativ.de)
* **Phone:** [+49 2166 9901-0](tel:+49216699010)
