**open-vm-tools 12.3.0 release based on build 22234872**

Please refer to the Release Notes at https://github.com/vmware/open-vm-tools/blob/stable-12.3.0/ReleaseNotes.md

The granular changes that have gone into the 12.3.0 release are in the ChangeLog at https://github.com/vmware/open-vm-tools/blob/stable-12.3.0/open-vm-tools/ChangeLog

There are no new features in the open-vm-tools 12.3.0 release.  This is primarily a maintenance release that addresses a few critical problems, including:

  - This release resolves CVE-2023-20900. For more information on this vulnerability and its impact on VMware products, see https://www.vmware.com/security/advisories/VMSA-2023-0019.html.
  - A tools.conf configuration setting is available to temporaily direct Linux quiesced snaphots to restore pre open-vm-tools 12.2.0 behavior of ignoring file systems already frozen.
  - Building of the VMware Guest Authentication Service (VGAuth) using "xml-security-c" and "xerces-c" is being deprecated.
  - A number of Coverity reported issues have been addressed.
  - A number of GitHub issues and pull requests have been handled. Please see the Resolves Issues section of the Release Notes.

- For issues resolved in this release, see the [Resolved Issues ](https://github.com/vmware/open-vm-tools/blob/stable-12.3.0/ReleaseNotes.md#resolved-issues) section of the Release Notes.

