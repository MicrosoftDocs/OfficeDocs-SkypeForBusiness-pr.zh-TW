---
title: Lync Server 2013： 備份和還原需求： 工具和權限
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
ms.openlocfilehash: 900421ed081d5fb8e37fb6b23ddbb80dc85963eb
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188086"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-requirements-in-lync-server-2013-tools-and-permissions"></a>Lync Server 2013 中的備份和還原需求： 工具和權限

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-02-17_

本主題會識別的工具，您可用於備份及還原 Lync Server 2013 中，您需要的權限，是否可以執行命令從遠端還是在本機。 具體而言，本主題著重於隨附的備份和還原 Lync Server 的工具。

<div>

## <a name="backups"></a>備份

若要備份 Lync Server，請使用下表中所識別的工具。 您必須備份 Lync Server 的所有命令可以寫成指令碼，且可以從遠端執行。

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
<td><p>Export-csconfiguration</p></td>
</tr>
<tr class="even">
<td><p>位置資訊服務 (E9-1-1) 資料 (Lis.mdf)</p></td>
<td><p>Export-cslisconfiguration</p></td>
</tr>
<tr class="odd">
<td><p>回應群組設定資料 (RgsConfig.mdf)</p></td>
<td><p>Export-csrgsconfiguration</p></td>
</tr>
<tr class="even">
<td><p>持續性的使用者資料 （Rtcxds.mdf 資料庫）</p>
<p>會議 ID</p></td>
<td><p>Export-csuserdata</p></td>
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
<td><p>常設聊天室資料庫 (Mgc.mdf)</p></td>
<td><p>SQL Server 備份程序或 Export-cspersistentchatdata。 Export-cspersistentchatdata 會將常設聊天室資料匯出成檔案。</p></td>
</tr>
<tr class="odd">
<td><p>所有檔案存放區： Lync Server 檔案存放區、 封存檔案存放區</p>
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

## <a name="restoration"></a>還原

若要還原 Lync Server，請在下表中使用的工具。 您需要還原 Lync Server 的所有命令可以寫成指令都碼。 部分可在遠端執行，但其他都需要在本機執行下, 表所示。

### <a name="tools-for-restoring-lync-server"></a>用來還原 Lync Server 工具

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
<td><p>Install-csdatabase</p></td>
</tr>
<tr class="even">
<td><p>還原中央管理存放區的 Active Directory 網域服務指標</p>
<div>

> [!NOTE]  
> 如果您在任何時候遺失服務連線點，都可以重新執行此 Cmdlet。


</div></td>
<td><p>Set-csconfigurationstorelocation</p></td>
</tr>
<tr class="odd">
<td><p>拓撲、 原則及組態設定匯入至中央管理存放區 (Xds.mdf)</p></td>
<td><p>Import-csconfiguration</p></td>
</tr>
<tr class="even">
<td><p>發佈及啟用拓撲</p></td>
<td><p>拓撲產生器</p>
<p>-或-</p>
<p>Publish-cstopology 和 Enable-cstopology</p></td>
</tr>
<tr class="odd">
<td><p>啟用上次發行的拓撲</p></td>
<td><p>Enable-cstopology</p></td>
</tr>
<tr class="even">
<td><p>重新安裝 Lync Server 元件</p></td>
<td><p>Lync Server 安裝程式</p>
<div>

> [!NOTE]  
> 位在 Lync Server 安裝資料夾或媒體 \setup\amd64\Setup.exe。


</div></td>
</tr>
<tr class="odd">
<td><p>還原位置資訊 (E9-1-1) 資料 (Lis.mdf)</p></td>
<td><p>匯入 CsLisConfiguration</p></td>
</tr>
<tr class="even">
<td><p>還原持續性的使用者資料 (Rtcxds.mdf)</p></td>
<td><p>Import-csuserdata</p></td>
</tr>
<tr class="odd">
<td><p>還原回應群組設定資料 (RgsConfig.mdf)</p></td>
<td><p>Import-csrgsconfiguration</p>
<div>

> [!NOTE]  
> 若要還原設定資料庫中有沒有回應群組資料的新部署集區中，您應該使用 – OverwriteOwner 選項。 即使要還原的資料位於相同的完整的網域名稱 (FQDN) 與集區，請使用此選項。 否則，匯入就會失敗，因為已在 Active Directory 中存在的回應群組的連絡人物件。


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
<td><p>常設聊天室資料庫 (Mgs.mdf)</p></td>
<td><p>SQL Server 還原程序或 Import-cspersistentchatdata。 您可以使用 Import-cspersistentchatdata Export-cspersistentchatdata，所建立的檔案和資料會匯入常設聊天室資料庫。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="required-permissions"></a>必要權限

使用者必須要執行本主題所述的所有命令的**RTCUniversalServerAdmins**群組成員。 大部分的備份與還原命令不支援角色型存取控制 (RBAC)。 兩個例外狀況，而常設聊天 cmdlet Export-cspersistentchatdata Import-cspersistentchatdata，必須執行由使用者身為 CsPersistentChatAdministrator 群組的成員。 若要執行 Lync Server 部署精靈，使用者也必須是本機系統管理員群組的成員。

</div>

</div>

<span> </span>

</div>

</div>

</div>

