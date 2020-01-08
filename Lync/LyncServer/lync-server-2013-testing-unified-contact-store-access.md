---
title: Lync Server 2013：測試整合連絡人存放區存取權
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing Unified Contact Store access
ms:assetid: 761f46bd-2e14-4f40-82b9-afa1eaa816b0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727309(v=OCS.15)
ms:contentKeyID: 63969621
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef1d8d8930b9e732faeef02c76d722331c726b67
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975625"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-unified-contact-store-access-in-lync-server-2013"></a>在 Lync Server 2013 中測試整合連絡人存放區存取權

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
<td><p>日常</p></td>
</tr>
<tr class="even">
<td><p>測試控管</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>需要許可權</p></td>
<td><p>使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</p>
<p>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行<strong>CsUnifiedContactStore</strong> Cmdlet 許可權的 RBAC 角色。 若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示執行下列命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsUnifiedContactStore&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>描述

在 Lync Server 2013 中引入的整合連絡人存放區，可讓系統管理員選擇將使用者的連絡人儲存在 Microsoft Exchange Server 2013 中，而不是在 Lync Server 中。 這可讓使用者除了 Lync 2013 之外，還能在 Outlook Web Access 中存取同一組連絡人。 （或者，您可以繼續在 Lync Server 中儲存連絡人。 在這種情況下，使用者將必須維護兩組不同的連絡人：一個用於 Outlook 與 Outlook Web Access，另一個用於 Lync 2013。）

您可以執行**CsUnifiedContactStore** Cmdlet，判斷是否已將使用者的連絡人移至 [整合連絡人存放區]。 **CsUnifiedContactStore** Cmdlet 會採用指定的使用者帳戶、連線到 [整合] 連絡人存放區，並嘗試為使用者檢索連絡人。 如果無法檢索任何連絡人，則命令會失敗，並出現「使用者沒有收到連絡人的訊息。 確認使用者有連絡人。」

請注意，如果使用者已成功遷移至 [整合連絡人] 存放區，但其連絡人清單中沒有連絡人，則**CsUnifiedContactStore** Cmdlet 將會失敗。 指定的使用者必須至少有一個連絡人， **CsUnifiedContactStore** Cmdlet 才能順利完成。

</div>

<div>

## <a name="running-the-test"></a>執行測試

下列範例所示的命令會判斷是否可在整合連絡人存放\\區中找到使用者 litwareinc kenmyer 的連絡人。 若要這樣做，範例中的第一個命令會使用**取得認證**Cmdlet 來為使用者 litwareinc\\kenmyer 建立 Windows PowerShell 命令列介面認證物件。 請注意，您必須為此帳戶提供密碼才能建立有效的認證物件，並確認**Test CsUnifiedContactStore** Cmdlet 可以執行其檢查。

這個範例中的第二個命令使用所提供的認證物件（$x）和使用者 litwareinc\\KENMYER 的 SIP 位址來判斷是否可在整合連絡人存放區中找到他的連絡人。

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsUnifiedContactStore -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a>判斷成功或失敗

如果正確設定對連絡人存放區的存取權，您會收到類似以下的輸出，結果屬性標示為**成功：**

目標 Fqdn： atl-cs-001.litwareinc.com

結果：成功

延隔時間：00：00：14.9862716

錯誤訊息：

自檢

如果未正確設定對連絡人存放區的存取權，結果將會顯示為**失敗**，而其他資訊將會記錄在錯誤與診斷屬性中：

警告：無法讀取指定之完全限定的註冊機構埠號碼

網功能變數名稱稱（FQDN）。 使用預設的註冊器埠號碼。 引發

InvalidOperationException：在拓撲中找不到相符的群集。

的

TryRetri 的 SyntheticTransactions。 SipSyntheticTransaction

eveRegistrarPortFromTopology （Int32& registrarPortNumber）

目標 Fqdn： atl-cs-001.litwareinc.com

結果：失敗

延遲：00:00:00

錯誤訊息：10060，連線嘗試失敗，因為已連接的方

在一段時間後沒有正確回應，或

已建立的連線失敗，因為連接的主機有

無法回應10.188.116.96：5061

內部例外狀況：連接嘗試失敗，因為

已連接的參與方在一段時間後沒有正確回應

時間或已建立的連線失敗，因為已連接主機

無法回應10.188.116.96：5061

自檢

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能失敗的原因

以下是**測試 CsUnifiedContactStore**可能失敗的一些常見原因：

  - 提供不正確的參數值。 如果使用，必須正確設定選用的參數，否則測試將會失敗。 重新執行不含選用參數的命令，並查看是否成功。

  - 連線至 [整合連絡人存放區] 失敗，且無法為使用者檢索連絡人的嘗試。 可能有網路連通性問題。

</div>

<div>

## <a name="see-also"></a>請參閱


[New-CsUserServicesPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsUserServicesPolicy)  
[Set-CsUserServicesPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsUserServicesPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

