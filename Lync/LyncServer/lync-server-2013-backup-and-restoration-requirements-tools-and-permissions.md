---
title: Lync Server 2013：備份和還原需求：工具和許可權
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Backup and restoration requirements: tools and permissions'
ms:assetid: 35ec2e33-f33e-4f84-9e64-6550fd78aa52
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202171(v=OCS.15)
ms:contentKeyID: 51541465
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 96eee88d6055d7a66d858dc5c6324a2592616ceb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532640"
---
# <a name="backup-and-restoration-requirements-in-lync-server-2013-tools-and-permissions"></a>Lync Server 2013 中的備份和還原需求：工具和許可權

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-17_

本主題識別您可以用來備份及還原 Lync Server 2013 的工具、所需的許可權，以及您是否可以從遠端或本機執行命令。 具體而言，本主題著重于 Lync Server 所提供的備份及還原工具。

<div>

## <a name="backups"></a>備份

若要備份 Lync Server，請使用下表中標出的工具。 備份 Lync Server 所需的所有命令都可以編寫腳本，而且可以從遠端執行。

### <a name="tools-for-backing-up-lync-server"></a>備份 Lync Server 的工具

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>若要備份這個：</th>
<th>使用此工具或 Cmdlet：</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>拓撲設定資料 (Xds.mdf)</p></td>
<td><p>Export-CsConfiguration</p></td>
</tr>
<tr class="even">
<td><p>位置資訊服務 (E9-1-1) 資料 (Lis.mdf)</p></td>
<td><p>Export-CsLisConfiguration</p></td>
</tr>
<tr class="odd">
<td><p>回應群組設定資料 (RgsConfig.mdf)</p></td>
<td><p>Export-CsRgsConfiguration</p></td>
</tr>
<tr class="even">
<td><p>持久性使用者資料 (Rtcxds 資料庫) </p>
<p>會議 ID</p></td>
<td><p>Export-CsUserData</p></td>
</tr>
<tr class="odd">
<td><ul>
<li><p>封存資料庫 (LcsLog.mdf)</p></li>
<li><p>監視詳細通話記錄資料庫 (LcsCDR.mdf)</p></li>
<li><p>監視 QoE 資料庫 (QoEMetrics.mdf)</p></li>
</ul></td>
<td><p>SQL Server 資料庫工具，例如 SQL Server Management Studio</p></td>
</tr>
<tr class="even">
<td><p>Persistent Chat database (Mgc) </p></td>
<td><p>SQL Server 備份程式或 Export-CsPersistentChatData。 Export-CsPersistentChatData 會將 Persistent Chat 資料當做檔案匯出。</p></td>
</tr>
<tr class="odd">
<td><p>所有檔案存放區： Lync Server 檔存放區、封存檔存放區</p>
<div>

> [!NOTE]  
> <STRONG>Meeting.Active</STRONG> 檔案不應備份。 會議進行期間會使用這些檔案並予以鎖定。


</div></td>
<td><p>標準檔案系統管理工具，如 Robocopy。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="restoration"></a>恢復

若要還原 Lync Server，請使用下表中的工具。 您可以為還原 Lync Server 所需的所有命令編寫腳本。 有些可以從遠端執行，但其他使用者必須在本機執行，如下表所指定。

### <a name="tools-for-restoring-lync-server"></a>用於還原 Lync Server 的工具

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>若要執行此作業：</th>
<th>使用此工具或 Cmdlet：</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>建立全新的電腦</p></td>
<td><ul>
<li><p>Windows 作業系統安裝軟體</p></li>
<li><p>SQL Server 安裝軟體</p></li>
<li><p>如果以可匯出的私密金鑰來還原憑證，則請認證 Microsoft Management Console (MMC) 嵌入式管理單元</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>還原檔案存放區資料</p></td>
<td><p>標準檔案系統管理工具，如 Robocopy</p></td>
</tr>
<tr class="odd">
<td><p>重新建立空的資料庫，並設定下列的權限：</p>
<ul>
<li><p>中央管理存放區</p></li>
<li><p>後端伺服器</p></li>
<li><p>監控資料庫</p></li>
<li><p>封存資料庫</p></li>
</ul></td>
<td><p>Install-CsDatabase</p></td>
</tr>
<tr class="even">
<td><p>將 Active Directory 網域服務指標還原至中央管理存放區</p>
<div>

> [!NOTE]  
> 如果您在任何時候遺失服務連線點，都可以重新執行此 Cmdlet。


</div></td>
<td><p>Set-CsConfigurationStoreLocation</p></td>
</tr>
<tr class="odd">
<td><p>將拓撲、原則及設定，匯入中央管理存放區 (Xds) </p></td>
<td><p>Import-CsConfiguration</p></td>
</tr>
<tr class="even">
<td><p>發行及啟用拓撲</p></td>
<td><p>拓撲產生器</p>
<p>- 或 -</p>
<p>Publish-CsTopology 和 Enable-CsTopology</p></td>
</tr>
<tr class="odd">
<td><p>啟用上次發行的拓撲</p></td>
<td><p>Enable-CsTopology</p></td>
</tr>
<tr class="even">
<td><p>重新安裝 Lync Server 元件</p></td>
<td><p>Lync Server 安裝程式</p>
<div>

> [!NOTE]  
> 位於 \setup\amd64\Setup.exe 的 Lync Server 安裝資料夾或媒體中。


</div></td>
</tr>
<tr class="odd">
<td><p>還原位置資訊 (E9-1-1) 資料 (Lis.mdf)</p></td>
<td><p>Import-CsLisConfiguration</p></td>
</tr>
<tr class="even">
<td><p>還原持續使用者資料 (Rtcxds) </p></td>
<td><p>Import-CsUserData</p></td>
</tr>
<tr class="odd">
<td><p>還原回應群組設定資料 (RgsConfig.mdf)</p></td>
<td><p>Import-CsRgsConfiguration</p>
<div>

> [!NOTE]  
> 若要在新部署的集區中還原設定，而該集區中沒有資料庫的回應群組資料，您應該使用– OverwriteOwner 選項。 您可以使用此選項，即使還原的資料位於具有相同完整功能變數名稱的集區中 (FQDN) 。 否則，由於連絡人物件已存在於 Active Directory 中的回應群組，所以匯入將會失敗。


</div></td>
</tr>
<tr class="even">
<td><p>還原下列資料庫：</p>
<ul>
<li><p>封存資料庫 (LcsLog.mdf)</p></li>
<li><p>監視資料庫：詳細通話記錄資料庫 (LcsCDR.mdf) 及 QoE 資料庫 (QoEMetrics.mdf)</p></li>
</ul></td>
<td><p>SQL Server 資料庫管理工具</p></td>
</tr>
<tr class="odd">
<td><p>Persistent Chat database (Mgs) </p></td>
<td><p>SQL Server 還原程式或 Import-CsPersistentChatData。 您可以使用 Import-CsPersistentChatData 與 Export-CsPersistentChatData 建立的檔案，然後將資料匯入至 Persistent Chat database。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="required-permissions"></a>必要權限

使用者必須是 **RTCUniversalServerAdmins** 群組的成員，才可執行本主題中所述的所有命令。 大多數備份及還原命令不支援以角色為基礎的存取控制 (RBAC) 。 有兩個例外狀況是 Persistent Chat Cmdlet Export-CsPersistentChatData 和 Import-CsPersistentChatData，必須由 CsPersistentChatAdministrator 群組成員的使用者執行。 若要執行 Lync Server 部署嚮導，使用者還必須是本機管理員群組的成員。

</div>

</div>

<span> </span>

</div>

</div>

</div>

