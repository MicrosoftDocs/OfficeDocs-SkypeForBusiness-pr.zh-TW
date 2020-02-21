---
title: Lync Server 2013： 測試使用者連線至 Exchange UM
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing user connection to Exchange UM
ms:assetid: 0b83fbf4-e124-4efd-a0a9-202eb849af82
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727300(v=OCS.15)
ms:contentKeyID: 63969573
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9cf7189df06549a3008fd86b9395617c6aea3e98
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193726"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-user-connection-to-exchange-um-in-lync-server-2013"></a>Lync Server 2013 中的測試使用者連線至 Exchange UM

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
<p>當執行使用 Windows PowerShell 的遠端執行個體時，使用者必須被指派具有執行<strong>Test-csexumconnectivity</strong> cmdlet 的權限的 RBAC 角色。 若要查看可以使用此 cmdlet 的所有 RBAC 角色的清單，請在 Windows PowerShell 命令提示執行下列命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsExUMConnectivity&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>說明

**Test-csexumconnectivity** cmdlet 會驗證指定的使用者可以連線至 Microsoft Exchange Server 2013 整合通訊服務。 請注意，此 cmdlet 只會驗證，可以連線至服務。 它不會測試服務本身。 若要測試整合通訊服務 （藉由執行實際使用者的信箱中留下語音郵件訊息綜合交易 cmdlet） 使用 Test-csexumvoicemail cmdlet。

</div>

<div>

## <a name="running-the-test"></a>執行測試

下列範例會測試 Exchange 整合通訊連線集區 atl-cs-001.litwareinc.com。 這個命令將會執行只有當測試使用者所定義的集區 atl-cs-001.litwareinc.com。 如果他們有此命令會判斷第一個測試使用者是否可以連線至整合通訊。 如果未設定之集區的測試使用者命令將會失敗。

    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" 

下列範例會測試 Exchange Unified Messaging 連線使用者 litwareinc 所示的命令\\kenmyer。 若要這麼做，在範例中的第一個命令會使用**Get-credential**指令程式來建立使用者 litwareinc 所需的 Windows PowerShell 命令列介面認證物件\\kenmyer。 請注意，您必須提供建立有效的認證物件和，以確保**Test-csexumconnectivity** cmdlet 可以執行其檢查此帳戶的密碼。

此範例中的第二個命令使用提供的認證物件 ($x) 和的 SIP 位址的使用者 litwareinc\\kenmyer 來決定是否或這個使用者可以連線至 Exchange 整合通訊。

    $credential = Get-Credential "litwareinc\kenmyer" 
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

在下一個範例中所示的命令是命令的如上所示的變化。 在此情況下，之後包含 OutLoggerVariable 參數會包含產生的成功或失敗的每個這些步驟即可**Test-csexumconnectivity** cmdletand 每個步驟的詳細資訊記錄。 若要這麼做，之後包含 OutLoggerVariable 參數會新增搭配參數值 ExumText;會導致儲存在名為 $ExumTest 變數的詳細的記錄資訊。 在範例中的最後一個命令，在 toxml （） 方法用於將轉換成 XML 格式的記錄資訊。 XML 資料然後寫入名為 c: 檔案\\記錄\\使用 ExumTest.xml Out-file cmdlet。

    $credential = Get-Credential "litwareinc\kenmyer" 
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential -OutLoggerVariable ExumTest 
    $ExumTest.ToXML() | Out-File C:\Logs\ExumTest.xml 

</div>

<div>

## <a name="determining-success-or-failure"></a>決定成功或失敗

如果已正確設定 Exchange 整合，您會收到類似，具有標示為 [**成功**結果屬性的輸出：

目標 Fqdn: atl-cs-001.litwareinc.com

結果： 成功

延遲： 00:00:00

錯誤訊息：

診斷：

如果指定的使用者無法收到通知，結果會顯示為**失敗**，及其他資訊會記錄在 [錯誤] 和 [診斷屬性：

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

以下是一些常見的原因為何**Test-csexumconnectivity**可能會失敗：

  - 提供不正確的參數值。 如果使用，必須正確設定選用的參數或測試將會失敗。 重新執行此命令不含選擇性參數，並查看是否成功。

  - 如果設定錯誤或尚未部署 Exchange 伺服器，此命令將會失敗。

  - 如果 Exchange 伺服器不是連線到您網路上，此命令會失敗。

</div>

<div>

## <a name="see-also"></a>另請參閱


[Test-csexumvoicemail](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMVoiceMail)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

