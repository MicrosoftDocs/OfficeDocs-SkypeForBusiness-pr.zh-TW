---
title: Lync Server 2013：測試使用者登入 Lync Server 的能力
description: Lync Server 2013：測試使用者登入 Lync Server 的能力。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing the ability of a user to log on to Lync Server
ms:assetid: d9cd0f9b-6ef2-4050-a4ca-263c5afa93ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743841(v=OCS.15)
ms:contentKeyID: 63969655
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8b86ae3e490af0b361799ed5fb3f56ed4de42c82
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556209"
---
# <a name="testing-the-ability-of-a-user-to-log-on-to-lync-server-2013"></a>測試使用者登入 Lync Server 2013 的能力

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
<p>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 Test-CsRegistration Cmdlet 許可權的 RBAC 角色。 若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsRegistration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>描述

Test-CsRegistration Cmdlet 可讓您確認組織中的使用者是否可以登入 Lync Server。 當您執行 Test-CsRegistration 時，指令程式會嘗試將測試使用者登入 Lync Server，如果成功，則會將測試使用者從系統上中斷連接。 發生以上所有狀況時，都不會有任何使用者介入，也不會影響任何實際的使用者。 例如，假設「測試帳戶 sip:kenmyer@litwareinc.com」會對應至具有實際 Lync 伺服器帳戶的實際使用者。 在該情況下，測試將會在不干擾實際的 Ken Myer 的情況下進行。 當 Ken Myer 測試帳戶從系統登出時，他將繼續登入的 Ken Myer。

</div>

<div>

## <a name="running-the-test"></a>執行測試

您可以使用預先設定的測試帳戶執行 Test-CsRegistration Cmdlet (請參閱設定測試帳戶以執行 Lync Server 測試) 或任何啟用 Lync Server 之使用者的帳戶。 若要使用測試帳戶執行這項檢查，您只需要指定所測試之 Lync Server 註冊集區的 FQDN。 例如：

    Test-CsRegistration -TargetFqdn "atl-cs-001.litwareinc.com"

若要使用實際使用者帳戶執行這種檢查，您必須先建立 Windows PowerShell 身分憑證物件，其中包含帳戶名稱和密碼。 接著，當您呼叫 Test-CsRegistration 時，必須包含該認證物件和指派給該帳戶的 SIP 位址：

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsRegistration -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

如需詳細資訊，請參閱 [Test-CsRegistration](https://docs.microsoft.com/powershell/module/skype/Test-CsRegistration) Cmdlet 的說明文件。

</div>

<div>

## <a name="determining-success-or-failure"></a>決定成功或失敗

如果指定的使用者可以登入 (，然後從) Lync Server 登出，您會收到與結果屬性標示為「成功」類似的輸出 **：**

TargetFqdn： atl-cs-001.litwareinc.com

結果：成功

延遲：00：00：06.8630376

錯誤：

診斷：

如果指定的使用者無法登入或登出，結果將會顯示為 [失敗]，而且會在 [錯誤及診斷] 屬性中記錄其他資訊：

TargetFqdn： atl-cs-001.litwareinc.com

結果：失敗

延遲：00:00:00

錯誤：404，未找到

診斷： ErrorCode = 1003，source = atl-ws-01，Reason，Reason = User 執行的動作

不存在

DiagnosticHeader。

例如，由於找不到指定的使用者，所以先前的輸出會指出測試失敗。 您可以執行下列命令，判斷 SIP 位址是否有效 (和使用者指派該 SIP 位址是否已啟用 Lync Server) ：

    Get-CsUser "sip:kenmyer@litwareinc.com"

如果 Test-CsRegistration 失敗，則您可能想要重新執行測試，這次包括 Verbose 參數：

    Test-CsRegistration -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

包含 Verbose 參數時，Test-CsRegistration 會傳回每個動作的逐步帳戶，檢查所嘗試的每一項動作時，檢查指定的使用者登入 Lync 伺服器的能力。 例如：

詳細：「註冊」活動已開始。

傳送註冊要求：

目標 Fqdn = atl-cs-011.litwareinc.com

使用者 Sip 位址 = sip:kenmyer@litwareinc.com

註冊機構埠 = 5061。

已選取 Auth Type ' Trusted」。

無法註冊端點的例外狀況。 請參閱在工作流程 SyntheticTransactions 期間發生的特定原因的 ErrorCode STRegistrerWorkflow 執行。

例外狀況堆疊：在 SipAsyncResult'1 中，ThrowIfFailed ( # A1

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能失敗的原因

以下是一些 Test-CsRegistration 可能失敗的常見原因：

  - 您指定了錯誤的使用者帳戶。 您可以執行類似如下的命令，以確認使用者帳戶是否存在：
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - 使用者帳戶有效，但目前未啟用 Lync Server 的帳戶。 若要確認是否已為 Lync Server 啟用使用者帳戶，請執行類似下列的命令：
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    如果 Enabled 屬性設定為 False，表示目前未啟用 Lync Server 的使用者。

  - 您指定了不正確的註冊集區。 您可以使用下列命令傳回註冊機集區的 Fqdn：
    
        Get-CsService -Registrar | Select-Object PoolFqdn

  - 註冊機構集區目前無法使用。 請嘗試 ping 集區，以查看它是否回應：
    
        ping atl-cs-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

