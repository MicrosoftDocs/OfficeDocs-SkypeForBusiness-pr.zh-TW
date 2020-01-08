---
title: Lync Server 2013：測試會議中的共用
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing sharing in conferences
ms:assetid: e6021d70-6ed9-414d-954c-06eef397dc1a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727314(v=OCS.15)
ms:contentKeyID: 63969660
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce4cd1a45d1eddf8875d85ff28886b0c04c29cfe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977553"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-sharing-in-conferences-in-lync-server-2013"></a>在 Lync Server 2013 中測試在會議中共用

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-11-01_


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
<p>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行<strong>CsDataConference</strong> Cmdlet 許可權的 RBAC 角色。 若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示執行下列命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDataConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>描述

在 Lync Server 2013 中，資料會議是使用諸如 whiteboarding 或批註等共同作業的任何會議。 **Test CsDataConference** Cmdlet 可讓您確認一組使用者可以參與資料會議。

</div>

<div>

## <a name="running-the-test"></a>執行測試

範例1中所示的命令會確認您可以在 [pool atl-cs-001.litwareinc.com] 上進行資料會議。 這個命令假設您已為指定的池子設定一對測試使用者。 如果不存在這樣的測試使用者，命令就會失敗。

    Test-CsDataConference -TargetFqdn "atl-cs-001.litwareinc.com" 

範例2所示的命令會測試一對使用者（litwareinc\\pilar 和 litwareinc\\kenmyer）的功能，以登入 Lync Server 2013，然後進行資料會議。 若要這樣做，範例中的第一個命令會使用**取得認證**Cmdlet 來建立 Windows PowerShell 命令列介面身分憑證物件，包含使用者 Pilar 方的名稱和密碼。 （因為登入名稱（litwareinc\\pilar）已包含為參數，所以 [Windows PowerShell 認證要求] 對話方塊只需要管理員輸入 pilar 方帳戶的密碼。）接著會將產生的認證物件儲存在名為 $cred 1 的變數中。 第二個命令會執行相同的動作，這次會傳回 Ken Myer 帳戶的認證物件。

使用身分認證物件時，第三個命令會判斷這兩個使用者是否可以登入 Lync Server 2013 並進行資料會議。 若要執行這項工作，請呼叫**CsDataConference** Cmdlet，以及下列參數： TargetFqdn （註冊機構池的 FQDN）;SenderSipAddress （第一個測試使用者的 SIP 位址）;SenderCredential （包含此相同使用者認證的 Windows PowerShell 物件）;ReceiverSipAddress （其他測試使用者的 SIP 位址）;與 ReceiverCredential （包含其他測試使用者認證的 Windows PowerShell 物件）。

    $credential1 = Get-Credential "litwareinc\pilar" 
    $credential2 = Get-Credential "litwareinc\kenmyer" 
    Test-CsDataConference -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $credential2

</div>

<div>

## <a name="determining-success-or-failure"></a>判斷成功或失敗

如果已正確設定資料會議，您將會收到類似以下的輸出，結果屬性標示為**成功：**

目標 Fqdn： atl-cs-001.litwareinc.com

結果：成功

延遲：00:00:00

錯誤訊息：

自檢

如果指定的使用者無法使用資料共用，結果就會顯示為**失敗**，而其他資訊將會記錄在錯誤與診斷屬性中：

目標 Fqdn： atl-cs-001.litwareinc.com

結果：失敗

延遲：00:00:00

錯誤訊息：10060，連線嘗試失敗，因為已連接的方

在一段時間後沒有正確回應，或

已建立的連線失敗，因為連接的主機有

無法回應\[2001：4898： e8： f39e：5c9a： ad83：81b3： 9944\]：5061

內部例外狀況：連接嘗試失敗，因為

已連接的參與方在一段時間後沒有正確回應

時間或已建立的連線失敗，因為已連接主機

無法回應

\[2001：4898： e8： f39e：5c9a： ad83：81b3： 9944\]：5061

自檢

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能失敗的原因

以下是**測試 CsDataConference**可能失敗的一些常見原因：

  - 提供不正確的參數值。 如果使用，必須正確設定選用的參數，否則測試將會失敗。 重新執行不含選用參數的命令，並查看是否成功。

  - 執行資料會議的能力取決於已指派給組織會議之使用者的會議原則（在**CsDataConference** Cmdlet 中為「寄件者」）。 如果召集人不能在會議中加入共同作業（例如，如果他/她的會議原則將 EnableDataCollaboration 屬性設為 False），則**CsDataConference** Cmdlet 將會失敗。

  - 如果 Edge 伺服器未正確設定或尚未部署，此命令就會失敗。

</div>

</div>

<span> </span>

</div>

</div>

</div>

