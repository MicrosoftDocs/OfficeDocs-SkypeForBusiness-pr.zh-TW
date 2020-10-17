---
title: Lync Server 2013：驗證通訊錄 web 查詢
description: Lync Server 2013：驗證通訊錄 web 查詢。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating address book web query
ms:assetid: e6ae0a5a-e131-4cfe-9a33-6e611831072d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720925(v=OCS.15)
ms:contentKeyID: 63969662
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e73c39fc33f8d1851fc89d277333a94aaa137790
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547249"
---
# <a name="validating-address-book-web-query-in-lync-server-2013"></a>在 Lync Server 2013 中驗證通訊錄 web 查詢

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
<p>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 Test-CsAddressBookWebQuery Cmdlet 許可權的 RBAC 角色。 若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAddressBookWebQuery&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>描述

Test-CsAddressBookWebQuery Cmdlet 可讓系統管理員驗證使用者是否可以使用通訊錄 Web 查詢服務來搜尋特定的連絡人。 當您執行 Cmdlet 時，Test-CsAddressBookWebQuery 會先連線至 Web 票證服務，以進行驗證。 如果驗證成功，則 Cmdlet 會連接到通訊錄 Web 查詢服務，並搜尋指定的連絡人。 如果找到該連絡人，Cmdlet 會嘗試將該資訊傳回本機電腦。 只有在所有這些步驟都可以完成時，才會將測試標記為成功。

如需詳細資訊，請參閱 [Test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) Cmdlet 的說明文件。

</div>

<div>

## <a name="running-the-test"></a>執行測試

您可以使用預先設定的測試帳戶執行 Test-CsAddressBookWebQuery Cmdlet (請參閱設定測試帳戶以執行 Lync Server 測試) 或任何啟用 Lync Server 之使用者的帳戶。 若要使用測試帳戶執行這項檢查，您只需要指定 Lync Server 集區的 FQDN，以及充當搜尋目標之使用者的 SIP 位址。 例如：

    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com"

若要使用實際使用者帳戶執行這種檢查，您必須建立 Windows PowerShell 身分憑證物件，該物件包含有效的使用者名稱和密碼。 然後，您必須在程式碼呼叫 Test-CsAddressBookWebQuery 時，包含該身分憑證物件和指派給該帳戶的 SIP 位址：

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

如需詳細資訊，請參閱 [Test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) Cmdlet 的說明文件。

</div>

<div>

## <a name="determining-success-or-failure"></a>決定成功或失敗

如果指定的使用者可以連線到通訊錄服務並取得目標使用者位址，則會以標記為 [成功] 的 Result 屬性傳回類似下列輸出：

TargetUri： https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

TargetFqdn： atl-cs-001.litwareinc.com

結果：成功

延遲：00：00：06.2611356

錯誤：

診斷：

如果指定的使用者無法連線，或無法檢索目標使用者位址，則結果會顯示為 [失敗]，而且會在 [錯誤及診斷] 屬性中記錄其他資訊：

TargetUri： https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

TargetFqdn： atl-cs-001.litwareinc.com

結果：失敗

延遲：00:00:00

錯誤：通訊錄 Web 服務要求失敗，回應碼

NoEntryFound.

診斷：

因為找不到目標使用者，所以先前的輸出會指出測試失敗。 您可以執行類似下列的命令，判斷是否已將有效的 SIP 位址傳遞給 Test-CsAddressBookWebQuery：

    Get-CsUser | Where-Object {$_.SipAddress -eq "sip:davidlongmire@litwareinc.com"

如果 Test-CsAddressBookWebQuery 失敗，則您可能想要重新執行測試，這次包括 Verbose 參數：

    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com" -Verbose

包含 Verbose 參數時，Test-CsAddressBookWebQuery 會傳回所嘗試之每個動作的逐步帳戶，檢查指定之使用者登入 Lync 伺服器的功能。 例如，此輸出指出 Test-CsAddressBookWebQuery 能夠連線至通訊錄服務，但無法找到目標 SIP 位址：

' QueryAddressBookWebService ' 活動已開始。

呼叫通訊錄 Web 查詢服務。 ABWS URL=

https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

通訊錄查詢例外狀況：由於回應碼 NoEntryFound，Address Book Web 服務要求失敗。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能失敗的原因

以下是一些 Test-CsAddressBookWebQuery 可能失敗的常見原因：

  - 您指定的使用者帳戶無效。 您可以執行類似如下的命令，以確認使用者帳戶是否存在：
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - 使用者帳戶有效，但目前未啟用 Lync Server 的帳戶。 若要確認已啟用 Lync Server 的使用者帳戶，請執行類似下列的命令：
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    如果 Enabled 屬性設定為 False，表示使用者目前未啟用 Lync Server。

  - 目標使用者可能不在通訊錄中。

  - 通訊錄可能尚未完全更新及複製。 您可以執行下列命令，強制更新組織中的所有通訊錄服務器：
    
        Update-CsAddressBook

</div>

</div>

<span> </span>

</div>

</div>

</div>

