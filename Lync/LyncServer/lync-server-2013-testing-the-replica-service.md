---
title: Lync Server 2013：測試複本服務
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing the replica service
ms:assetid: 4ff2cc91-0036-4c5a-9792-7bf43d8ce18d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727303(v=OCS.15)
ms:contentKeyID: 63969600
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c955da727a4213098a5b6af4f6fbb348bb60dd21
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745433"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-the-replica-service-in-lync-server-2013"></a>在 Lync Server 2013 中測試複本服務

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-11-03_


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
<td><p>使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</p>
<p>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行<strong>CsReplica</strong> Cmdlet 許可權的 RBAC 角色。 若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示執行下列命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsReplica&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>說明

**CsReplica** Cmdlet 會確認 Lync Server 2013 複本服務正在本機電腦上執行。 **CsReplica** Cmdlet 會執行下列工作：

  - 檢查複製器代理程式與集中式記錄代理程式服務的狀態

  - 確認已在 Windows 防火牆中開啟所需的埠

  - 確定所需的 Active Directory 和本機電腦安全性組存在。

請注意，這個 Cmdlet 必須在本機執行。 也就是說，它必須在執行複本服務的同一部電腦上執行。 在遠端伺服器上執行**CsReplica** Cmdlet 沒有任何選項。

</div>

<div>

## <a name="running-the-test"></a>執行測試

範例1中所示的命令會測試本機電腦上的 Lync Server 2013 副本服務。 在這個範例中，Verbose 參數是用來保證有關測試的資訊（包括最終失敗，或測試產生的報告位置）會顯示在畫面上。

    Test-CsReplica -Verbose

範例2是範例1中所示命令的變化。 在這種情況下，會包含報表參數，以指定測試所產生之報表的資料夾路徑和名稱。 如果您沒有指定報表路徑，系統會為報表提供自動產生的名稱，類似以下所示：

C：\\使用者\\Litwareinc\\AppData\\本機\\溫度\\1\\測試-Cs-Replica-3db40ee0-4b5d-4f58-8d3d-b1e61253129e

    Test-CsReplica -Verbose -Report C:\Logs\ReplicaTest.html

</div>

<div>

## <a name="determining-success-or-failure"></a>判斷成功或失敗

在此插入章節本文。

詳細：建立新的記錄檔 "C\\：\\使用者\\測試\\AppData\\本機\\Temp Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c"。

詳細：建立新的記錄檔 "C\\：\\使用者\\測試\\AppData\\本機\\Temp Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c"。

詳細：「Test-CsReplica」處理已順利完成。

詳細：您可以在「C\\：使用者\\測試\\AppData\\本機\\Temp\\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c .xml」中找到詳細的結果。

詳細：建立新的記錄檔

"C：\\使用者\\測試\\AppData\\本機\\Temp\\2\\測試-CsReplica-29fddb35-f56e-4e3c-8f4c-e

d3bd0e4a083 "。

詳細：建立新的記錄檔

"C：\\使用者\\測試\\AppData\\本機\\Temp\\2\\測試-CsReplica-29fddb35-f56e-4e3c-8f4c-e

d3bd0e4a083 "。

警告：測試 CsReplica 失敗。

警告：您可以在以下網址找到詳細的結果

"C：\\使用者\\測試\\AppData\\本機\\Temp\\2\\測試-CsReplica-29fddb35-f56e-4e3c-8f4c-e

d3bd0e4a083 "。

測試-CsReplica：命令執行失敗：要求的登錄存取權不是

允許.

在第一行：1個字元：1

\+Test-CsReplica-詳細資訊

\+ ~~~~~~~~~~~~~~~~~~~~~~~

\+CategoryInfo： InvalidOperation：（:)\[測試 CsReplica\]、安全性

引發

\+FullyQualifiedErrorId： ProcessingFailed、Microsoft Rtc. Deploy

）。TestReplicaCmdlet

PS C：\\使用者\\測試\>

PS C：\\使用者\\測試\> Test-CsUcwaConference-TargetFqdn "LyncTest. SelfHost

icrosoft.com "

警告：無法讀取指定之完全限定的註冊機構埠號碼

網功能變數名稱稱（FQDN）。 使用預設的註冊器埠號碼。 引發

InvalidOperationException：在拓撲中找不到相符的群集。

的

TryRetri 的 SyntheticTransactions。 SipSyntheticTransaction

eveRegistrarPortFromTopology （Int32& registrarPortNumber）

Test-CsUcwaConference：沒有指派測試使用者

\[LyncTest.SelfHost.Corp.Microsoft.com\]。 驗證測試使用者配置。

在第一行：1個字元：1

\+Test-CsUcwaConference-TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"

\+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

\+CategoryInfo： ResourceUnavailable：（:)\[Test-CsUcwaConference\]

, InvalidOperationException

\+FullyQualifiedErrorId： NotFoundTestUsers，，

eticTransactions.TestUcwaConferenceCmdlet

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能失敗的原因

以下是**測試 CsReplica**可能失敗的一些常見原因：

  - 複製器代理程式與集中式記錄代理程式服務可能會有更大的問題

  - 所需的埠可能無法在 Windows 防火牆中開啟

  - 所需的 Active Directory 和本機電腦安全性組可能不存在

</div>

</div>

<span> </span>

</div>

</div>

</div>

