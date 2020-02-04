---
title: Lync Server 2013：防毒掃描排除項目
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Antivirus scanning exclusions for Lync Server 2013
ms:assetid: 71e1f1cc-2d16-4111-9864-9276bf24dfe0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440138(v=OCS.15)
ms:contentKeyID: 57793042
ms.date: 11/03/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 90847830d9f2586e0d111846f2867400c52fc940
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737773"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="antivirus-scanning-exclusions-for-lync-server-2013"></a>Lync Server 2013 的防毒掃描排除項目

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2015-11-02_

若要確保防病毒掃描程式不會干擾 Lync Server 2013 的作業，您必須針對執行防病毒掃描程式的每個 Lync Server 2013 伺服器或伺服器角色排除特定程式和目錄。 下列處理常式與目錄應被排除：

<div>


> [!NOTE]  
> 下列列出的資料夾和檔案位置為 Lync Server 2013 的預設位置。 針對您未使用預設值的任何位置，請排除您指定給組織的位置，而不是本主題中指定的預設位置。



</div>

<div>


> [!IMPORTANT]  
> 請注意，某些防毒程式可能需要其排除清單的絕對（不是相對路徑）。



</div>

  - Lync Server 2013 處理常式：
    
      - ABServer
    
      - AcpMcuSvc
    
      - ASMCUSvc
    
      - AVMCUSvc
    
      - ChannelService
    
      - ClsAgent
    
      - ComplianceService
    
      - DataMCUSvc
    
      - DataProxy
    
      - FileTransferAgent
    
      - IMMCUSvc
    
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
    
      - % systemroot%\\system32\\inetsrv\\w3wp
    
      - % systemroot%\\SysWOW64\\inetsrv\\w3wp

  - SQL Server 後端處理常式：
    
      - % ProgramFiles%\\Microsoft SQL Server\\MSSQL11。MSSQLSERVER\\MSSQL\\Binn\\SQLServr
    
      - % ProgramFiles%\\Microsoft SQL Server\\MSRS11。MSSQLSERVER\\Reporting Services\\ReportServer\\Bin\\ReportingServicesService .exe
    
      - % ProgramFiles%\\Microsoft SQL Server\\MSAS11。MSSQLSERVER\\OLAP\\Bin\\MSMDSrv

  - SQL Server 前端程式：
    
      - % ProgramFiles%\\Microsoft SQL Server\\MSSQL11。LYNCLOCAL\\MSSQL\\Binn\\SQLServr
    
      - % ProgramFiles%\\Microsoft SQL Server\\MSSQL11。RTCLOCAL\\MSSQL\\Binn\\SQLServr

  - 目錄和檔案：
    
      - % systemroot%\\System32\\日誌
    
      - % systemroot%\\SysWow64\\的日誌
    
      - % systemroot%\\Microsoft.NET\\元件\\GAC\_MSIL
    
      - % programfiles%\\Microsoft Lync Server 2013
    
      - % programfiles%\\常見檔案\\Microsoft Lync Server 2013\\觀察程式節點
    
      - % programfiles%\\常見檔案\\Microsoft Lync Server 2013
    
      - % SystemDrive%\\RtcReplicaRoot
    
      - [檔案共用] 存放區（在 [拓撲建立器] 中指定）。 檔案存放區是在拓撲建立器中指定。
    
      - SQL Server 資料和記錄檔案，包括後端資料庫、使用者儲存、封存儲存、監視儲存及應用程式存放區的檔案。 您可以在拓撲結構建立器中指定資料庫和記錄檔。 如需每個資料庫的資料和記錄檔案（包括預設名稱）的詳細資料，請參閱部署檔中[Lync Server 2013 的 SQL Server 資料和記錄檔位置](lync-server-2013-sql-server-data-and-log-file-placement.md)。
    
      - SQL Server 資料和記錄檔案，包括前端資料庫、Lync store 及 RtcDatabase store 的檔案。 它們通常在 [% localdrive%\\CSData] 下。

</div>

<span> </span>

</div>

</div>

</div>

