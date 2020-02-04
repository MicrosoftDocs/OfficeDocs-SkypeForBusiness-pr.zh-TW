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
ms.openlocfilehash: 9e24f579a4fcaca2651c0225b515241db00ff990
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745703"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

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
<td><p>日常</p></td>
</tr>
<tr class="even">
<td><p>測試控管</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>需要許可權</p></td>
<td><p>使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</p>
<p>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 CsClientAuth Cmdlet 許可權的 RBAC 角色。 若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示執行下列命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsClientAuth&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>說明

CsClientAuth Cmdlet 可讓您判斷使用者是否可以使用用戶端憑證登入 Lync Server，您可以執行 Test-CsClientAuth Cmdlet。 在呼叫 Test CsClientAuth 之後，此 Cmdlet 會與憑證提供服務取得聯繫，並為指定的使用者下載任何用戶端憑證的複本。 如果可以找到並下載用戶端憑證，測試 CsClientAuth 就會嘗試使用該憑證登入。 如果登入成功，測試 CsClientAuth 就會登出並報告測試已成功完成。 如果找不到或無法下載證書，或者 Cmdlet 無法使用該憑證登入，則 CsClientAuth 會報告測試失敗。

</div>

<div>

## <a name="running-the-test"></a>執行測試

CsClientAuth Cmdlet 是使用任何已啟用 Lync Server 的使用者帳戶來執行。 若要使用實際的使用者帳戶執行此檢查，您必須先建立包含帳戶名稱和密碼的 Windows PowerShell 認證物件。 然後，您必須在系統呼叫 Test-CsClientAuth 時包含該認證物件以及指派給該帳戶的 SIP 位址：

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsClientAuth -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

如需詳細資訊，請參閱[Test CsClientAuth](http://technet.microsoft.com/en-us/library/gg398712\(v=ocs.14\).aspx) Cmdlet 的說明文件。

</div>

<div>

## <a name="determining-success-or-failure"></a>判斷成功或失敗

如果指定的使用者可以使用用戶端憑證登入 Lync Server，您會收到類似以下的輸出，結果屬性標示為**成功：**

TargetFqdn： atl-cs-001.litwareinc.com

結果：成功

延隔時間：00：00：06.8630376

出錯

自檢

如果指定的使用者無法登入，則會將結果顯示為失敗，並會在錯誤與診斷屬性中記錄其他資訊：

TargetFqdn： atl-cs-001.litwareinc.com

結果：失敗

延隔時間：00：00：03.3645259

錯誤：無法下載指定使用者的 CS 憑證。 檢查是否

提供的 uri 與認證正確無誤。

自檢

例如，由於找不到指定使用者的有效用戶端憑證，所以先前的輸出指出測試失敗。 您可以執行下列命令，以傳回頒發給使用者的用戶端憑證清單：

    Get-CsClientCertificate -Identity "sip:kenmyer@litwareinc.com"

如果測試 CsClientAuth 失敗，您可能會想要重新執行測試，這次包括詳細參數：

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsClientAuth -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential -Verbose

包含詳細參數時，當您檢查指定的使用者是否已登入 Lync Server 的功能時，測試 CsClientAuth 會傳回其嘗試的每個動作的逐步帳戶。 例如：

嘗試下載適用于使用者的 CS 憑證： kenmyer@litwareinc.com 端點： STEpid

Web 服務 url：https://atl-cs-001.litwareinc.com:443/CertProv/CertprovisioningService.svc

無法從 web 服務下載 CS 憑證。

確認

\-Web 服務 url 有效且 web 服務正常運作

\-如果您使用\\\\PhoneNo Pin 來進行驗證，請確定它們與使用者 uri 相符

\-如果您使用\\的是 NTLM Kerberos 驗證，請確認您提供的是有效認證

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能失敗的原因

以下是測試 CsClientAuth 可能失敗的一些常見原因：

  - 您指定的使用者帳戶無效。 您可以執行如下的命令來確認使用者帳戶已存在：
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - 使用者帳戶有效，但目前尚未啟用 Lync Server 的帳戶。 若要確認已啟用 Lync Server 的使用者帳戶，請執行如下所示的命令：
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    如果 Enabled 屬性設為 False，表示目前尚未啟用 Lync Server 的使用者。

  - 測試使用者可能沒有有效的用戶端憑證。 您可以使用類似以下的命令，返回指派給使用者的用戶端憑證資訊：
    
        Get-CsClientCertificate -Identity "sip:kenmyer@litwareinc.com"

</div>

</div>

<span> </span>

</div>

</div>

</div>

