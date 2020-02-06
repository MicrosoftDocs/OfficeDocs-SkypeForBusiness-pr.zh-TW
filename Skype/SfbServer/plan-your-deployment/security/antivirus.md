---
title: 商務用 Skype Server 的防病毒掃描排除
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5d742259-ef3b-417a-920b-e1fa0e48f043
description: 與商務用 Skype Server 的防病毒掃描程式交互操作概覽。
ms.openlocfilehash: 10d296e36324fdbc8bca8f7da48370d619774501
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815691"
---
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server"></a>商務用 Skype Server 的防病毒掃描排除

與商務用 Skype Server 的防病毒掃描程式交互操作概覽。

若要確保防病毒掃描程式不會干擾商務用 Skype Server 的作業，您必須針對執行防病毒掃描程式的每個商務用 Skype 伺服器伺服器或伺服器角色排除特定程式和目錄。 下列處理常式與目錄應被排除：

> [!NOTE]
> 下列列出的資料夾和檔案位置是商務用 Skype Server 的預設位置。 針對您未使用預設值的任何位置，請排除您指定給組織的位置，而不是本主題中指定的預設位置。

> [!IMPORTANT]
> 請注意，某些防毒程式可能需要其排除清單的絕對（不是相對路徑）。

- 商務用 Skype Server 進程：

  - ABServer

  - ASMCUSvc

  - AVMCUSvc

  - ChannelService

  - ClsAgent

  - ComplianceService

  - DataMCUSvc

  - DataProxy

  - FileTransferAgent

  - HealthAgent

  - IMMCUSvc
  
  - LyncBackupService

  - LysSvc

  - MasterReplicatorAgent

  - MediaRelaySvc

  - MediationServerSvc

  - MRASSvc

  - OcsAppServerHost

  - ReplicaReplicatorAgent

  - ReplicationApp

  - RtcHost

  - RTCSrv

  - XmppProxy

  - XmppTGW

- Windows Fabric 主機服務處理常式：

  - 構造 .exe

  - FabricDCA

  - FabricHost

- IIS 處理常式：

  - %systemroot%\system32\inetsrv\w3wp.exe

  - %systemroot%\SysWOW64\inetsrv\w3wp.exe

- SQL Server 後端處理常式：

    > [!NOTE]
    > 請注意，這些路徑是 SQL Server 版本所特有的。

  - %ProgramFiles%\Microsoft SQL Server\MSSQL11。MSSQLSERVER\MSSQL\Binn\SQLServr.exe

  - %ProgramFiles%\Microsoft SQL Server\MSRS11。MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe

  - %ProgramFiles%\Microsoft SQL Server\MSAS11。MSSQLSERVER\OLAP\Bin\MSMDSrv.exe

- SQL Server 前端程式：

  - %ProgramFiles%\Microsoft SQL Server\MSSQL12。LYNCLOCAL\MSSQL\Binn\SQLServr.exe

  - %ProgramFiles%\Microsoft SQL Server\MSSQL12。RTCLOCAL\MSSQL\Binn\SQLServr.exe

  - 標準版安裝 RTC 實例

  - %ProgramFiles%\Microsoft SQL Server\MSSQL12。RTC\MSSQL\Binn\SQLServr.exe

- 目錄和檔案：

  - %systemroot%\System32\LogFiles

  - %systemroot%\SysWow64\LogFiles

  - %systemroot%\Microsoft.NET\assembly\ GAC_MSIL

    > [!NOTE]
    > 請注意，這些路徑是針對商務用 Skype 伺服器版本所特有。

  - 商務用%programfiles%\Skype Server 2015

  - %programfiles%\Common Files\Skype for Business Server 2015 \ 觀察程式節點

  - %programfiles%\Common Files\Skype for Business Server 2015

  - %programfiles%\Common Files\Skype for Business Online

  - %SystemDrive%\RtcReplicaRoot

  - [檔案共用] 存放區（在 [拓撲建立器] 中指定）。 檔案存放區是在拓撲建立器中指定。

  - SQL Server 資料和記錄檔案，包括後端資料庫、使用者儲存、封存儲存、監視儲存及應用程式存放區的檔案。 您可以在拓撲結構建立器中指定資料庫和記錄檔。 如需每個資料庫的資料與記錄檔（包括預設名稱）的詳細資料，請參閱部署檔中的[SQL Server 資料和記錄檔案位置](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx)。

  - SQL Server 資料和記錄檔案，包括前端資料庫、商務用 Skype 商店及 RtcDatabase 書店的檔案。 它們通常在%localdrive%\CSData. 下


