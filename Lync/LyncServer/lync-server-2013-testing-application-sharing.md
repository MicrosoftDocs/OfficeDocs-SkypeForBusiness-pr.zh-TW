---
title: Lync Server 2013： 測試應用程式共用
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
ms.openlocfilehash: bb9f5771651f68d36666e039a9af71436ac3635b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141479"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-application-sharing-in-lync-server-2013"></a>Lync Server 2013 中共用的測試應用程式

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2014年-11-01_


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
<p>當執行使用 Windows PowerShell 的遠端執行個體時，使用者必須被指派具有執行 Test-csasconference cmdlet 的權限的 RBAC 角色。 若要查看可以使用此 cmdlet 的所有 RBAC 角色的清單，請在 Windows PowerShell 命令提示執行下列命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsASConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>描述

**Test-csasconference** cmdlet 會驗證測試使用者的一組可參與線上會議，其中包含應用程式共用。 若要這麼做，cmdlet 會登錄兩位使用者與 Lync Server 2013 中，並再使用其中一個使用者帳戶建立新的會議，其中包含應用程式共用。 然後指令程式會驗證第二個使用者就可以加入會議。

</div>

<div>

## <a name="running-the-test"></a>執行測試

範例 1 所示的命令會驗證應用程式共用會議，可以在集區 atl-cs-001.litwareinc.com 上進行。 這個命令會假設您已設定的測試使用者指定的集區配對。 如果沒有這類測試使用者存在，命令將會失敗。

    Test-CsASConference -TargetFqdn "atl-cs-001.litwareinc.com"

範例 2 會測試參與在集區 atl-cs-001.litwareinc.com 上應用程式共用會議 Join Launcher 服務的能力。 請注意，此命令會測試本身; 的服務您不需要任何行動裝置才能執行此命令。

    Test-CsASConference -TargetFqdn "atl-cs-001.litwareinc.com" -TestJoinLauncher 

範例 2 所示的命令會測試的一組使用者的能力 (litwareinc\\pilar 和 litwareinc\\kenmyer) 來登入 Lync Server 2013 和再進行應用程式共用會議。 若要這麼做，在範例中的第一個命令會使用 Get-credential 指令程式來建立包含其名稱和密碼的使用者為 Pilar Ackerman 的 Windows PowerShell 命令列介面認證物件。 (因為登入名稱中，litwareinc\\pilar，已包含做為參數，[Windows PowerShell 認證要求] 對話方塊只需要系統管理員輸入為 Pilar Ackerman 帳戶的密碼。)產生的認證物件然後儲存在名為 $cred1 變數。 第二個命令會執行相同的程序，但這次會傳回 Ken Myer 帳戶的認證物件。

在手中的認證物件，第三個命令會決定這些兩個使用者可以登入 Lync Server 2013，並先進行應用程式共用會議。 若要執行這項工作， **Test-csasconference** cmdlet 呼叫時，以及下列參數： TargetFqdn (之登錄器集區 FQDN);SenderSipAddress （第一個測試使用者的 SIP 位址）;與 SenderCredential （包含這個相同的使用者認證的 Windows PowerShell 物件）;ReceiverSipAddress （其他測試使用者的 SIP 位址）;並與 ReceiverCredential （Windows PowerShell 物件包含其他測試使用者的認證）。

    $cred1 = Get-Credential "litwareinc\pilar" 
    $cred2 = Get-Credential "litwareinc\kenmyer" 
    Test-CsASConference -TargetFqdn atl-cs-001.litwareinc.com -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $cred1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a>決定成功或失敗

如果正確設定應用程式共用，您會收到類似，具有標示為 Result 屬性的輸出**成功：**

目標 Fqdn: atl-cs-001.litwareinc.com

結果： 成功

延遲： 00:00:01

錯誤訊息：

診斷：

如果指定的使用者無法共用應用程式，結果會顯示為失敗，以及其他資訊會記錄在 [錯誤] 和 [診斷屬性：

目標 Fqdn: atl-cs-001.litwareinc.com

結果： 失敗

延遲： 00:00:00

錯誤訊息： 10060 的連線嘗試失敗，因為連線對象

正常後沒有回應一段時間，或

已建立的連線失敗，因為已連線的主機

失敗回應 10.188.116.96:5061

內部的例外狀況： 的連線嘗試失敗，因為

連線對象正確後沒有回應一段

時間，或已建立的連線失敗，因為連線的主機

失敗回應 10.188.116.96:5061

診斷：

例如，先前的輸出包含 「 連線的對象並未正確回應 「 附註這通常表示 Edge Server 的問題。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能有為何失敗的原因

以下是一些常見的原因為何**Test-csasconference**可能會失敗：

  - 提供不正確的參數值。 如果使用，必須正確設定選用的參數或測試將會失敗。 重新執行此命令不含選擇性參數，並查看是否成功。

  - 如果測試使用者已指派防止使用應用程式共用會議原則，此命令將會失敗。

  - 如果設定錯誤或尚未部署 Edge Server，此命令將會失敗。

</div>

<div>

## <a name="see-also"></a>另請參閱


[Get-csconferencingpolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsConferencingPolicy)  
[Test-csdataconference](https://docs.microsoft.com/powershell/module/skype/Test-CsDataConference)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

