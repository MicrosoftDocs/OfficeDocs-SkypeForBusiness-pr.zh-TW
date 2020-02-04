---
title: Lync Server 2013：設定 Microsoft Exchange Server 2013 整合 Lync Server 2013 語音信箱的訊息
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
ms.openlocfilehash: 367f4cc517771f51d7a1452293ad9803075d285f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755927"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-exchange-server-2013-unified-messaging-for-microsoft-lync-server-2013-voice-mail"></a><span data-ttu-id="94b54-102">針對 Microsoft Lync Server 2013 語音信箱設定 Microsoft Exchange Server 2013 整合通訊</span><span class="sxs-lookup"><span data-stu-id="94b54-102">Configuring Microsoft Exchange Server 2013 Unified Messaging for Microsoft Lync Server 2013 voice mail</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="94b54-103">_**主題上次修改日期：** 2013-02-04_</span><span class="sxs-lookup"><span data-stu-id="94b54-103">_**Topic Last Modified:** 2013-02-04_</span></span>

<span data-ttu-id="94b54-104">Microsoft Lync Server 2013 可讓您在 Microsoft Exchange Server 2013 中儲存語音信箱訊息;這些語音信箱訊息就會以電子郵件訊息的方式顯示在使用者的收件匣中。</span><span class="sxs-lookup"><span data-stu-id="94b54-104">Microsoft Lync Server 2013 enables you to have voicemail messages stored in Microsoft Exchange Server 2013; those voicemail messages will then appear as email messages in your users' Inboxes.</span></span> <span data-ttu-id="94b54-105">您也可以在2010版的 Lync Server 和 Exchange 中找到這項功能。不過，我們已在2013版本中簡化了配置此「整合通訊」的程式，感謝您瞭解 UM 呼叫路由器元件。</span><span class="sxs-lookup"><span data-stu-id="94b54-105">This capability was also found in the 2010 editions of Lync Server and Exchange; however, the process of configuring this "unified messaging" has been simplified in the 2013 editions thanks to the introduction of the UM Call Router component.</span></span> <span data-ttu-id="94b54-106">這個元件是安裝在 Exchange 2013 用戶端存取伺服器上，Exchange 整合通訊的所有呼叫（例如語音信箱）首先透過呼叫路由器進行路由，然後再重新導向至適當的信箱伺服器。</span><span class="sxs-lookup"><span data-stu-id="94b54-106">This component is installed on the Exchange 2013 Client Access server, and all calls to Exchange unified messaging (such as a voicemail) are first routed through the Call Router and then are redirected to the appropriate Mailbox server.</span></span>

<span data-ttu-id="94b54-107">如果您已在 Lync Server 2013 與 Exchange 2013 之間設定伺服器對伺服器驗證，就表示您已準備好設定整合訊息。</span><span class="sxs-lookup"><span data-stu-id="94b54-107">If you have already configured server-to-server authentication between Lync Server 2013 and Exchange 2013 then you are ready to setup unified messaging.</span></span> <span data-ttu-id="94b54-108">若要這樣做，您必須先在 Exchange 伺服器上建立並指派新的統一訊息撥號方案。</span><span class="sxs-lookup"><span data-stu-id="94b54-108">To do so, you must first create and assign a new unified messaging dial plan on your Exchange server.</span></span> <span data-ttu-id="94b54-109">例如，這兩個命令（從 Exchange 管理命令介面內部執行）會為 Exchange 設定新的3位數撥號方案：</span><span class="sxs-lookup"><span data-stu-id="94b54-109">For example, these two commands (run from within the Exchange Management Shell) configure a new 3-digit dial plan for Exchange:</span></span>

    New-UMDialPlan -Name "RedmondDialPlan" -VoIPSecurity "Secured" -NumberOfDigitsInExtension 3 -URIType "SipName" -CountryOrRegionCode 1
    Set-UMDialPlan "RedmondDialPlan" -ConfiguredInCountryOrRegionGroups "Anywhere,*,*,*" -AllowedInCountryOrRegionGroups "Anywhere"

<span data-ttu-id="94b54-110">在範例中的第一個命令中，VoIPSecurity 參數和參數值「受保護」，表示信號通道是使用傳輸層安全性（TLS）來加密。</span><span class="sxs-lookup"><span data-stu-id="94b54-110">In the first command in the example, the VoIPSecurity parameter, and the parameter value "Secured" indicate that the signaling channel is encrypted by using Transport Layer Security (TLS).</span></span> <span data-ttu-id="94b54-111">URIType "SipName" 代表將使用 SIP 通訊協定來傳送和接收郵件，而 CountryOrRegionCode 1 則表示您的撥號計畫適用于美國。</span><span class="sxs-lookup"><span data-stu-id="94b54-111">The URIType "SipName" indicates that messages will be sent and received using the SIP protocol, and the CountryOrRegionCode of 1 indicates that the dial plan applies to the US.</span></span>

<span data-ttu-id="94b54-112">在第二個命令中，傳遞給 ConfiguredInCountryOrRegionGroups 參數的參數值會指定可與此撥號方案搭配使用的國家/地區群組。</span><span class="sxs-lookup"><span data-stu-id="94b54-112">In the second command, the parameter value passed to the ConfiguredInCountryOrRegionGroups parameter specifies the in-country groups that can be used with this dial plan.</span></span> <span data-ttu-id="94b54-113">參數值 "隨處，\*"\*，\*"會設定下列專案：</span><span class="sxs-lookup"><span data-stu-id="94b54-113">The parameter value "Anywhere,\*,\*,\*" sets the following:</span></span>

  - <span data-ttu-id="94b54-114">組名（"隨處"）</span><span class="sxs-lookup"><span data-stu-id="94b54-114">Group name ("Anywhere")</span></span>

  - <span data-ttu-id="94b54-115">AllowedNumberString （\*，萬用字元代表允許的任何數位字串）</span><span class="sxs-lookup"><span data-stu-id="94b54-115">AllowedNumberString (\*, a wildcard character indicating that any number string is allowed)</span></span>

  - <span data-ttu-id="94b54-116">DialNumberString （\*，代表允許任何撥入號碼的萬用字元）</span><span class="sxs-lookup"><span data-stu-id="94b54-116">DialNumberString (\*, a wildcard character indicating that any dialed number is allowed)</span></span>

  - <span data-ttu-id="94b54-117">TextComment （\*，萬用字元代表允許使用任何文字命令）</span><span class="sxs-lookup"><span data-stu-id="94b54-117">TextComment (\*, a wildcard character indicating that any text command is allowed)</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="94b54-118">建立新的撥號方案也會建立預設信箱原則。</span><span class="sxs-lookup"><span data-stu-id="94b54-118">Creating a new dial plan will also create a Default Mailbox Policy.</span></span>



</div>

<span data-ttu-id="94b54-119">建立及設定新的撥號方案之後，您必須將新的撥號方案新增至您的統一訊息伺服器，然後修改該伺服器的啟動模式。特別是，您必須將 [啟動模式] 設定為 "雙"。</span><span class="sxs-lookup"><span data-stu-id="94b54-119">After creating and configuring the new dial plan you must add the new dial plan to your unified messaging server and then modify the startup mode of that server; in particular, you must set the startup mode to "Dual".</span></span> <span data-ttu-id="94b54-120">您可以從 Exchange 管理命令介面內執行這兩項工作：</span><span class="sxs-lookup"><span data-stu-id="94b54-120">You can perform both of these tasks from within the Exchange Management Shell:</span></span>

    Set-UmService -Identity "atl-exchangeum-001.litwareinc.com" -DialPlans "RedmondDialPlan" -UMStartupMode "Dual"

<span data-ttu-id="94b54-121">在已設定統一訊息伺服器之後，您必須接著執行 ExchangeCertificate Cmdlet，以確保您的 Exchange 憑證已套用到整合訊息服務：</span><span class="sxs-lookup"><span data-stu-id="94b54-121">After the unified messaging server has been configured you should next run the Enable-ExchangeCertificate cmdlet to ensure that your Exchange certificate is applied to the unified messaging service:</span></span>

    Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "EA5A332496CC05DA69B75B66111C0F78A110D22d" -Services "SMTP","IIS","UM"

<span data-ttu-id="94b54-122">在正確指派憑證之後，您必須停止並重新啟動統一訊息伺服器上的 MsExchangeUM 服務。</span><span class="sxs-lookup"><span data-stu-id="94b54-122">After the certificate has been correctly assigned you must then stop and restart the MsExchangeUM service on the unified messaging server.</span></span> <span data-ttu-id="94b54-123">每當您變更啟動模式時，都必須停止並重新啟動此服務。</span><span class="sxs-lookup"><span data-stu-id="94b54-123">This service must be stopped and restarted any time you change the startup mode.</span></span>

<span data-ttu-id="94b54-124">完成整合郵件伺服器的設定之後，您就可以設定 UM 呼叫路由器：</span><span class="sxs-lookup"><span data-stu-id="94b54-124">After finishing configuration of the unified messaging server you can then configure the UM Call Router:</span></span>

    Set-UMCallRouterSettings -Server "atl-exchange-001.litwareinc.com" -UMStartupMode "Dual" -DialPlans "RedmondDialPlan" 
    Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "45BAA32496CC891169B75B9811320F78A1075DDA" -Services "IIS","UMCallRouter"

<span data-ttu-id="94b54-125">因為啟動模式已變更，所以您必須停止並重新啟動託管 UM 呼叫路由器的電腦上的 MsExchangeUMCR 服務。</span><span class="sxs-lookup"><span data-stu-id="94b54-125">Because the startup mode has changed you must stop and restart the MsExchangeUMCR service on the computer hosting the UM Call Router.</span></span>

<span data-ttu-id="94b54-126">若要完成統一訊息設定，您必須建立 UM 信箱原則，然後使用該原則來允許使用者使用整合訊息。</span><span class="sxs-lookup"><span data-stu-id="94b54-126">To complete the unified messaging setup, you then need to create a UM mailbox policy and then use that policy to enable users for unified messaging.</span></span> <span data-ttu-id="94b54-127">您可以使用類似以下的命令來建立信箱原則：</span><span class="sxs-lookup"><span data-stu-id="94b54-127">You can create a mailbox policy by using a command similar to this:</span></span>

    New-UMMailboxPolicy -Name "RedmondMailboxPolicy" -AllowedInCountryOrRegionGroups "Anywhere"

<span data-ttu-id="94b54-128">而且，您可以使用類似以下的命令，讓使用者能夠使用整合訊息：</span><span class="sxs-lookup"><span data-stu-id="94b54-128">And you can enable a user for unified messaging by using a command similar to this:</span></span>

    Enable-UMMailbox -Extensions 100 -SIPResourceIdentifier "kenmyer@litwareinc.com" -Identity "litwareinc\kenmyer" -UMMailboxPolicy "RedmondMailboxPolicy"

<span data-ttu-id="94b54-129">在上述命令中，Extensions 參數代表使用者的電話分機號碼。</span><span class="sxs-lookup"><span data-stu-id="94b54-129">In the preceding command, the Extensions parameter represents the telephone extension number for the user.</span></span> <span data-ttu-id="94b54-130">在這個範例中，使用者的分機號碼是100。</span><span class="sxs-lookup"><span data-stu-id="94b54-130">In this example, the user has the extension number 100.</span></span>

<span data-ttu-id="94b54-131">在您啟用自己的信箱之後，使用者 kenmyer@litwareinc.com 應該能夠使用 Exchange 整合訊息。</span><span class="sxs-lookup"><span data-stu-id="94b54-131">After you have enabled his mailbox, the user kenmyer@litwareinc.com should be able to use Exchange unified messaging.</span></span> <span data-ttu-id="94b54-132">您可以從 Lync Server Management Shell 中執行[Test CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMConnectivity) Cmdlet，以確認使用者可以連線到 Exchange UM：</span><span class="sxs-lookup"><span data-stu-id="94b54-132">You can verify that the user can connect to Exchange UM by running the [Test-CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMConnectivity) cmdlet from within the Lync Server Management Shell:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="94b54-133">如果您有另一個已啟用整合訊息的使用者，您可以使用[CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMVoiceMail) Cmdlet，確認此第二位使用者可以為第一個使用者留下語音信箱訊息。</span><span class="sxs-lookup"><span data-stu-id="94b54-133">If you have a second user who has been enabled for unified messaging you can use the [Test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMVoiceMail) cmdlet to verify that this second user can leave a voicemail message for the first user.</span></span>

    $credential = Get-Credential "litwareinc\pilar"
    
    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential

</div>

<span> </span>

</div>

</div>

</div>

