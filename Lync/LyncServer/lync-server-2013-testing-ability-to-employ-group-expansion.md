---
title: Lync Server 2013：測試使用群組擴充的能力
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing ability to employ group expansion
ms:assetid: 9b0fc954-6f9c-411a-ab32-94ebabc42de2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743836(v=OCS.15)
ms:contentKeyID: 63969634
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 358d869f212ac3acef91e28ddb8d08322133970f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194336"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-employ-group-expansion-in-lync-server-2013"></a>在 Lync Server 2013 中測試使用群組擴充的能力

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
<p>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 Test-CsGroupExpansion Cmdlet 許可權的 RBAC 角色。 若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsGroupExpansion&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>描述

Test-CsGroupExpansion Cmdlet 可讓您判斷群組擴充是否可在組織內運作。 啟用群組擴充功能時，使用者會將通訊群組設定為連絡人。 這表示，使用者可以將郵件定為群組，而不是該群組的個別成員，就能將相同的立即訊息傳送給所有群組成員。 群組擴充功能可讓您快速而輕鬆地查看所有群組成員及其目前的狀態。

使用 Test-CsGroupExpansion Cmdlet，您可以使用群組的電子郵件地址來指定 Active Directory 通訊群組。 Test-CsGroupExpansion 然後使用群組擴充來取得群組成員資格，並將所檢索的清單與所提供之群組電子郵件地址的成員資格進行比較。 如果兩個清單相符，群組擴充就能正常運作。 請注意，您可以使用兩種方式測試群組擴充：測試服務本身，或測試相關聯的 web 服務。

如需詳細資訊，請參閱[Test-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) Cmdlet 的說明文件。

</div>

<div>

## <a name="running-the-test"></a>執行測試

您可以使用預先設定的測試帳戶執行 Test-CsGroupExpansion Cmdlet (請參閱設定測試帳戶以執行 Lync Server 測試) 或任何已啟用 Lync Server 的使用者帳戶。 若要使用測試帳戶執行這項檢查，您只需要指定所測試之 Lync 伺服器集區的 FQDN 和有效通訊群組的電子郵件地址。 例如：

    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com"

若要使用實際使用者帳戶執行這種檢查，您必須先建立一個包含帳戶名稱和密碼的 Lync Server 身分憑證物件。 然後，您必須在系統呼叫 Test-CsGroupExpansion 時，包含該身分憑證物件和指派給該帳戶的 SIP 位址：

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

如需詳細資訊，請參閱[Test-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) Cmdlet 的說明文件。

</div>

<div>

## <a name="determining-success-or-failure"></a>決定成功或失敗

如果指定的使用者可以使用群組擴充，您會收到類似下列的輸出，其 Result 屬性標示為 [**成功]：**

TargetUri：https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

TargetFqdn： atl-cs-001.litwareinc.com

結果：成功

延遲：00：00：01.1234976

錯誤：

診斷：

如果指定的使用者無法使用群組擴充，則結果會顯示為失敗，而且會在錯誤和診斷屬性中記錄其他資訊：

TargetUri：https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

TargetFqdn： atl-cs-001.litwareinc.com

結果：失敗

延遲：00:00:00

錯誤：

診斷：

Test-CsGroupExpansion：端點無法註冊。 如需特定原因，請參閱 ErrorCode。

先前的輸出表明測試失敗，因為指定的使用者無法使用 Lync Server 註冊。 如果測試帳戶不存在或尚未對 Lync Server 啟用，則通常會發生這種情況。 您可以確認該帳戶是否存在，並執行類似如下的命令，以判斷該帳戶是否已啟用（如有）。

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled

如果 Test-CsGroupExpansion 失敗，則您可能想要重新執行測試，這次包括 Verbose 參數：

    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com" -Verbose

包含 Verbose 參數時 Test-CsGroupExpansion 會傳回每個動作的逐步帳戶，檢查所嘗試的特定使用者登入 Lync Server 的能力。 例如，下列輸出指出找不到指定的通訊群組：

嘗試取得 web 票證。

Web 服務 url：https://atl-cs-001.litwareinc.com:443/WebTicket/WebTicketService.svc

使用 NTLM/Kerb 驗證。

GetWebTicketActivity 已完成。

' VerifyDistributionList ' 活動已開始。

DLX Web 服務回應狀態為： NotFound。

' VerifyDistributionList ' activity 在 ' 0.2597923 ' 秒內完成。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能失敗的原因

以下是一些 Test-CsGroupExpansion 可能失敗的常見原因：

  - 您指定的使用者帳戶無效。 您可以執行類似如下的命令，以確認使用者帳戶是否存在：
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - 使用者帳戶有效，但目前未啟用 Lync Server 的帳戶。 若要確認已啟用 Lync Server 的使用者帳戶，請執行類似下列的命令：
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    如果 Enabled 屬性設定為 False，表示目前未啟用 Lync Server 的使用者。

  - 可能停用群組擴充。 可以關閉群組擴充。 如果停用群組擴充，Test-CsGroupExpansion Cmdlet 會失敗。 若要判斷是否已啟用群組擴充，請使用類似下列的命令：
    
        Get-CsWebServiceConfiguration | Select-Object Identity, EnableGroupExpansion

</div>

</div>

<span> </span>

</div>

</div>

</div>

