#    [GOSC] Update Guest OS Customization to utilize systemd system init

Currently the "telinit 6" command is used to reboot a Linux VM
following Guest OS Customization.  As the classic Linux init system,
SysVinit, is deprecated in favor of a newer init system, systemd,
the telinit command may not be available on the base Linux OS.

This change adds support to Guest OS Customization for the systemd init
system.  If the modern init system, systemd, is available, then a
"systemctl reboot" command will be used to trigger reboot.  Otherwise,
the "telinit 6" command will be used assuming the traditional init
system, SysVinit, is still available.

---

The accompanying patch **0001-GOSC-Update-Guest-OS-Customization-to-utilize-system.patch** can simply be dropped into the SLES open-vm-tools packaging source in the same directory as the existing **pam-vmtoolsd.patch** and **open-vm-tools.spec** files

Make the follow additions / changes to **open-vm-tools.spec**.

'
@@ -160,6 +160,7 @@ ExclusiveArch:  %ix86 x86_64 aarch64
 
 #SUSE specific patches
 Patch0:         pam-vmtoolsd.patch
+Patch1:         0001-GOSC-Update-Guest-OS-Customization-to-utilize-system.patch 
 
 %if 0%{?suse_version} >= 1500
 %systemd_ordering
@@ -263,6 +264,7 @@ sed -i -e "s/\r//" README
 
 #SUSE specific patches
 %patch0 -p2
+%patch1 -p2
 
 %build
 %if %{with_X}
'

Condition the application of the patch to specific releases if desired.
