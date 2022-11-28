**open-vm-tools 12.1.5 release based on build 20735119**

Please refer to the release notes at https://github.com/vmware/open-vm-tools/blob/stable-12.1.5/ReleaseNotes.md

The granular changes that have gone into the 12.1.0 release are in the ChangeLog at https://github.com/vmware/open-vm-tools/blob/stable-12.1.5/open-vm-tools/ChangeLog

There are no new features in the open-vm-tools 12.1.5 release.  This is primarily a maintenance release that addresses a few potential problems, including:

  - The deployPkg plugin may prematurely reboot the guest VM before cloud-init has completed user data setup
  - A SIGSEGV may be encountered when a non-quiescing snapshot times out.
  - A number of Coverity reported issues have been addressed.

- For issues resolved in this release, see the [Resolved Issues ](https://github.com/vmware/open-vm-tools/blob/stable-12.1.5/ReleaseNotes.md#resolved-issues) section of the Release Notes.

