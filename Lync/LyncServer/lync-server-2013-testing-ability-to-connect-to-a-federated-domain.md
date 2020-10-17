---
title: Lync Server 2013：測試連接至同盟網域的能力
description: Lync Server 2013：測試連接至同盟網域的能力。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing ability to connect to a federated domain
ms:assetid: d8ccfade-ef54-47a4-9f87-36213a635ce5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743840(v=OCS.15)
ms:contentKeyID: 63969653
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf1f5bdef66d34b9ca2e39797df0b4ad32d9afde
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560819"
---
# <a name="testing-ability-to-connect-to-a-federated-domain-from-lync-server-2013"></a>從 Lync Server 2013 測試連線到同盟網域的能力

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



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
<p>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 Test-CsFederatedPartner Cmdlet 許可權的 RBAC 角色。 若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsFederatedPartner&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>描述

Test-CsFederatedPartner 會驗證您是否能夠連線到同盟協力廠商的網域。 若要驗證網域的連線能力，該網域必須列在 (同盟) 網域的允許集合中。 您可以使用下列命令，在允許的網域清單上檢索網域清單：

    Get-CsAllowedDomain

如需詳細資訊，請參閱 [Test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) Cmdlet 的說明文件。

</div>

<div>

## <a name="running-the-test"></a>執行測試

Test-FederatedPartner Cmdlet 需要兩部分資訊： Edge Server 的 FQDN 和同盟協力廠商的 FQDN。 例如，此命令會測試連線至網域 contoso.com 的功能：

    Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com"

這個命令可讓您測試目前允許的網域清單上的所有網域的連線：

    Get-CsAllowedDomain | ForEach-Object {Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain $_.Identity}

如需詳細資訊，請參閱 [Test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) Cmdlet 的說明文件。

</div>

<div>

## <a name="determining-success-or-failure"></a>決定成功或失敗

如果可以聯繫指定的網域，則會收到類似下列的輸出，並將 Result 屬性標示為 [ **成功]：**

TargetFqdn： atl-cs-001.litwareinc.com

結果：成功

延遲：00:00:00

錯誤：

診斷：

若無法連絡指定的網域，則結果會顯示為 [失敗]，而且會在 [錯誤及診斷] 屬性中記錄其他資訊：

TargetFqdn： atl-cs-001.litwareinc.com

結果：失敗

延遲：00:00:00

錯誤：504，伺服器超時

診斷： ErrorCode = 2，Source = atl-ws-01-cs，Reason = 請參閱

回應碼和 reason 片語。

DiagnosticHeader。

例如，上一個輸出規定因伺服器逾時錯誤，測試失敗。 這通常表示網路連線問題或聯繫 Edge Server 的問題。

如果 Test-CsFederatedPartner 失敗，則您可能想要重新執行測試，這次包括 Verbose 參數：

    Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com" -Verbose

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能失敗的原因

以下是一些 Test-CsFederatedPartner 可能失敗的常見原因：

  - Edge Server 可能無法使用。 您可以使用下列命令來執行 Edge Server 的 Fqdn：
    
        Get-CsService -EdgeServer | Select-Object PoolFqdn
    
    然後，您可以 ping 每一部 Edge Server，以確認可透過網路存取它。 例如：
    
        ping atl-edge-001.litwareinc.com

  - 指定的網域可能並未列在允許的網域清單上。 若要驗證新增至允許的網域清單中的網域，請使用下列命令：
    
        Get-CsAllowedDomain
    
    如果您想要查看封鎖使用者通訊的網域清單，請使用下列命令：
    
        Get-CsBlockedDomain

</div>

</div>

<span> </span>

</div>

</div>

</div>

