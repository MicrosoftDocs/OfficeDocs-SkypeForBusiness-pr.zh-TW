---
title: Lync Server 2013：測試 Web App 存取權
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test Web App access
ms:assetid: 17d67ea3-f74d-4952-ac2b-92c0dacc8014
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767944(v=OCS.15)
ms:contentKeyID: 63969584
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7618bcc9a69d177950bae64354106a67721e822a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746003"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-web-app-access-in-lync-server-2013"></a>在 Lync Server 2013 中測試 Web 應用程式存取權

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-06-07_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>驗證排程</p></td>
<td><p>次</p></td>
</tr>
<tr class="even">
<td><p>測試控管</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>需要許可權</p></td>
<td><p>使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</p>
<p>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 CsWebApp Cmdlet 許可權的 RBAC 角色。 若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示執行下列命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsWebApp&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>說明

CsWebApp Cmdlet 會驗證經過驗證的使用者可以使用 Lync Web App 加入 Lync Server 會議。 當您執行 Cmdlet 時，CsWebApp 會與 Web 票證服務聯絡，以取得指定使用者的網頁入場券。 這些入場券可有效地充當 Lync Server 會議的「許可票證」。 如果可以檢索票證，且如果使用者可以進行驗證，CsWebApp 將會與 Lync Server 取得聯繫，並嘗試建立獨立的會議以進行立即訊息、應用程式共用及資料共同作業。

請注意，測試 CsWebApp 只會驗證用來建立這些會議的 Api 和連線。 這個 Cmdlet 的設計目的是要確認 Lync Web App 可以用來建立及加入會議。 不過，它不會實際建立及執行會議。

</div>

<div>

## <a name="running-the-test"></a>執行測試

CsWebApp Cmdlet 可以使用一組預先配置的測試帳戶或任何兩個已啟用 Lync Server 的使用者帳戶執行。 若要使用測試帳戶執行此檢查，您只需指定要測試的 Lync 伺服器池的完整功能變數名稱。 例如：

    Test-CsWebApp -TargetFqdn "atl-cs-001.litwareinc.com"

若要使用實際的使用者帳戶執行這項檢查，您必須為每個帳戶建立兩個 Windows PowerShell 認證物件（包含帳戶名稱和密碼的物件）。 當您呼叫 Test CsWebApp 時，您必須包含這些認證物件和兩個帳戶的 SIP 位址：

    $cred1 = Get-Credential "litwareinc\kenmyer"
    $cred2 = Get-Credential "litwareinc\pilar"
    
    Test-CsWebApp -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $cred1 -User2SipAddress "sip:pilar@litwareinc.com" -User2Credential $cred2

如需詳細資訊，請參閱[Test CsWebApp](https://docs.microsoft.com/powershell/module/skype/Test-CsWebApp) Cmdlet 的說明主題。 請注意，CsWebApp 已過時，無法在 Lync Server 2013 上使用。

</div>

<div>

## <a name="determining-success-or-failure"></a>判斷成功或失敗

如果測試 CsWebApp 可以將使用者加入其會議，則 Cmdlet 會傳回測試結果成功：

目標 Fqdn：

結果：成功

延遲：00:00:00

錯誤訊息：

自檢

如果使用者無法加入必要的會議，則測試結果會標示為失敗。 通常測試 CsWebApp 也會傳回詳細的錯誤訊息及診斷資訊：

目標 Fqdn： atl-cs-001.litwareinc.com

結果：失敗

延遲：00:00:00

錯誤訊息：沒有收到 Web 票證服務的回應

診斷： HTTP 要求未經用戶端的授權

驗證配置 "Ntlm"。 驗證

從伺服器接收到的標頭是「協商，NTLM」。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能失敗的原因

測試 CsWebApp 的失敗通常會涉及使用者驗證錯誤。 如果測試 CsWebApp 失敗，您應該先確認指定的使用者擁有有效的使用者帳戶，且已啟用 Lync Server。 您可以使用類似以下的命令來取得帳戶資訊：

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

如果 Enabled 屬性不等於 True 或命令失敗，則表示使用者沒有有效的 Lync Server 帳戶。您也應該確認您提供給 Cmdlet 的密碼是有效的。

</div>

</div>

<span> </span>

</div>

</div>

</div>

