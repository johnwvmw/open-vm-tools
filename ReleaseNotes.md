#                      Open-vm-tools 12.1.5 Release Notes

Updated on: 29th NOV 2022

Open-vm-tools | 29th NOV 2022 | Build BLD-nnnnnn

Check back for additions and updates to these release notes.

## What's in the Release Notes

The release notes cover the following topics:

* [What's New](#whatsnew) 
* [Internationalization](#i18n) 
* [End of Feature Support Notice](#endoffeaturesupport) 
* [Guest Operating System Customization Support](#guestop) 
* [Interoperability Matrix](#interop) 
* [Resolved Issues](#resolvedissues) 
* [Known Issues](#knownissues)

## <a id="whatsnew" name="whatsnew"></a>What's New

*  Guest customization (deployPkg plugin) has been modified to allow Perl base Linux customization better work in concert with cloud-init when updating user data and configuring the network.

*   Please see the [Resolved Issues](#resolvedissues) and [Known Issues](#knownissues) sections below.


## <a id="i18n" name="i18n"></a>Internationalization

Open-vm-tools 12.1.5 is available in the following languages:

* English
* French
* German
* Spanish
* Italian
* Japanese
* Korean
* Simplified Chinese
* Traditional Chinese

## <a id="endoffeaturesupport" name="endoffeaturesupport"></a>End of Feature Support Notice

 * The tar tools (linux.iso) and OSPs shipped with VMware Tools 10.3.x release will continue to be supported. However, releases after VMware Tools 10.3.5 will only include critical and security fixes. No new feature support will be provided in these types of VMware Tools (tar tools and OSP's). It is recommended that customers use open-vm-tools for those operating systems that support open-vm-tools. For more information about open-vm-tools, see [KB 2073803](https://kb.vmware.com/s/article/2073803).

## <a id="guestop" name="guestop"></a>Guest Operating System Customization Support
The [Guest OS Customization Support Matrix](http://partnerweb.vmware.com/programs/guestOS/guest-os-customization-matrix.pdf) provides details about the guest operating systems supported for customization.

## <a id="interop" name="interop"></a>Interoperability Matrix

The [VMware Product Interoperability Matrix](http://partnerweb.vmware.com/comp_guide2/sim/interop_matrix.php) provides details about the compatibility of current and earlier versions of VMware Products. 

## <a id="resolvedissues" name ="resolvedissues"></a> Resolved Issues

*   **A number of Coverity reported issues have been addressed.**

*   **The deployPkg plugin may prematurely reboot the guest VM before cloud-inithas completed user data setup.**

    If both the Perl based Linux customization script and cloud-init run when the guest VM boots, the Perl script may disable the network or reboot the guest before cloud-init has finished.  The deployPkg plugin has been updated to wait for a running cloud-init process to finish before the guest VM reboot is initiated.

    This issue is fixed in this release.

*   **A SIGSEGV may be encountered when a non-quiesing snapshot times out.**

    This issue is fixed in this release.

*   **Unwanted vmtoolsd service error message if not on a VMware hypervisor.**

    When open-vm-tools comes preinstalled in a base Linux release, the vmtoolsd services are started automatically at system start and desktop login.  If running on physical hardware or in a non-VMware hypervisor, the services will emit an error message to the systemd's logging service before stopping.

    This issue is fixed in this release.

*   **A complete list of the granular changes in the open-vm-tools 12.1.5 release is available at:**

    [Open-vm-tools ChangeLog](https://github.com/vmware/open-vm-tools/blob/stable-12.1.5/open-vm-tools/ChangeLog)

## <a id="knownissues" name="knownissues"></a>Known Issues


*   **Shared Folders mount is unavailable on Linux VM.**

    If the **Shared Folders** feature is enabled on a Linux VM while it is powered off, the shared folders mount is not available on restart.

    Note: This issue is applicable to open-vm-tools running on VMware Workstation and VMware Fusion.

    Workaround:

    If the VM is powered on, disable and enable the **Shared Folders** feature from the interface. For resolving the issue permanently, edit **/etc/fstab** and add an entry to mount the Shared Folders automatically on boot.  For example, add the line:

    <tt>vmhgfs-fuse   /mnt/hgfs    fuse    defaults,allow_other    0    0</tt>

