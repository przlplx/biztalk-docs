---
description: "Learn more about: HIS VSS Writer"
title: "VSS Writer"
ms.custom: ""
ms.date: "11/30/2017"
ms.prod: "host-integration-server"
ms.reviewer: ""
ms.suite: ""
ms.topic: "article"
---
# HIS VSS Writer
## Purpose  
 The Host Integration Server VSS Writer Service provides added functionality for backup and restore of Host Integration Server through the Volume Shadow Copy Service framework.  The Host Integration Server Writer Service is installed automatically.  
  
## Volume Shadow Copy Service  
 The VSS is a set of COM APIs that implements a framework to allow volume backups to be performed while applications on a system continue to write to the volumes. The VSS provides a consistent interface that allows coordination between user applications that update data on disk (writers) and those that back up applications (requestors).  
  
 The VSS captures and copies stable images for backup on running systems, particularly servers, without unduly degrading the performance and stability of the services they provide. For more information on the VSS, see your Windows documentation.  
  
## Permissions  
 The Host Integration Server VSS Writer service must run under the Local System account.  
  
## Features  
 Host Integration Server VSS Writer supports backup and restore of the following components.  
  
|Component|Description|  
|---------------|-----------------|  
|*ComCfg*|SNA Gateway configuration (com.cfg)|  
|*HostEmulator.exe.config*|TN3270 Emulator configuration|  
|*MsDrdaService.exe.config*|MS DRDA Service configuration|  
|*HipService.exe.config*|HIP Service configuration|
