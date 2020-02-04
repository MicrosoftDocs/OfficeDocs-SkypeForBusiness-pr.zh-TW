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
ms.openlocfilehash: ea5e4ce57e61be50bfd1e2a78529830b4a40e3ed
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730403"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-requirements-in-lync-server-2013-tools-and-permissions"></a>Lync Server 2013 中的備份和還原需求：工具和許可權

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-17_

本主題識別您可以用來備份及還原 Lync Server 2013 的工具、所需的許可權，以及您是否可以遠端或本機執行命令。 具體來說，本主題將重點放在 Lync Server 提供以進行備份和還原的工具上。

<div>

## <a name="backups"></a>資料備份

若要備份 Lync Server，請使用下表中所述的工具。 您需要用來備份 Lync Server 的所有命令都可以進行腳本化，而且可以遠端執行。

### <a name="tools-for-backing-up-lync-server"></a>備份 Lync Server 的工具

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>若要備份，請執行下列動作：</th>
<th>使用這個工具或 Cmdlet：</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>拓朴配置資料（Xds）</p></td>
<td><p>Export-CsConfiguration</p></td>
</tr>
<tr class="even">
<td><p>位置資訊服務（E9-1-1）資料（.Lis）</p></td>
<td><p>Export-CsLisConfiguration</p></td>
</tr>
<tr class="odd">
<td><p>回應群組設定資料（RgsConfig）</p></td>
<td><p>Export-CsRgsConfiguration</p></td>
</tr>
<tr class="even">
<td><p>持久性使用者資料（Rtcxds .mdf 資料庫）</p>
<p>會議 Id</p></td>
<td><p>Export-CsUserData</p></td>
</tr>
<tr class="odd">
<td><ul>
<li><p>存檔資料庫（LcsLog）</p></li>
<li><p>監控通話詳細資料記錄資料庫（LcsCDR）</p></li>
<li><p>監視 QoE 資料庫（QoEMetrics）</p></li>
</ul></td>
<td><p>SQL server 資料庫工具，例如 SQL Server Management Studio</p></td>
</tr>
<tr class="even">
<td><p>持續聊天資料庫（Mgc）</p></td>
<td><p>[SQL Server 備份程式] 或 [匯出-CsPersistentChatData]。 Export-CsPersistentChatData 會將永久性聊天資料匯出為檔案。</p></td>
</tr>
<tr class="odd">
<td><p>所有檔案儲存區： Lync Server 檔存放區、封存檔案存放區</p>
<div>

> [!NOTE]  
> 名為「<STRONG>會議」的</STRONG>檔案不應備份。 在會議進行時，這些檔案正在使用中且已鎖定。


</div></td>
<td><p>標準檔案系統管理工具，例如 Robocopy。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="restoration"></a>還原

若要還原 Lync Server，請使用下表中的工具。 您可以為還原 Lync Server 所需的所有命令進行腳本化。 有些可以在遠端執行，但其他人需要在本機執行，如下表所示。

### <a name="tools-for-restoring-lync-server"></a>還原 Lync Server 的工具

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>若要執行此動作：</th>
<th>使用這個工具或 Cmdlet：</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>建立新的或乾淨的電腦</p></td>
<td><ul>
<li><p>Windows 作業系統安裝軟體</p></li>
<li><p>SQL Server 安裝軟體</p></li>
<li><p>[憑證 Microsoft 管理主控台（MMC）] 管理單元（如果使用可匯出的私密金鑰還原憑證）</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>還原檔案儲存區資料</p></td>
<td><p>標準檔案系統管理工具，例如 Robocopy</p></td>
</tr>
<tr class="odd">
<td><p>重新建立空白資料庫並設定下列專案的許可權：</p>
<ul>
<li><p>中央管理存放區</p></li>
<li><p>後端伺服器</p></li>
<li><p>監控資料庫</p></li>
<li><p>封存資料庫</p></li>
</ul></td>
<td><p>Install-CsDatabase</p></td>
</tr>
<tr class="even">
<td><p>將 Active Directory 網域服務指標還原到中央管理存放區</p>
<div>

> [!NOTE]  
> 如果您在任何時候遺失服務連接點，您可以重新執行這個 Cmdlet。


</div></td>
<td><p>Set-CsConfigurationStoreLocation</p></td>
</tr>
<tr class="odd">
<td><p>將拓撲、原則和設定的設定匯入中央管理商店（Xds）</p></td>
<td><p>匯入-CsConfiguration</p></td>
</tr>
<tr class="even">
<td><p>發佈並啟用拓撲</p></td>
<td><p>拓撲建立器</p>
<p>或</p>
<p>發佈-CsTopology 和 Enable-CsTopology</p></td>
</tr>
<tr class="odd">
<td><p>啟用上次發佈的拓撲</p></td>
<td><p>Enable-CsTopology</p></td>
</tr>
<tr class="even">
<td><p>重新安裝 Lync Server 元件</p></td>
<td><p>Lync Server 設定</p>
<div>

> [!NOTE]  
> 位於 Lync Server 安裝資料夾或 \setup\amd64\Setup.exe. 中的媒體


</div></td>
</tr>
<tr class="odd">
<td><p>還原位置資訊（E9-1-1）資料（.Lis）</p></td>
<td><p>匯入-CsLisConfiguration</p></td>
</tr>
<tr class="even">
<td><p>還原永久性使用者資料（Rtcxds）</p></td>
<td><p>匯入-CsUserData</p></td>
</tr>
<tr class="odd">
<td><p>還原回應群組設定資料（RgsConfig）</p></td>
<td><p>匯入-CsRgsConfiguration</p>
<div>

> [!NOTE]  
> 如果在新部署的池中，在資料庫中沒有任何回應群組資料的配置，則應使用– OverwriteOwner 選項。 即使要還原的資料位於擁有相同完整功能變數名稱（FQDN）的池中，您也能使用這個選項。 否則，匯入將無法成功，因為連絡人物件已存在 Active Directory 中的回應群組。


</div></td>
</tr>
<tr class="even">
<td><p>還原下列資料庫：</p>
<ul>
<li><p>存檔資料庫（LcsLog）</p></li>
<li><p>監視資料庫：通話詳細資料記錄資料庫（LcsCDR .mdf）和 QoE 資料庫（QoEMetrics）</p></li>
</ul></td>
<td><p>SQL Server 資料庫管理工具</p></td>
</tr>
<tr class="odd">
<td><p>持續聊天資料庫（Mgs）</p></td>
<td><p>[SQL Server 還原程式] 或 [匯入-CsPersistentChatData]。 您可以使用匯入-CsPersistentChatData 搭配由 Export CsPersistentChatData 建立的檔案，然後將資料匯入到持久聊天資料庫中。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="required-permissions"></a>所需許可權

使用者必須是**RTCUniversalServerAdmins**群組的成員，才能執行本主題中所述的所有命令。 大多數的備份和還原命令不支援以角色為基礎的存取控制（RBAC）。 有兩個例外情況是永久聊天 Cmdlet 的 Export CsPersistentChatData 和 Import-CsPersistentChatData，這必須由成為 CsPersistentChatAdministrator 群組成員的使用者執行。 若要執行 Lync Server 部署嚮導，使用者也必須是本機管理員群組的成員。

</div>

</div>

<span> </span>

</div>

</div>

</div>

