---
title: Lync Server 2013：測試連線到聯盟網域的能力
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing ability to connect to a federated domain
ms:assetid: d8ccfade-ef54-47a4-9f87-36213a635ce5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743840(v=OCS.15)
ms:contentKeyID: 63969653
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2176008e3e941068f61a2fb385fa6230df6b25dd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976985"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-connect-to-a-federated-domain-from-lync-server-2013"></a>從 Lync Server 2013 到聯盟網域的測試能力

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
<p>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 CsFederatedPartner Cmdlet 許可權的 RBAC 角色。 若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示執行下列命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsFederatedPartner&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>描述

CsFederatedPartner 會驗證您是否能夠連線到聯盟合作夥伴的網域。 若要驗證與網域的連線性，該網域必須列在允許（同盟）網域的集合中。 您可以使用此命令，在 [允許的網域] 清單中檢索網域清單：

    Get-CsAllowedDomain

如需詳細資訊，請參閱[Test CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) Cmdlet 的說明文件。

</div>

<div>

## <a name="running-the-test"></a>執行測試

FederatedPartner Cmdlet 需要兩種資訊：邊緣伺服器的 FQDN 和聯盟夥伴的 FQDN。 例如，這個命令會測試連接至網域 contoso.com 的能力：

    Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com"

這個命令可讓您測試目前 [允許的網域] 清單中所有網域的連線：

    Get-CsAllowedDomain | ForEach-Object {Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain $_.Identity}

如需詳細資訊，請參閱[Test CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) Cmdlet 的說明文件。

</div>

<div>

## <a name="determining-success-or-failure"></a>判斷成功或失敗

如果您可以與指定的網域取得聯繫，您會收到類似以下的輸出，結果屬性標示為**成功：**

TargetFqdn： atl-cs-001.litwareinc.com

結果：成功

延遲：00:00:00

出錯

自檢

如果無法連絡指定的網域，則會將結果顯示為失敗，而且會在錯誤與診斷屬性中記錄其他資訊：

TargetFqdn： atl-cs-001.litwareinc.com

結果：失敗

延遲：00:00:00

錯誤：504，伺服器超時

診斷： ErrorCode = 2，Source = litwareinc = atl-ws-01，原因 = 請參閱

回應程式碼與原因片語。

DiagnosticHeader 中的 [Rtc]

例如，先前的輸出指出伺服器因逾時錯誤而失敗。 這通常表示網路連通性問題，或與邊緣伺服器聯絡時會發生問題。

如果測試 CsFederatedPartner 失敗，您可能會想要重新執行測試，這次包括詳細參數：

    Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com" -Verbose

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能失敗的原因

以下是測試 CsFederatedPartner 可能失敗的一些常見原因：

  - Edge 伺服器可能無法使用。 您可以使用此命令，讓您的邊緣伺服器的 Fqdn 如下：
    
        Get-CsService -EdgeServer | Select-Object PoolFqdn
    
    然後，您可以 ping 每個 Edge 伺服器，以確認可以在網路上存取它。 例如：
    
        ping atl-edge-001.litwareinc.com

  - 指定的網域可能不會列于 [允許的網域] 清單中。 若要驗證已新增至 [允許的網域] 清單中的網域，請使用此命令：
    
        Get-CsAllowedDomain
    
    如果您想要查看已封鎖使用者與之通訊的網域清單，請使用此命令：
    
        Get-CsBlockedDomain

</div>

</div>

<span> </span>

</div>

</div>

</div>

