---
title: Lync Server 2013：測試應用程式共用
description: Lync Server 2013：測試應用程式共用。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing application sharing
ms:assetid: 8d21db9b-10d1-4b43-b057-0deb1df1c205
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727310(v=OCS.15)
ms:contentKeyID: 63969629
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f857908e374239b4054985b88951cd12720ed418
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560719"
---
# <a name="testing-application-sharing-in-lync-server-2013"></a>在 Lync Server 2013 中測試應用程式共用

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-11-01_


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
<p>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 Test-CsASConference Cmdlet 許可權的 RBAC 角色。 若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsASConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>描述

**Test-CsASConference** Cmdlet 會驗證一組測試使用者是否可以參與包含應用程式共用的線上會議。 若要這麼做，指令程式會向 Lync Server 2013 註冊兩位使用者，然後使用其中一個使用者帳戶來建立包含應用程式共用的新會議。 然後，此 Cmdlet 會驗證第二個使用者是否可以加入該會議。

</div>

<div>

## <a name="running-the-test"></a>執行測試

範例1所示的命令會驗證是否可以在集區 atl-cs-001.litwareinc.com 上進行應用程式共用會議。 這個命令假設您已針對指定的集區設定一對測試使用者。 如果不存在這樣的測試使用者，命令將會失敗。

    Test-CsASConference -TargetFqdn "atl-cs-001.litwareinc.com"

範例2會測試 Join 啟動器服務加入集區 atl-cs-001.litwareinc.com 上的應用程式共用會議的能力。 請注意，此命令只會測試服務本身;您不需要任何行動裝置即可執行命令。

    Test-CsASConference -TargetFqdn "atl-cs-001.litwareinc.com" -TestJoinLauncher 

範例2所示的命令會測試一對使用者 (litwareinc \\ pilar and litwareinc \\ kenmyer) 登入 Lync Server 2013，然後執行應用程式共用會議。 為做到這一點，範例中的第一個命令會使用 Get-Credential Cmdlet 來建立 Windows PowerShell 命令列介面憑證物件，該物件包含使用者 Pilar Ackerman 的名稱和密碼。  (因為登入名稱 litwareinc \\ pilar 已包含為參數，所以 [Windows PowerShell 認證要求] 對話方塊只要求系統管理員輸入 Pilar Ackerman 帳戶的密碼。 ) 所產生的身分憑證物件會儲存在名為 $cred 1 的變數中。 第二個命令會執行相同的程序，但這次會傳回 Ken Myer 帳戶的認證物件。

使用 credential 物件，第三個命令會判斷這兩位使用者是否可以登入 Lync Server 2013 並執行應用程式共用會議。 若要執行此工作，會呼叫 **Test-CsASConference** Cmdlet，以及下列參數： TargetFqdn (註冊機構集區的 FQDN) ;SenderSipAddress (第一個測試使用者的 SIP 位址) ;SenderCredential (包含此相同使用者之認證的 Windows PowerShell 物件) ;ReceiverSipAddress (其他測試使用者) 的 SIP 位址;和 ReceiverCredential (包含其他測試使用者) 之認證的 Windows PowerShell 物件。

    $cred1 = Get-Credential "litwareinc\pilar" 
    $cred2 = Get-Credential "litwareinc\kenmyer" 
    Test-CsASConference -TargetFqdn atl-cs-001.litwareinc.com -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $cred1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a>決定成功或失敗

若應用程式共用已正確設定，則會收到類似以下的輸出，其 Result 屬性標示為 [ **成功]：**

目標 Fqdn： atl-cs-001.litwareinc.com

結果：成功

延遲：00:00:01

錯誤訊息：

診斷：

如果指定的使用者無法共用應用程式，則結果會顯示為 [失敗]，而且會在 [錯誤] 和 [診斷] 屬性中記錄其他資訊：

目標 Fqdn： atl-cs-001.litwareinc.com

結果：失敗

延遲：00:00:00

錯誤訊息：10060，連接嘗試失敗，因為連接的方

在一段時間後沒有正確回應，或

已建立連線失敗，因為連接的主機已

無法回應10.188.116.96：5061

內部例外狀況：連接嘗試失敗，因為

在一段時間後，連接的通訊錄未正確回應

時間或已建立的連線失敗，因為連接的主機

無法回應10.188.116.96：5061

診斷：

例如，上一個輸出包含的附注「連接的團體沒有正確回應」，這通常表示 Edge Server 發生問題。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能失敗的原因

以下是一些 **Test-CsASConference** 可能失敗的常見原因：

  - 提供的參數值不正確。 如果使用，必須正確設定選用參數，否則測試將會失敗。 請重新執行不含選用參數的命令，然後查看是否成功。

  - 如果測試使用者已獲指派會議原則，可防止使用者使用應用程式共用，此命令將會失敗。

  - 如果 Edge Server 設定不當或尚未部署，此命令將會失敗。

</div>

<div>

## <a name="see-also"></a>另請參閱


[Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsConferencingPolicy)  
[Test-CsDataConference](https://docs.microsoft.com/powershell/module/skype/Test-CsDataConference)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

