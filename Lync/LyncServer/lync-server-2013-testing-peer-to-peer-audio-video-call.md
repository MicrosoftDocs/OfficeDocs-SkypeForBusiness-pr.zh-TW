---
title: Lync Server 2013：測試對等音訊/視頻通話
description: Lync Server 2013：測試對等音訊/視頻通話。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing peer to peer audio/video call
ms:assetid: 95eb3693-b866-4652-bc45-9b75fdb40b49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743835(v=OCS.15)
ms:contentKeyID: 63969627
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03bab69d926a99c091a510ce64b78dbf505d4cbc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556289"
---
# <a name="testing-peer-to-peer-audiovideo-call-in-lync-server-2013"></a>在 Lync Server 2013 中測試對等音訊/視頻通話

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
<p>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 Test-CsP2PAV Cmdlet 許可權的 RBAC 角色。 若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsP2PAV&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>描述

Test-CsP2PAV 是用來判斷一組測試使用者是否可以參與對等 A/V 交談。 若要測試此案例，指令程式會從兩個使用者登入 Lync Server，以啟動 Cmdlet。 假設這兩次登入都成功，則第一位使用者會邀請第二位使用者加入 A/V 呼叫。 第二位使用者接受通話時，會測試兩位使用者之間的連線，然後結束通話，然後從系統中登出測試使用者。

Test-CsP2PAV 實際上不會進行 A/V 通話。 測試使用者間的多媒體資訊不會互換。 相反地，此 Cmdlet 只會驗證是否可以進行適當的連線，以及兩位使用者是否可以進行這類呼叫。

如需詳細資訊，請參閱 [Test-CsP2PAV](https://docs.microsoft.com/powershell/module/skype/Test-CsP2PAV) Cmdlet 的說明文件。

</div>

<div>

## <a name="running-the-test"></a>執行測試

您可以使用一對預先設定的測試帳戶來執行 Test-CsP2PAV Cmdlet (請參閱設定測試帳戶以執行 Lync Server 測試) 或任何兩個已啟用 Lync Server 之使用者的帳戶。 若要使用測試帳戶執行此檢查，您只需要指定所測試之 Lync Server 集區的 FQDN。 例如：

    Test-CsP2PAV -TargetFqdn "atl-cs-001.litwareinc.com"

若要使用實際使用者帳戶執行這項檢查，您必須為每個帳戶 (包含帳戶名稱和密碼) 的物件建立兩個 Lync Server 身分憑證物件。 當您呼叫 Test-CsP2PAV 時，您必須包含這兩個帳戶的認證物件和 SIP 位址：

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsP2PAV -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

</div>

<div>

## <a name="determining-success-or-failure"></a>決定成功或失敗

如果兩個測試使用者可以完成對等 A/V 呼叫，則會收到與結果屬性標示為「成功」類似的輸出 **：**

TargetFqdn： atl-cs-001.litwareinc.com

結果：成功

延遲：00：00：06.8630376

錯誤：

診斷：

如果測試使用者無法完成通話，則結果會顯示為 [失敗]，而且會在 [錯誤] 和 [診斷] 屬性中記錄其他資訊：

TargetFqdn： atl-cs-001.litwareinc.com

結果：失敗

延遲：00:00:00

錯誤：480，暫時無法使用

診斷： ErrorCode = 15030，Source = atl-cs-001，Reason = Failed

路由傳送至 Exchange Server

DiagnosticHeader。

例如，上一個輸出會指出測試失敗，因為無法與 Microsoft Exchange Server 取得聯繫。 這項錯誤訊息通常表示 Exchange 整合通訊的設定發生問題。

如果 Test-CsP2PAV 失敗，則您可能想要重新執行測試，這次包括 Verbose 參數：

Test-CsP2PAV-TargetFqdn "atl-cs-001.litwareinc.com"-Verbose

包含 Verbose 參數時，Test-CsP2PAV 將會傳回其嘗試的每個動作的逐步帳戶，以檢查指定使用者登入 Lync 伺服器的能力。 例如，假設測試失敗併發生下列診斷：

ErrorCode = 6003，Source = atl-ws-01-cs-001，Reason = 不支援的對話方塊要求

如果您重新執行 Test-CsP2PAV 並包含 Verbose 參數，您會收到類似以下的輸出：

詳細：「註冊」活動已開始。

傳送註冊要求：

目標 Fqdn = atl-cs-011.litwareinc.com

使用者 Sip 位址 = sip:kenmyer@litwareinc.com

註冊機構埠 = 5062。

已選取驗證類型 ' IWA '。

無法註冊端點的例外狀況。 如需特定原因，請參閱 ErrorCode。 ' 在工作流程 SyntheticTransactions 中發生 STP2PAVWorkflow 執行。

雖然它可能不會立即顯而易見，但如果您仔細檢查輸出，您會看到不正確的註冊埠 (埠 5062) 指定。 進而又導致測試失敗。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能失敗的原因

以下是一些 Test-CsP2PAV 可能失敗的常見原因：

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

