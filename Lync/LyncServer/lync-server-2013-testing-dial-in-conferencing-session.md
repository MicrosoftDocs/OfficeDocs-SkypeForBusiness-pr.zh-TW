---
title: Lync Server 2013：測試電話撥入式會議會話
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing dial-in conferencing session
ms:assetid: 6c505be5-5af7-450c-b3ca-10d9122bee5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743834(v=OCS.15)
ms:contentKeyID: 63969613
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a7c3251ef5ff907dbf9964daaca222584953e75
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536080"
---
# <a name="testing-dial-in-conferencing-session-in-lync-server-2013"></a>在 Lync Server 2013 中測試電話撥入式會議會話

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-06-05_


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
<p>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 Test-CsDialInConferencing Cmdlet 許可權的 RBAC 角色。 若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDialInConferencing&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>描述

Test-CsDialInConferencing Cmdlet 會驗證使用者是否可以加入電話撥入式會議。 Test-CsDialInConferencing 會嘗試將測試使用者登入系統來運作。 如果登入成功，則 Cmdlet 會使用使用者的認證和許可權，以嘗試所有可用的電話撥入式會議存取號碼。 每次撥入嘗試的成功或失敗都會記下，然後會從 Lync Server 登出測試使用者。 Test-CsDialInConferencing 只會驗證是否可以進行適當的連線。 此 Cmdlet 不會實際撥打任何電話，也不會建立其他使用者可以加入的電話撥入式會議。

</div>

<div>

## <a name="running-the-test"></a>執行測試

您可以使用預先設定的測試帳戶執行 Test-CsDialInConferencing Cmdlet (請參閱設定測試帳戶以執行 Lync Server 測試) 或任何啟用 Lync Server 之使用者的帳戶。 若要使用測試帳戶執行這項檢查，您只需要指定所測試之 Lync 伺服器集區的 FQDN。 例如：

    Test-CsDialInConferencing -TargetFqdn "atl-cs-001.litwareinc.com" 

若要使用實際使用者帳戶執行這種檢查，您必須建立 Windows PowerShell 身分憑證物件，其中包含帳戶名稱和密碼。 然後，您必須包含該認證物件，以及呼叫 Test-CsDialInConferencing 的帳戶 SIP 位址：

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsDialInConferencing -TargetFqdn atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

如需詳細資訊，請參閱 [Test-CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/Test-CsDialInConferencing) Cmdlet 的說明文件。

</div>

<div>

## <a name="determining-success-or-failure"></a>決定成功或失敗

如果指定的使用者可以登入 Lync 伺服器，然後使用其中一個可用的電話撥入式會議存取號碼進行連線，則會收到類似下列的輸出，並將 Result 屬性標示為「 **成功」：**

TargetFqdn： atl-cs-001.litwareinc.com

結果：成功

延遲：00：00：06.8630376

錯誤：

診斷：

如果指定的使用者無法進行此連線，則結果會顯示為 [失敗]，而且會在 [錯誤] 和 [診斷] 屬性中記錄其他資訊：

TargetFqdn： atl-cs-001.litwareinc.com

結果：失敗

延遲：00:00:00

錯誤：登入已遭拒絕。 檢查適當的認證是否

正在使用中，且帳戶為作用中狀態。

內部例外狀況： NegotiateSecurityAssociation 失敗，錯誤：-

2146893044

診斷：

先前的輸出表明已拒絕對 Lync Server 自身進行存取的測試使用者。 這通常表示傳遞給 Test-CsDialInConferencing 的使用者認證無效。 反過來，您應該重新建立 [Windows PowerShell 認證] 物件。 雖然您可以為使用者帳戶取得密碼，但是您可以使用類似下列的命令來驗證 SIP 位址：

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能失敗的原因

以下是一些 Test-CsDialInConferencing 可能失敗的常見原因：

  - 您指定的使用者帳戶無效。 您可以執行類似如下的命令，以確認使用者帳戶是否存在：
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - 使用者帳戶有效，但目前未啟用 Lync Server 的帳戶。 若要確認是否已為 Lync Server 啟用使用者帳戶，請執行類似下列的命令：
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    如果 Enabled 屬性設定為 False，表示目前未啟用 Lync Server 的使用者。

  - 您可能會有不正確的電話撥入式會議存取號碼。 您可以使用下列命令，傳回目前設定的電話撥入式會議存取號碼清單：
    
        Get-CsDialConferencingAccessNumber

</div>

</div>

<span> </span>

</div>

</div>

</div>

