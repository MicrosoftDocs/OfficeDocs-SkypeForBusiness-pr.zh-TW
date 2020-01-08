---
title: Lync Server 2013：測試使用者登入 Lync Server 的能力
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing the ability of a user to log on to Lync Server
ms:assetid: d9cd0f9b-6ef2-4050-a4ca-263c5afa93ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743841(v=OCS.15)
ms:contentKeyID: 63969655
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: adf6cae2899d08765faf5d605ea20ae111f395ce
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974099"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-the-ability-of-a-user-to-log-on-to-lync-server-2013"></a>測試使用者登入 Lync Server 2013 的能力

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
<p>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 CsRegistration Cmdlet 許可權的 RBAC 角色。 若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示執行下列命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsRegistration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>描述

CsRegistration Cmdlet 可讓您確認貴組織中的使用者可以登入 Lync Server。 當您執行 Test CsRegistration 時，此 Cmdlet 會嘗試將測試使用者登入 Lync Server，然後，如果成功，則會將測試使用者從系統中斷連線。 在任何情況下，都不會發生任何使用者互動，也不會影響任何實際的使用者。 例如，假設 [測試帳戶 sip:kenmyer@litwareinc.com] 對應給擁有真正的 Lync 伺服器帳戶的真實使用者。 在這種情況下，將會執行測試，而不會對真正的 Ken Myer 造成任何干擾。 當 Ken Myer 測試帳戶從系統登出時，該人員將會保持登入狀態的 Ken Myer。

</div>

<div>

## <a name="running-the-test"></a>執行測試

CsRegistration Cmdlet 可以使用預先配置的測試帳戶（請參閱設定執行 Lync Server 測試的測試帳戶）或任何已啟用 Lync Server 的使用者帳戶執行。 若要使用測試帳戶執行這項檢查，您只需指定要測試的 Lync Server 註冊機構的 FQDN 即可。 例如：

    Test-CsRegistration -TargetFqdn "atl-cs-001.litwareinc.com"

若要使用實際的使用者帳戶執行此檢查，您必須先建立包含帳戶名稱和密碼的 Windows PowerShell 認證物件。 當您呼叫 Test CsRegistration 時，您必須包含該認證物件以及指派給該帳戶的 SIP 位址：

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsRegistration -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

如需詳細資訊，請參閱[Test CsRegistration](https://docs.microsoft.com/powershell/module/skype/Test-CsRegistration) Cmdlet 的說明文件。

</div>

<div>

## <a name="determining-success-or-failure"></a>判斷成功或失敗

如果指定的使用者可以登入（然後從 Lync Server 登出），您將會收到類似以下的輸出，並將 Result 屬性標示為**成功：**

TargetFqdn： atl-cs-001.litwareinc.com

結果：成功

延隔時間：00：00：06.8630376

出錯

自檢

如果指定的使用者無法登入或登出，結果就會顯示為失敗，而其他資訊將會記錄在錯誤與診斷屬性中：

TargetFqdn： atl-cs-001.litwareinc.com

結果：失敗

延遲：00:00:00

錯誤：404，找不到

診斷： ErrorCode = 1003，來源 = atl-cs-001. litwareinc，原因 = 使用者執行

不存在

DiagnosticHeader 中的 [Rtc]

例如，由於找不到指定的使用者，所以先前的輸出指出測試失敗。 您可以執行此命令來判斷 SIP 位址是否有效（以及使用者是否已為 Lync Server 啟用指派該 SIP 位址的使用者）：

    Get-CsUser "sip:kenmyer@litwareinc.com"

如果測試 CsRegistration 失敗，您可能會想要重新執行測試，這次包括詳細參數：

    Test-CsRegistration -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

包含詳細參數時，當您檢查指定的使用者是否已登入 Lync Server 的功能時，測試 CsRegistration 會傳回其嘗試的每個動作的逐步帳戶。 例如：

詳細：「註冊」活動已開始。

傳送註冊要求：

目標 Fqdn = atl-cs-011.litwareinc.com

使用者 Sip 位址 = sip:kenmyer@litwareinc.com

註冊機構埠 = 5061。

已選取 [已信任] 驗證類型。

無法註冊端點的例外狀況。 請參閱在工作流程 SyntheticTransactions STRegistrerWorkflow 執行期間發生的特定原因的 ErrorCode。

例外狀況堆疊： SipAsyncResult'1 （ThrowIfFailed （））

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能失敗的原因

以下是測試 CsRegistration 可能失敗的一些常見原因：

  - 您指定的使用者帳戶不正確。 您可以執行如下的命令來確認使用者帳戶已存在：
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - 使用者帳戶有效，但目前尚未啟用 Lync Server 的帳戶。 若要確認已啟用 Lync Server 的使用者帳戶，請執行如下所示的命令：
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    如果 Enabled 屬性設為 False，表示目前尚未啟用 Lync Server 的使用者。

  - 您指定的註冊機構池不正確。 您可以使用此命令傳回註冊機構池的 Fqdn：
    
        Get-CsService -Registrar | Select-Object PoolFqdn

  - 註冊機構池目前無法使用。 嘗試 ping 該池以查看它是否回應：
    
        ping atl-cs-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

