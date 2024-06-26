#                      open-vm-tools 12.4.5 Release Notes

Updated on: 27 June 2024

open-vm-tools | 27 JUNE 2024 | Build 23787635

Check back for additions and updates to these release notes.

## What's in the Release Notes

The release notes cover the following topics:

* [What's New](#whatsnew) 
* [End of Feature Support Notice](#endsupport)
* [Internationalization](#i18n) 
* [Guest Operating System Customization Support](#guestop) 
* [Interoperability Matrix](#interop) 
* [Resolved Issues](#resolvedissues) 
* [Known Issues](#knownissues)

## <a id="whatsnew" name="whatsnew"></a>What's New


*   Please see the [Resolved Issues](#resolvedissues) and [Known Issues](#knownissues) sections below.

*   A complete list of the granular changes in the open-vm-tools 12.4.5 release is available at:

    [open-vm-tools ChangeLog](https://github.com/vmware/open-vm-tools/blob/stable-12.4.5/open-vm-tools/ChangeLog)

## <a id="endsupport" name="endsupport"></a>End of Feature Support Notice

*   Discontinued: Using "xml-security-c" and "xerces-c" to build the VMware Guest Authentication Service (VGAuth)

    Starting with open-vm-tools 12.4.0, and going forward, the VGAuth service build will require the "xmlsec1" and "libxml2" development and runtime packages.  If still using the "xml-security-c" and "xerces-c" open source projects to build open-vm-tools, you must make the change now.  The open-vm-tools 12.3.x series will be the last version that can use "xml-security-c" and "xerces-c".

## <a id="i18n" name="i18n"></a>Internationalization

open-vm-tools 12.4.5 is available in the following languages:

* English
* French
* German
* Spanish
* Italian
* Japanese
* Korean
* Simplified Chinese
* Traditional Chinese

## <a id="guestop" name="guestop"></a>Guest Operating System Customization Support

The [Guest OS Customization Support Matrix](http://partnerweb.vmware.com/programs/guestOS/guest-os-customization-matrix.pdf) provides details about the guest operating systems supported for customization.

## <a id="interop" name="interop"></a>Interoperability Matrix

The [VMware Product Interoperability Matrix](http://partnerweb.vmware.com/comp_guide2/sim/interop_matrix.php) provides details about the compatibility of current and earlier versions of VMware Products. 

## <a id="resolvedissues" name ="resolvedissues"></a> Resolved Issues

*   **A number of issues flagged by Coverity and ShellCheck have been addressed.**

      The changes include code fixes and Coverity escapes for reported false positives.

*   **Permission on the vmware-network.log file incorrecly defaults to (0644).**

    Fixed in this release;   The correct default is set to (0600).

*   **The NetworkManager calls in the Linux "network" have been updated.**

    Defaults to using the "Sleep" method over the "Enabled" method used to
    work around a 0.9.0 bug.

    Resolves :
      [Pull request #626](https://github.com/vmware/open-vm-tools/pull/699)
      [Issue #426](https://github.com/vmware/open-vm-tools/issues/426)

*   **Unused header files have been dropped from the current open-have been dropped from the **

*   **Accomodate newer releases of libxml2 and xmlsec1.**

    The configure.ac and VGAuth code updated to avoid deprecated functions and build options based on OSS product version.

## <a id="knownissues" name="knownissues"></a>Known Issues


*   **Shared Folders mount is unavailable on Linux VM.**

    If the **Shared Folders** feature is enabled on a Linux VM while it is powered off, the shared folders mount is not available on restart.

    Note: This issue is applicable to open-vm-tools running on VMware Workstation and VMware Fusion.

    Workaround:

    If the VM is powered on, disable and enable the **Shared Folders** feature from the interface. For resolving the issue permanently, edit **/etc/fstab** and add an entry to mount the Shared Folders automatically on boot.  For example, add the line:

    <tt>vmhgfs-fuse   /mnt/hgfs    fuse    defaults,allow_other    0    0</tt>

    For more information on how to configure VMware Tools Shared Folders, see [KB 60262](https://kb.vmware.com/s/article/60262)