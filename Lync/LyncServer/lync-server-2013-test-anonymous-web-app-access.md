---
title: Lync Server 2013：測試匿名 Web 應用程式存取
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test anonymous Web App access
ms:assetid: 92f691cd-e05e-4bab-beb5-251d4b837a19
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767949(v=OCS.15)
ms:contentKeyID: 63969630
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a3d90d3de8624f9965b04990ad996d9c04a954f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519310"
---
# <a name="test-anonymous-web-app-access-in-lync-server-2013"></a>在 Lync Server 2013 中測試匿名 Web 應用程式存取權

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



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
<p>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 Test-CsWebAppAnonymous Cmdlet 許可權的 RBAC 角色。 若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsWebAppAnonymous&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>描述

Test-CsWebAppAnonymous Cmdlet 會驗證匿名使用者是否可以使用 Lync Web App 加入 Lync Server 會議。 當您執行 Cmdlet 時，Test-CsWebAppAnonymous 會聯繫 Web Ticket 服務，以取得匿名使用者的 web 票證。 如果此 Cmdlet 成功取得此票證，Test-CsWebAppAnonymous 將會聯繫 Lync Server，並嘗試建立個別會議以進行立即訊息、應用程式共用及資料共同作業。

請注意，Test-CsWebAppAnonymous 只會驗證用來建立這些會議的 APIs 和連線。 此 Cmdlet 不會實際建立及執行任何會議。

</div>

<div>

## <a name="running-the-test"></a>執行測試

您可以使用一組預先設定的測試帳戶或任何兩個啟用 Lync Server 之使用者的帳戶執行 Test-CsWebAppAnonymous Cmdlet。 若要使用測試帳戶執行這項檢查，您只需要指定所測試之 Lync Server 集區的完整功能變數名稱。 例如：

    Test-CsWebAppAnonymous -TargetFqdn atl-cs-001.litwareinc.com

若要使用實際使用者帳戶執行這項檢查，您必須建立兩個 Lync Server 管理命令介面認證物件 (包含每個帳戶的帳戶名稱和密碼) 的物件。 當您呼叫 Test-CsWebAppAnonymous 時，您必須包含這兩個帳戶的認證物件和 SIP 位址：

    $cred1 = Get-Credential "litwareinc\kenmyer"
    
    Test-CsWebApp -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $cred1

如需詳細資訊，請參閱 Test-CsWebAppAnonymous Cmdlet 的 [說明] 主題。 請注意，Test-CsWebAppAnonymous 已過時，無法在 Lync Server 2013 上使用。

</div>

<div>

## <a name="determining-success-or-failure"></a>決定成功或失敗

如果 Test-CsWebAppAnonymous 可以將匿名使用者加入其會議，此 Cmdlet 將會傳回測試結果成功：

目標 Fqdn：

結果：成功

延遲：00:00:00

錯誤訊息：

診斷：

如果匿名使用者無法加入必要的會議，則測試結果會標示為失敗。 通常 Test-CsWebAppAnonymous 也會報告詳細的錯誤訊息和診斷：

目標 Fqdn： atl-cs-001.litwareinc.com

結果：失敗

延遲：00：00：05.9746266

錯誤訊息：沒有為 Web-Ticket 服務接收任何回應

診斷：未授權用戶端的 HTTP 要求

驗證架構「Ntlm」。 驗證

從伺服器收到的標頭是「協商，NTLM」。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能失敗的原因

Test-CsWebAppAnonymous 失敗通常會圍繞使用者驗證錯誤進行旋轉：您必須使用有效的使用者帳戶執行測試，即使此 Cmdlet 檢查匿名使用者連線到 Lync Server 的能力也是一樣。 如果 Test-CsWebAppAnonymous 失敗，您應該確認指定的使用者是否有有效的 Lync Server 使用者帳戶。 您可以使用類似下列的命令，來取得 Lync Server 帳戶資訊：

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

如果 Enabled 屬性不等於 True 或如果命令失敗，則表示使用者沒有有效的 Lync 伺服器帳戶。

您也應該確認執行 Cmdlet 時所提供的密碼是有效的密碼。

Office Web Apps Server 的設定問題也會導致 Test-CsWebAppAnonymous 失敗。當您收到下列診斷時，通常會發生這種情況：

以用戶端驗證架構 ' Ntlm ' 未授權的 HTTP 要求。 從伺服器接收的驗證標頭為「協商，NTLM」。

如需診斷及解決 Office Web Apps Server 問題的詳細資訊，請參閱博客文章中的 [Office Web Apps server 2013-電腦永不報告為狀況不良](http://www.wictorwilen.se/office-web-apps-server-2013---machines-are-always-reported-as-unhealthy)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

