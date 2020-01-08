---
title: Lync Server 2013：測試使用者與 Exchange UM 的連線
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing user connection to Exchange UM
ms:assetid: 0b83fbf4-e124-4efd-a0a9-202eb849af82
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727300(v=OCS.15)
ms:contentKeyID: 63969573
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0cc54577e94f7679e833f06a4a5de060aaf761a6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977202"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-user-connection-to-exchange-um-in-lync-server-2013"></a>在 Lync Server 2013 中測試使用者與 Exchange UM 的連線

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
<p>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行<strong>CsExUMConnectivity</strong> Cmdlet 許可權的 RBAC 角色。 若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示執行下列命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsExUMConnectivity&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>描述

**CsExUMConnectivity** Cmdlet 會驗證指定的使用者是否可以連線到 Microsoft Exchange Server 2013 整合通訊服務。 請注意，這個 Cmdlet 只會驗證是否可以與服務建立連線。 它不會測試服務本身。 若要測試整合訊息服務（執行綜合交易 Cmdlet，以實際在使用者信箱中留下語音信箱），請使用 CsExUMVoiceMail Cmdlet。

</div>

<div>

## <a name="running-the-test"></a>執行測試

下列範例會測試 [pool atl-cs-001.litwareinc.com] 的 Exchange 整合訊息連線。 只有在針對 [池 atl-cs-001.litwareinc.com] 定義測試使用者時，才能使用此命令。 如果有的話，命令會判斷第一個測試使用者是否可以連線至整合通訊。 如果沒有為該 pool 設定測試使用者，命令就會失敗。

    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" 

下列範例中所示的命令會針對使用者 litwareinc\\Kenmyer 測試 Exchange 整合訊息連線。 若要這樣做，範例中的第一個命令會使用**取得認證**Cmdlet 來為使用者 litwareinc\\kenmyer 建立 Windows PowerShell 命令列介面認證物件。 請注意，您必須為此帳戶提供密碼才能建立有效的認證物件，並確保**Test CsExUMConnectivity** Cmdlet 可以執行其檢查。

這個範例中的第二個命令使用所提供的認證物件（$x）和使用者 litwareinc\\KENMYER 的 SIP 位址來判斷使用者是否可以連線到 Exchange 整合訊息。

    $credential = Get-Credential "litwareinc\kenmyer" 
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

下一個範例中所示的命令就是剛才所示的命令變化。 在這種情況下，會包含 OutLoggerVariable 參數，以產生由**Test CsExUMConnectivity** Cmdletand 每個步驟成功或失敗所完成的每個步驟的詳細記錄。 若要這樣做，OutLoggerVariable 參數會與參數值 ExumText 一起新增;這會使詳細的記錄資訊儲存在名為 $ExumTest 的變數中。 在這個範例的最後一個命令中，ToXML （）方法是用來將記錄資訊轉換成 XML 格式。 然後，該 XML 資料會寫入一個名為 C：\\ExumTest 的檔案\\，並使用 Out file Cmdlet 來登入。

    $credential = Get-Credential "litwareinc\kenmyer" 
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential -OutLoggerVariable ExumTest 
    $ExumTest.ToXML() | Out-File C:\Logs\ExumTest.xml 

</div>

<div>

## <a name="determining-success-or-failure"></a>判斷成功或失敗

如果 Exchange 整合設定正確，您將會收到類似以下的輸出，結果屬性標示為**成功**：

目標 Fqdn： atl-cs-001.litwareinc.com

結果：成功

延遲：00:00:00

錯誤訊息：

自檢

如果指定的使用者無法接收通知，結果就會顯示為**失敗**，而其他資訊將會記錄在錯誤與診斷屬性中：

目標 Fqdn： atl-cs-001.litwareinc.com

結果：失敗

延遲：00:00:00

錯誤訊息：10060，連線嘗試失敗，因為已連接的方

在一段時間後沒有正確回應，或

已建立的連線失敗，因為連接的主機有

無法回應10.188.116.96：5061

內部例外狀況：連接嘗試失敗，因為

已連接的參與方在一段時間後沒有正確回應

時間或已建立的連線失敗，因為已連接主機

無法回應10.188.116.96：5061

自檢

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能失敗的原因

以下是**測試 CsExUMConnectivity**可能失敗的一些常見原因：

  - 提供不正確的參數值。 如果使用，必須正確設定選用的參數，否則測試將會失敗。 重新執行不含選用參數的命令，並查看是否成功。

  - 如果 Exchange 伺服器未正確設定或尚未部署，此命令就會失敗。

  - 如果您的網路無法達到 Exchange 伺服器，此命令就會失敗。

</div>

<div>

## <a name="see-also"></a>請參閱


[Test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMVoiceMail)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

