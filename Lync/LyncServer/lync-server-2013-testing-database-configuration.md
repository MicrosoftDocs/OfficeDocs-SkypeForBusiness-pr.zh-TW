---
title: Lync Server 2013：測試資料庫設定
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
ms.openlocfilehash: f1d57659c93aa42392f5408721157df1d14b56b0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504100"
---
# <a name="testing-database-configuration-in-lync-server-2013"></a>在 Lync Server 2013 中測試資料庫設定

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2016-07-07_


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
<td><p>測試控管</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>必要的權限</p></td>
<td><p>使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員，而且必須具備 SQL Server 的系統管理員許可權。</p>
<p>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 <strong>Test-CsDatabase</strong> Cmdlet 許可權的 RBAC 角色。 若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDatabase&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>描述

**Test-CsDatabase** Cmdlet 會驗證一或多部 Lync Server 2013 資料庫的連線能力。 執行時， **Test-CsDatabase** 指令指令會讀取 Lync Server 拓撲，嘗試連線至相關資料庫，然後傳回每次嘗試的成功或失敗報告。 若連線成功，此 Cmdlet 亦會回報資料庫名稱、SQL Server 版本資訊與所安裝之鏡像資料庫的位置等資訊。

</div>

<div>

## <a name="running-the-test"></a>執行測試

範例 1 所示的命令會驗證中央管理資料庫的組態。

    Test-CsDatabase -CentralManagementDatabase

範例2會驗證所有安裝在電腦 atl-sql-001.litwareinc.com 上的 Lync 伺服器資料庫。

    Test-CsDatabase -ConfiguredDatabases -SqlServerFqdn "atl-sql-001.litwareinc.com"

在範例 3 中，只會驗證安裝在 atl-sql-001.litwareinc.com 電腦上的封存資料庫。請注意，會包含 SqlInstanceName 參數來指定封存資料庫所在的 SQL Server 執行個體 (Archinst)。

    Test-CsDatabase -DatabaseType "Archiving" -SqlServerFqdn "atl-sql-001.litwareinc.com" -SqlInstanceName "archinst"

範例 4 所示的命令會驗證本機電腦上所安裝的資料庫。

    Test-CsDatabase -LocalService

</div>

<div>

## <a name="determining-success-or-failure"></a>決定成功或失敗

如果資料庫連線設定正確，您會收到類似以下的輸出，其成功的屬性會標示為 **True**：

SqlServerFqdn： atl-sql-001.litwareinc.com

SqlInstanceName： rtc

MirrorSqlServerFqdn :

MirrorSqlInstanceName :

DatabaseName： xds

DataSource：

SQLServerVersion :

ExpectedVersion : 10.13.2

InstalledVersion :

成功： True

SqlServerFqdn： atl-sql-001.litwareinc.com

SqlInstanceName： rtc

MirrorSqlServerFqdn :

MirrorSqlInstanceName :

DatabaseName： .lis

DataSource：

SQLServerVersion :

ExpectedVersion : 3.1.1

InstalledVersion :

成功： True

如果資料庫設定正確但仍然可用，[成功] 欄位就會顯示為 **False**，並且會提供其他警告和資訊：

SqlServerFqdn： atl-sql-001.litwareinc.com

SqlInstanceName： rtc

MirrorSqlServerFqdn :

MirrorSqlInstanceName :

DatabaseName： xds

DataSource：

SQLServerVersion :

ExpectedVersion : 10.13.2

InstalledVersion :

成功： False

SqlServerFqdn： atl-cs-001.litwareinc.com

SqlInstanceName： rtc

MirrorSqlServerFqdn :

MirrorSqlInstanceName :

DatabaseName： .lis

DataSource：

SQLServerVersion :

ExpectedVersion : 3.1.1

InstalledVersion :

成功： False

警告： Test-CsDatabase 發生錯誤。 請參閱記錄檔中的

詳細分析，並確定所有的錯誤 (2) 和警告 (均已定址) 

繼續之前。

警告：您可以在以下位置找到詳細的結果：

"C： \\ 使用者 \\ 測試 \\ AppData \\ 本機 \\ Temp \\ 2 \\ Test-CsDatabase-b18d488a-8044-4679-bbf2-

04d593cce8e6.html "。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能失敗的原因

以下是一些 **Test-CsDatabase** 可能失敗的常見原因：

  - 提供的參數值不正確。 如果使用，必須正確設定選用參數，否則測試將會失敗。 請重新執行不含選用參數的命令，然後查看是否成功。

  - 如果資料庫設定不當或尚未部署，此命令將會失敗。

</div>

<div>

## <a name="see-also"></a>另請參閱


[Get-CsDatabaseMirrorState](https://docs.microsoft.com/powershell/module/skype/Get-CsDatabaseMirrorState)  
[Get-CsService](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[Get-CsUserDatabaseState](https://docs.microsoft.com/powershell/module/skype/Get-CsUserDatabaseState)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

