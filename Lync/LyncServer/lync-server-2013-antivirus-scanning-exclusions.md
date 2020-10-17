---
title: Lync Server 2013：防病毒掃描排除
description: Lync Server 2013：防病毒掃描排除專案。
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
ms.openlocfilehash: 20c395f529cad91993d003efdeb231bd66f4b9bc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561909"
---
# <a name="antivirus-scanning-exclusions-for-lync-server-2013"></a>Lync Server 2013 的防病毒掃描排除

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2015-11-02_

為了確保防病毒掃描程式不會干擾 Lync Server 2013 的運作，您必須針對每個執行防病毒掃描程式的 Lync Server 2013 伺服器或伺服器角色排除特定的程式和目錄。 應該排除下列程式和目錄：

<div>


> [!NOTE]  
> 下列列出的資料夾和檔案位置是 Lync Server 2013 的預設位置。 針對您未使用預設值的任何位置，請排除您為組織所指定的位置，而不是本主題中指定的預設位置。



</div>

<div>


> [!IMPORTANT]  
> 請注意，某些防毒程式可能需要絕對的相對路徑，其排除清單。



</div>

  - Lync Server 2013 處理常式：
    
      - ABServer.exe
    
      - AcpMcuSvc.exe
    
      - ASMCUSvc.exe
    
      - AVMCUSvc.exe
    
      - ChannelService.exe
    
      - ClsAgent.exe
    
      - ComplianceService.exe
    
      - DataMCUSvc.exe
    
      - DataProxy.exe
    
      - FileTransferAgent.exe
    
      - IMMCUSvc.exe
    
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
    
      - % systemroot% \\ system32 \\ inetsrv \\w3wp.exe
    
      - % systemroot% \\ SysWOW64 \\ inetsrv \\w3wp.exe

  - SQL Server Back-End 處理常式：
    
      - %ProgramFiles% \\ MICROSOFT SQL Server \\ MSSQL11。MSSQLSERVER \\ MSSQL \\ Binn \\SQLServr.exe
    
      - %ProgramFiles% \\ MICROSOFT SQL Server \\ MSRS11。MSSQLSERVER \\ Reporting Services \\ ReportServer \\ Bin \\ReportingServicesService.exe
    
      - %ProgramFiles% \\ MICROSOFT SQL Server \\ MSAS11。MSSQLSERVER \\ OLAP \\ Bin \\MSMDSrv.exe

  - SQL Server Front-End 處理常式：
    
      - %ProgramFiles% \\ MICROSOFT SQL Server \\ MSSQL11。LYNCLOCAL \\ MSSQL \\ Binn \\SQLServr.exe
    
      - %ProgramFiles% \\ MICROSOFT SQL Server \\ MSSQL11。RTCLOCAL \\ MSSQL \\ Binn \\SQLServr.exe

  - 目錄及檔案：
    
      - % systemroot% \\ System32 \\ 日誌
    
      - % systemroot% \\ SysWow64 \\ 日誌
    
      - % systemroot% \\ Microsoft.NET \\ 元件 \\ GAC \_ MSIL
    
      - % programfiles% \\ Microsoft Lync Server 2013
    
      - % programfiles% \\ Common Files \\ Microsoft Lync Server 2013 監看員 \\ 節點
    
      - % programfiles% \\ Common Files \\ Microsoft Lync Server 2013
    
      - % 系統磁片% \\ RtcReplicaRoot
    
      - 在拓撲產生器) 中指定的檔案共用儲存區 (。 檔存放區是在拓撲產生器中指定的。
    
      - SQL Server 資料和記錄檔，包括後端資料庫、使用者存放區、封存儲存區、監控儲存區及應用程式存放區的檔案。 您可以在拓撲產生器中指定資料庫和記錄檔。 如需每個資料庫之資料和記錄檔（包括預設名稱）的詳細資訊，請參閱部署檔中的 [SQL Server 資料和記錄檔位置（適用于 Lync Server 2013](lync-server-2013-sql-server-data-and-log-file-placement.md) ）。
    
      - SQL Server 資料和記錄檔，包括前端資料庫、Lync 存放區和 RtcDatabase 存放區的檔案。 它們一般位於% localdrive% \\ CSData。

</div>

<span> </span>

</div>

</div>

</div>

