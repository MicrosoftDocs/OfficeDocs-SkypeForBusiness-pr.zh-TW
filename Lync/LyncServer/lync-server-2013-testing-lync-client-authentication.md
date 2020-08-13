---
title: Lync Server 2013：測試 Lync 用戶端驗證
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing Lync Client authentication
ms:assetid: e22114cb-4456-4e5f-93ab-51592c4a8209
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689120(v=OCS.15)
ms:contentKeyID: 63969659
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 490068a9c9eec3e582471d9ff228b9bbccad43bf
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194086"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-lync-client-authentication-in-lync-server-2013"></a>在 Lync Server 2013 中測試 Lync 用戶端驗證

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
<p>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 Test-CsClientAuth Cmdlet 許可權的 RBAC 角色。 若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsClientAuth&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>描述

Test-CsClientAuth Cmdlet 可讓您判斷使用者是否可以使用用戶端憑證登入 Lync Server，您可以執行 Test-CsClientAuth Cmdlet。 呼叫 Test-CsClientAuth 後，Cmdlet 會聯繫憑證布建服務，並為指定的使用者下載任何用戶端憑證的複本。 如果可以找到並下載用戶端憑證，Test-CsClientAuth 會嘗試使用該憑證登入。 登入成功時，Test-CsClientAuth 會登出並報告測試已成功。 如果找不到憑證或無法下載憑證，或者 Cmdlet 無法使用該憑證登入，則 Test-CsClientAuth 將會報告測試失敗。

</div>

<div>

## <a name="running-the-test"></a>執行測試

使用啟用 Lync Server 之任何使用者的帳戶來執行 Test-CsClientAuth Cmdlet。 若要使用實際使用者帳戶執行這種檢查，您必須先建立 Windows PowerShell 身分憑證物件，其中包含帳戶名稱和密碼。 然後，您必須在系統呼叫 Test-CsClientAuth 時，包含該身分憑證物件和指派給該帳戶的 SIP 位址：

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsClientAuth -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

如需詳細資訊，請參閱[Test-CsClientAuth](https://technet.microsoft.com/library/gg398712\(v=ocs.14\).aspx) Cmdlet 的說明文件。

</div>

<div>

## <a name="determining-success-or-failure"></a>決定成功或失敗

如果指定的使用者可以使用用戶端憑證登入 Lync Server，則會收到類似下列的輸出，並將 Result 屬性標示為 [**成功]：**

TargetFqdn： atl-cs-001.litwareinc.com

結果：成功

延遲：00：00：06.8630376

錯誤：

診斷：

如果指定的使用者無法登入，則結果會顯示為失敗，而且會在錯誤和診斷屬性中記錄其他資訊：

TargetFqdn： atl-cs-001.litwareinc.com

結果：失敗

延遲：00：00：03.3645259

錯誤：無法下載指定使用者的 CS 憑證。 檢查是否

提供的 uri 和認證是正確的。

診斷：

例如，由於找不到指定使用者的有效用戶端憑證，所以先前的輸出會指出測試失敗。 您可以執行下列命令，傳回向使用者發出之用戶端憑證的清單，如下所示：

    Get-CsClientCertificate -Identity "sip:kenmyer@litwareinc.com"

如果 Test-CsClientAuth 失敗，則您可能想要重新執行測試，這次包括 Verbose 參數：

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsClientAuth -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential -Verbose

包含 Verbose 參數時，Test-CsClientAuth 會傳回每個動作的逐步帳戶，檢查所嘗試的每一項動作時，檢查指定的使用者登入 Lync 伺服器的能力。 例如：

嘗試為使用者下載 CS 憑證： kenmyer@litwareinc.com 端點： STEpid

Web 服務 url：https://atl-cs-001.litwareinc.com:443/CertProv/CertprovisioningService.svc

無法從 web 服務下載 CS 憑證。

檢查：

\-Web 服務 url 有效且 web 服務可運作

\-若要使用 PhoneNo \\ \\ Pin 來驗證，請確定它們符合使用者 uri

\-若要使用 NTLM \\ Kerberos 驗證，請確定您提供有效的認證

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能失敗的原因

以下是一些 Test-CsClientAuth 可能失敗的常見原因：

  - 您指定的使用者帳戶無效。 您可以執行類似如下的命令，以確認使用者帳戶是否存在：
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - 使用者帳戶有效，但目前未啟用 Lync Server 的帳戶。 若要確認是否已為 Lync Server 啟用使用者帳戶，請執行類似下列的命令：
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    如果 Enabled 屬性設定為 False，表示目前未啟用 Lync Server 的使用者。

  - 測試使用者可能沒有有效的用戶端憑證。 您可以使用類似下列的命令，傳回指派給使用者之用戶端憑證的相關資訊：
    
        Get-CsClientCertificate -Identity "sip:kenmyer@litwareinc.com"

</div>

</div>

<span> </span>

</div>

</div>

</div>

