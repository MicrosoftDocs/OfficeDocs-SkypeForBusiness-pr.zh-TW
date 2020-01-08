---
title: Lync Server 2013：測試群組 IM 的功能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing ability to do group IM
ms:assetid: ca5545bc-51ac-490f-b96b-917bb742ad04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743839(v=OCS.15)
ms:contentKeyID: 63969652
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c371db385b29f68aa8cc9280a901d095c43f2ac2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977535"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-do-group-im-in-lync-server-2013"></a>在 Lync Server 2013 中進行群組 IM 的測試能力

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
<p>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 CsGroupIM Cmdlet 許可權的 RBAC 角色。 若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示執行下列命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsGroupIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>描述

CsGroupIM Cmdlet 會確認貴組織中的使用者可以執行群組立即訊息會話。 當您執行 Test CsGroupIM 時，此 Cmdlet 會嘗試將一組測試使用者登入 Lync Server。 如果成功，測試 CsGroupIM 會使用第一個測試使用者建立新的會議，然後邀請第二位使用者加入會議。 在交換郵件之後，這兩個使用者就會中斷與系統的連線。 請注意，所有這一切都不會發生任何使用者互動，也不會影響任何實際的使用者。 例如，假設 [測試帳戶 sip:kenmyer@litwareinc.com] 對應給擁有真正的 Lync 伺服器帳戶的真實使用者。 在這種情況下，將會執行測試，而不會對真正的 Ken Myer 造成任何干擾。 例如，即使 Ken Myer 測試帳戶登入系統，該人員仍會保持登入狀態。 同樣地，實際的 Ken Myer 不會收到加入會議的邀請。 該邀請將由測試帳戶傳送給及接受。

如需詳細資訊，請參閱[Test CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) Cmdlet 的說明文件。

</div>

<div>

## <a name="running-the-test"></a>執行測試

CsGroupIM Cmdlet 可以使用一組預先配置的測試帳戶（請參閱設定執行 Lync Server 測試的測試帳戶），或是任何已啟用 Lync Server 的任何兩個使用者的帳戶執行。 若要使用測試帳戶執行此檢查，您只需指定要測試的 Lync 伺服器池的 FQDN 即可。 例如：

    Test-CsGroupIM -TargetFqdn "atl-cs-001.litwareinc.com"

若要使用實際的使用者帳戶執行此檢查，您必須為每個帳戶建立兩個 Lync Server 管理命令介面身分憑證物件（包含帳戶名稱和密碼的物件）。 當您呼叫 Test CsGroupIM 時，您必須包含這些認證物件和兩個帳戶的 SIP 位址：

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsGroupIm -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

如需詳細資訊，請參閱[Test CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) Cmdlet 的說明文件。

</div>

<div>

## <a name="determining-success-or-failure"></a>判斷成功或失敗

如果兩個使用者可以完成群組立即訊息會話，您會收到類似以下的輸出，並將 Result 屬性標示為**成功：**

TargetFqdn： atl-cs-001.litwareinc.com

結果：成功

延隔時間：00：00：06.3812203

出錯

自檢

如果兩個使用者無法完成立即訊息會話，則會將結果顯示為失敗，而且會在錯誤與診斷屬性中記錄其他資訊：

TargetFqdn： atl-cs-001.litwareinc.com

結果：失敗

延遲：00:00:00

錯誤：404，找不到

診斷： ErrorCode = 4005，Source = atl-cs-001.litwareinc.com，

原因 = 無法針對 SIP 啟用目的 URI，或無法

有.

DiagnosticHeader 中的 [Rtc]

由於帳戶不存在或使用者尚未啟用 Lync Server，所以先前的輸出指出測試失敗的原因，因為至少有一個測試帳戶無效。 您可以透過執行如下命令，確認帳戶存在，以及帳戶是否已啟用 nm-ocs-14-3：

    "Ken Myer", "David Longmire" | Get-CsUser | Select-Object SipAddress, Enabled

如果測試 CsGroupIM 失敗，您可能會想要重新執行測試，這次包括詳細參數：

    Test-CsGroupIM -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

在包含詳細參數的情況下，CsGroupIM 會在檢查指定使用者在群組立即訊息會話中的每個動作時，傳回其嘗試的每個動作的逐步帳戶。 例如，如果您的測試失敗，而且您收到一或多個使用者帳戶無效，您可以使用詳細參數重新執行測試，並判斷哪個使用者帳戶無效：

傳送註冊要求：

 目標 Fqdn = atl-cs-001.litwareinc.com

 使用者 SIP 位址 = sip:kenmyer@litwareinc.com

 寄存器埠 = 5061

已選取 Auth 類型 ' IWA」。

[登錄已遭到拒絕] 例外狀況。 檢查是否已使用正確的認證，且帳戶處於作用中」

您可以看到，在這個範例中，擁有 SIP 位址 sip:kenmyer@litwareinc.com 的使用者無法登入。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能失敗的原因

以下是測試 CsGroupIM 可能失敗的一些常見原因：

  - 您指定的使用者帳戶不正確。 您可以執行如下的命令來確認使用者帳戶已存在：
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - 使用者帳戶有效，但目前尚未啟用 Lync Server 的帳戶。 若要確認使用者帳戶已啟用 Lync Server，請執行類似下列的命令：
    
    Move-csuser "sip:kenmyer@litwareinc.com" |選取-已啟用物件
    
    如果 Enabled 屬性設為 False，表示目前尚未啟用 Lync Server 的使用者。

  - [立即訊息服務] 可能無法使用。 使用 Lync Server，您可以設定系統，以便在無法存取封存資料庫時，立即訊息無法使用。 您可以執行類似下列的命令來驗證：
    
        Get-CsArchivingConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object BlockOnArchiveFailure
    
    如果 BlockOnArchiveFailure 設定為 True，則應該判斷封存資料庫是否可用。 您可以使用下列命令，返回封存資料庫的位置：
    
        Get-CsService -ArchivingDatabase

  - 存檔伺服器可能無法使用。 您可以使用此命令來檢索封存伺服器的 FQDN：
    
        Get-CsService -ArchivingServer
    
    接著，您可以 ping 適當的伺服器，確認它可以使用。 例如：
    
        ping atl-archiving-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

