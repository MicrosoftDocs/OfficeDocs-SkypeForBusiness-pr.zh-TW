---
title: Lync Server 2013： 測試複本服務
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
ms.openlocfilehash: 2784796d0eaca5d37aa841ee3db351a841c3c397
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141269"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-the-replica-service-in-lync-server-2013"></a>Lync Server 2013 中的測試複本服務

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2014年-11-03_


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
<td><p>當執行在本機上使用 Lync Server 管理命令介面，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</p>
<p>當執行使用 Windows PowerShell 的遠端執行個體時，使用者必須被指派具有執行<strong>Test-csreplica</strong> cmdlet 的權限的 RBAC 角色。 若要查看可以使用此 cmdlet 的所有 RBAC 角色的清單，請在 Windows PowerShell 命令提示執行下列命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsReplica&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>描述

**Test-csreplica** cmdlet 會驗證 Lync Server 2013 複本服務在本機電腦上執行。 **Test-csreplica** cmdlet 所執行的這類的工作：

  - 檢查複寫器代理程式和集中式記錄代理程式服務的狀態

  - 驗證在 [Windows 防火牆已開啟的必要連接埠

  - 確定本機電腦的安全性群組與必要的 Active Directory 存在。

請注意，必須在本機上執行此 cmdlet。 也就是說，它必須執行相同的電腦上的複本服務執行所在。 沒有針對遠端伺服器執行**Test-csreplica** cmdlet 選項。

</div>

<div>

## <a name="running-the-test"></a>執行測試

範例 1 所示的命令會測試本機電腦上的 Lync Server 2013 複本服務。 本範例會在 Verbose 參數用於保證 – 包括最終失敗或成功的測試和測試所產生的報告的位置 – 測試的相關資訊會顯示在螢幕上。

    Test-CsReplica -Verbose

範例 2 是範例 1 所示命令的變化。 在此情況下，Report 參數是包含指定的資料夾路徑和測試所產生的報表名稱。 如果您未指定報表的路徑報表會提供類似自動產生名稱：

C:\\使用者\\Administrator.Litwareinc\\AppData\\本機\\Temp\\1\\Test-Cs-Replica-3db40ee0-4b5d-4f58-8d3d-b1e61253129e.html

    Test-CsReplica -Verbose -Report C:\Logs\ReplicaTest.html

</div>

<div>

## <a name="determining-success-or-failure"></a>決定成功或失敗

在此處插入區段主體。

VERBOSE： 建立新的記錄檔 」 c:\\使用者\\測試\\AppData\\本機\\Temp\\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml 」。

VERBOSE： 建立新的記錄檔 」 c:\\使用者\\測試\\AppData\\本機\\Temp\\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml 」。

VERBOSE: 「 Test-csreplica 」 處理已順利完成。

VERBOSE： 可以在找到詳細的結果 」 c:\\使用者\\測試\\AppData\\本機\\Temp\\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml 」。

VERBOSE： 建立新的記錄檔

「 C:\\使用者\\測試\\AppData\\本機\\Temp\\2\\Test-CsReplica-29fddb35-f56e-4e3c-8f4c-e

d3bd0e4a083.xml 」。

VERBOSE： 建立新的記錄檔

「 C:\\使用者\\測試\\AppData\\本機\\Temp\\2\\Test-CsReplica-29fddb35-f56e-4e3c-8f4c-e

d3bd0e4a083.html 」。

警告： Test-csreplica 失敗。

警告： 可以在找到詳細的結果

「 C:\\使用者\\測試\\AppData\\本機\\Temp\\2\\Test-CsReplica-29fddb35-f56e-4e3c-8f4c-e

d3bd0e4a083.html 」。

Test-csreplica： 命令執行失敗： 要求不是登錄的存取

允許。

在線條： 1 char: 1

\+Test-csreplica-Verbose

\+ ~~~~~~~~~~~~~~~~~~~~~~~

\+CategoryInfo: InvalidOperation: （:）\[Test-csreplica\]，安全性

Exception

\+FullyQualifiedErrorId: ProcessingFailed,Microsoft.Rtc.Management.Deploy

ment。TestReplicaCmdlet

PS C:>\\使用者\\測試\>

PS C:>\\使用者\\測試\>Test-csucwaconference TargetFqdn 」 LyncTest.SelfHost.Corp.M

icrosoft.com 」

警告： 無法讀取登錄器的連接埠號碼指定完整

網域名稱 (FQDN)。 使用預設登錄器連接埠號碼。 例外狀況：

System.InvalidOperationException： 拓撲中找不到比對叢集。

在

Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri

eveRegistrarPortFromTopology (Int32& registrarPortNumber)

Test-csucwaconference： 沒有指派的測試使用者

\[LyncTest.SelfHost.Corp.Microsoft.com\]。 驗證測試使用者設定。

在線條： 1 char: 1

\+Test-csucwaconference TargetFqdn 「 LyncTest.SelfHost.Corp.Microsoft.com 」

\+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

\+CategoryInfo: ResourceUnavailable: （:）\[Test-csucwaconference\]

InvalidOperationException

\+FullyQualifiedErrorId: NotFoundTestUsers,Microsoft.Rtc.Management.Synth

eticTransactions.TestUcwaConferenceCmdlet

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能有為何失敗的原因

以下是一些常見的原因為何**Test-csreplica**可能會失敗：

  - 可能會有較大的複寫器代理程式和集中式記錄代理程式服務問題

  - 必要的連接埠可能無法開啟在 [Windows 防火牆

  - 本機電腦的安全性群組與必要的 Active Directory 可能不存在

</div>

</div>

<span> </span>

</div>

</div>

</div>

