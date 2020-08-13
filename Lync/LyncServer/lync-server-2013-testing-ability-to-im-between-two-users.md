---
title: Lync Server 2013：測試兩個使用者之間的 IM 功能
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
ms.openlocfilehash: 810a49a35f9b2597e8a84427e513217ff35efefb
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194276"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-im-between-two-users-in-lync-server-2013"></a>在 Lync Server 2013 中測試兩個使用者之間的 IM 功能

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
<p>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 Test-CsIM Cmdlet 許可權的 RBAC 角色。 若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>描述

Test-CsIM Cmdlet 會驗證一對測試使用者是否可以 exchange 立即訊息。 呼叫時，Test-CsIM Cmdlet 會從嘗試將一組測試使用者登入 Lync Server 開始。 假設兩次登入都成功，則 Cmdlet 會在兩個測試使用者之間啟動 IM 會話。  (使用者1邀請使用者2到 IM 會話，而使用者2接受邀請。 ) 之後，請確認郵件可以在兩個使用者之間交換，Test-CsIM 然後結束 IM 會話，並將這兩位使用者從系統登出。

如需詳細資訊，請參閱[Test-CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM) Cmdlet 的說明文件。

</div>

<div>

## <a name="running-the-test"></a>執行測試

您可以使用一對預先設定的測試帳戶來執行 Test-CsIM Cmdlet (請參閱設定測試帳戶以執行 Lync Server 測試) 或任何兩個已啟用 Lync Server 之使用者的帳戶。 若要使用測試帳戶執行此檢查，您只需要指定所測試之 Lync Server 集區的 FQDN。 例如：

    Test-CsIM -TargetFqdn "atl-cs-001.litwareinc.com"

若要使用實際使用者帳戶執行這項檢查，您必須建立兩個 Windows PowerShell 認證物件 (包含每個帳戶之帳戶名稱和密碼) 的物件。 當您呼叫 Test-CsIM 時，您必須包含這兩個帳戶的認證物件和 SIP 位址：

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsIm -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

如需詳細資訊，請參閱[Test-CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM) Cmdlet 的說明文件。

</div>

<div>

## <a name="determining-success-or-failure"></a>決定成功或失敗

如果這兩個使用者可以完成立即訊息會話，則會收到類似下列的輸出，並將 Result 屬性標示為 [**成功]：**

TargetFqdn： atl-cs-001.litwareinc.com

結果：成功

延遲：00：00：06.6630911

錯誤：

診斷：

如果測試使用者無法完成會話，結果將會顯示為 [失敗]，而且會在 [錯誤及診斷] 屬性中記錄其他資訊：

TargetFqdn： atl-cs-001.litwareinc.com

結果：失敗

延遲：00:00:00

錯誤：504，伺服器超時

診斷： ErrorCode = 2，Source = atl-ws-01-cs，Reason = 請參閱

回應碼和 reason 片語。

DiagnosticHeader。

例如，由於找不到指定的使用者，所以先前的輸出會指出測試失敗。 您可以執行下列命令，判斷 SIP 位址是否有效 (，以及指派該 SIP 位址是否已啟用 Lync Server) 的使用者：

    Get-CsUser "Ken Myer" | Select-Object SipAddress, Enabled

如果 Test-CsIM 失敗，則您可能想要重新執行測試，這次包括 Verbose 參數：

    Test-CsIM -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

包含 Verbose 參數時，Test-CsIM 會傳回每個動作所嘗試的每個動作的逐步帳戶，檢查這兩個測試使用者在 IM 會話中所採取的功能。 例如，在這種情況下，會發生錯誤的使用者 (認證集合時，會發生範例輸出，Test-CsIM 中) 提供錯誤的密碼：

傳送註冊要求：

目標 Fqdn = atl-cs-011.litwareinc.com

使用者 Sip 位址 = sip:kenmyer@litwareinc.com

註冊機構埠 = 5061

已選取驗證類型 ' IWA '。

對 sip/atl-cs-001-001 的註冊點擊 litwareinc

' Register ' activity 在 ' 0.0601795 ' 秒內完成。

「登入已遭拒絕」例外狀況。 請檢查是否已使用正確的認證，以及帳戶是否有效。 ' 在工作流程中發生。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能失敗的原因

以下是一些 Test-CsIM 可能失敗的常見原因：

  - 您指定的使用者帳戶無效。 您可以執行類似如下的命令，以確認使用者帳戶是否存在：
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - 使用者帳戶有效，但目前未啟用 Lync Server 的帳戶。 若要確認是否已為 Lync Server 啟用使用者帳戶，請執行類似下列的命令：
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    如果 Enabled 屬性設定為 False，表示目前未啟用 Lync Server 的使用者。

  - 立即訊息服務可能無法使用。 透過 Lync Server，您可以設定系統，以便在無法存取封存資料庫時，無法使用 IM。 您可以執行類似下列的命令來確認：
    
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

