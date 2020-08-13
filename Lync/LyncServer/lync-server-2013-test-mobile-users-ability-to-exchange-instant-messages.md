---
title: Lync Server 2013：測試行動使用者對 exchange 立即訊息的能力
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
ms.openlocfilehash: f3536e7bc95aced3a8bd68cab15b8994aa9e697c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194548"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-mobile-users-ability-to-exchange-instant-messages-in-lync-server-2013"></a>在 Lync Server 2013 中測試行動使用者的 exchange 立即訊息能力

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
<td><p>每月</p></td>
</tr>
<tr class="even">
<td><p>測試控管</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>必要的權限</p></td>
<td><p>使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</p>
<p>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 Test-CsMcxP2PIM Cmdlet 許可權的 RBAC 角色。 若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxP2PIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>描述

行動服務可讓行動裝置使用者執行下列工作：

1.  Exchange 立即訊息和目前狀態資訊。

2.  內部儲存及取回語音信箱，而不是與其無線提供者。

3.  利用 Lync Server 功能（例如透過工作和撥出會議進行通話）。

CsMxcP2PIM Cmdlet 提供一種快速而簡單的方法，可驗證使用者是否可以使用行動服務來交換立即訊息。

</div>

<div>

## <a name="running-the-test"></a>執行測試

若要執行此測試，您必須建立兩個 Windows PowerShell 認證物件 (包含每個帳戶之帳戶名稱和密碼) 的物件。 當您呼叫 Test-CsMcxP2PIM 時，您必須包含這兩個帳戶的認證物件和 SIP 位址：

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\pilar"
    
    Test-CsMcxP2PIM -TargetFqdn "atl-cs-001.litwareinc.com" -Authentication Negotiate -SenderSipAddres "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:packerman@litwareinc.com" -ReceiverCredential $credential2

如需詳細資訊，請參閱[Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM) Cmdlet 的 [說明] 主題。

</div>

<div>

## <a name="determining-success-or-failure"></a>決定成功或失敗

如果兩個測試使用者可以使用行動服務來交換立即訊息，Test-CsMcxP2PIM 會傳回測試結果成功：

目標 Fqdn： atl-cs-001.litwareinc.com

目標 Uri：http://atl-cs-001.litwareinc.com:443/mcx

結果：成功

延遲：00:00:00

錯誤訊息：

診斷：

如果測試失敗，則結果會設定為 [失敗]，並且會顯示詳細的錯誤訊息和診斷：

目標 Fqdn： atl-cs-001.litwareinc.com

目標 Uri：https://atl-cs-001.litwareinc.com:443/mcx

結果：失敗

延遲：00:00:00

錯誤訊息： Web 票證服務沒有收到任何回應。

內部例外狀況： HHTP 要求未經授權使用

用戶端協商架構「Ntlm」。 驗證

從伺服器收到的標頭是「協商，NTLM」。

內部例外狀況：遠端伺服器傳回錯誤：

 (401) 未經授權。

診斷：

內部診斷： X-MS-Fqdb： atl-cs-

001.litwareinc.com

快取控制：私人

Content-Type：文字/html;字元集 = utf-8。

伺服器： Microsoft-IIS/8。5

WWW-驗證：協商，NTLM

X-供電方式： ASP.NET

X-Content-Type-選項： nosniff

日期：星期三，28月 2014 19:16:05 （格林威治）

內容長度：6305

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能失敗的原因

如果 Test-CsMcxP2PIM 失敗第一個步驟，應驗證行動性服務是否已啟動並在運作中。 可以使用網頁瀏覽器來驗證 Lync Server 集區的行動服務 URL 是否可以存取。 例如，下列命令會驗證集區 atl-cs-001.litwareinc.com 的 URL：

    https://atl-cs-001.litwareinc.com/mcx/mcxservice.svc

若行動服務似乎已執行，請確認您的兩個測試使用者具有有效的 Lync 伺服器帳戶。 您可以使用類似下列的命令來取得帳戶資訊：

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

如果 Enabled 屬性不等於 True 或如果命令失敗，則表示使用者沒有有效的 Lync 伺服器帳戶。

您也應該確認使用者已啟用行動性。 若要這麼做，請先決定指派給該帳戶的行動原則：

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object MobilityPolicy

在您知道原則名稱後，請使用 Get-CsMobilityPolicy 指令程式確認問題原則 (例如，RedmondMobilityPolicy) 具有 EnableMobility 屬性設定為 True：

    Get-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

如果您收到錯誤訊息及驗證標頭，這通常表示您未指定有效的使用者帳戶。 請確認使用者名稱和密碼，然後再試一次測試。 如果您確信使用者帳戶是有效的，請使用 Get-CsWebServiceConfiguration Cmdlet，並檢查 UseWindowsAuth 屬性的值。 這會告訴您您的組織中已啟用哪種驗證方法。如需如何疑難排解行動性服務的更多秘訣，請參閱博客文章[疑難排解外部 Lync 行動連線問題逐步](https://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx)執行。

</div>

</div>

<span> </span>

</div>

</div>

</div>

