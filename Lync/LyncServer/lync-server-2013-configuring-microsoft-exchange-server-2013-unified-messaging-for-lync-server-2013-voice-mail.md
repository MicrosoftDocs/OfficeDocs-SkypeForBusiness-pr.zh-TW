---
title: Lync Server 2013： 設定 Microsoft Exchange Server 2013 整合通訊的 Lync Server 2013 語音信箱
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Exchange Server 2013 Unified Messaging for Lync Server 2013 voice mail
ms:assetid: 1be9c4f4-fd8e-4d64-9798-f8737b12e2ab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687983(v=OCS.15)
ms:contentKeyID: 49733573
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 33c506e8b9f1201ad9382e361afc376590c6feca
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134769"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-exchange-server-2013-unified-messaging-for-microsoft-lync-server-2013-voice-mail"></a><span data-ttu-id="b16d1-102">設定 Microsoft Exchange Server 2013 整合通訊的 Microsoft Lync Server 2013 語音信箱</span><span class="sxs-lookup"><span data-stu-id="b16d1-102">Configuring Microsoft Exchange Server 2013 Unified Messaging for Microsoft Lync Server 2013 voice mail</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b16d1-103">_**上次修改主題：** 2013年-02-04_</span><span class="sxs-lookup"><span data-stu-id="b16d1-103">_**Topic Last Modified:** 2013-02-04_</span></span>

<span data-ttu-id="b16d1-104">Microsoft Lync Server 2013 可讓您能夠儲存在 Microsoft Exchange Server 2013 中; 的語音信箱訊息這些語音郵件訊息將會顯示為使用者的收件匣中的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="b16d1-104">Microsoft Lync Server 2013 enables you to have voicemail messages stored in Microsoft Exchange Server 2013; those voicemail messages will then appear as email messages in your users' Inboxes.</span></span> <span data-ttu-id="b16d1-105">在 2010年版本的 Lync 伺服器和 Exchange; 也找到這項功能不過，設定此 「 整合通訊 」 的程序已經過簡化 UM 呼叫路由器元件的簡介感謝 2013年版本。</span><span class="sxs-lookup"><span data-stu-id="b16d1-105">This capability was also found in the 2010 editions of Lync Server and Exchange; however, the process of configuring this "unified messaging" has been simplified in the 2013 editions thanks to the introduction of the UM Call Router component.</span></span> <span data-ttu-id="b16d1-106">在 Exchange 2013 用戶端存取伺服器上，安裝此元件和 Exchange 整合通訊 （例如語音信箱） 的所有呼叫會先路由傳送經由呼叫路由器然後不斷重新導向至適當的 Mailbox server。</span><span class="sxs-lookup"><span data-stu-id="b16d1-106">This component is installed on the Exchange 2013 Client Access server, and all calls to Exchange unified messaging (such as a voicemail) are first routed through the Call Router and then are redirected to the appropriate Mailbox server.</span></span>

<span data-ttu-id="b16d1-107">如果您已設定 Lync Server 2013 和 Exchange 2013 之間的伺服器對伺服器驗證您已準備好設定整合通訊。</span><span class="sxs-lookup"><span data-stu-id="b16d1-107">If you have already configured server-to-server authentication between Lync Server 2013 and Exchange 2013 then you are ready to setup unified messaging.</span></span> <span data-ttu-id="b16d1-108">若要這麼做，您必須先建立並指派新整合通訊撥號對應表上您的 Exchange 伺服器。</span><span class="sxs-lookup"><span data-stu-id="b16d1-108">To do so, you must first create and assign a new unified messaging dial plan on your Exchange server.</span></span> <span data-ttu-id="b16d1-109">例如，（從 Exchange 管理命令介面中執行） 這兩個命令設定 Exchange 新的 3 位數字撥號對應表：</span><span class="sxs-lookup"><span data-stu-id="b16d1-109">For example, these two commands (run from within the Exchange Management Shell) configure a new 3-digit dial plan for Exchange:</span></span>

    New-UMDialPlan -Name "RedmondDialPlan" -VoIPSecurity "Secured" -NumberOfDigitsInExtension 3 -URIType "SipName" -CountryOrRegionCode 1
    Set-UMDialPlan "RedmondDialPlan" -ConfiguredInCountryOrRegionGroups "Anywhere,*,*,*" -AllowedInCountryOrRegionGroups "Anywhere"

<span data-ttu-id="b16d1-p103">在上述範例的第一個命令中，VoIPSecurity 參數和參數值 "Secured" 指出信號通道是使用傳輸層安全性 (TLS) 來加密的。URIType "SipName" 指出會使用 SIP 通訊協定來傳送和接收訊息，而 CountryOrRegionCode 的 1 則指出撥號對應表是套用至美國。</span><span class="sxs-lookup"><span data-stu-id="b16d1-p103">In the first command in the example, the VoIPSecurity parameter, and the parameter value "Secured" indicate that the signaling channel is encrypted by using Transport Layer Security (TLS). The URIType "SipName" indicates that messages will be sent and received using the SIP protocol, and the CountryOrRegionCode of 1 indicates that the dial plan applies to the US.</span></span>

<span data-ttu-id="b16d1-112">在第二個命令中，傳送至 ConfiguredInCountryOrRegionGroups 參數的參數值指定了可使用此撥號對應表的的國內群組。</span><span class="sxs-lookup"><span data-stu-id="b16d1-112">In the second command, the parameter value passed to the ConfiguredInCountryOrRegionGroups parameter specifies the in-country groups that can be used with this dial plan.</span></span> <span data-ttu-id="b16d1-113">參數值 「 無所不在，\*、\*、\*」 設定下列：</span><span class="sxs-lookup"><span data-stu-id="b16d1-113">The parameter value "Anywhere,\*,\*,\*" sets the following:</span></span>

  - <span data-ttu-id="b16d1-114">群組名稱 ("Anywhere")</span><span class="sxs-lookup"><span data-stu-id="b16d1-114">Group name ("Anywhere")</span></span>

  - <span data-ttu-id="b16d1-115">AllowedNumberString (\*，萬用字元表示可允許任何號碼字串)</span><span class="sxs-lookup"><span data-stu-id="b16d1-115">AllowedNumberString (\*, a wildcard character indicating that any number string is allowed)</span></span>

  - <span data-ttu-id="b16d1-116">DialNumberString (\*，萬用字元表示可允許任何撥打的號碼)</span><span class="sxs-lookup"><span data-stu-id="b16d1-116">DialNumberString (\*, a wildcard character indicating that any dialed number is allowed)</span></span>

  - <span data-ttu-id="b16d1-117">TextComment (\*，萬用字元表示可允許任何文字命令)</span><span class="sxs-lookup"><span data-stu-id="b16d1-117">TextComment (\*, a wildcard character indicating that any text command is allowed)</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b16d1-118">建立新的撥號對應表也會建立預設信箱原則。</span><span class="sxs-lookup"><span data-stu-id="b16d1-118">Creating a new dial plan will also create a Default Mailbox Policy.</span></span>



</div>

<span data-ttu-id="b16d1-119">建立並設定新的撥號對應表之後，您必須將新的撥號對應表新增至整合通訊伺服器，然後修改該伺服器的啟動模式；明確地說，您必須將啟動模式設定為「雙重」模式。</span><span class="sxs-lookup"><span data-stu-id="b16d1-119">After creating and configuring the new dial plan you must add the new dial plan to your unified messaging server and then modify the startup mode of that server; in particular, you must set the startup mode to "Dual".</span></span> <span data-ttu-id="b16d1-120">您可以執行這兩項工作從內 Exchange 管理命令介面：</span><span class="sxs-lookup"><span data-stu-id="b16d1-120">You can perform both of these tasks from within the Exchange Management Shell:</span></span>

    Set-UmService -Identity "atl-exchangeum-001.litwareinc.com" -DialPlans "RedmondDialPlan" -UMStartupMode "Dual"

<span data-ttu-id="b16d1-121">在設定整合通訊伺服器之後您接下來應該執行 Enable-exchangecertificate cmdlet 以確保您的 Exchange 憑證會套用至整合通訊服務：</span><span class="sxs-lookup"><span data-stu-id="b16d1-121">After the unified messaging server has been configured you should next run the Enable-ExchangeCertificate cmdlet to ensure that your Exchange certificate is applied to the unified messaging service:</span></span>

    Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "EA5A332496CC05DA69B75B66111C0F78A110D22d" -Services "SMTP","IIS","UM"

<span data-ttu-id="b16d1-p106">正確指派憑證之後，您就必須停止並重新啟動整合通訊伺服器上的 MsExchangeUM 服務。每當您變更啟動模式時，都必須停止並重新啟動此服務。</span><span class="sxs-lookup"><span data-stu-id="b16d1-p106">After the certificate has been correctly assigned you must then stop and restart the MsExchangeUM service on the unified messaging server. This service must be stopped and restarted any time you change the startup mode.</span></span>

<span data-ttu-id="b16d1-124">完成整合通訊伺服器的設定之後，您就可以開始設定 UM 通話路由器：</span><span class="sxs-lookup"><span data-stu-id="b16d1-124">After finishing configuration of the unified messaging server you can then configure the UM Call Router:</span></span>

    Set-UMCallRouterSettings -Server "atl-exchange-001.litwareinc.com" -UMStartupMode "Dual" -DialPlans "RedmondDialPlan" 
    Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "45BAA32496CC891169B75B9811320F78A1075DDA" -Services "IIS","UMCallRouter"

<span data-ttu-id="b16d1-125">由於啟動模式已變更，因此您必須停止並重新啟動主控 UM 通話路由器之電腦上的 MsExchangeUMCR 服務。</span><span class="sxs-lookup"><span data-stu-id="b16d1-125">Because the startup mode has changed you must stop and restart the MsExchangeUMCR service on the computer hosting the UM Call Router.</span></span>

<span data-ttu-id="b16d1-p107">若要完成整合通訊設定，您還需要建立 UM 信箱原則，然後使用該原則來啟用使用者的整合通訊。您可使用類似下列的命令，來建立信箱原則：</span><span class="sxs-lookup"><span data-stu-id="b16d1-p107">To complete the unified messaging setup, you then need to create a UM mailbox policy and then use that policy to enable users for unified messaging. You can create a mailbox policy by using a command similar to this:</span></span>

    New-UMMailboxPolicy -Name "RedmondMailboxPolicy" -AllowedInCountryOrRegionGroups "Anywhere"

<span data-ttu-id="b16d1-128">您可使用類似下列的命令，來啟用使用者的整合通訊：</span><span class="sxs-lookup"><span data-stu-id="b16d1-128">And you can enable a user for unified messaging by using a command similar to this:</span></span>

    Enable-UMMailbox -Extensions 100 -SIPResourceIdentifier "kenmyer@litwareinc.com" -Identity "litwareinc\kenmyer" -UMMailboxPolicy "RedmondMailboxPolicy"

<span data-ttu-id="b16d1-p108">在上一個命令中，Extensions 參數代表使用者的電話分機號碼。在此範例中，使用者的分機號碼為 100。</span><span class="sxs-lookup"><span data-stu-id="b16d1-p108">In the preceding command, the Extensions parameter represents the telephone extension number for the user. In this example, the user has the extension number 100.</span></span>

<span data-ttu-id="b16d1-131">啟用 kenmyer@litwareinc.com 的信箱後，該使用者應該就能使用 Exchange 整合通訊。</span><span class="sxs-lookup"><span data-stu-id="b16d1-131">After you have enabled his mailbox, the user kenmyer@litwareinc.com should be able to use Exchange unified messaging.</span></span> <span data-ttu-id="b16d1-132">您可以確認使用者可以連線至 Exchange UM，藉由執行 Lync Server 管理命令介面中的 [從[Test-csexumconnectivity](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMConnectivity) cmdlet:</span><span class="sxs-lookup"><span data-stu-id="b16d1-132">You can verify that the user can connect to Exchange UM by running the [Test-CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMConnectivity) cmdlet from within the Lync Server Management Shell:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="b16d1-133">若您還有第二個啟用了整合通訊的使用者，您可使用 [Test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMVoiceMail) Cmdlet 來驗證第二個使用者是否能語音留言給第一個使用者。</span><span class="sxs-lookup"><span data-stu-id="b16d1-133">If you have a second user who has been enabled for unified messaging you can use the [Test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMVoiceMail) cmdlet to verify that this second user can leave a voicemail message for the first user.</span></span>

    $credential = Get-Credential "litwareinc\pilar"
    
    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential

</div>

<span> </span>

</div>

</div>

</div>

