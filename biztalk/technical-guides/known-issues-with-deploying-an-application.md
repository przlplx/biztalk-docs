---
title: "Known Issues with Deploying an Application | Microsoft Docs"
ms.custom: ""
ms.date: "06/08/2017"
ms.prod: "biztalk-server-2013"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7e5fb4f6-f9bd-4322-93f9-723e9e3c3317
caps.latest.revision: 2
author: "MandiOhlinger"
ms.author: "mandia"
manager: "anneta"
---
# Known Issues with Deploying an Application
## Deploying a BizTalk Application  
 **Deploying an updated application requires correcting references**  
  
 If you deploy an entirely new application to replace an existing application, you must correct any references between other applications and the application that you are replacing.  
  
 **Using Visual Studio to deploy an application can stop applications**  
  
> [!NOTE]  
>  We recommend that you avoid using Visual Studio to deploy an application into a production environment.  
  
 If you use Visual Studio to deploy an application into a production environment and the Restart Host Instances option is set to True in project properties, all host instances will restart when you deploy the application, including those that are not associated with this application. This will stop all other applications that are running on any host instance on the local computer.  
  
## Adding Artifacts to a BizTalk Application  
 **Moving an artifact can move dependencies**  
  
 When you move an artifact to a new application, any other artifacts on which it has dependencies are also moved unless the new application has a reference to the application(s) containing the artifacts that the moved artifact depends upon. Also, any artifacts that have dependencies on the moved artifact also will be moved unless the application(s) containing them have a reference to the new application. When moving an artifact, you will be shown the list of other artifacts that will also be moved. For instructions on moving an artifact, see [How to Move an Artifact to a Different Application](http://go.microsoft.com/fwlink/?LinkId=154999) (http://go.microsoft.com/fwlink/?LinkId=154999).  
  
## Exporting a BizTalk Application  
 **An incorrect error can be displayed when installing an .msi file on Windows Vista**  
  
 When installing an .msi package exported using [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)] on [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] running on Windows Vista®, you may receive the following incorrect error, "The installer has encountered an unexpected error installing this package. This may indicate a problem with this package. The error code is 2869." To correct this error, first import the package using [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] and then re-export and install the package.  
  
## Importing a BizTalk Application  
 **Passwords are not removed from binding files added to an application**  
  
 For security reasons, during application export, passwords are removed from application bindings. They are not, however, removed from any binding files that were added to the application. After importing the application, you will need to reconfigure the passwords in order for the application to function. You can do this by editing the binding file or by using the Administration console. For more information about editing a binding file, see [Customizing Binding Files](http://go.microsoft.com/fwlink/?LinkId=155000) (http://go.microsoft.com/fwlink/?LinkId=155000). For more information about configuring security for adapters, see [Using Adapters](http://go.microsoft.com/fwlink/?LinkId=155001) (http://go.microsoft.com/fwlink/?LinkId=155001).  
  
 **BizTalk Server does not roll back scripted imports or installs**  
  
 If an import fails, BizTalk Server rolls back all import operations except for any actions performed by custom scripts. This is also true for install and uninstall operations.  
  
 **A missing schema might not be reported after an import**  
  
 If you create a filter for a send port in one application that uses a property schema in another application, and then import the first application into a new BizTalk group, you will not receive a warning that the schema is missing, and filtering will not function when the application is installed and started. You can correct the problem by importing the application that contains the schema before you install the application that does not contain the schema.  
  
## See Also  
 [Deploying an Application](../technical-guides/deploying-an-application.md)