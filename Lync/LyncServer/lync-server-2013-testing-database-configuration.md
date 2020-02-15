---
title: Lync Server 2013： 測試資料庫組態
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing database configuration
ms:assetid: 60f7fcd2-5efe-4791-b159-b0f9bf39a41b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727307(v=OCS.15)
ms:contentKeyID: 63969606
ms.date: 07/07/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 45781238f7fb8aa461e050f2e8f0cbf04e45a950
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038175"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-database-configuration-in-lync-server-2013"></a>Lync Server 2013 中的測試資料庫組態

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2016年-07-07_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>驗證排程</p></td>
<td><p>每日</p></td>
</tr>
<tr class="even">
<td><p>測試工具</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>必要的權限</p></td>
<td><p>當執行在本機上使用 Lync Server 管理命令介面，使用者必須屬於 RTCUniversalServerAdmins 安全性] 群組中，並需要 SQL server 上有系統管理員權限。</p>
<p>當執行使用 Windows PowerShell 的遠端執行個體時，使用者必須被指派具有執行<strong>Test-csdatabase</strong> cmdlet 的權限的 RBAC 角色。 若要查看可以使用此 cmdlet 的所有 RBAC 角色的清單，請在 Windows PowerShell 命令提示執行下列命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDatabase&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>描述

**Test-csdatabase** cmdlet 驗證連線至一或多個 Lync Server 2013 資料庫。 當執行時， **Test-csdatabase** cmdlet 會讀取 Lync Server 拓撲、 嘗試連線至相關的資料庫，並再回復報告成功或失敗的每個嘗試。 若連線成功，此 Cmdlet 亦會回報資料庫名稱、SQL Server 版本資訊與所安裝之鏡像資料庫的位置等資訊。

</div>

<div>

## <a name="running-the-test"></a>執行測試

範例 1 所示的命令會驗證中央管理資料庫的組態。

    Test-CsDatabase -CentralManagementDatabase

範例 2 會驗證安裝在電腦 atl-cs-001.litwareinc.com sql-001.litwareinc.com 上的所有 Lync Server 資料庫。

    Test-CsDatabase -ConfiguredDatabases -SqlServerFqdn "atl-sql-001.litwareinc.com"

在範例 3 中，只會驗證安裝在 atl-sql-001.litwareinc.com 電腦上的封存資料庫。請注意，會包含 SqlInstanceName 參數來指定封存資料庫所在的 SQL Server 執行個體 (Archinst)。

    Test-CsDatabase -DatabaseType "Archiving" -SqlServerFqdn "atl-sql-001.litwareinc.com" -SqlInstanceName "archinst"

範例 4 所示的命令會驗證本機電腦上所安裝的資料庫。

    Test-CsDatabase -LocalService

</div>

<div>

## <a name="determining-success-or-failure"></a>決定成功或失敗

如果已正確設定資料庫連線，您會收到類似，具有標示為 **，則為 True**的成功屬性的輸出：

SqlServerFqdn: atl-cs-sql-001.litwareinc.com

SqlInstanceName: rtc

MirrorSqlServerFqdn:

MirrorSqlInstanceName:

DatabaseName: xds

資料來源：

SQLServerVersion:

ExpectedVersion: 10.13.2

InstalledVersion:

成功： True

SqlServerFqdn: atl-cs-sql-001.litwareinc.com

SqlInstanceName: rtc

MirrorSqlServerFqdn:

MirrorSqlInstanceName:

DatabaseName: lis

資料來源：

SQLServerVersion:

ExpectedVersion: 3.1.1

InstalledVersion:

成功： True

如果資料庫已正確設定，但仍可使用，[成功] 欄位會顯示為**False**，並會提供額外的警告和資訊：

SqlServerFqdn: atl-cs-sql-001.litwareinc.com

SqlInstanceName: rtc

MirrorSqlServerFqdn:

MirrorSqlInstanceName:

DatabaseName: xds

資料來源：

SQLServerVersion:

ExpectedVersion: 10.13.2

InstalledVersion:

成功： False

SqlServerFqdn: atl-cs-001.litwareinc.com

SqlInstanceName: rtc

MirrorSqlServerFqdn:

MirrorSqlInstanceName:

DatabaseName: lis

資料來源：

SQLServerVersion:

ExpectedVersion: 3.1.1

InstalledVersion:

成功： False

警告： Test-csdatabase 遇到錯誤。 請洽詢的記錄檔

詳細的分析，並確定已解決所有錯誤 (2) 及警告 (0)

再繼續。

警告： 可以在找到詳細的結果

「 C:\\使用者\\測試\\AppData\\本機\\Temp\\2\\Test-CsDatabase-b18d488a-8044-4679-bbf2-

04d593cce8e6.html 」。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能有為何失敗的原因

以下是一些常見的原因為何**Test-csdatabase**可能會失敗：

  - 提供不正確的參數值。 如果使用，必須正確設定選用的參數或測試將會失敗。 重新執行此命令不含選擇性參數，並查看是否成功。

  - 如果資料庫設定正確，或是尚未部署，此命令將會失敗。

</div>

<div>

## <a name="see-also"></a>另請參閱


[Get-csdatabasemirrorstate](https://docs.microsoft.com/powershell/module/skype/Get-CsDatabaseMirrorState)  
[Get-csservice](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[Get-csuserdatabasestate](https://docs.microsoft.com/powershell/module/skype/Get-CsUserDatabaseState)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

