---
title: Lync Server 2013：測試 Web 計畫程式
description: Lync Server 2013：測試 Web 計畫程式。
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
ms.openlocfilehash: 6512bf074078005eac66d1e4f5cd3d8ba2dc4bc7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556149"
---
# <a name="testing-the-web-scheduler-in-lync-server-2013"></a>在 Lync Server 2013 中測試 Web 計畫程式

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
<p>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 <strong>Test-CsWebScheduler</strong> Cmdlet 許可權的 RBAC 角色。 若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsWebScheduler&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>描述

**Test-CsWebScheduler** Cmdlet 可讓您判斷特定使用者是否可以使用 Web 排程器排程會議。 Web 排程器可讓未執行 Outlook 的使用者排程線上會議。 此外，這項新功能 (會結合 Microsoft Lync Server 2010 資源套件隨附的 Web 排程器工具中所提供的功能，) 讓使用者能夠：

  - 排程新的線上會議。

  - 列出自己所排程的所有會議。

  - 檢視/修改現有的會議。

  - 刪除現有的會議。

  - 使用預先設定的 SMTP 郵件伺服器，傳送電子郵件邀請給會議參與者。

  - 加入現有的會議。

</div>

<div>

## <a name="running-the-test"></a>執行測試

下列範例會驗證集區 atl-cs-001.litwareinc.com 的 Web 調度程式。 只有針對集區 atl-cs-001.litwareinc.com 定義測試使用者時，此命令才會運作。 如果有的話，此命令會判斷第一個測試使用者是否可以使用 Web 排程器排程線上會議。

若未定義測試使用者，命令將會失敗，因為它不會知道哪個使用者登入。 若尚未定義集區的測試使用者，則必須包括 UserSipAddress 參數，以及在嘗試登入時，該命令應該使用之使用者的認證。

    Test-CsWebScheduler -TargetFqdn "atl-cs-001.litwareinc.com"

下一個範例中所示的命令會測試特定使用者 (litwareinc \\ kenmeyer) 的功能，以使用 Web 排程器排程線上會議。 為做到這一點，範例中的第一個命令會使用 **Get-Credential** Cmdlet 來建立 Windows PowerShell 命令列介面身分介面，該物件包含使用者 Ken Meyer 的名稱和密碼。  (因為登入名稱 litwareinc \\ kenmeyer 包含為參數，所以 [Windows PowerShell 認證要求] 對話方塊只要求系統管理員輸入 Ken Meyer 帳戶的密碼。 ) 所產生的身分憑證物件會儲存在名為 $cred 1 的變數中。

然後，第二個命令會檢查此使用者是否可以登入集區 atl-cs-001.litwareinc.com 及排程線上會議。 若要執行此工作，會呼叫 **Test-CsWebScheduler** Cmdlet 及三個參數： TargetFqdn (註冊機構集區的 FQDN) ;UserCredential (包含 Pilar Ackerman 使用者認證) 的 Windows PowerShell 物件。和 UserSipAddress (與所提供使用者認證) 相對應的 SIP 位址。

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsWebScheduler -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a>決定成功或失敗

如果 web 排程器設定正確，您會收到類似下列的輸出，並將 Result 屬性標示為 [ **成功**]：

目標 Fqdn： atl-cs-001.litwareinc.com

目標 Uri： HTTPs://atl-cs-001.litwareinc.com。

litwareinc.com:443/Scheduler

結果：成功

延遲：00:00:00

錯誤訊息：

診斷：

如果未正確設定 web 排程器，結果將會顯示為 [ **失敗**]，而且會在 [錯誤及診斷] 屬性中記錄其他資訊：

警告：無法讀取指定之完全限定的註冊器通訊埠號碼

功能變數名稱 (FQDN) 。 使用預設的註冊器埠號碼。 例外：

InvalidOperationException：在拓撲中找不到相符的群集。

在

SipSyntheticTransaction TryRetri （SyntheticTransactions）

eveRegistrarPortFromTopology (Int32& registrarPortNumber) 

目標 Fqdn： atl-cs-001.litwareinc.com

目標 Uri：

結果：失敗

延遲：00:00:00

錯誤訊息：在拓撲中找不到相符的集群。

診斷：

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能失敗的原因

以下是一些 **Test-CsWebScheduler** 可能失敗的常見原因：

  - 提供的參數值不正確。 如果使用，必須正確設定選用參數，否則測試將會失敗。 請重新執行不含選用參數的命令，然後查看是否成功。

  - 如果 Web 排程器設定不當或尚未部署，此命令將會失敗。

</div>

<div>

## <a name="see-also"></a>另請參閱


[Set-CsWebServer](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServer)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

