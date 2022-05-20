
## My version of Linux is not recognized.  How do I add my Linux name to the known list?##

The open-vm-tools source contains a table mapping the guest distro name to the officially recognized short name.  __Please do not submit pull requests altering this table and associated code.__  Any changes here must be accompanied by additional changes in the VMware host.  Values that are not recognized by the VMware host will be ignored. 

If you are interested in extending this table, do not send a pull request.  Instead, submit a request via the [open-vm-tools github issue tracker](https://github.com/vmware/open-vm-tools/issues).

Use the appropriate generic Linux designation when configuring a VM for your Linux version.  The selection available will vary by virtual hardware version being used.
- Other 5.x or later Linux (64-bit)
- Other 5.x or later Linux (64-bit)
- Other 4.x Linux (64-bit)
- Other 4.x Linux (32-bit)
- Other 3.x Linux (64-bit)
- Other 3.x Linux (32-bit)
- Other Linux (64-bit)
- Other Linux (32-bit)
