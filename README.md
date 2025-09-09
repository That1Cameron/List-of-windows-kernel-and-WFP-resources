### WFP (Windows Filtering Platform):
* https://scorpiosoftware.net/2022/12/25/introduction-to-the-windows-filtering-platform/
* https://blog.quarkslab.com/guided-tour-inside-windefenders-network-inspection-driver.html
* https://learn.microsoft.com/en-us/windows-hardware/drivers/network/introduction-to-windows-filtering-platform-callout-drivers
* https://learn.microsoft.com/en-us/samples/microsoft/windows-driver-samples/windows-filtering-platform-sample/
* https://learn.microsoft.com/en-us/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpscalloutregister0
* https://learn.microsoft.com/en-us/windows/win32/fwp/management-filtering-layer-identifiers-

### inverted call model (overlaps with IoCTL):
* https://www.osr.com/nt-insider/2013-issue1/inverted-call-model-kmdf/
* https://www.osronline.com/article.cfm%5eid=94.htm (old version of ^)
* https://github.com/OSRDrivers/Inverted  
  ##### (usermode service side)
* https://learn.microsoft.com/en-us/dotnet/api/microsoft.win32.safehandles.safefilehandle?view=net-9.0
* https://learn.microsoft.com/en-us/dotnet/api/system.threading.waithandle.waitone?view=net-9.0#system-threading-waithandle-waitone
* https://learn.microsoft.com/en-us/answers/questions/1726443/how-to-call-fsctl-get-ntfs-volume-data-ioctl-from
* https://learn.microsoft.com/en-us/dotnet/framework/windows-services/how-to-add-installers-to-your-service-application (not requried)

### IoCTL:
* https://www.ired.team/miscellaneous-reversing-forensics/windows-kernel-internals/sending-commands-from-userland-to-your-kernel-driver-using-ioctl
* https://www.osronline.com/article.cfm%5Eid=92.htm
* https://learn.microsoft.com/en-us/windows-hardware/drivers/ddi/wdm/nf-wdm-iocreatesymboliclink
* https://learn.microsoft.com/en-us/windows/win32/api/ioapiset/nf-ioapiset-deviceiocontrol
* https://learn.microsoft.com/en-us/windows-hardware/drivers/gettingstarted/i-o-request-packets
* https://learn.microsoft.com/en-us/windows-hardware/drivers/ddi/wdm/ns-wdm-_irp
* https://learn.microsoft.com/en-us/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_status_block
* https://learn.microsoft.com/en-us/windows-hardware/drivers/kernel/using-the-system-s-cancel-spin-lock
* https://learn.microsoft.com/en-us/windows-hardware/drivers/ddi/wdm/nf-wdm-ioacquirecancelspinlock
* https://ericasselin.com/userlandkernel-communication-deviceiocontrol-method

### General kernel:
* https://www.youtube.com/watch?v=n463QJ4cjsU
* https://stackoverflow.com/questions/16569526/what-is-the-difference-between-a-wdm-driver-a-kmdf-driver-and-a-umdf-driver
* https://learn.microsoft.com/en-us/windows-hardware/drivers/gettingstarted/
* https://www-user.tu-chemnitz.de/~heha/oney_wdm/ch02b.htm
* https://learn.microsoft.com/en-us/openspecs/windows_protocols/ms-erref/596a1078-e883-4972-9bbc-49e60bebca55
* https://learn.microsoft.com/en-us/windows-hardware/drivers/kernel/introduction-to-spin-locks
* https://learn.microsoft.com/en-us/windows-hardware/drivers/ddi/wdm/nf-wdm-ioqueueworkitem <- important
* https://www-user.tu-chemnitz.de/~heha/oney_wdm/ch04c.htm#:~:text=DISPATCH_LEVEL%20is%20so%20called%20because,SYNCH_LEVEL%2C%20if%20you%20care.) <- very important to mind the context callbacks register to (wfp callbacks register to DISPATCH_LEVEL, heavy operations like IoCTL responses in this layer will cause BSoD)

### other:
* https://www.mdsec.co.uk/2020/12/bypassing-user-mode-hooks-and-direct-invocation-of-system-calls-for-red-teams/
* https://learn.microsoft.com/en-us/windows/win32/api/processthreadsapi/nf-processthreadsapi-createprocessasusera
* https://learn.microsoft.com/en-us/windows-hardware/drivers/ddi/ntddk/nf-ntddk-zwterminateprocess
