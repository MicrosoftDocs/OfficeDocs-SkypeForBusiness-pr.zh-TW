---
title: Lync Server 2013：測試群組 IM 的能力
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing ability to do group IM
ms:assetid: ca5545bc-51ac-490f-b96b-917bb742ad04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743839(v=OCS.15)
ms:contentKeyID: 63969652
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7f33d34644f76c9773edbfd9ad5d3945c0c1974c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527820"
---
# <a name="testing-ability-to-do-group-im-in-lync-server-2013"></a>在 Lync Server 2013 中測試群組 IM 的能力

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
<p>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 Test-CsGroupIM Cmdlet 許可權的 RBAC 角色。 若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsGroupIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>描述

Test-CsGroupIM Cmdlet 會驗證組織中的使用者是否可以進行群組立即訊息會話。 當您執行 Test-CsGroupIM，指令 Cmdlet 會嘗試將一對測試使用者登入 Lync Server。 如果成功，Test-CsGroupIM 會使用第一個測試使用者建立新的會議，然後邀請第二個使用者加入該會議。 交換訊息之後，兩個使用者都會中斷與系統的連線。 請注意，所有的動作都沒有任何使用者互動，也不會影響任何實際的使用者。 例如，假設「測試帳戶 sip:kenmyer@litwareinc.com」會對應至具有實際 Lync 伺服器帳戶的實際使用者。 在該情況下，測試將會在不干擾實際的 Ken Myer 的情況下進行。 例如，即使在 Ken Myer 測試帳戶從系統登出時，Ken Myer 這個人仍然維持登入狀態。 同樣地，real Ken Myer 不會收到加入會議的邀請。 該邀請將會傳送到測試帳戶，並由測試帳戶接受。

如需詳細資訊，請參閱 [Test-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) Cmdlet 的說明文件。

</div>

<div>

## <a name="running-the-test"></a>執行測試

您可以使用一對預先設定的測試帳戶來執行 Test-CsGroupIM Cmdlet (請參閱設定測試帳戶以執行 Lync Server 測試) 或任何兩個已啟用 Lync Server 之使用者的帳戶。 若要使用測試帳戶執行此檢查，您只需要指定所測試之 Lync Server 集區的 FQDN。 例如：

    Test-CsGroupIM -TargetFqdn "atl-cs-001.litwareinc.com"

若要使用實際使用者帳戶執行這項檢查，您必須建立兩個 Lync Server 管理命令介面認證物件 (包含每個帳戶的帳戶名稱和密碼) 的物件。 當您呼叫 Test-CsGroupIM 時，您必須包含這兩個帳戶的認證物件和 SIP 位址：

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsGroupIm -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

如需詳細資訊，請參閱 [Test-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) Cmdlet 的說明文件。

</div>

<div>

## <a name="determining-success-or-failure"></a>決定成功或失敗

如果兩位使用者可以完成群組立即訊息會話，則會收到與結果屬性標示為 [成功] 的輸出 **：**

TargetFqdn： atl-cs-001.litwareinc.com

結果：成功

延遲：00：00：06.3812203

錯誤：

診斷：

如果兩位使用者無法完成立即訊息會話，則結果會顯示為失敗，而且會在錯誤和診斷屬性中記錄其他資訊：

TargetFqdn： atl-cs-001.litwareinc.com

結果：失敗

延遲：00:00:00

錯誤：404，未找到

診斷： ErrorCode = 4005、Source = atl-cs-001.litwareinc.com、

原因 = 未啟用 SIP 的目的 URI 或不是

存在。

DiagnosticHeader。

先前的輸出指出測試失敗的原因是至少一個測試帳戶無效，原因是該帳戶不存在，或是尚未啟用 Lync Server 的使用者。 您可以透過執行類似如下的命令，確認帳戶是否存在，以及帳戶是否已啟用的帳戶已啟用。

    "Ken Myer", "David Longmire" | Get-CsUser | Select-Object SipAddress, Enabled

如果 Test-CsGroupIM 失敗，則您可能想要重新執行測試，這次包括 Verbose 參數：

    Test-CsGroupIM -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

包含 Verbose 參數時，Test-CsGroupIM 會傳回每個動作所嘗試的每個動作的逐步帳戶，檢查指定使用者是否可以加入群組立即訊息會話。 例如，如果測試失敗，而且您已告知一或多個使用者帳戶無效，您可以使用 Verbose 參數來重新執行測試，並判斷哪個使用者帳戶無效：

傳送註冊要求：

 目標 Fqdn = atl-cs-001.litwareinc.com

 使用者 SIP 位址 = sip:kenmyer@litwareinc.com

 寄存器埠 = 5061

已選取驗證類型 ' IWA '。

「登入已遭拒絕」例外狀況。 請檢查是否已使用正確的認證，且帳戶為使用中。

如您所見，在此範例中，具有 SIP 位址 sip:kenmyer@litwareinc.com 的使用者無法登入。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能失敗的原因

以下是一些 Test-CsGroupIM 可能失敗的常見原因：

  - 您指定了錯誤的使用者帳戶。 您可以執行類似如下的命令，以確認使用者帳戶是否存在：
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - 使用者帳戶有效，但目前未啟用 Lync Server 的帳戶。 若要確認已啟用 Lync Server 的使用者帳戶，請執行類似下列的命令：
    
    Get-CsUser "sip:kenmyer@litwareinc.com" |Select-Object 啟用
    
    如果 Enabled 屬性設定為 False，表示目前未啟用 Lync Server 的使用者。

  - 立即訊息服務可能無法使用。 透過 Lync Server，您可以設定系統，以便在無法存取封存資料庫時，立即訊息無法使用。 您可以執行類似下列的命令來確認：
    
        Get-CsArchivingConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object BlockOnArchiveFailure
    
    如果 BlockOnArchiveFailure 設定為 True，則應該決定封存資料庫是否可用。 您可以使用下列命令回到封存資料庫的位置：
    
        Get-CsService -ArchivingDatabase

  - 可能無法使用封存伺服器。 您可以使用下列命令來取得封存伺服器的 FQDN：
    
        Get-CsService -ArchivingServer
    
    然後，您可以 ping 適當的伺服器以驗證其是否可供使用。 例如：
    
        ping atl-archiving-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

