---
title: Lync Server 2013：測試使用群組延伸的能力
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing ability to employ group expansion
ms:assetid: 9b0fc954-6f9c-411a-ab32-94ebabc42de2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743836(v=OCS.15)
ms:contentKeyID: 63969634
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f99be38a906c508346f580b36d055ccba86a168e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975762"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-employ-group-expansion-in-lync-server-2013"></a>測試在 Lync Server 2013 中使用群組延伸的能力

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
<td><p>日常</p></td>
</tr>
<tr class="even">
<td><p>測試控管</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>需要許可權</p></td>
<td><p>使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</p>
<p>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 CsGroupExpansion Cmdlet 許可權的 RBAC 角色。 若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示執行下列命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsGroupExpansion&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>描述

CsGroupExpansion Cmdlet 可讓您判斷群組延伸在貴組織內是否正常運作。 啟用群組展開時，使用者會將通訊群組設定為連絡人。 這表示這些使用者只要將訊息定至群組，而不是群組成員，就可以傳送相同的立即訊息給所有的群組成員。 [群組延伸] 可讓您快速且輕鬆地查看所有群組成員及其目前狀態。

使用 Test CsGroupExpansion Cmdlet，您可以使用群組的電子郵件地址來指定 Active Directory 通訊群組。 CsGroupExpansion 然後使用群組延伸來取得群組成員資格，並將檢索到的清單與您所提供的群組電子郵件地址的成員資格進行比較。 如果兩個清單相符，則群組延伸作業正常運作。 請注意，您可以使用兩種方式來測試群組延伸：測試服務本身，或測試相關的 web 服務。

如需詳細資訊，請參閱[Test CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) Cmdlet 的說明文件。

</div>

<div>

## <a name="running-the-test"></a>執行測試

CsGroupExpansion Cmdlet 可以使用預先配置的測試帳戶（請參閱設定執行 Lync Server 測試的測試帳戶）或任何已啟用 Lync Server 的使用者帳戶執行。 若要使用測試帳戶執行這項檢查，您只需指定要測試的 Lync 伺服器池 FQDN，以及有效通訊群組的電子郵件地址即可。 例如：

    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com"

若要使用實際的使用者帳戶執行此檢查，您必須先建立一個包含帳戶名稱和密碼的 Lync Server 認證物件。 然後，您必須在系統呼叫 Test-CsGroupExpansion 時包含該認證物件以及指派給該帳戶的 SIP 位址：

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

如需詳細資訊，請參閱[Test CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) Cmdlet 的說明文件。

</div>

<div>

## <a name="determining-success-or-failure"></a>判斷成功或失敗

如果指定的使用者可以使用群組延伸，您會收到類似以下的輸出，並將 Result 屬性標示為**成功：**

TargetUri :https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

TargetFqdn： atl-cs-001.litwareinc.com

結果：成功

延隔時間：00：00：01.1234976

出錯

自檢

如果指定的使用者無法使用群組延伸，結果就會顯示為失敗，而其他資訊將會記錄在錯誤與診斷屬性中：

TargetUri :https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

TargetFqdn： atl-cs-001.litwareinc.com

結果：失敗

延遲：00:00:00

出錯

自檢

測試-CsGroupExpansion：端點無法註冊。 請參閱 ErrorCode，瞭解特定原因。

先前的輸出指出測試失敗，因為指定的使用者無法使用 Lync Server 進行註冊。 如果測試帳戶不存在，或沒有為 Lync Server 啟用，則通常會發生這種情況。 您可以透過執行類似下列的命令，確認帳戶存在，並判斷是否已啟用 nm 版 ocs-14-3 的帳戶：

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled

如果測試 CsGroupExpansion 失敗，您可能會想要重新執行測試，這次包括詳細參數：

    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com" -Verbose

在包含詳細參數的情況下，CsGroupExpansion 會傳回其在檢查指定使用者登入 Lync Server 的能力時所嘗試的每個動作的逐步帳戶。 例如，此輸出表示找不到指定的通訊群組：

正在嘗試取得 web 票證。

Web 服務 url：https://atl-cs-001.litwareinc.com:443/WebTicket/WebTicketService.svc

使用 NTLM/Kerb auth。

GetWebTicketActivity 已完成。

「VerifyDistributionList」活動已開始。

DLX Web Services 回應狀態為： NotFound。

"VerifyDistributionList" 活動在 "0.2597923" 秒內完成。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能失敗的原因

以下是測試 CsGroupExpansion 可能失敗的一些常見原因：

  - 您指定的使用者帳戶無效。 您可以執行如下的命令來確認使用者帳戶已存在：
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - 使用者帳戶有效，但目前尚未啟用 Lync Server 的帳戶。 若要確認使用者帳戶已啟用 Lync Server，請執行類似下列的命令：
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    如果 Enabled 屬性設為 False，表示目前尚未啟用 Lync Server 的使用者。

  - [群組延伸] 可能已停用。 您可以關閉群組延伸。 如果群組延伸已停用，則 CsGroupExpansion Cmdlet 將會失敗。 若要判斷是否已啟用群組延伸，請使用類似以下的命令：
    
        Get-CsWebServiceConfiguration | Select-Object Identity, EnableGroupExpansion

</div>

</div>

<span> </span>

</div>

</div>

</div>

