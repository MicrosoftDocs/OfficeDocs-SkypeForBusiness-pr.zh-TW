---
title: Lync Server 2013：測試行動使用者的 exchange 立即訊息功能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test mobile users' ability to exchange instant messages
ms:assetid: a78a048f-d413-4bee-8626-d62b8b74f811
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767950(v=OCS.15)
ms:contentKeyID: 63969638
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: db5af113c6ea87a700ca824bcef09b525338f4e6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746233"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-mobile-users-ability-to-exchange-instant-messages-in-lync-server-2013"></a>在 Lync Server 2013 中測試行動使用者的 exchange 立即訊息功能

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
<p>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 CsMcxP2PIM Cmdlet 許可權的 RBAC 角色。 若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示執行下列命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxP2PIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>說明

行動裝置服務可讓行動裝置使用者執行如下動作：

1.  Exchange 立即訊息和目前狀態資訊。

2.  在內部儲存及檢索語音信箱，而不是使用其無線提供者。

3.  利用 Lync 伺服器的功能，例如透過工作和撥出式會議進行通話。

CsMxcP2PIM Cmdlet 能快速且輕鬆地確認使用者可以使用行動服務來交換立即訊息。

</div>

<div>

## <a name="running-the-test"></a>執行測試

若要執行此測試，您必須為每個帳戶建立兩個 Windows PowerShell 認證物件（包含帳戶名稱和密碼的物件）。 當您呼叫 Test CsMcxP2PIM 時，您必須包含這些認證物件和兩個帳戶的 SIP 位址：

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\pilar"
    
    Test-CsMcxP2PIM -TargetFqdn "atl-cs-001.litwareinc.com" -Authentication Negotiate -SenderSipAddres "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:packerman@litwareinc.com" -ReceiverCredential $credential2

如需詳細資訊，請參閱[Test CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM) Cmdlet 的說明主題。

</div>

<div>

## <a name="determining-success-or-failure"></a>判斷成功或失敗

如果兩個測試使用者可以使用行動服務來交換立即訊息，則 CsMcxP2PIM 會傳回測試結果成功：

目標 Fqdn： atl-cs-001.litwareinc.com

目標 Uri：http://atl-cs-001.litwareinc.com:443/mcx

結果：成功

延遲：00:00:00

錯誤訊息：

自檢

如果測試失敗，則會將結果設定為 [失敗]，並會顯示詳細的錯誤訊息和診斷：

目標 Fqdn： atl-cs-001.litwareinc.com

目標 Uri：https://atl-cs-001.litwareinc.com:443/mcx

結果：失敗

延遲：00:00:00

錯誤訊息：網路票證服務沒有收到任何回應。

內部例外狀況：未授權的 HHTP 要求

用戶端協商配置 "Ntlm"。 驗證

從伺服器接收到的標頭是「協商，NTLM」。

內部例外狀況：遠端伺服器傳回錯誤：

（401）未授權。

自檢

內部診斷： X MS-伺服器-Fqdb： atl-cs-

001.litwareinc.com

緩存控制：私人

內容類型：文字/html;字元集 = utf-8。

伺服器： Microsoft-IIS/8。5

WWW-驗證：協商，NTLM

X-電源： ASP.NET

X 內容-類型選項： nosniff

日期：週三，28年5月 2014 19:16:05 GMT

內容-長度：6305

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能失敗的原因

如果 CsMcxP2PIM 測試失敗，您的第一個步驟應該是確認行動服務已啟動且正在執行。 您可以使用網頁瀏覽器來驗證您的 Lync 伺服器池行動服務 URL 是否可存取。 例如，這個命令會驗證 [pool atl-cs-001.litwareinc.com] 的 URL：

    https://atl-cs-001.litwareinc.com/mcx/mcxservice.svc

如果行動服務似乎正在執行，請確認您的兩個測試使用者擁有有效的 Lync 伺服器帳戶。 您可以使用類似以下的命令來取得帳戶資訊：

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

如果 Enabled 屬性不等於 True 或命令失敗，則表示使用者沒有有效的 Lync Server 帳戶。

您也應該確認使用者已啟用行動性。 若要這樣做，請先決定指派給帳戶的行動原則：

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object MobilityPolicy

在您知道原則名稱之後，請使用 CsMobilityPolicy Cmdlet，確認有問題的原則（例如，RedmondMobilityPolicy）已將 EnableMobility 屬性設為 True：

    Get-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

如果您收到含驗證標頭的錯誤訊息，這通常表示您尚未指定有效的使用者帳戶。 確認使用者名稱和密碼，然後再次嘗試測試。 如果您確信使用者帳戶有效，請使用 CsWebServiceConfiguration Cmdlet，然後檢查 UseWindowsAuth 屬性的值。 這會告訴您組織中已啟用哪些驗證方法。如需有關如何排查行動服務問題的其他秘訣，請參閱博客文章[疑難排解外部 Lync 行動連線問題](http://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

