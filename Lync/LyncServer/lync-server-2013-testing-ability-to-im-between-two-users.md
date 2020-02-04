---
title: Lync Server 2013：測試在兩個使用者之間 IM 的功能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing ability to IM between two users
ms:assetid: a0f3f5c6-f115-4c3f-90ac-5fdc932b417e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743838(v=OCS.15)
ms:contentKeyID: 63969635
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 201aceceadeba3c6c97530925273097fe039bc08
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745893"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-im-between-two-users-in-lync-server-2013"></a>在 Lync Server 2013 的兩位使用者之間進行 IM 測試的功能

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
<p>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 CsIM Cmdlet 許可權的 RBAC 角色。 若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示執行下列命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>說明

CsIM Cmdlet 會驗證一對測試使用者可以交換立即訊息。 在呼叫時，CsIM Cmdlet 會嘗試將一組測試使用者登入 Lync Server 來啟動。 假設兩次登入成功，則 Cmdlet 會在兩個測試使用者之間啟動 IM 會話。 （使用者1邀請使用者2加入 IM 會話，而使用者2則接受邀請。）在確認郵件可以在兩個使用者之間交換之後，測試 CsIM 接著結束 IM 會話，並將使用者從系統中記錄。

如需詳細資訊，請參閱[Test CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM) Cmdlet 的說明文件。

</div>

<div>

## <a name="running-the-test"></a>執行測試

CsIM Cmdlet 可以使用一組預先配置的測試帳戶（請參閱設定執行 Lync Server 測試的測試帳戶），或是任何已啟用 Lync Server 的任何兩個使用者的帳戶執行。 若要使用測試帳戶執行此檢查，您只需指定要測試的 Lync 伺服器池的 FQDN 即可。 例如：

    Test-CsIM -TargetFqdn "atl-cs-001.litwareinc.com"

若要使用實際的使用者帳戶執行這項檢查，您必須為每個帳戶建立兩個 Windows PowerShell 認證物件（包含帳戶名稱和密碼的物件）。 當您呼叫 Test CsIM 時，您必須包含這些認證物件和兩個帳戶的 SIP 位址：

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsIm -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

如需詳細資訊，請參閱[Test CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM) Cmdlet 的說明文件。

</div>

<div>

## <a name="determining-success-or-failure"></a>判斷成功或失敗

如果兩個使用者可以完成立即訊息會話，您將會收到類似以下的輸出，結果屬性標示為**成功：**

TargetFqdn： atl-cs-001.litwareinc.com

結果：成功

延隔時間：00：00：06.6630911

出錯

自檢

如果測試使用者無法完成會話，結果就會顯示為失敗，而其他資訊將會記錄在錯誤與診斷屬性中：

TargetFqdn： atl-cs-001.litwareinc.com

結果：失敗

延遲：00:00:00

錯誤：504，伺服器超時

診斷： ErrorCode = 2，Source = litwareinc = atl-ws-01，原因 = 請參閱

回應程式碼與原因片語。

DiagnosticHeader 中的 [Rtc]

例如，由於找不到指定的使用者，所以先前的輸出指出測試失敗。 您可以執行此命令來判斷 SIP 位址是否有效（以及使用者是否已為 Lync Server 啟用指派該 SIP 位址的使用者）：

    Get-CsUser "Ken Myer" | Select-Object SipAddress, Enabled

如果測試 CsIM 失敗，您可能會想要重新執行測試，這次包括詳細參數：

    Test-CsIM -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

在包含詳細參數的情況下，當您檢查兩個測試使用者要在 IM 會話中參與的每個動作時，測試 CsIM 會傳回它嘗試的每個動作的逐步帳戶。 例如，以下是當使用者認證（在此例中為不正確的密碼）提供給 Test CsIM 時所發生的樣本輸出：

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

以下是測試 CsIM 可能失敗的一些常見原因：

  - 您指定的使用者帳戶無效。 您可以執行如下的命令來確認使用者帳戶已存在：
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - 使用者帳戶有效，但目前尚未啟用 Lync Server 的帳戶。 若要確認已啟用 Lync Server 的使用者帳戶，請執行如下所示的命令：
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    如果 Enabled 屬性設為 False，表示目前尚未啟用 Lync Server 的使用者。

  - [立即訊息服務] 可能無法使用。 使用 Lync Server，您可以設定系統，以便在無法存取封存資料庫時，無法使用 IM。 您可以執行類似下列的命令來驗證：
    
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

