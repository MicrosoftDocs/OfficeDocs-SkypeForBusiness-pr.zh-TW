---
title: Lync Server 2013：測試使用者與 Exchange UM 語音信箱的連線
description: Lync Server 2013：測試使用者與 Exchange UM 語音信箱的連線。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing user connection to Exchange UM voicemail
ms:assetid: 574da104-8823-4061-9fb6-353639f1884d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727305(v=OCS.15)
ms:contentKeyID: 63969604
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b887b5b0df02a5864e0a39f2b62893d20105a86a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552609"
---
# <a name="testing-user-connection-to-exchange-um-voicemail-in-lync-server-2013"></a>在 Lync Server 2013 中測試使用者與 Exchange UM 語音信箱的連線

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



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
<td><p>每日</p></td>
</tr>
<tr class="even">
<td><p>測試控管</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>必要的權限</p></td>
<td><p>使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</p>
<p>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 <strong>Test-CsExUMVoiceMail</strong> Cmdlet 許可權的 RBAC 角色。 若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsExUMVoiceMail&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>描述

**Test-CsExUMVoiceMail** Cmdlet 可讓系統管理員確認使用者是否可以存取和使用 Microsoft Exchange Server 2013 整合通訊服務。 若要這麼做，Cmdlet 會連線至整合通訊服務，並在指定的信箱中留下語音信箱。 這可以是系統提供的語音信箱，也可以是自訂。您自行錄製的 WAV 檔案。

</div>

<div>

## <a name="running-the-test"></a>執行測試

下列範例會測試集區 atl-cs-001.litwareinc.com 的 Exchange 整合通訊語音信箱連線能力。 只有針對集區 atl-cs-001.litwareinc.com 定義的測試使用者才能使用此命令。 如果有的話，此命令會判斷第一個測試使用者是否可以使用整合通訊語音信箱。 如果未設定集區的測試使用者，命令將會失敗。

    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" 

下一個範例中所示的命令會測試使用者 litwareinc kenmyer 的 Exchange 整合通訊語音信箱連線能力 \\ 。 為做到這一點，範例中的第一個命令會使用 **Get-Credential** Cmdlet 為使用者 litwareinc Kenmyer 建立 Windows PowerShell 命令列介面認證物件 \\ 。 請注意，您必須為此帳戶提供密碼，才能建立有效的認證物件，並確保 **Test-CsExUMVoiceMail** Cmdlet 可以執行其檢查。

範例中的第二個命令會使用提供的認證物件 ($x) 和使用者 litwareinc kenmyer 的 SIP 位址， \\ 以判斷使用者是否可以連線至 Exchange 整合通訊語音信箱。

    $credential = Get-Credential "litwareinc\pilar" 
    
    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential 

下一個範例中所示的命令是範例1所示命令的變化。在此情況下，會包含 OutLoggerVariable 參數，以產生每個步驟所執行之每個步驟的詳細記錄 **Test-CsExUMVoiceMail** Cmdletand 每個步驟的成功或失敗。 若要這麼做，OutLoggerVariable 參數會加上參數值 ExumText;這會導致詳細記錄資訊儲存在名為 $ExumTest 的變數中。 在範例的最後一個命令中，會使用 ToXML ( # A1 方法將記錄資訊轉換成 XML 格式。 然後，會 \\ 使用 Out-File Cmdlet，將 XML 資料寫入名為 C： LogsVoicemailTest.xml 的檔案 \\ 。

    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -OutLoggerVariable VoicemailTest 
     
    $VoicemailTest.ToXML() | Out-File C:\Logs\VoicemailTest.xml

</div>

<div>

## <a name="determining-success-or-failure"></a>決定成功或失敗

如果已正確設定 Exchange 整合，您會收到類似以下的輸出，其 Result 屬性標示為 [ **成功**]：

目標 Fqdn： atl-cs-001.litwareinc.com

結果：成功

延遲：00：00：02.9911345

錯誤訊息：

診斷：

如果指定的使用者無法連線至語音信箱，結果將會顯示為 [ **失敗**]，而且會在 [錯誤及診斷] 屬性中記錄其他資訊：

警告：無法讀取指定之完全限定的註冊器通訊埠號碼

功能變數名稱 (FQDN) 。 使用預設的註冊器埠號碼。 例外：

InvalidOperationException：在拓撲中找不到相符的群集。

在

SipSyntheticTransaction TryRetri （SyntheticTransactions）

eveRegistrarPortFromTopology (Int32& registrarPortNumber) 

目標 Fqdn： atl-cs-001.litwareinc.com

結果：失敗

延遲：00:00:00

錯誤訊息：10060，連接嘗試失敗，因為連接的方

在一段時間後沒有正確回應，或

已建立連線失敗，因為連接的主機已

無法回應10.188.116.96：5061

內部例外狀況：連接嘗試失敗，因為

在一段時間後，連接的通訊錄未正確回應

時間或已建立的連線失敗，因為連接的主機

無法回應10.188.116.96：5061

診斷：

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能失敗的原因

以下是一些 **Test-CsExUMVoiceMail** 可能失敗的常見原因：

  - 提供的參數值不正確。 如果使用，必須正確設定選用參數，否則測試將會失敗。 請重新執行不含選用參數的命令，然後查看是否成功。

  - 如果 Exchange 伺服器設定不當或尚未部署，此命令將會失敗。

</div>

<div>

## <a name="see-also"></a>另請參閱


[Test-CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMConnectivity)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

