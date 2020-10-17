---
title: Lync Server 2013：測試位置原則
description: Lync Server 2013：測試位置原則。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing location policy
ms:assetid: 23d06fd3-31ee-4480-ba1e-d179a55b8b14
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690127(v=OCS.15)
ms:contentKeyID: 63969591
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4efc7ac6f3beef875ce1496b19b875ff252b145b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560599"
---
# <a name="testing-location-policy-in-lync-server-2013"></a>Lync Server 2013 中的測試位置原則

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
<p>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 Test-CsLocationPolicy Cmdlet 許可權的 RBAC 角色。 若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLocationPolicy&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>描述

Test-CsLocationPolicy Cmdlet 會驗證是否已將位置原則指派給使用者。 位置原則用來套用與 E9-1-1 功能和用戶端位置相關的設定。 位置原則會決定使用者是否已啟用 E9-1-1，如果答案是「是」，表示緊急通話的行為為何。 例如，您可以使用位置原則來定義哪些號碼會在美國) 中 (911，是否應自動通知公司的安全性，以及如何路由傳送通話。

您可以針對使用者或網路子網路測試位置原則。 如果您針對子網路執行測試 (透過指定 Subnet 參數的值)，Cmdlet 就會嘗試解析該子網路的位置原則。 如果該子網路未指派位置原則，則會擷取已設定之使用者的位置原則。 如果成功地取回子網原則，輸出會包含以 subnet-tagid 開頭的 LocationPolicyTagID 值。 如果找不到子網路的位置原則，則 LocationPolicyTagID 的開頭為 user-tagid。

</div>

<div>

## <a name="running-the-test"></a>執行測試

您可以使用預先設定的測試帳戶執行 Test-CsLocationPolicy Cmdlet (請參閱設定測試帳戶以執行 Lync Server 測試) 或任何啟用 Lync Server 之使用者的帳戶。 若要使用測試帳戶執行這項檢查，您只需要指定所測試之 Lync 伺服器集區的 FQDN。 例如：

    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com"

若要使用實際使用者帳戶執行這種檢查，您必須先建立 Windows PowerShell 身分憑證物件，其中包含帳戶名稱和密碼。 接著，當您呼叫 Test-CsLocationPolicy 時，必須包含該認證物件和指派給該帳戶的 SIP 位址：

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

如需詳細資訊，請參閱 [Test-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Test-CsLocationPolicy) Cmdlet 的說明文件。

</div>

<div>

## <a name="determining-success-or-failure"></a>決定成功或失敗

如果指定的使用者有有效的位置原則，則會收到類似下列的輸出，並將 Result 屬性標示為 [ **成功]：**

EnhancedEmergencyServicesEnabled： true

LocationPolicyTagID： user-tagid

TargetFqdn： atl-cs-001.litwareinc.com

結果：成功

延遲：00：00：06.8630376

錯誤：

診斷：

如果找不到指定使用者的有效位置原則，則會顯示 [結果]，並在 [錯誤及診斷] 屬性中記錄其他資訊：

TargetFqdn： atl-cs-001.litwareinc.com

結果：失敗

延遲：00:00:00

錯誤：404，未找到

診斷： ErrorCode = 4005、Source = atl-cs-001.litwareinc.com、

原因 = 未啟用 SIP 的目的 URI 或不是

存在。

DiagnosticHeader。

先前的輸出指出測試失敗的原因是指定的使用者無效：帳戶不存在，或尚未啟用 Lync Server 的使用者。 您可以驗證帳戶是否有效，以及執行類似如下的命令，以判斷該帳戶是否已啟用（包含）。

    Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled

如果 Test-CsLocationPolicy 失敗，則您可能想要重新執行測試，這次包括 Verbose 參數：

    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

包含 Verbose 參數時，Test-CsLocationPolicy 會傳回在驗證位置原則時所嘗試之每個動作的逐步帳戶。 例如，此輸出表示 Lync Server 無法登入測試使用者，可能是因為提供的密碼無效：

傳送註冊要求：

目標 Fqdn = atl-cs-011.litwareinc.com

使用者 Sip 位址 = sip:kenmyer@litwareinc.com

註冊機構埠 = 5061

已選取驗證類型 ' IWA '。

對 sip/atl-cs-001-001 的註冊點擊 litwareinc

' Register ' activity 在 ' 0.0601795 ' 秒內完成。

「登入已遭拒絕」例外狀況。 請檢查是否已使用正確的認證，以及帳戶是否有效。 ' 在工作流程中發生。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能失敗的原因

以下是一些 Test-CsLocationPolicy 可能失敗的常見原因：

  - 您指定的使用者帳戶無效。 您可以執行類似如下的命令，以確認使用者帳戶是否存在：
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - 使用者帳戶有效，但目前未啟用 Lync Server 的帳戶。 若要確認是否已為 Lync Server 啟用使用者帳戶，請執行類似下列的命令：
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    如果 Enabled 屬性設定為 False，表示目前未啟用 Lync Server 的使用者。

</div>

</div>

<span> </span>

</div>

</div>

</div>

