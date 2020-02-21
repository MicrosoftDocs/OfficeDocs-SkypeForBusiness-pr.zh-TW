---
title: Lync Server 2013： 測試整合連絡人存放區的存取
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing Unified Contact Store access
ms:assetid: 761f46bd-2e14-4f40-82b9-afa1eaa816b0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727309(v=OCS.15)
ms:contentKeyID: 63969621
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 34dbf6ede9f58b39df1722e742511ee0844c41f7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42218289"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-unified-contact-store-access-in-lync-server-2013"></a>在 Lync Server 2013 中進行測試整合連絡人存放區的存取

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2015年-05-15_


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
<p>當執行使用 Windows PowerShell 的遠端執行個體時，使用者必須被指派具有執行<strong>Test-csunifiedcontactstore</strong> cmdlet 的權限的 RBAC 角色。 若要查看可以使用此 cmdlet 的所有 RBAC 角色的清單，請在 Windows PowerShell 命令提示執行下列命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsUnifiedContactStore&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>說明

在 Lync Server 2013 中引進整合連絡人存放區提供系統管理員將使用者的連絡人儲存在 Microsoft Exchange Server 2013 而不是在 Lync Server 中的選項。 這可讓使用者存取相同的 Outlook Web Access，除了 Lync 2013 中的連絡人集合。 （或者，您可以繼續將連絡人儲存在 Lync Server。 In that case，使用者仍必須維護兩組不同的連絡人： 一個用於 Outlook 和 Outlook Web Access，一個用於與 Lync 2013 搭配使用。)

您可以判斷使用者的連絡人已執行**Test-csunifiedcontactstore** cmdlet 來移至整合連絡人存放區。 **Test-csunifiedcontactstore** cmdlet 將會採取指定的使用者帳戶，連線至整合連絡人存放區，並嘗試擷取使用者的連絡人。 如果可以不擷取任何連絡人然後命令將會失敗搭配 「 沒有連絡人已收到郵件的使用者。 確認連絡人存在的使用者。 」

請注意，如果使用者已成功地移轉至整合連絡人存放區，但不有他/她的連絡人清單上的任何連絡人**Test-csunifiedcontactstore** cmdlet 將會失敗。 指定的使用者必須至少一個連絡人**Test-csunifiedcontactstore** cmdlet 才能順利完成。

</div>

<div>

## <a name="running-the-test"></a>執行測試

下列範例所示的命令判斷是否連絡人使用者 litwareinc\\kenmyer 可以在整合連絡人存放區中找到。 若要這麼做，在範例中的第一個命令會使用**Get-credential**指令程式來建立使用者 litwareinc 所需的 Windows PowerShell 命令列介面認證物件\\kenmyer。 請注意，您必須提供建立有效的認證物件，並確定**Test-csunifiedcontactstore** cmdlet 可以執行其檢查此帳戶的密碼。

此範例中的第二個命令使用提供的認證物件 ($x) 和的 SIP 位址的使用者 litwareinc\\kenmyer 來判斷是否可以在整合連絡人存放區中找到他的連絡人。

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsUnifiedContactStore -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a>決定成功或失敗

如果已正確設定的存取權的連絡人存放區，您會收到類似，具有標示為 Result 屬性的輸出**成功：**

目標 Fqdn: atl-cs-001.litwareinc.com

結果： 成功

延遲： 00:00:14.9862716

錯誤訊息：

診斷：

如果未正確設定的存取權的連絡人存放區，結果會顯示為**失敗**，以及其他資訊會記錄在 [錯誤] 和 [診斷屬性：

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

以下是一些常見的原因為何**Test-csunifiedcontactstore**可能會失敗：

  - 提供不正確的參數值。 如果使用，必須正確設定選用的參數或測試將會失敗。 重新執行此命令不含選擇性參數，並查看是否成功。

  - 連接至整合連絡人存放區失敗，並嘗試擷取使用者的連絡人是不可行。 可能有網路連線問題。

</div>

<div>

## <a name="see-also"></a>另請參閱


[New-csuserservicespolicy](https://docs.microsoft.com/powershell/module/skype/New-CsUserServicesPolicy)  
[Set-csuserservicespolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsUserServicesPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

