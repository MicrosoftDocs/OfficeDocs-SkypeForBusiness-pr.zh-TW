---
title: Lync Server 2013：驗證通訊錄存取權
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Validating address book access
ms:assetid: 630682c6-9262-46c5-9af1-6193db70374b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720916(v=OCS.15)
ms:contentKeyID: 63969611
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 233ad9804ea0f9ddd1075ea01bf7a4c8f35da819
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974919"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validating-address-book-access-in-lync-server-2013"></a>驗證 Lync Server 2013 中的通訊錄存取權

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
<p>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 CsAddressBookService Cmdlet 許可權的 RBAC 角色。 若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示執行下列命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAddressBookService&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>描述

CsAddressBookService Cmdlet 提供一種驗證使用者是否可以連線到通訊錄下載 Web 服務的方式。 當您執行 Cmdlet 時，測試 CsAddressBookService 會連線至指定的池中的通訊錄下載 Web 服務，並要求通訊錄檔案的位置。 如果通訊錄下載 Web 服務提供該位置，則會認為測試已成功完成。 如果要求遭到拒絕，則會認為測試失敗。

</div>

<div>

## <a name="running-the-test"></a>執行測試

CsAddressBookService Cmdlet 可以使用預先配置的測試帳戶來執行（請參閱設定執行 Lync Server 測試的測試帳戶），或任何已啟用 Lync Server 的使用者帳戶。 若要使用測試帳戶執行這項檢查，您只需指定要測試的 Lync 伺服器池的完整功能變數名稱（FQDN）。 例如：

    Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com"

若要使用實際的使用者帳戶執行此檢查，您必須先建立包含帳戶名稱和密碼的 Windows PowerShell 認證物件。 在呼叫 Test CsAddressBookService 時，您必須包含該認證物件以及指派給該帳戶的 SIP 位址：

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

如需詳細資訊，請參閱[Test CsAddressBookService](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService) Cmdlet 的說明文件。

</div>

<div>

## <a name="determining-success-or-failure"></a>判斷成功或失敗

如果指定的使用者能夠連線到通訊錄服務，您會收到與此類似的輸出，結果屬性標示為**成功**：

TargetUri :https://lync-se.fabrikam.com:443/abs/handler

TargetFqdn： atl-cs-001.litwareinc.com

結果：成功

延隔時間：00：00：06.2260399

出錯

自檢

如果指定的使用者無法進行這個連線，則會將結果顯示為失敗，而且會在錯誤與診斷屬性中記錄其他資訊：

TargetUri :

TargetFqdn： atl-cs-001.litwareinc.com

結果：失敗

延遲：00:00:00

診斷： ErrorCode = 4005，Source = atl-cs-001.litwareinc.com，

原因 = 無法針對 SIP 啟用目的 URI，或無法

有.

DiagnosticHeader 中的 [Rtc]

例如，由於指定的使用者（也就是「目標 URI」）不存在或尚未針對 Lync Server 啟用，因此前面的輸出指出測試失敗。 您可以透過執行如下命令來驗證使用者帳戶是否有效，並驗證您是否已提供正確的 SIP 位址：

Move-csuser-身分識別 "sip:kenmyer@litwareinc.com" |選取-物件 SipAddress，已啟用

如果測試 CsAddressBookService 失敗，您可能會想要重新執行測試，這次包括詳細參數：

Test-CsAddressBookService-TargetFqdn "atl-cs-001.litwareinc.com"-詳細資訊

在包含詳細參數的情況下，當您檢查指定使用者登入 Lync Server 的功能時，CsAddressBookService 會傳回其嘗試的每個動作的逐步帳戶。 例如，此範例輸出顯示的是 Test CsAddressBookService （至少在這個範例中），它可以下載通訊錄檔：

傳送 Http 取得要求。

檔案路徑 =https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs

嘗試次數 = 1

TimeOut （毫秒） = 60000

成功下載 ABS 檔案https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能失敗的原因

以下是測試 CsAddressBookService 可能失敗的一些常見原因：

  - 您指定的使用者帳戶無效。 您可以執行如下的命令來確認使用者帳戶已存在：
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - 使用者帳戶有效，但目前沒有為 Lync Server 啟用該帳戶。 若要確認已啟用 Lync Server 的使用者帳戶，請執行如下所示的命令：
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    如果 Enabled 屬性設為 False，表示目前尚未啟用 Lync Server 的使用者。

</div>

<div>

## <a name="see-also"></a>請參閱


[Test-CsAddressBookService](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

