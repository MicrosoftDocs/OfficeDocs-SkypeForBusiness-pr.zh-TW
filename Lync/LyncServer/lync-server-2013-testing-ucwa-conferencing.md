---
title: Lync Server 2013：測試 UCWA 會議
description: Lync Server 2013：測試 UCWA 會議。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing UCWA conferencing
ms:assetid: 62b3866a-0759-4b1f-99ec-5a68d6a74f00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727306(v=OCS.15)
ms:contentKeyID: 63969610
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 37f88a683abb67d55211422fc4dcf45fc1d5c966
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556089"
---
# <a name="testing-ucwa-conferencing-in-lync-server-2013"></a>在 Lync Server 2013 中測試 UCWA 會議

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
<p>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 <strong>Test-CsUcwaConference</strong> Cmdlet 許可權的 RBAC 角色。 若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsUcwaConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>描述

**Test-CsUcwaConference** Cmdlet 會驗證一對測試使用者是否可以使用整合通訊 Web API (UCWA) ，排程、加入和執行線上會議。 若要這樣做，此 Cmdlet 會使用 Lync Server web ticket 服務來驗證這兩個測試使用者，並將其註冊至 Lync Server。 接著，Cmdlet 會使用召集人認證來召開會議，然後邀請參與者加入會議。 在加入會議之後， **Test-CsUcwaConference** Cmdlet 會驗證使用者是否可以做為 exchange 立即訊息和執行集區等事項，然後中斷會議，並取消註冊這兩個測試使用者。 測試完成後，也會刪除排程的會議。

**Test-CsUcwaConference** Cmdlet 也可以用來判斷匿名使用者是否可以加入線上會議。

請注意，除非 UCWA 是安裝在該集區上，否則不應針對 Microsoft Lync Server 2010 集區執行 **Test-CsUcwaConference** Cmdlet。 若尚未安裝 UCWA，則對 **Test-CsUcwaConference** Cmdlet 的呼叫將會失敗。

</div>

<div>

## <a name="running-the-test"></a>執行測試

範例 1 所示的命令可確認一對測試使用者能夠參與集區 atl-cs-001.litwareinc.com 上的 UCWA 會議。請注意，如果您未針對 atl-cs-001.litwareinc.com 預先定義一對狀況監控組態的測試使用者，這個命令將會失敗。

    Test-CsUcwaConference -TargetFqdn "atl-cs-001.litwareinc.com"

範例2所示的命令會測試一對使用者 (litwareinc \\ pilar and litwareinc \\ kenmyer) 加入 UCWA 會議。 為做到這一點，範例中的第一個命令會使用 Get-Credential Cmdlet 來建立 Windows PowerShell 命令列介面身分介面，該物件包含使用者 Pilar Ackerman 的名稱和密碼。  (由於登入名稱 litwareinc \\ pilar 已包含為參數，所以 [Windows PowerShell 認證要求] 對話方塊只要求系統管理員輸入 Pilar Ackerman 帳戶的密碼。 ) 產生的認證物件會儲存在名為 $cred 1 的變數中。 第二個命令會執行相同的程序，但這次會傳回 Ken Myer 帳戶的認證物件。

在手頭的兩個認證物件中，範例中的第三個命令會決定兩個使用者是否可以參與 UCWA 會議。 若要執行此工作，會呼叫 **Test-CsUcwaConference** Cmdlet 及下列參數： TargetFqdn (註冊機構集區的 FQDN) ;OrganizerSipAddress (會議召集人的 SIP 位址) ;OrganizerCredential (包含此相同使用者之認證的 Windows PowerShell 物件) ;ParticipantSipAddress (其他測試使用者) 的 SIP 位址;和 ParticipantCredential (Windows PowerShell 命令列介面物件，該物件包含其他使用者) 的認證。

    $cred1 = Get-Credential "litwareinc\pilar"
    $cred2 = Get-Credential "litwareinc\kenmyer"
    Test-CsUcwaConference -TargetFqdn atl-cs-001.litwareinc.com -OrganizerSipAddress "sip:pilar@litwareinc.com" -OrganizerCredential $cred1 -ParticipantSipAddress "sip:kenmyer@litwareinc.com" -ParticipantCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a>決定成功或失敗

如果會議已正確設定，則會收到類似以下的輸出，其 Result 屬性標示為 [ **成功]：**

目標 Fqdn： atl-cs-001.litwareinc.com

目標 Uri： HTTPs://LyncTest-LyncTest。

Microsoft.com:443/CertProv/CertProvisiongService.svc

結果：成功

延遲：00：00：14.9862716

錯誤訊息：

診斷：

如果指定的使用者無法使用會議，結果將會顯示為 [ **失敗**]，而且會在 [錯誤] 和 [診斷] 屬性中記錄其他資訊：

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

以下是一些 **Test-CsUcwaConference** 可能失敗的常見原因：

  - 提供的參數值不正確。 如果使用，必須正確設定選用參數，否則測試將會失敗。 請重新執行不含選用參數的命令，然後查看是否成功。

  - 召開會議的能力取決於已指派給組織會議 (的會議原則，也就是 "sender" ) 的 **Test-CsUcwaConference** Cmdlet 的情況。 如果召集人不允許在其會議中包含共同作業活動 (例如，如果其會議原則的 EnableDataCollaboration 屬性設定為 False) 則 **Test-CsUcwaConference** 指令程式將會失敗。

  - 如果 Edge Server 設定不當或尚未部署，此命令將會失敗。

</div>

<div>

## <a name="see-also"></a>另請參閱


[Test-CsASConference](https://docs.microsoft.com/powershell/module/skype/Test-CsASConference)  
[Test-CsDataConference](https://docs.microsoft.com/powershell/module/skype/Test-CsDataConference)  
[Test-CsAVConference](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

