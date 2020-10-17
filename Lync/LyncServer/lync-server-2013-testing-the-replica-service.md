---
title: Lync Server 2013：測試複本服務
description: Lync Server 2013：測試複本服務。
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
ms.openlocfilehash: a61751b95115da3d6519f20f52262b7159ffcbfe
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556159"
---
# <a name="testing-the-replica-service-in-lync-server-2013"></a>在 Lync Server 2013 中測試複本服務

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



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
<td><p>每日</p></td>
</tr>
<tr class="even">
<td><p>測試控管</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>必要的權限</p></td>
<td><p>使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</p>
<p>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 <strong>Test-CsReplica</strong> Cmdlet 許可權的 RBAC 角色。 若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsReplica&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>描述

**Test-CsReplica** Cmdlet 會驗證 Lync Server 2013 複本服務是否正在本機電腦上執行。 **Test-CsReplica** Cmdlet 會執行下列工作：

  - 檢查複製器代理程式的狀態及集中式記錄代理程式服務

  - 確認已在 Windows 防火牆中開啟必要的埠

  - 確定所需的 Active Directory 和本機電腦安全性組都存在。

請注意，此 Cmdlet 必須在本機執行。 也就是說，您必須在執行複本服務的同一部電腦上執行。 在遠端伺服器上執行 **Test-CsReplica** Cmdlet 沒有任何選項。

</div>

<div>

## <a name="running-the-test"></a>執行測試

範例1所示的命令會測試本機電腦上的 Lync Server 2013 複本服務。 在此範例中，Verbose 參數是用來保證有關測試的資訊（包括測試的最終失敗或測試的成功所在位置）顯示在螢幕上。

    Test-CsReplica -Verbose

範例 2 是範例 1 所示命令的變化。 在此情況下，Report 參數會包含在內，以指定測試所產生之報告的資料夾路徑和名稱。 如果您未指定報告路徑，將會為報告指定自動產生的名稱，如下所示：

C： \\ 使用者 \\ Litwareinc \\ AppData \\ 本機 \\ Temp \\ 1 \\Test-Cs-Replica-3db40ee0-4b5d-4f58-8d3d-b1e61253129e.html

    Test-CsReplica -Verbose -Report C:\Logs\ReplicaTest.html

</div>

<div>

## <a name="determining-success-or-failure"></a>決定成功或失敗

在此處插入區段主體。

詳細：建立新的記錄檔 "C： \\ 使用者 \\ 測試 \\ AppData \\ 本機 \\ Temp \\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml"。

詳細：建立新的記錄檔 "C： \\ 使用者 \\ 測試 \\ AppData \\ 本機 \\ Temp \\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml"。

詳細： "Test-CsReplica" 處理已成功完成。

詳細：請參閱 "C： \\ 使用者 \\ 測試 \\ AppData \\ Local \\ Temp \\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml" 的詳細結果。

詳細：建立新的記錄檔

"C： \\ 使用者 \\ 測試 \\ AppData \\ 本機 \\ Temp \\ 2 \\ Test-CsReplica-29fddb35-f56e-4e3c-8f4c-e"

d3bd0e4a083.xml "。

詳細：建立新的記錄檔

"C： \\ 使用者 \\ 測試 \\ AppData \\ 本機 \\ Temp \\ 2 \\ Test-CsReplica-29fddb35-f56e-4e3c-8f4c-e"

d3bd0e4a083.html "。

警告： Test-CsReplica 失敗。

警告：您可以在以下位置找到詳細的結果：

"C： \\ 使用者 \\ 測試 \\ AppData \\ 本機 \\ Temp \\ 2 \\ Test-CsReplica-29fddb35-f56e-4e3c-8f4c-e"

d3bd0e4a083.html "。

Test-CsReplica：命令執行失敗：要求的登錄存取不是

允許。

線上：1個字元：1

\+ Test-CsReplica-Verbose

\+ ~~~~~~~~~~~~~~~~~~~~~~~

\+ CategoryInfo： InvalidOperation： (： ) \[ Test-CsReplica \] ，安全性

Exception

\+ FullyQualifiedErrorId： ProcessingFailed，Microsoft，.Deploy

。TestReplicaCmdlet

PS C： \\ 使用者 \\ 測試\>

PS C： \\ 使用者 \\ 測試 \> Test-CsUcwaConference-TargetFqdn "SelfHost"

icrosoft.com "

警告：無法讀取指定之完全限定的註冊器通訊埠號碼

功能變數名稱 (FQDN) 。 使用預設的註冊器埠號碼。 例外：

InvalidOperationException：在拓撲中找不到相符的群集。

在

SipSyntheticTransaction TryRetri （SyntheticTransactions）

eveRegistrarPortFromTopology (Int32& registrarPortNumber) 

Test-CsUcwaConference：沒有指派的測試使用者

\[LyncTest.SelfHost.Corp.Microsoft.com \] 。 驗證測試使用者設定。

線上：1個字元：1

\+ Test-CsUcwaConference TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"

\+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

\+ CategoryInfo： ResourceUnavailable： (： ) \[ Test-CsUcwaConference\]

, InvalidOperationException

\+ FullyQualifiedErrorId： NotFoundTestUsers、、Microsoft Rtc。合成

eticTransactions.TestUcwaConferenceCmdlet

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能失敗的原因

以下是一些 **Test-CsReplica** 可能失敗的常見原因：

  - 複寫器代理程式和集中式記錄代理程式服務可能會發生較大的問題

  - 在 Windows 防火牆中，可能未開啟必要的埠

  - 必要的 Active Directory 和本機電腦安全性組可能不存在

</div>

</div>

<span> </span>

</div>

</div>

</div>

