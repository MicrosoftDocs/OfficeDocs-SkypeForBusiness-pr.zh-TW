---
title: Lync Server 2013： 測試 Web 應用程式的匿名存取
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
ms.openlocfilehash: 9df6a040e71b0dfe82a52cf519357d058b78a1d7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141709"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-anonymous-web-app-access-in-lync-server-2013"></a>測試 Lync Server 2013 中的 Web 應用程式的匿名存取

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2014年-06-07_


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
<td><p>測試工具</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>必要的權限</p></td>
<td><p>當執行在本機上使用 Lync Server 管理命令介面，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</p>
<p>當執行使用 Windows PowerShell 的遠端執行個體時，使用者必須被指派具有執行 Test-cswebappanonymous cmdlet 的權限的 RBAC 角色。 若要查看可以使用此 cmdlet 的所有 RBAC 角色的清單，請在 Windows PowerShell 命令提示執行下列命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsWebAppAnonymous&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>描述

Test-cswebappanonymous cmdlet 會驗證匿名使用者可以加入 Lync Server 會議使用 Lync Web App。 當您執行 cmdlet 時，Test-cswebappanonymous 會連絡的 Web 票證服務，以取得匿名使用者的 web 票證。 如果此 cmdlet 成功中取得此票證，Test-cswebappanonymous 會再連絡 Lync Server，並嘗試建立獨立部署會議的立即訊息，應用程式共用，以及資料共同作業。

請注意 Test-cswebappanonymous 只驗證 Api，用來建立這些會議的連線。 指令程式不會不會實際建立，並先進行任何會議。

</div>

<div>

## <a name="running-the-test"></a>執行測試

Test-cswebappanonymous 指令程式可以使用預先設定的測試帳戶的一組或已啟用 Lync Server 的任何兩個使用者的帳戶來執行。 若要執行這項檢查使用測試帳戶，您只需指定要測試的 Lync 伺服器集區的完整的網域名稱。 例如：

    Test-CsWebAppAnonymous -TargetFqdn atl-cs-001.litwareinc.com

若要執行這項檢查使用實際使用者帳戶，您必須為每個帳戶建立兩個 Lync Server 管理命令介面的認證物件 （包含的帳戶名稱和密碼的物件）。 當您呼叫 Test-cswebappanonymous 時，您必須再包含這些認證物件與兩個帳戶的 SIP 位址：

    $cred1 = Get-Credential "litwareinc\kenmyer"
    
    Test-CsWebApp -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $cred1

如需詳細資訊，請參閱 < Test-cswebappanonymous cmdlet 的說明主題。 請注意 Test-cswebappanonymous 已過時，以在 Lync Server 2013 上使用。

</div>

<div>

## <a name="determining-success-or-failure"></a>決定成功或失敗

如果 Test-cswebappanonymous 可以匿名使用者加入他/她的會議，此 cmdlet 會傳回成功的測試結果：

目標 Fqdn:

結果： 成功

延遲： 00:00:00

錯誤訊息：

診斷：

如果匿名使用者不能加入所需的會議的測試結果會被標示為失敗。 通常 Test-cswebappanonymous 也會報告回詳細的錯誤訊息和診斷：

目標 Fqdn: atl-cs-001.litwareinc.com

結果： 失敗

延遲： 00:00:05.9746266

錯誤訊息： 接收 Web 票證服務沒有回應

診斷： HTTP 要求是使用用戶端未經授權

驗證配置 'Ntlm'。 驗證

從伺服器收到的標頭已 '交涉，NTLM'。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能有為何失敗的原因

Test-cswebappanonymous 失敗通常為中心的使用者驗證錯誤： 您必須執行使用有效的使用者帳戶，即使指令程式會檢查匿名使用者能夠連線至 Lync Server 的測試。 如果 Test-cswebappanonymous 失敗，您應該確認所指定的使用者具有有效的 Lync Server 使用者帳戶。 您可以使用類似如下的命令擷取 Lync Server 的帳戶資訊：

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

如果 Enabled 屬性值不等於，則為 True，或如果命令就會失敗，這表示使用者沒有有效的 Lync Server 帳戶。

您也應確認您執行 cmdlet 時，所提供的密碼是有效的密碼。

Office Web Apps Server 的組態問題也可能會導致 Test-cswebappanonymous 失敗;如果您收到下列診斷，，通常會是這種情況：

HTTP 要求的用戶端驗證配置 'Ntlm' 未經授權。 收到來自伺服器的驗證標頭已 '交涉，NTLM'。

如需有關診斷和解決 Office Web Apps Server 問題請參閱部落格文章[Office Web Apps Server 2013-機器一律回報為 Unhealthy](http://www.wictorwilen.se/office-web-apps-server-2013---machines-are-always-reported-as-unhealthy)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

