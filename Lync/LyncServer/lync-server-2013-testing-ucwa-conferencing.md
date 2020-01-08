---
title: Lync Server 2013：測試 UCWA 會議
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing UCWA conferencing
ms:assetid: 62b3866a-0759-4b1f-99ec-5a68d6a74f00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727306(v=OCS.15)
ms:contentKeyID: 63969610
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9b05b67f6f235cdcf3153149c9bd2373c30815d9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974369"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-ucwa-conferencing-in-lync-server-2013"></a>在 Lync Server 2013 中測試 UCWA 會議

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
<p>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行<strong>CsUcwaConference</strong> Cmdlet 許可權的 RBAC 角色。 若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示執行下列命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsUcwaConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>描述

**CsUcwaConference** Cmdlet 會確認一組測試使用者可以使用整合通訊 Web API （UCWA）排程、加入並進行線上會議。 若要這樣做，此 Cmdlet 會使用 Lync Server web ticket 服務來驗證這兩個測試使用者，然後使用 Lync Server 進行註冊。 然後，該 Cmdlet 會使用召集人認證開始會議，並邀請參與者加入會議。 加入會議之後，**測試 CsUcwaConference** Cmdlet 會驗證使用者是否可以執行 exchange 立即訊息和執行池等動作，然後中斷會議連線並登出兩個測試使用者。 當測試完成時，也會刪除排程的會議。

**CsUcwaConference** Cmdlet 也可以用來判斷匿名使用者是否可以加入線上會議。

請注意，除非已在該池中安裝 UCWA，否則不應針對 Microsoft Lync Server 2010 pool 執行**Test CsUcwaConference** Cmdlet。 如果尚未安裝 UCWA，則**CsUcwaConference** Cmdlet 的呼叫將會失敗。

</div>

<div>

## <a name="running-the-test"></a>執行測試

範例1中所示的命令會確認一組測試使用者可以參與 UCWA 會議的 [pool atl-cs-001.litwareinc.com]。 請注意，如果您未預先定義一對 atl-cs-001.litwareinc.com 的健康情況監視設定測試使用者，此命令就會失敗。

    Test-CsUcwaConference -TargetFqdn "atl-cs-001.litwareinc.com"

範例2所示的命令會測試一對使用者（litwareinc\\pilar 和 litwareinc\\kenmyer）的功能，以參與 UCWA 會議。 若要這樣做，範例中的第一個命令會使用取得認證 Cmdlet 來建立 Windows PowerShell 命令列介面身分憑證物件，該物件包含使用者 Pilar 方的名稱和密碼。 （因為登入名稱（litwareinc\\pilar）是以參數的形式提供，所以 [Windows PowerShell 認證要求] 對話方塊只需要管理員輸入 pilar 方帳戶的密碼。）接著會將產生的認證物件儲存在名為 $cred 1 的變數中。 第二個命令會執行相同的動作，這次會傳回 Ken Myer 帳戶的認證物件。

使用這兩個認證物件時，範例中的第三個命令會判斷兩個使用者是否可以參與 UCWA 會議。 若要執行這項工作，請使用下列參數來呼叫**CsUcwaConference** Cmdlet： TargetFqdn （註冊機構池的 FQDN）;OrganizerSipAddress （會議召集人的 SIP 位址）;OrganizerCredential （包含此相同使用者認證的 Windows PowerShell 物件）;ParticipantSipAddress （其他測試使用者的 SIP 位址）;與 ParticipantCredential （包含其他使用者認證的 Windows PowerShell 命令列介面物件）。

    $cred1 = Get-Credential "litwareinc\pilar"
    $cred2 = Get-Credential "litwareinc\kenmyer"
    Test-CsUcwaConference -TargetFqdn atl-cs-001.litwareinc.com -OrganizerSipAddress "sip:pilar@litwareinc.com" -OrganizerCredential $cred1 -ParticipantSipAddress "sip:kenmyer@litwareinc.com" -ParticipantCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a>判斷成功或失敗

如果會議設定正確，您將會收到類似以下的輸出，結果屬性標示為**成功：**

目標 Fqdn： atl-cs-001.litwareinc.com

目標 Uri： HTTPs://LyncTest-LyncTest. SelfHost。

Microsoft.com:443/CertProv/CertProvisiongService.svc

結果：成功

延隔時間：00：00：14.9862716

錯誤訊息：

自檢

如果指定的使用者無法使用會議，則會將結果顯示為**失敗**，而且會在錯誤與診斷屬性中記錄其他資訊：

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

以下是**測試 CsUcwaConference**可能失敗的一些常見原因：

  - 提供不正確的參數值。 如果使用，必須正確設定選用的參數，否則測試將會失敗。 重新執行不含選用參數的命令，並查看是否成功。

  - 執行會議的功能，取決於已指派給組織會議之使用者的會議原則（在**CsUcwaConference** Cmdlet 中為「寄件者」）。 如果召集人不能在會議中加入共同作業（例如，如果他/她的會議原則將 EnableDataCollaboration 屬性設為 False），則**CsUcwaConference** Cmdlet 將會失敗。

  - 如果 Edge 伺服器未正確設定或尚未部署，此命令就會失敗。

</div>

<div>

## <a name="see-also"></a>請參閱


[Test-CsASConference](https://docs.microsoft.com/powershell/module/skype/Test-CsASConference)  
[Test-CsDataConference](https://docs.microsoft.com/powershell/module/skype/Test-CsDataConference)  
[Test-CsAVConference](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

