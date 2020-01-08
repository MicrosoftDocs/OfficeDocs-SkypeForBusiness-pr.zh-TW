---
title: Lync Server 2013：設定 Microsoft Exchange Server 2013 整合 Lync Server 2013 語音信箱的訊息
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Exchange Server 2013 Unified Messaging for Lync Server 2013 voice mail
ms:assetid: 1be9c4f4-fd8e-4d64-9798-f8737b12e2ab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687983(v=OCS.15)
ms:contentKeyID: 49733573
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2e1d2bac84183e6cc274d6bb297c17401b3ff7f1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977532"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-exchange-server-2013-unified-messaging-for-microsoft-lync-server-2013-voice-mail"></a>針對 Microsoft Lync Server 2013 語音信箱設定 Microsoft Exchange Server 2013 整合通訊

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-04_

Microsoft Lync Server 2013 可讓您在 Microsoft Exchange Server 2013 中儲存語音信箱訊息;這些語音信箱訊息就會以電子郵件訊息的方式顯示在使用者的收件匣中。 您也可以在2010版的 Lync Server 和 Exchange 中找到這項功能。不過，我們已在2013版本中簡化了配置此「整合通訊」的程式，感謝您瞭解 UM 呼叫路由器元件。 這個元件是安裝在 Exchange 2013 用戶端存取伺服器上，Exchange 整合通訊的所有呼叫（例如語音信箱）首先透過呼叫路由器進行路由，然後再重新導向至適當的信箱伺服器。

如果您已在 Lync Server 2013 與 Exchange 2013 之間設定伺服器對伺服器驗證，就表示您已準備好設定整合訊息。 若要這樣做，您必須先在 Exchange 伺服器上建立並指派新的統一訊息撥號方案。 例如，這兩個命令（從 Exchange 管理命令介面內部執行）會為 Exchange 設定新的3位數撥號方案：

    New-UMDialPlan -Name "RedmondDialPlan" -VoIPSecurity "Secured" -NumberOfDigitsInExtension 3 -URIType "SipName" -CountryOrRegionCode 1
    Set-UMDialPlan "RedmondDialPlan" -ConfiguredInCountryOrRegionGroups "Anywhere,*,*,*" -AllowedInCountryOrRegionGroups "Anywhere"

在範例中的第一個命令中，VoIPSecurity 參數和參數值「受保護」，表示信號通道是使用傳輸層安全性（TLS）來加密。 URIType "SipName" 代表將使用 SIP 通訊協定來傳送和接收郵件，而 CountryOrRegionCode 1 則表示您的撥號計畫適用于美國。

在第二個命令中，傳遞給 ConfiguredInCountryOrRegionGroups 參數的參數值會指定可與此撥號方案搭配使用的國家/地區群組。 參數值 "隨處，\*"\*，\*"會設定下列專案：

  - 組名（"隨處"）

  - AllowedNumberString （\*，萬用字元代表允許的任何數位字串）

  - DialNumberString （\*，代表允許任何撥入號碼的萬用字元）

  - TextComment （\*，萬用字元代表允許使用任何文字命令）

<div>


> [!NOTE]  
> 建立新的撥號方案也會建立預設信箱原則。



</div>

建立及設定新的撥號方案之後，您必須將新的撥號方案新增至您的統一訊息伺服器，然後修改該伺服器的啟動模式。特別是，您必須將 [啟動模式] 設定為 "雙"。 您可以從 Exchange 管理命令介面內執行這兩項工作：

    Set-UmService -Identity "atl-exchangeum-001.litwareinc.com" -DialPlans "RedmondDialPlan" -UMStartupMode "Dual"

在已設定統一訊息伺服器之後，您必須接著執行 ExchangeCertificate Cmdlet，以確保您的 Exchange 憑證已套用到整合訊息服務：

    Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "EA5A332496CC05DA69B75B66111C0F78A110D22d" -Services "SMTP","IIS","UM"

在正確指派憑證之後，您必須停止並重新啟動統一訊息伺服器上的 MsExchangeUM 服務。 每當您變更啟動模式時，都必須停止並重新啟動此服務。

完成整合郵件伺服器的設定之後，您就可以設定 UM 呼叫路由器：

    Set-UMCallRouterSettings -Server "atl-exchange-001.litwareinc.com" -UMStartupMode "Dual" -DialPlans "RedmondDialPlan" 
    Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "45BAA32496CC891169B75B9811320F78A1075DDA" -Services "IIS","UMCallRouter"

因為啟動模式已變更，所以您必須停止並重新啟動託管 UM 呼叫路由器的電腦上的 MsExchangeUMCR 服務。

若要完成統一訊息設定，您必須建立 UM 信箱原則，然後使用該原則來允許使用者使用整合訊息。 您可以使用類似以下的命令來建立信箱原則：

    New-UMMailboxPolicy -Name "RedmondMailboxPolicy" -AllowedInCountryOrRegionGroups "Anywhere"

而且，您可以使用類似以下的命令，讓使用者能夠使用整合訊息：

    Enable-UMMailbox -Extensions 100 -SIPResourceIdentifier "kenmyer@litwareinc.com" -Identity "litwareinc\kenmyer" -UMMailboxPolicy "RedmondMailboxPolicy"

在上述命令中，Extensions 參數代表使用者的電話分機號碼。 在這個範例中，使用者的分機號碼是100。

在您啟用自己的信箱之後，使用者 kenmyer@litwareinc.com 應該能夠使用 Exchange 整合訊息。 您可以從 Lync Server Management Shell 中執行[Test CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMConnectivity) Cmdlet，以確認使用者可以連線到 Exchange UM：

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

如果您有另一個已啟用整合訊息的使用者，您可以使用[CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMVoiceMail) Cmdlet，確認此第二位使用者可以為第一個使用者留下語音信箱訊息。

    $credential = Get-Credential "litwareinc\pilar"
    
    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential

</div>

<span> </span>

</div>

</div>

</div>

