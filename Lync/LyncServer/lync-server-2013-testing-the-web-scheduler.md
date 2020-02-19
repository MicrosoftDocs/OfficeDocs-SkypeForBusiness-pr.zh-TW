---
title: Lync Server 2013： 測試 Web 排程器
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
ms.openlocfilehash: f6cd00192a7e2a9695a078768a6cf6ad9fac5873
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141259"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-the-web-scheduler-in-lync-server-2013"></a>在 Lync Server 2013 中進行測試 Web 排程器

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
<p>當執行使用 Windows PowerShell 的遠端執行個體時，使用者必須被指派具有執行<strong>Test-cswebscheduler</strong> cmdlet 的權限的 RBAC 角色。 若要查看可以使用此 cmdlet 的所有 RBAC 角色的清單，請在 Windows PowerShell 命令提示執行下列命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsWebScheduler&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>描述

**Test-cswebscheduler** cmdlet 可讓您判斷特定的使用者是否可以排程會議使用 Web 排程器。 Web 排程器可讓使用者不執行 Outlook 重新排程線上會議。 除此之外，這項新功能 （，並包含 Web Scheduler 工具所隨附的 Microsoft Lync Server 2010 resource kit 中找到的功能） 可讓使用者：

  - 排程新的線上會議。

  - 列出自己所排程的所有會議。

  - 檢視/修改現有的會議。

  - 刪除現有的會議。

  - 使用預先設定的 SMTP 郵件伺服器，傳送電子郵件邀請給會議參與者。

  - 加入現有的會議。

</div>

<div>

## <a name="running-the-test"></a>執行測試

下列範例會驗證的 Web 排程器集區 atl-cs-001.litwareinc.com。 這個命令將會執行只有當測試使用者所定義的集區 atl-cs-001.litwareinc.com。 如果他們有命令將會判斷第一個測試使用者是否可以排程線上會議使用 Web 排程器。

如果沒有定義的測試使用者，然後將會失敗命令，因為它不會知道哪些使用者身分登入。 如果您還沒有定義的集區的測試使用者，就必須納入 UserSipAddress 參數，此命令應使用時，嘗試登入使用者的認證。

    Test-CsWebScheduler -TargetFqdn "atl-cs-001.litwareinc.com"

下一個範例所示的命令會測試特定使用者的能力 (litwareinc\\kenmeyer) 排程線上會議使用 Web 排程器。 若要這麼做，在範例中的第一個命令會使用**Get-credential**指令程式來建立 Windows PowerShell 命令列介面認證物件，其中包含的名稱和密碼的使用者 Ken Meyer。 (因為登入名稱 litwareinc\\kenmeyer 是包含做為參數，[Windows PowerShell 認證要求] 對話方塊只需要系統管理員輸入 Ken Meyer 帳戶的密碼。)產生的認證物件然後儲存在名為 $cred1 變數。

此使用者是否可以登入集區 atl-cs-001.litwareinc.com 及排程線上會議，然後會檢查第二個命令。 若要執行這項工作， **Test-cswebscheduler** cmdlet 會呼叫，以及三個參數： TargetFqdn (之登錄器集區 FQDN);UserCredential （包含為 Pilar Ackerman 的使用者認證的 Windows PowerShell 物件）;和 UserSipAddress （會對應至提供的使用者認證的 SIP 位址）。

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsWebScheduler -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a>決定成功或失敗

如果 web 排程器已正確設定，您會收到類似，具有標示為 [**成功**結果屬性的輸出：

目標 Fqdn: atl-cs-001.litwareinc.com

目標 Uri: https:// atl-cs-001.litwareinc.com。

litwareinc.com:443/Scheduler

結果： 成功

延遲： 00:00:00

錯誤訊息：

診斷：

如果未正確地設定 web 排程器，結果會顯示為**失敗**，及其他資訊會記錄在 [錯誤] 和 [診斷屬性：

警告： 無法讀取登錄器的連接埠號碼指定完整

網域名稱 (FQDN)。 使用預設登錄器連接埠號碼。 例外狀況：

System.InvalidOperationException： 拓撲中找不到比對叢集。

在

Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri

eveRegistrarPortFromTopology (Int32& registrarPortNumber)

目標 Fqdn: atl-cs-001.litwareinc.com

目標 Uri:

結果： 失敗

延遲： 00:00:00

錯誤訊息： 在拓撲中找到不到相符叢集。

診斷：

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能有為何失敗的原因

以下是一些常見的原因為何**Test-cswebscheduler**可能會失敗：

  - 提供不正確的參數值。 如果使用，必須正確設定選用的參數或測試將會失敗。 重新執行此命令不含選擇性參數，並查看是否成功。

  - 如果設定錯誤或尚未部署 Web Scheduler，此命令會失敗。

</div>

<div>

## <a name="see-also"></a>另請參閱


[Set-cswebserver](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServer)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

