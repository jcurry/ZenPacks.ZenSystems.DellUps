==========================
ZenPacks.ZenSystems.DellUps
==========================


Description
===========

Provides support for Dell UPS devices with component and performance information for batteries.

Components
==========

The ZenPack has the following new Device Class
    * /Devices/Power/UPS/DellUps

     
    * Components are: 
        * DellUpsBattery   which has details for:
            * Various elements of battery status 

    * Modeler plugins are: 
        * DellUpsDeviceMap  
            * Gathers Hardware and Software manufacturer and product
            * Serial number
        * DellUpsBatteryMap  
            * Gathers Advanced Battery Monitoring (ABM) status
            * Battery test status

    * No device templates are provided in this ZenPack.

    * A component template is provided for DellUpsBattery which provides:
        * Data Sources  
            * Battery seconds remaining
            * Output instant headroom
            * Output present consumption 
        * Thresholds  
            * Low time remaining
        * Graph Definitions  
            * Battery seconds remaining
            * Output instant headroom
            * Output present consumption 
        * Event classes are provided for
            * /Power
            * /Power/Dell
            * /Power/Dell/battery with mappings for
                * UPS on battery
                * Battery low
                * Battery OK
            * /Power/Dell/utility with mapping for
                * Utility present
                * Utility not present

         

Requirements & Dependencies
===========================

    * Zenoss Versions Supported: 3.x and 4.x
    * External Dependencies: The Dell UPS MIB needs to be available on target devices
    * ZenPack Dependencies:
    * Note that the standard device class /Power/UPS needs to exist.  If not, recreate it.
    * Installation Notes: zenhub and zopectl restart after installing this ZenPack.
    * Configuration: 

Download
========
Download the appropriate package for your Zenoss version from the list
below.

* Zenoss 3.0+ `Latest Package for Python 2.6`_
* Zenoss 4.0+ `Latest Package for Python 2.7`_

Installation
============
Normal Installation (packaged egg)
----------------------------------
Copy the downloaded .egg to your Zenoss server and run the following commands as the zenoss
user::

   zenpack --install <package.egg>
   zenhub restart
   zopectl restart

Developer Installation (link mode)
----------------------------------
If you wish to further develop and possibly contribute back to this 
ZenPack you should clone the git repository, then install the ZenPack in
developer mode::

   zenpack --link --install <package>
   zenhub restart
   zopectl restart

Configuration
=============

Tested with Zenoss 3.1 and Zenoss 4.2 against various Dell UPSdevices

Change History
==============
* 1.0
   * Initial Release
* 1.1
   * Some updates for extra debug
* 1.2
   * Transferred to new github methods
* 2.0
   * Updated for Zenoss 4

Screenshots
===========
|DellUpsBatteriesComponent|


.. External References Below. Nothing Below This Line Should Be Rendered

.. _Latest Package for Python 2.6: https://github.com/downloads/jcurry/ZenPacks.ZenSystems.DellUps/ZenPacks.ZenSystems.DellUps-1.2-py2.6.egg
.. _Latest Package for Python 2.7: https://github.com/downloads/jcurry/ZenPacks.ZenSystems.DellUps/ZenPacks.ZenSystems.DellUps-2.0-py2.7.egg

.. |DellUpsBatteriesComponent| image:: http://github.com/jcurry/ZenPacks.ZenSystems.ApcUps/raw/master/screenshots/ApcUpsBatteries.jpg

                                                                        

