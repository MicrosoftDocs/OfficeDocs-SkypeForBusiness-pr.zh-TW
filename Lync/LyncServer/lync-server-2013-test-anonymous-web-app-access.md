---
title: Lync Server 2013：測試匿名 Web 應用程式存取權
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test anonymous Web App access
ms:assetid: 92f691cd-e05e-4bab-beb5-251d4b837a19
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767949(v=OCS.15)
ms:contentKeyID: 63969630
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 701954a872645e80d6aac82cab1fbf5745ad6984
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982440"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-anonymous-web-app-access-in-lync-server-2013"></a>在 Lync Server 2013 中測試匿名 Web 應用程式存取權

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
<p>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 CsWebAppAnonymous Cmdlet 許可權的 RBAC 角色。 若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示執行下列命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsWebAppAnonymous&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>描述

Test CsWebAppAnonymous Cmdlet 會驗證匿名使用者是否可以使用 Lync Web App 加入 Lync Server 會議。 當您執行 Cmdlet 時，測試 CsWebAppAnonymous 會與 Web 票證服務聯絡，以取得匿名使用者的 Web 票證。 如果 Cmdlet 成功取得此票證，測試 CsWebAppAnonymous 就會與 Lync Server 取得聯繫，並嘗試建立獨立的會議以進行立即訊息、應用程式共用及資料共同作業。

請注意，測試 CsWebAppAnonymous 只會驗證用來建立這些會議的 Api 和連線。 這個 Cmdlet 不會實際建立並執行任何會議。

</div>

<div>

## <a name="running-the-test"></a>執行測試

CsWebAppAnonymous Cmdlet 可以使用一組預先配置的測試帳戶或任何兩個已啟用 Lync Server 的使用者帳戶執行。 若要使用測試帳戶執行此檢查，您只需指定要測試的 Lync 伺服器池的完整功能變數名稱。 例如：

    Test-CsWebAppAnonymous -TargetFqdn atl-cs-001.litwareinc.com

若要使用實際的使用者帳戶執行此檢查，您必須為每個帳戶建立兩個 Lync Server 管理命令介面身分憑證物件（包含帳戶名稱和密碼的物件）。 當您呼叫 Test CsWebAppAnonymous 時，您必須包含這些認證物件和兩個帳戶的 SIP 位址：

    $cred1 = Get-Credential "litwareinc\kenmyer"
    
    Test-CsWebApp -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $cred1

如需詳細資訊，請參閱 Test CsWebAppAnonymous Cmdlet 的說明主題。 請注意，CsWebAppAnonymous 已過時，無法在 Lync Server 2013 上使用。

</div>

<div>

## <a name="determining-success-or-failure"></a>判斷成功或失敗

如果測試 CsWebAppAnonymous 可以將匿名使用者加入其會議，此 Cmdlet 會傳回測試結果成功：

目標 Fqdn：

結果：成功

延遲：00:00:00

錯誤訊息：

自檢

如果匿名使用者無法加入必要的會議，則測試結果會標示為失敗。 通常測試 CsWebAppAnonymous 也會傳回詳細的錯誤訊息及診斷資訊：

目標 Fqdn： atl-cs-001.litwareinc.com

結果：失敗

延隔時間：00：00：05.9746266

錯誤訊息：沒有收到 Web 票證服務的回應

診斷： HTTP 要求未經用戶端的授權

驗證配置 "Ntlm"。 驗證

從伺服器接收到的標頭是「協商，NTLM」。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能失敗的原因

測試 CsWebAppAnonymous 的失敗通常會繞過使用者驗證錯誤：您必須使用有效的使用者帳戶來執行測試，即使 Cmdlet 要檢查匿名使用者連線至 Lync Server 的能力。 如果測試 CsWebAppAnonymous 失敗，您應該確認指定的使用者擁有有效的 Lync Server 使用者帳戶。 您可以使用類似以下的命令來取得 Lync Server 帳戶資訊：

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

如果 Enabled 屬性不等於 True 或命令失敗，則表示使用者沒有有效的 Lync Server 帳戶。

您也應該確認執行 Cmdlet 時所提供的密碼是有效的密碼。

Office Web Apps Server 的設定問題也可能會導致測試 CsWebAppAnonymous 失敗;如果您收到下列診斷，通常會發生這種情況：

HTTP 要求未經用戶端驗證配置 "Ntlm" 的授權。 從伺服器接收到的驗證標頭是「協商，NTLM」。

如需診斷及解決 Office Web Apps 伺服器問題的詳細資訊，請參閱博客文章[Office Web Apps server 2013-電腦總是報告為不正常](http://www.wictorwilen.se/office-web-apps-server-2013---machines-are-always-reported-as-unhealthy)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

