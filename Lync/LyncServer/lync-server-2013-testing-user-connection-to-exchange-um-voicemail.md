---
title: Lync Server 2013： 測試 Exchange UM 語音信箱使用者連線
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
ms.openlocfilehash: 4fa3ad3f51d1342ac99d3c58be66931ba0770bf6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141219"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-user-connection-to-exchange-um-voicemail-in-lync-server-2013"></a>在 Lync Server 2013 中進行測試 Exchange UM 語音信箱的使用者連線

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2014年-11-01_


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
<td><p>測試工具</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>必要的權限</p></td>
<td><p>當執行在本機上使用 Lync Server 管理命令介面，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</p>
<p>當執行使用 Windows PowerShell 的遠端執行個體時，使用者必須被指派具有執行<strong>Test-csexumvoicemail</strong> cmdlet 的權限的 RBAC 角色。 若要查看可以使用此 cmdlet 的所有 RBAC 角色的清單，請在 Windows PowerShell 命令提示執行下列命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsExUMVoiceMail&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>描述

**Test-csexumvoicemail** cmdlet 可讓系統管理員確認使用者可以存取及使用 Microsoft Exchange Server 2013 整合通訊服務。 若要這麼做，指令程式連接至整合通訊服務，並留下語音信箱在指定的信箱。 這可以是系統提供語音信箱，或自訂。您所錄製您自己的 WAV 檔案。

</div>

<div>

## <a name="running-the-test"></a>執行測試

下列範例會測試 Exchange 整合通訊語音郵件連線集區 atl-cs-001.litwareinc.com。 這個命令將會執行只有當測試使用者所定義的集區 atl-cs-001.litwareinc.com。 如果他們有此命令會決定是否第一個測試使用者可以使用整合通訊語音信箱。 如果未設定之集區的測試使用者命令將會失敗。

    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" 

下一個範例會測試 Exchange Unified Messaging 語音郵件連線使用者 litwareinc 所示的命令\\kenmyer。 若要這麼做，在範例中的第一個命令會使用**Get-credential**指令程式來建立使用者 litwareinc 所需的 Windows PowerShell 命令列介面認證物件\\kenmyer。 請注意，您必須提供建立有效的認證物件和，以確保**Test-csexumvoicemail** cmdlet 可以執行其檢查此帳戶的密碼。

此範例中的第二個命令使用提供的認證物件 ($x) 和的 SIP 位址的使用者 litwareinc\\kenmyer 來決定是否或此使用者是否能夠連線至 Exchange 整合通訊語音信箱。

    $credential = Get-Credential "litwareinc\pilar" 
    
    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential 

在下一個範例中所示的命令是命令的範例 1; 所示的變化在此情況下，之後包含 OutLoggerVariable 參數會包含產生的成功或失敗的每個這些步驟即可**Test-csexumvoicemail** cmdletand 每個步驟的詳細資訊記錄。 若要這麼做，之後包含 OutLoggerVariable 參數會新增旁參數值 ExumText;會導致儲存在名為 $ExumTest 變數的詳細的記錄資訊。 在範例中的最後一個命令，在 toxml （） 方法用於將轉換成 XML 格式的記錄資訊。 XML 資料然後寫入名為 c: 檔案\\記錄\\使用 VoicemailTest.xml Out-file cmdlet。

    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -OutLoggerVariable VoicemailTest 
     
    $VoicemailTest.ToXML() | Out-File C:\Logs\VoicemailTest.xml

</div>

<div>

## <a name="determining-success-or-failure"></a>決定成功或失敗

如果已正確設定 Exchange 整合，您會收到類似，具有標示為 [**成功**結果屬性的輸出：

目標 Fqdn: atl-cs-001.litwareinc.com

結果： 成功

延遲： 00:00:02.9911345

錯誤訊息：

診斷：

如果指定的使用者無法連線到語音信箱，結果會顯示為**失敗**，以及其他資訊會記錄在 [錯誤] 和 [診斷屬性：

警告： 無法讀取登錄器的連接埠號碼指定完整

網域名稱 (FQDN)。 使用預設登錄器連接埠號碼。 例外狀況：

System.InvalidOperationException： 拓撲中找不到比對叢集。

在

Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri

eveRegistrarPortFromTopology (Int32& registrarPortNumber)

目標 Fqdn: atl-cs-001.litwareinc.com

結果： 失敗

延遲： 00:00:00

錯誤訊息： 10060 的連線嘗試失敗，因為連線對象

正常後沒有回應一段時間，或

已建立的連線失敗，因為已連線的主機

失敗回應 10.188.116.96:5061

內部的例外狀況： 的連線嘗試失敗，因為

連線對象正確後沒有回應一段

時間，或已建立的連線失敗，因為連線的主機

失敗回應 10.188.116.96:5061

診斷：

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能有為何失敗的原因

以下是一些常見的原因為何**Test-csexumvoicemail**可能會失敗：

  - 提供不正確的參數值。 如果使用，必須正確設定選用的參數或測試將會失敗。 重新執行此命令不含選擇性參數，並查看是否成功。

  - 如果設定錯誤或尚未部署 Exchange 伺服器，此命令將會失敗。

</div>

<div>

## <a name="see-also"></a>另請參閱


[Test-csexumconnectivity](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMConnectivity)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

