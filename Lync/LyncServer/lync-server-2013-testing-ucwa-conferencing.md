---
title: Lync Server 2013： 測試 UCWA 會議
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
ms.openlocfilehash: 8c5daad2d43cf5a7e61dd0e87fac79eb98b9c82e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038105"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-ucwa-conferencing-in-lync-server-2013"></a>Lync Server 2013 中的測試 UCWA 會議

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
<p>當執行使用 Windows PowerShell 的遠端執行個體時，使用者必須被指派具有執行<strong>Test-csucwaconference</strong> cmdlet 的權限的 RBAC 角色。 若要查看可以使用此 cmdlet 的所有 RBAC 角色的清單，請在 Windows PowerShell 命令提示執行下列命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsUcwaConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>描述

**Test-csucwaconference**會確認一組的測試使用者可以排程、 加入，然後進行線上會議使用 Unified Communications Web API (UCWA)。 若要這麼做，指令程式將使用 Lync Server 的 web 票證服務來驗證兩位測試使用者，以及它們登錄與 Lync Server。 接著，Cmdlet 會使用召集人認證來召開會議，然後邀請參與者加入會議。 加入會議之後， **test-csucwaconference**會確認使用者可以執行下列項目為交換立即訊息和管理辦法集區]，然後中斷會議及取消註冊的兩個測試使用者。 測試完成時，也會一併刪除排定的會議。

**Test-csucwaconference**也可用來判斷匿名使用者是否可以加入線上會議。

請注意， **test-csucwaconference**應該不針對 Microsoft Lync Server 2010 集區執行，除非 UCWA 已安裝在該集區上。 如果未安裝 UCWA **test-csucwaconference**呼叫將會失敗。

</div>

<div>

## <a name="running-the-test"></a>執行測試

範例 1 所示的命令可確認一對測試使用者能夠參與集區 atl-cs-001.litwareinc.com 上的 UCWA 會議。請注意，如果您未針對 atl-cs-001.litwareinc.com 預先定義一對狀況監控組態的測試使用者，這個命令將會失敗。

    Test-CsUcwaConference -TargetFqdn "atl-cs-001.litwareinc.com"

範例 2 所示的命令會測試的一組使用者的能力 (litwareinc\\pilar 和 litwareinc\\kenmyer) 參與 UCWA 會議。 若要這麼做，在範例中的第一個命令會使用 Get-credential 指令程式來建立 Windows PowerShell 命令列介面認證物件，其中包含的名稱和密碼為 Pilar Ackerman 的使用者。 (因為登入名稱中，litwareinc\\pilar，包含做為參數，[Windows PowerShell 認證要求] 對話方塊只需要系統管理員輸入為 Pilar Ackerman 帳戶的密碼。)產生的認證物件然後儲存在名為 $cred1 變數。 第二個命令會執行相同的程序，但這次會傳回 Ken Myer 帳戶的認證物件。

使用這兩個認證物件手中，在範例中的第三個命令會決定是否為兩位使用者可以參與 UCWA 會議。 若要執行這項工作， **test-csucwaconference**呼叫時，與下列參數： TargetFqdn (之登錄器集區 FQDN);OrganizerSipAddress （如會議召集人的 SIP 位址）;與 OrganizerCredential （包含這個相同的使用者認證的 Windows PowerShell 物件）;ParticipantSipAddress （其他測試使用者的 SIP 位址）;和 ParticipantCredential （Windows PowerShell 命令列介面物件，其中包含其他使用者的認證）。

    $cred1 = Get-Credential "litwareinc\pilar"
    $cred2 = Get-Credential "litwareinc\kenmyer"
    Test-CsUcwaConference -TargetFqdn atl-cs-001.litwareinc.com -OrganizerSipAddress "sip:pilar@litwareinc.com" -OrganizerCredential $cred1 -ParticipantSipAddress "sip:kenmyer@litwareinc.com" -ParticipantCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a>決定成功或失敗

如果已正確設定會議，您會收到類似，具有標示為 Result 屬性的輸出**成功：**

目標 Fqdn: atl-cs-001.litwareinc.com

目標 Uri: https:// LyncTest-SE.LyncTest.SelfHost.Corp。

Microsoft.com:443/CertProv/CertProvisiongService.svc

結果： 成功

延遲： 00:00:14.9862716

錯誤訊息：

診斷：

如果指定的使用者無法使用會議，結果會顯示為**失敗**，以及其他資訊會記錄在 [錯誤] 和 [診斷屬性：

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

以下是一些常見的原因為何**Test-csucwaconference**可能會失敗：

  - 提供不正確的參數值。 如果使用，必須正確設定選用的參數或測試將會失敗。 重新執行此命令不含選擇性參數，並查看是否成功。

  - 進行會議的功能取決於已指派給召開會議 （若是**Test-csucwaconference**指令程式，為 「 寄件者 」） 之使用者的會議原則。 如果召集人不允許包含共同作業活動他/她的會議中 （例如，如果他/她的會議原則有 EnableDataCollaboration 屬性設為 False） 然後**Test-csucwaconference** cmdlet 會失敗。

  - 如果設定錯誤或尚未部署 Edge Server，此命令將會失敗。

</div>

<div>

## <a name="see-also"></a>另請參閱


[Test-csasconference](https://docs.microsoft.com/powershell/module/skype/Test-CsASConference)  
[Test-csdataconference](https://docs.microsoft.com/powershell/module/skype/Test-CsDataConference)  
[Test-csavconference](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

