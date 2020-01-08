---
title: Lync Server 2013：測試行動使用者存取權
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test mobile user access
ms:assetid: 81d97420-428b-41b7-91ef-185d572d3456
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767947(v=OCS.15)
ms:contentKeyID: 63969624
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eda2ec2d02fe4189c8e34cf700f6f1fd07895ef6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977605"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-mobile-user-access-in-lync-server-2013"></a>在 Lync Server 2013 中測試行動使用者存取權

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
<p>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 CsMcxConference Cmdlet 許可權的 RBAC 角色。 若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示執行下列命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>描述

行動裝置服務可讓行動裝置使用者執行如下動作：

1.  Exchange 立即訊息和目前狀態資訊。

2.  在內部儲存及檢索語音信箱，而不是使用其無線提供者。

3.  利用 Lync 伺服器的功能，例如透過工作和撥出式會議進行通話。 CsMcxConference Cmdlet 能快速且輕鬆地確認使用者可以使用行動裝置加入和參與 Lync Server 會議。

</div>

<div>

## <a name="running-the-test"></a>執行測試

若要執行這項檢查，您必須為每個帳戶建立三個 Windows PowerShell 認證物件（包含帳戶名稱和密碼的物件）。 您必須在呼叫 Test CsMcxConference 時包含這些認證物件和兩個帳戶的 SIP 位址，如下列範例所示：

    $organizerCred = Get-Credential "litwareinc\kenmyer"
    $user1Cred = Get-Credential "litwareinc\packerman"
    $user2Cred = Get-Credential "litwareinc\adelaney"
    
    Test-CsMcxConference -TargetFqdn "atl-cs-001.litwareinc.com" -Authentication Negotiate -OrganizerSipAddress "sip:kenmyer@litwareinc.com" -OrganizerCredential $organizerCred -UserSipAddress "sip:pilar@litwareinc.com" -UserCredential $user1Cred -User2SipAddress "sip:adelaney@litwareinc.com" -User2Credential $user2Cred

如需詳細資訊，請參閱[Test CsMcxConference](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxConference) Cmdlet 的說明主題。

</div>

<div>

## <a name="determining-success-or-failure"></a>判斷成功或失敗

如果檢查成功，測試 CsMcxConference 會報告成功的測試結果：

目標 Fqdn： atl-cs-001.litwareinc.com

目標 Uri：http://atl-cs-001.litwareinc.com:443/mcx

結果：成功

延遲：00:00:00

錯誤訊息：

自檢

如果檢查失敗，CsMcxConference 將會報告失敗的測試結果。 此測試結果通常會伴隨詳細的錯誤訊息和診斷。 例如：

目標 Fqdn： atl-cs-001.litwareinc.com

目標 Uri：https://atl-cs-001.litwareinc.com:443/mcx

結果：失敗

延遲：00:00:00

錯誤訊息：網路票證服務沒有收到任何回應。

內部例外狀況： HHTP 要求未獲用戶端授權

協商配置 "Ntlm"。 收到的驗證標頭

從伺服器為「協商」。

內部例外狀況：遠端伺服器傳回錯誤：（401）

取消.

自檢

內部診斷： X-MS-伺服器-Fqdb： atl-cs-001.litwareinc.com

緩存控制：私人

內容類型：文字/html;字元集 = utf-8。

伺服器： Microsoft-IIS/8。5

WWW-驗證：協商，NTLM

X-電源： ASP.NET

X 內容-類型選項： nosniff

日期：週三，28年5月 2014 19:22:19 GMT

內容-長度：6305

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能失敗的原因

如果測試 CsMcxConference 失敗，您應該先確認行動服務正在執行且可以存取。 您可以使用網頁瀏覽器來驗證您的 Lync 伺服器池行動服務 URL 是否可存取。 例如，這個命令會驗證 [pool atl-cs-001.litwareinc.com] 的 URL：

`https://atl-cs-001.litwareinc.com/mcx/mcxservice.svc`

如果您可以存取行動服務，請確認您的測試使用者擁有有效的 Lync 伺服器帳戶。 您可以使用類似以下的命令來取得帳戶資訊：

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

如果 Enabled 屬性不等於 True 或命令失敗，則表示使用者沒有有效的 Lync Server 帳戶。您也應該確認每個使用者帳戶都已啟用行動。 若要這樣做，請先決定指派給帳戶的行動原則：

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object MobilityPolicy

在您知道原則名稱之後，請使用 CsMobilityPolicy Cmdlet，確認有問題的原則（例如，RedmondMobilityPolicy）已將 EnableMobility 屬性設為 True：

    Get-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

如果您在執行測試 CsMcxConference 時收到「驗證頭」錯誤訊息，這通常表示您尚未指定有效的使用者帳戶，請確認使用者名稱和密碼，然後再次嘗試測試。 如果您確信使用者帳戶有效，請使用 CsWebServiceConfiguration Cmdlet，然後檢查 UseWindowsAuth 屬性的值。 這會告訴您組織中已啟用哪些驗證方法。

如需有關如何排查行動服務問題的其他秘訣，請參閱博客文章[疑難排解外部 Lync 行動連線問題](http://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

