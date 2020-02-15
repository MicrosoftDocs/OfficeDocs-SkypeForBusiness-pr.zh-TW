---
title: Lync Server 2013： 防毒掃描排除項目
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
ms.openlocfilehash: f8faeba1d3b661110bcaf633d3c780dc2c2ad2b1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029034"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="antivirus-scanning-exclusions-for-lync-server-2013"></a>防毒掃描排除的 Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2015年-11-02_

若要確保防毒掃描程式不干擾 Lync Server 2013 的作業，您必須排除特定處理程序和每個 Lync Server 2013 伺服器或伺服器角色您用來執行防毒掃描程式的目錄。 應該排除下列程序及目錄：

<div>


> [!NOTE]  
> 以下列出的資料夾和檔案位置是 Lync Server 2013 的預設位置。 沒有使用預設的任何位置，但不包括為您的組織，而不在本主題中所指定的預設位置是您所指定的位置。



</div>

<div>


> [!IMPORTANT]  
> 請注意，某些防毒程式可能需要絕對、 而非相對路徑，其排除項目清單。



</div>

  - Lync Server 2013 的程序：
    
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

  - Windows Fabric 主機服務處理程序：
    
      - Fabric.exe
    
      - FabricDCA.exe
    
      - FabricHost.exe

  - IIS 程序：
    
      - %systemroot%\\system32\\inetsrv\\w3wp.exe
    
      - %systemroot%\\SysWOW64\\inetsrv\\w3wp.exe

  - SQL Server 後端程序：
    
      - %Programfiles%\\Microsoft SQL Server\\MSSQL11。MSSQLSERVER\\MSSQL\\Binn\\SQLServr.exe
    
      - %Programfiles%\\Microsoft SQL Server\\MSRS11。MSSQLSERVER\\Reporting Services\\ReportServer\\Bin\\ReportingServicesService.exe
    
      - %Programfiles%\\Microsoft SQL Server\\MSAS11。MSSQLSERVER\\OLAP\\Bin\\MSMDSrv.exe

  - SQL Server 前端程序：
    
      - %Programfiles%\\Microsoft SQL Server\\MSSQL11。LYNCLOCAL\\MSSQL\\Binn\\SQLServr.exe
    
      - %Programfiles%\\Microsoft SQL Server\\MSSQL11。RTCLOCAL\\MSSQL\\Binn\\SQLServr.exe

  - 目錄和檔案：
    
      - %systemroot%\\System32\\記錄檔
    
      - %systemroot%\\SysWow64\\記錄檔
    
      - %systemroot%\\Microsoft.NET\\組件\\GAC\_MSIL
    
      - %programfiles%\\Microsoft Lync Server 2013
    
      - %programfiles%\\通用檔案\\Microsoft Lync Server 2013\\監看員節點
    
      - %programfiles%\\通用檔案\\Microsoft Lync Server 2013
    
      - %Systemdrive%並\\RtcReplicaRoot
    
      - 檔案共用存放區 （在拓撲產生器中指定）。 拓撲產生器] 中，會指定檔案存放區。
    
      - SQL Server 資料和記錄檔，包括後端資料庫、 使用者存放區、 封存存放區、 監控存放區和應用程式存放區。 在拓撲產生器可以指定資料庫和記錄檔。 如需每個資料庫的資料與記錄檔的詳細資訊，包括預設名稱，請參閱[Lync Server 2013 的 SQL Server 資料和記錄檔位置](lync-server-2013-sql-server-data-and-log-file-placement.md) 部署 > 文件中。
    
      - SQL Server 資料和記錄檔，包括前端資料庫、 Lync 存放區中，與 RtcDatabase 存放區。 它們通常是在 %localdrive%下\\CSData。

</div>

<span> </span>

</div>

</div>

</div>

