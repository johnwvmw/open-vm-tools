**open-vm-tools 12.2.0 release based on build 21223074**

Please refer to the release notes at https://github.com/vmware/open-vm-tools/blob/stable-12.2.0/ReleaseNotes.md

The granular changes that have gone into the 12.2.0 release are in the ChangeLog at https://github.com/vmware/open-vm-tools/blob/stable-12.2.0/open-vm-tools/ChangeLog

There are no new features in the open-vm-tools 12.2.0 release.  This is primarily a maintenance release that addresses a few critical problems, including:

  - Linux quiesced snapshots have been updated to avoid intermittent hangs of the vmtoolsd process.
  - Updated the guestOps to handle some edge cases when File_GetSize() fails or returns -1.
  - A number of Coverity reported issues have been addressed.
  - Detect the proto files for the containerd grpc client in alternate locations.
      - [Pull request #626](https://github.com/vmware/open-vm-tools/pull/626)
  - FreeBSD: Support newer releases and code clean-up for earlier versions.
      - [Pull request #584](https://github.com/vmware/open-vm-tools/pull/584)

- For issues resolved in this release, see the [Resolved Issues ](https://github.com/vmware/open-vm-tools/blob/stable-12.2.0/ReleaseNotes.md#resolved-issues) section of the Release Notes.

