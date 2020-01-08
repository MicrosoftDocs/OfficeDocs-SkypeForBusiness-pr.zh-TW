---
title: Lync Server 2013：測試電話撥入式會議會話
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing dial-in conferencing session
ms:assetid: 6c505be5-5af7-450c-b3ca-10d9122bee5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743834(v=OCS.15)
ms:contentKeyID: 63969613
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: efcc6d9277f7333989c59b812ed76087b9b6ca9b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982644"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-dial-in-conferencing-session-in-lync-server-2013"></a>在 Lync Server 2013 中測試電話撥入式會議會話

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
<p>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 CsDialInConferencing Cmdlet 許可權的 RBAC 角色。 若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示執行下列命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDialInConferencing&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>描述

CsDialInConferencing Cmdlet 會驗證使用者是否可以參與電話撥入式會議。 測試 CsDialInConferencing 的運作方式是嘗試將測試使用者記錄在系統上。 如果登入成功，則 Cmdlet 會使用使用者的認證和許可權來嘗試所有可用的電話撥入式會議存取號碼。 每次撥入嘗試的成功或失敗都會說出，然後從 Lync Server 登出測試使用者。測試 CsDialInConferencing 只會驗證是否可以建立適當的連線。 Cmdlet 不會實際撥打任何電話或建立任何其他使用者可以加入的撥入會議。

</div>

<div>

## <a name="running-the-test"></a>執行測試

CsDialInConferencing Cmdlet 可以使用預先配置的測試帳戶（請參閱設定執行 Lync Server 測試的測試帳戶）或任何已啟用 Lync Server 的使用者帳戶執行。 若要使用測試帳戶執行這項檢查，您只需指定要測試的 Lync 伺服器池的 FQDN 即可。 例如：

    Test-CsDialInConferencing -TargetFqdn "atl-cs-001.litwareinc.com" 

若要使用實際的使用者帳戶執行此檢查，您必須建立包含帳戶名稱和密碼的 Windows PowerShell 認證物件。 接著，您必須將該認證物件與帳戶 SIP 位址納入呼叫測試-CsDialInConferencing：

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsDialInConferencing -TargetFqdn atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

如需詳細資訊，請參閱[Test CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/Test-CsDialInConferencing) Cmdlet 的說明文件。

</div>

<div>

## <a name="determining-success-or-failure"></a>判斷成功或失敗

如果指定的使用者可以登入 Lync Server，然後使用其中一個可用的電話撥入式會議存取號碼進行連線，則會收到與此類似的輸出，且 Result 屬性標示為**成功：**

TargetFqdn： atl-cs-001.litwareinc.com

結果：成功

延隔時間：00：00：06.8630376

出錯

自檢

如果指定的使用者無法進行這個連線，則會將結果顯示為失敗，而且會在錯誤與診斷屬性中記錄其他資訊：

TargetFqdn： atl-cs-001.litwareinc.com

結果：失敗

延遲：00:00:00

錯誤：登入遭到拒絕。 檢查是否有適當的認證

正在使用中，且帳戶處於作用中狀態。

內部例外狀況： NegotiateSecurityAssociation 失敗，錯誤：-

2146893044

自檢

前一個輸出表示已拒絕測試使用者存取 Lync Server 本身。 這通常表示傳遞給 Test CsDialInConferencing 的使用者認證無效。 接著，您應該重新建立 Windows PowerShell 認證物件。 雖然您可以取得使用者帳戶的密碼，但是您可以使用類似以下的命令來驗證 SIP 位址：

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能失敗的原因

以下是測試 CsDialInConferencing 可能失敗的一些常見原因：

  - 您指定的使用者帳戶無效。 您可以執行如下的命令來確認使用者帳戶已存在：
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - 使用者帳戶有效，但目前尚未啟用 Lync Server 的帳戶。 若要確認已啟用 Lync Server 的使用者帳戶，請執行如下所示的命令：
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    如果 Enabled 屬性設為 False，表示目前尚未啟用 Lync Server 的使用者。

  - 您的電話撥入式會議存取號碼可能不正確。 您可以使用此命令，返回目前設定的電話撥入式會議存取號碼清單：
    
        Get-CsDialConferencingAccessNumber

</div>

</div>

<span> </span>

</div>

</div>

</div>

