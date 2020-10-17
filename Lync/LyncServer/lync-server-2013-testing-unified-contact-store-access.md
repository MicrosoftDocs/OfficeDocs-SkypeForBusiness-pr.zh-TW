---
title: Lync Server 2013：測試整合連絡人存放區存取
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing Unified Contact Store access
ms:assetid: 761f46bd-2e14-4f40-82b9-afa1eaa816b0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727309(v=OCS.15)
ms:contentKeyID: 63969621
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5552c03ac18ddd373385674da03d872ce89eb585
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503900"
---
# <a name="testing-unified-contact-store-access-in-lync-server-2013"></a>在 Lync Server 2013 中測試整合連絡人存放區存取權

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2015-05-15_


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
<p>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 <strong>Test-CsUnifiedContactStore</strong> Cmdlet 許可權的 RBAC 角色。 若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsUnifiedContactStore&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>描述

Lync Server 2013 中引入的整合連絡人存放區可讓管理員選擇將使用者的連絡人儲存在 Microsoft Exchange Server 2013 中，而不是在 Lync Server 中。 這樣一來，除了 Lync 2013 之外，使用者還是可以存取 Outlook Web Access 中的同一組連絡人。  (或者，您可以繼續在 Lync Server 中儲存連絡人。 在此情況下，使用者必須維護兩組不同的連絡人：一個用於 Outlook 和 Outlook Web Access，另一個則用於 Lync 2013。 ) 

您可以執行 **Test-CsUnifiedContactStore** Cmdlet，判斷使用者的連絡人是否已移至整合連絡人存放區。 **Test-CsUnifiedContactStore** Cmdlet 會使用指定的使用者帳戶，並聯機至整合連絡人存放區，並嘗試為使用者取回連絡人。 若未取得任何連絡人，命令會一起失敗，並顯示 [使用者未收到任何連絡人] 的訊息。 確認使用者已存在連絡人。

請注意，如果使用者已成功遷移至整合連絡人存放區，但其連絡人清單中沒有連絡人，則 **Test-CsUnifiedContactStore** Cmdlet 會失敗。 指定的使用者至少必須有一個連絡人， **Test-CsUnifiedContactStore** Cmdlet 才能成功完成。

</div>

<div>

## <a name="running-the-test"></a>執行測試

下列範例所示的命令會決定使用者 litwareinc kenmyer 的連絡人是否 \\ 可以在整合連絡人存放區中找到。 為做到這一點，範例中的第一個命令會使用 **Get-Credential** Cmdlet 為使用者 litwareinc Kenmyer 建立 Windows PowerShell 命令列介面認證物件 \\ 。 請注意，您必須為此帳戶提供密碼才能建立有效的認證物件，並確定 **Test-CsUnifiedContactStore** 指令程式可以執行其檢查。

範例中的第二個命令會使用提供的認證物件 ($x) 和使用者 litwareinc kenmyer 的 SIP 位址， \\ 以判斷是否可以在整合連絡人存放區中找到其連絡人。

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsUnifiedContactStore -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a>決定成功或失敗

如果已正確設定連絡人存放區的存取權，您會收到類似下列的輸出，並將 Result 屬性標示為「 **成功」：**

目標 Fqdn： atl-cs-001.litwareinc.com

結果：成功

延遲：00：00：14.9862716

錯誤訊息：

診斷：

如果未正確設定連絡人存放區的存取權，結果將會顯示為 [ **失敗**]，而且會在 [錯誤] 和 [診斷] 內容中記錄其他資訊：

警告：無法讀取指定之完全限定的註冊器通訊埠號碼

功能變數名稱 (FQDN) 。 使用預設的註冊器埠號碼。 例外：

InvalidOperationException：在拓撲中找不到相符的群集。

在

SipSyntheticTransaction TryRetri （SyntheticTransactions）

eveRegistrarPortFromTopology (Int32& registrarPortNumber) 

目標 Fqdn： atl-cs-001.litwareinc.com

結果：失敗

延遲：00:00:00

錯誤訊息：10060，連接嘗試失敗，因為連接的方

在一段時間後沒有正確回應，或

已建立連線失敗，因為連接的主機已

無法回應10.188.116.96：5061

內部例外狀況：連接嘗試失敗，因為

在一段時間後，連接的通訊錄未正確回應

時間或已建立的連線失敗，因為連接的主機

無法回應10.188.116.96：5061

診斷：

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能失敗的原因

以下是一些 **Test-CsUnifiedContactStore** 可能失敗的常見原因：

  - 提供的參數值不正確。 如果使用，必須正確設定選用參數，否則測試將會失敗。 請重新執行不含選用參數的命令，然後查看是否成功。

  - 連線至整合連絡人存放區失敗，但嘗試為使用者取回連絡人失敗。 可能是網路連線問題。

</div>

<div>

## <a name="see-also"></a>另請參閱


[New-CsUserServicesPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsUserServicesPolicy)  
[Set-CsUserServicesPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsUserServicesPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

