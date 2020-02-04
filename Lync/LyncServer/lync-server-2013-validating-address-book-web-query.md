---
title: Lync Server 2013：驗證通訊錄網頁查詢
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
ms.openlocfilehash: 31d6a38c0c1d8a67977f9dd66da2a94b51a4f9ab
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763657"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validating-address-book-web-query-in-lync-server-2013"></a>在 Lync Server 2013 中驗證通訊錄網頁查詢

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
<p>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 CsAddressBookWebQuery Cmdlet 許可權的 RBAC 角色。 若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示執行下列命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAddressBookWebQuery&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>說明

CsAddressBookWebQuery Cmdlet 可讓系統管理員確認使用者可以使用通訊錄網頁查詢服務來搜尋特定的連絡人。 當您執行 Cmdlet 時，測試 CsAddressBookWebQuery 會先連線到要驗證的 Web 票證服務。 如果驗證成功，則 Cmdlet 會連線至通訊錄網頁查詢服務，並搜尋指定的連絡人。 如果找到該連絡人，則 Cmdlet 會嘗試將該資訊傳回本機電腦。 只有在所有這些步驟都能完成時，才會將測試標示為成功。

如需詳細資訊，請參閱[Test CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) Cmdlet 的說明文件。

</div>

<div>

## <a name="running-the-test"></a>執行測試

CsAddressBookWebQuery Cmdlet 可以使用預先配置的測試帳戶（請參閱設定執行 Lync Server 測試的測試帳戶）或任何已啟用 Lync Server 的使用者帳戶執行。 若要使用測試帳戶執行這項檢查，您只需指定 Lync Server pool 的 FQDN，以及充當搜尋目標之使用者的 SIP 位址即可。 例如：

    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com"

若要使用實際的使用者帳戶執行此檢查，您必須建立包含有效使用者名稱和密碼的 Windows PowerShell 認證物件。 接著，當程式碼呼叫 Test-CsAddressBookWebQuery 時，您必須包含該認證物件以及指派給該帳戶的 SIP 位址：

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

如需詳細資訊，請參閱[Test CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) Cmdlet 的說明文件。

</div>

<div>

## <a name="determining-success-or-failure"></a>判斷成功或失敗

如果指定的使用者可以連線到通訊錄服務並檢索目標使用者位址，您將會傳回類似以下所示的輸出，並將 Result 屬性標示為成功：

TargetUri :https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

TargetFqdn： atl-cs-001.litwareinc.com

結果：成功

延隔時間：00：00：06.2611356

出錯

自檢

如果指定的使用者無法連線，或者如果無法檢索目標使用者位址，則會將結果顯示為失敗，而且會在錯誤與診斷屬性中記錄其他資訊：

TargetUri :https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

TargetFqdn： atl-cs-001.litwareinc.com

結果：失敗

延遲：00:00:00

錯誤：通訊錄 Web 服務要求失敗，回應代碼為

NoEntryFound.

自檢

先前的輸出指出由於找不到目標使用者，測試失敗。 您可以執行如下所示的命令，判斷是否已將有效的 SIP 位址傳遞到 Test CsAddressBookWebQuery：

    Get-CsUser | Where-Object {$_.SipAddress -eq "sip:davidlongmire@litwareinc.com"

如果測試 CsAddressBookWebQuery 失敗，您可能會想要重新執行測試，這次包括詳細參數：

    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com" -Verbose

在包含詳細參數時，測試 CsAddressBookWebQuery 會傳回其在檢查指定使用者登入 Lync Server 的功能時所嘗試的每個動作的逐步帳戶。 例如，此輸出表示測試 CsAddressBookWebQuery 能夠連線至通訊錄服務，但無法找出目標 SIP 位址：

「QueryAddressBookWebService」活動已開始。

呼叫通訊錄網頁查詢服務。 ABWS URL =

https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

通訊錄查詢例外狀況：通訊錄 Web 服務要求失敗，回應碼 NoEntryFound。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能失敗的原因

以下是測試 CsAddressBookWebQuery 可能失敗的一些常見原因：

  - 您指定的使用者帳戶無效。 您可以執行如下的命令來確認使用者帳戶已存在：
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - 使用者帳戶有效，但目前沒有為 Lync Server 啟用該帳戶。 若要確認已啟用 Lync Server 的使用者帳戶，請執行如下所示的命令：
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    如果 Enabled 屬性設為 False，表示目前尚未啟用 Lync Server 的使用者。

  - 目標使用者可能不在通訊錄中。

  - 通訊錄可能未完全更新及複製。 您可以執行下列命令，強制更新貴組織中的所有通訊錄服務器：
    
        Update-CsAddressBook

</div>

</div>

<span> </span>

</div>

</div>

</div>

