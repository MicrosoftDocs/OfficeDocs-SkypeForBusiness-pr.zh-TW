---
title: Lync Server 2013：驗證通訊錄存取權
description: Lync Server 2013：驗證通訊錄存取權。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating address book access
ms:assetid: 630682c6-9262-46c5-9af1-6193db70374b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720916(v=OCS.15)
ms:contentKeyID: 63969611
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6da08e48be24b3325bc1f415b9baa3c9197717c3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547239"
---
# <a name="validating-address-book-access-in-lync-server-2013"></a>驗證 Lync Server 2013 中的通訊錄存取權

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
<p>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 Test-CsAddressBookService Cmdlet 許可權的 RBAC 角色。 若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAddressBookService&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>描述

Test-CsAddressBookService Cmdlet 為您提供一種方法，讓您確認使用者可以連線至通訊錄下載 Web 服務。 當您執行 Cmdlet 時，Test-CsAddressBookService 會連線至指定集區上的通訊錄下載 Web 服務，並要求通訊錄檔案的位置。 [！注意] 如果通訊錄下載 Web 服務提供該位置，測試會視為成功。 如果要求遭到拒絕，則會將測試視為失敗。

</div>

<div>

## <a name="running-the-test"></a>執行測試

您可以使用預先設定的測試帳戶執行 Test-CsAddressBookService Cmdlet (請參閱設定測試帳戶以執行 Lync Server 測試) 或已啟用 Lync Server 之任何使用者的帳戶。 若要使用測試帳戶執行這項檢查，您只需要指定所測試之 Lync Server 集區的完整功能變數名稱 (FQDN) 。 例如：

    Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com"

若要使用實際使用者帳戶執行這種檢查，您必須先建立 Windows PowerShell 身分憑證物件，其中包含帳戶名稱和密碼。 然後，您必須在呼叫 Test-CsAddressBookService 時，包含該認證物件和指派給該帳戶的 SIP 位址：

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

如需詳細資訊，請參閱 [Test-CsAddressBookService](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService) Cmdlet 的說明文件。

</div>

<div>

## <a name="determining-success-or-failure"></a>決定成功或失敗

如果指定的使用者可以連線到通訊錄服務，您會收到類似如下的輸出，並將 Result 屬性標示為 [ **成功**]：

TargetUri： https://lync-se.fabrikam.com:443/abs/handler

TargetFqdn： atl-cs-001.litwareinc.com

結果：成功

延遲：00：00：06.2260399

錯誤：

診斷：

如果指定的使用者無法進行此連線，則結果會顯示為 [失敗]，而且會在 [錯誤] 和 [診斷] 屬性中記錄其他資訊：

TargetUri：

TargetFqdn： atl-cs-001.litwareinc.com

結果：失敗

延遲：00:00:00

診斷： ErrorCode = 4005、Source = atl-cs-001.litwareinc.com、

原因 = 未啟用 SIP 的目的 URI 或不是

存在。

DiagnosticHeader。

例如，上述輸出會指出測試失敗的原因是指定的使用者 (也就是說，「目的地 URI」 ) 不存在，或是尚未為 Lync Server 啟用。 您可以透過執行類似下列的命令，確認使用者帳戶是否有效，並確認您提供正確的 SIP 位址。

Get-CsUser-Identity "sip:kenmyer@litwareinc.com" |Select-Object SipAddress，啟用

如果 Test-CsAddressBookService 失敗，則您可能想要重新執行測試，這次包括 Verbose 參數：

Test-CsAddressBookService-TargetFqdn "atl-cs-001.litwareinc.com"-Verbose

包含 Verbose 參數時 Test-CsAddressBookService 會傳回所嘗試之每個動作的逐步帳戶，檢查指定之使用者登入 Lync 伺服器的功能。 例如，此範例輸出會顯示 Test-CsAddressBookService （至少在此範例中）可以下載通訊錄檔案：

傳送 Http GET 要求。

檔路徑 = https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs

嘗試次數 = 1

TimeOut (毫秒) = 60000

成功下載 ABS 檔 https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能失敗的原因

以下是一些 Test-CsAddressBookService 可能失敗的常見原因：

  - 您指定的使用者帳戶無效。 您可以執行類似如下的命令，以確認使用者帳戶是否存在：
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - 使用者帳戶有效，但目前未啟用 Lync Server 的帳戶。 若要確認已啟用 Lync Server 的使用者帳戶，請執行類似下列的命令：
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    如果 Enabled 屬性設定為 False，表示使用者目前未啟用 Lync Server。

</div>

<div>

## <a name="see-also"></a>另請參閱


[Test-CsAddressBookService](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

