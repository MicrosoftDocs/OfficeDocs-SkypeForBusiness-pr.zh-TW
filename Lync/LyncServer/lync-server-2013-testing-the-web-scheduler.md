---
title: Lync Server 2013：測試網頁排程程式
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing the Web scheduler
ms:assetid: 58e34058-1afa-42e3-9096-c4ea1954c237
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727304(v=OCS.15)
ms:contentKeyID: 63969603
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 65d7dc70bad90dc4e4c94e2db273f44ed20c50ce
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745413"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-the-web-scheduler-in-lync-server-2013"></a>在 Lync Server 2013 中測試網頁排程程式

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
<p>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行<strong>CsWebScheduler</strong> Cmdlet 許可權的 RBAC 角色。 若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示執行下列命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsWebScheduler&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>說明

**Test CsWebScheduler** Cmdlet 可讓您判斷特定使用者是否可以使用 Web 排程器來排程會議。 Web 排程器可讓未執行 Outlook 的使用者排程線上會議。 在其他專案中，這項新功能（包含在 Microsoft Lync Server 2010 資源套件隨附的網頁排程工具中找到的功能）可讓使用者：

  - 排程新的線上會議。

  - 列出他或她排程的所有會議。

  - [查看] 或 [修改現有的會議]。

  - 刪除現有的會議。

  - 使用預先設定的 SMTP 郵件伺服器傳送電子郵件邀請給會議參與者。

  - 加入現有的會議。

</div>

<div>

## <a name="running-the-test"></a>執行測試

下列範例會驗證 [pool atl-cs-001.litwareinc.com] 的網頁排程程式。 只有針對 [pool atl-cs-001.litwareinc.com] 定義測試使用者時，才能使用此命令。 如果有的話，命令會判斷第一個測試使用者是否可以使用 Web 排程器來排程線上會議。

如果沒有定義測試使用者，命令將會失敗，因為它不會知道哪個使用者登入。 如果您沒有為某個池定義測試使用者，則您必須加入 UserSipAddress 參數，以及嘗試登入時該命令應該使用的使用者認證。

    Test-CsWebScheduler -TargetFqdn "atl-cs-001.litwareinc.com"

下一個範例中所示的命令會測試特定使用者（litwareinc\\kenmeyer）的功能，以使用 Web 排程器來排程線上會議。 若要這樣做，範例中的第一個命令會使用 [**取得認證**Cmdlet] 來建立 Windows PowerShell 命令列介面身分憑證物件，其中包含使用者 Ken Meyer 的名稱和密碼。 （因為登入名稱 litwareinc\\kenmeyer 是以參數的形式提供，所以 [Windows PowerShell 認證要求] 對話方塊只需要系統管理員輸入 Ken Meyer 帳戶的密碼。）接著會將產生的認證物件儲存在名為 $cred 1 的變數中。

然後，第二個命令會檢查此使用者是否可以登入 [pool atl-cs-001.litwareinc.com]，並排程線上會議。 若要執行這項工作，請使用三個參數： TargetFqdn （註冊機構池的 FQDN）來呼叫**CsWebScheduler** Cmdlet;UserCredential （包含 Pilar 方使用者認證的 Windows PowerShell 物件）;與 UserSipAddress （與提供的使用者認證相對應的 SIP 位址）。

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsWebScheduler -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a>判斷成功或失敗

如果網頁排程器設定正確，您將會收到類似以下的輸出，結果屬性標示為**成功**：

目標 Fqdn： atl-cs-001.litwareinc.com

目標 Uri： HTTPs://atl-cs-001.litwareinc.com。

litwareinc.com:443/Scheduler

結果：成功

延遲：00:00:00

錯誤訊息：

自檢

如果未正確設定 web 排程器，結果將會顯示為**失敗**，而其他資訊將會記錄在錯誤與診斷屬性中：

警告：無法讀取指定之完全限定的註冊機構埠號碼

網功能變數名稱稱（FQDN）。 使用預設的註冊器埠號碼。 引發

InvalidOperationException：在拓撲中找不到相符的群集。

的

TryRetri 的 SyntheticTransactions。 SipSyntheticTransaction

eveRegistrarPortFromTopology （Int32& registrarPortNumber）

目標 Fqdn： atl-cs-001.litwareinc.com

目標 Uri：

結果：失敗

延遲：00:00:00

錯誤訊息：在拓撲中找不到相符的群集。

自檢

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能失敗的原因

以下是**測試 CsWebScheduler**可能失敗的一些常見原因：

  - 提供不正確的參數值。 如果使用，必須正確設定選用的參數，否則測試將會失敗。 重新執行不含選用參數的命令，並查看是否成功。

  - 如果網頁排程程式未正確設定或尚未部署，此命令就會失敗。

</div>

<div>

## <a name="see-also"></a>請參閱


[Set-CsWebServer](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServer)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

