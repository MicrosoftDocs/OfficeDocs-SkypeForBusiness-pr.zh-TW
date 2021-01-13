---
title: 商務用 Skype Server 的防病毒掃描排除
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5d742259-ef3b-417a-920b-e1fa0e48f043
description: 與商務用 Skype Server 的防病毒掃描程式互用性。
ms.openlocfilehash: b59a5c474a96d312ebe3a648536ebe827e684931
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832263"
---
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server"></a>商務用 Skype Server 的防病毒掃描排除

與商務用 Skype Server 的防病毒掃描程式互用性。

為了確保防病毒掃描程式不會干擾商務用 Skype Server 的運作，您必須針對每個執行防病毒掃描程式的商務用 Skype Server 伺服器或伺服器角色排除特定的程式和目錄。 應該排除下列程式和目錄：

> [!NOTE]
> 下列列出的資料夾和檔案位置是商務用 Skype Server 的預設位置。 針對您未使用預設值的任何位置，請排除您為組織所指定的位置，而不是本主題中指定的預設位置。

> [!IMPORTANT]
> 請注意，某些防毒程式可能需要絕對的相對路徑，其排除清單。

- 商務用 Skype 伺服器處理常式：

  - ABServer.exe

  - ASMCUSvc.exe

  - AVMCUSvc.exe

  - ChannelService.exe

  - ClsAgent.exe

  - ComplianceService.exe

  - DataMCUSvc.exe

  - DataProxy.exe

  - FileTransferAgent.exe

  - HealthAgent.exe

  - IMMCUSvc.exe
  
  - LyncBackupService.exe

  - LysSvc.exe

  - MasterReplicatorAgent.exe

  - MediaRelaySvc.exe

  - MediationServerSvc.exe

  - MRASSvc.exe

  - OcsAppServerHost.exe

  - ReplicaReplicatorAgent.exe

  - ReplicationApp.exe

  - RtcHost.exe

  - RTCSrv.exe

  - XmppProxy.exe

  - XmppTGW.exe

- Windows Fabric 主機服務處理常式：

  - Fabric.exe

  - FabricDCA.exe

  - FabricHost.exe

- IIS 處理常式：

  - % systemroot% \system32\inetsrv\w3wp.exe

  - % systemroot% \SysWOW64\inetsrv\w3wp.exe

- SQL Server Back-End 處理常式：

    > [!NOTE]
    > 請注意，這些路徑是 SQL Server 版本特有的。

  - %ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe

  - %ProgramFiles%\Microsoft SQL Server\MSRS11。MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe

  - %ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe

- SQL Server Front-End 處理常式：

  - %ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe

  - %ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe

  - Standard Edition 安裝 RTC 實例

  - %ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe

- 目錄及檔案：

  - %systemroot%\System32\LogFiles

  - %systemroot%\SysWow64\LogFiles

  - %systemroot%\Microsoft.NET\assembly\ GAC_MSIL

    > [!NOTE]
    > 請注意，這些路徑是商務用 Skype Server 版本特有的。

  - %programfiles%\Skype for Business Server 2015

  - %programfiles%\Common Files\Skype for Business Server 2015 \ 觀察程式節點

  - %programfiles%\Common Files\Skype for Business Server 2015

  - %programfiles%\Common Files\Skype for Business Online

  - %SystemDrive%\RtcReplicaRoot

  - 在拓撲產生器) 中指定的檔案共用儲存區 (。 檔存放區是在拓撲產生器中指定的。

  - SQL Server 資料和記錄檔，包括後端資料庫、使用者存放區、封存儲存區、監控儲存區及應用程式存放區的檔案。 您可以在拓撲產生器中指定資料庫和記錄檔。 如需每個資料庫之資料和記錄檔（包括預設名稱）的詳細資訊，請參閱部署檔中的 [SQL Server 資料和記錄檔位置](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) 。

  - SQL Server 資料和記錄檔，包括前端資料庫、商務用 Skype 書店和 RtcDatabase 存放區的檔案。 它們通常是在%localdrive%\CSData。


