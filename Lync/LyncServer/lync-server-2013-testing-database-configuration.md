---
title: Lync Server 2013：測試資料庫配置
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
ms.openlocfilehash: 6fcf6679481d4f35a457eb72960a8ae999b004d3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745823"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-database-configuration-in-lync-server-2013"></a>在 Lync Server 2013 中測試資料庫配置

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
<td><p>日常</p></td>
</tr>
<tr class="even">
<td><p>測試控管</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>需要許可權</p></td>
<td><p>使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員，且需要在 SQL Server 上擁有系統管理員許可權。</p>
<p>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行<strong>CsDatabase</strong> Cmdlet 許可權的 RBAC 角色。 若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示執行下列命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDatabase&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>說明

**CsDatabase** Cmdlet 會驗證一或多個 Lync Server 2013 資料庫的連線能力。 在執行時， **Test CsDatabase** Cmdlet 會讀取 Lync Server 拓撲，嘗試連線至相關資料庫，然後傳回每次嘗試的成功或失敗。 如果可以建立連線，則 Cmdlet 也會傳回此類資訊，例如資料庫名稱、SQL Server 版本資訊，以及任何已安裝鏡像資料庫的位置。

</div>

<div>

## <a name="running-the-test"></a>執行測試

範例1中所示的命令會驗證中央管理資料庫的配置。

    Test-CsDatabase -CentralManagementDatabase

範例2驗證所有安裝在電腦 atl-sql-001.litwareinc.com 上的 Lync Server 資料庫。

    Test-CsDatabase -ConfiguredDatabases -SqlServerFqdn "atl-sql-001.litwareinc.com"

在範例3中，僅針對電腦 atl-sql-001.litwareinc.com 上安裝的封存資料庫執行驗證。 請注意，SqlInstanceName 參數包含于指定封存資料庫所在的 SQL Server 實例（Archinst）。

    Test-CsDatabase -DatabaseType "Archiving" -SqlServerFqdn "atl-sql-001.litwareinc.com" -SqlInstanceName "archinst"

範例4所示的命令會驗證本機電腦上已安裝的資料庫。

    Test-CsDatabase -LocalService

</div>

<div>

## <a name="determining-success-or-failure"></a>判斷成功或失敗

如果資料庫連線設定正確，您會收到類似以下的輸出，並將 [成功] 屬性標示為**True**：

SqlServerFqdn： atl-sql-001.litwareinc.com

SqlInstanceName： rtc

MirrorSqlServerFqdn :

MirrorSqlInstanceName :

DatabaseName： xds

資料來源

SQLServerVersion :

ExpectedVersion : 10.13.2

InstalledVersion :

成功： True

SqlServerFqdn： atl-sql-001.litwareinc.com

SqlInstanceName： rtc

MirrorSqlServerFqdn :

MirrorSqlInstanceName :

DatabaseName： .lis

資料來源

SQLServerVersion :

ExpectedVersion : 3.1.1

InstalledVersion :

成功： True

如果資料庫已正確設定但仍可使用，則 [成功] 欄位會顯示為**False**，並提供額外的警告和資訊：

SqlServerFqdn： atl-sql-001.litwareinc.com

SqlInstanceName： rtc

MirrorSqlServerFqdn :

MirrorSqlInstanceName :

DatabaseName： xds

資料來源

SQLServerVersion :

ExpectedVersion : 10.13.2

InstalledVersion :

成功： False

SqlServerFqdn： atl-cs-001.litwareinc.com

SqlInstanceName： rtc

MirrorSqlServerFqdn :

MirrorSqlInstanceName :

DatabaseName： .lis

資料來源

SQLServerVersion :

ExpectedVersion : 3.1.1

InstalledVersion :

成功： False

警告：測試 CsDatabase 遇到錯誤。 請參閱記錄檔

詳細分析，並確保所有錯誤（2）和警告（0）都得到解決

然後再繼續進行。

警告：您可以在以下網址找到詳細的結果

"C：\\使用者\\測試\\AppData\\本機\\Temp\\2\\測試-CsDatabase-b18d488a-8044-4679-bbf2-

04d593cce8e6 "。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能失敗的原因

以下是**測試 CsDatabase**可能失敗的一些常見原因：

  - 提供不正確的參數值。 如果使用，必須正確設定選用的參數，否則測試將會失敗。 重新執行不含選用參數的命令，並查看是否成功。

  - 如果資料庫的配置錯誤或尚未部署，此命令就會失敗。

</div>

<div>

## <a name="see-also"></a>請參閱


[Get-CsDatabaseMirrorState](https://docs.microsoft.com/powershell/module/skype/Get-CsDatabaseMirrorState)  
[Get-CsService](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[CsUserDatabaseState](https://docs.microsoft.com/powershell/module/skype/Get-CsUserDatabaseState)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

