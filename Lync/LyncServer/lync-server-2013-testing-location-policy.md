---
title: Lync Server 2013：測試位置原則
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
ms.openlocfilehash: 2a954405cb8dbba842250e0545ac8661d4f3795c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745773"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-location-policy-in-lync-server-2013"></a>在 Lync Server 2013 中測試位置原則

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
<p>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 CsLocationPolicy Cmdlet 許可權的 RBAC 角色。 若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示執行下列命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLocationPolicy&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>說明

Test CsLocationPolicy Cmdlet 會驗證是否已將位置原則指派給使用者。 位置原則是用來套用與 E9-1-1 功能及用戶端位置相關的設定。 位置原則會判斷使用者是否已啟用 E9-1-1，如果答案是「是」，則是緊急通話的行為。 例如，您可以使用位置原則來定義哪一個號碼是由緊急通話（911在美國）、企業安全性是否應該自動通知，以及應該如何傳送通話。

您可以在使用者或網路子網上測試位置原則。 如果您針對子網執行測試（透過指定子網參數的值），則 Cmdlet 會嘗試解析該子網上的位置原則。 如果未將位置原則指派給子網，則會檢索已設定使用者的位置原則。 如果成功地檢索到子網原則，則輸出會包含以 subnet-tagid 開頭的 LocationPolicyTagID 值。 如果找不到子網的位置原則，LocationPolicyTagID 將會以使用者 tagid 開始。

</div>

<div>

## <a name="running-the-test"></a>執行測試

CsLocationPolicy Cmdlet 可以使用預先配置的測試帳戶（請參閱設定執行 Lync Server 測試的測試帳戶）或任何已啟用 Lync Server 的使用者帳戶執行。 若要使用測試帳戶執行這項檢查，您只需指定要測試的 Lync 伺服器池的 FQDN 即可。 例如：

    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com"

若要使用實際的使用者帳戶執行此檢查，您必須先建立包含帳戶名稱和密碼的 Windows PowerShell 認證物件。 當您呼叫 Test CsLocationPolicy 時，您必須包含該認證物件以及指派給該帳戶的 SIP 位址：

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

如需詳細資訊，請參閱[Test CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Test-CsLocationPolicy) Cmdlet 的說明文件。

</div>

<div>

## <a name="determining-success-or-failure"></a>判斷成功或失敗

如果指定的使用者有有效的位置原則，您將會收到類似這樣的輸出，結果屬性標示為**成功：**

EnhancedEmergencyServicesEnabled： true

LocationPolicyTagID：使用者-tagid

TargetFqdn： atl-cs-001.litwareinc.com

結果：成功

延隔時間：00：00：06.8630376

出錯

自檢

如果找不到指定使用者的有效位置原則，則會將結果顯示為失敗，而且會在錯誤與診斷屬性中記錄其他資訊：

TargetFqdn： atl-cs-001.litwareinc.com

結果：失敗

延遲：00:00:00

錯誤：404，找不到

診斷： ErrorCode = 4005，Source = atl-cs-001.litwareinc.com，

原因 = 無法針對 SIP 啟用目的 URI，或無法

有.

DiagnosticHeader 中的 [Rtc]

先前的輸出指出測試失敗的原因是指定的使用者無效：帳戶不存在，或尚未啟用 Lync Server 的使用者。 您可以透過執行如下的命令，來確認帳戶的有效性，並判斷是否已啟用 nm 版 ocs-14-協力廠商的帳戶：

    Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled

如果測試 CsLocationPolicy 失敗，您可能會想要重新執行測試，這次包括詳細參數：

    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

包含詳細參數時，測試 CsLocationPolicy 會傳回在驗證位置原則時所嘗試的每個動作的逐步帳戶。 例如，此輸出表示 Lync Server 無法登入測試使用者，可能是因為提供了不正確密碼：

傳送註冊要求：

目標 Fqdn = atl-cs-011.litwareinc.com

使用者 Sip 位址 = sip:kenmyer@litwareinc.com

註冊機構埠 = 5061

已選取 Auth 類型 ' IWA」。

針對 sip/atl-cs-001-litwareinc 的註冊。

"Register" 活動在 "0.0601795" 秒內完成。

[登錄已遭到拒絕] 例外狀況。 檢查是否已使用正確的認證，且帳戶處於作用中狀態。 在工作流程期間發生。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能失敗的原因

以下是測試 CsLocationPolicy 可能失敗的一些常見原因：

  - 您指定的使用者帳戶無效。 您可以執行如下的命令來確認使用者帳戶已存在：
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - 使用者帳戶有效，但目前尚未啟用 Lync Server 的帳戶。 若要確認已啟用 Lync Server 的使用者帳戶，請執行如下所示的命令：
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    如果 Enabled 屬性設為 False，表示目前尚未啟用 Lync Server 的使用者。

</div>

</div>

<span> </span>

</div>

</div>

</div>

