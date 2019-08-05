---
title: 針對商務用 Skype Server 2015 語音信箱設定 Exchange Server 2013 整合通訊
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/11/2019
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1be9c4f4-fd8e-4d64-9798-f8737b12e2ab
description: '摘要: 針對商務用 Skype Server 語音信箱設定 Exchange Server 整合訊息。'
ms.openlocfilehash: a1c83b4ec92e6e3b3d678d2d7e0a65f58fc9d6ce
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188146"
---
# <a name="configure-exchange-server-unified-messaging-for-skype-for-business-server-voice-mail"></a><span data-ttu-id="8cc84-103">針對商務用 Skype Server 2015 語音信箱設定 Exchange Server 2013 整合通訊</span><span class="sxs-lookup"><span data-stu-id="8cc84-103">Configure Exchange Server Unified Messaging for Skype for Business Server voice mail</span></span>
 
<span data-ttu-id="8cc84-104">**摘要:** 針對商務用 Skype Server 語音信箱設定 Exchange Server 整合訊息。</span><span class="sxs-lookup"><span data-stu-id="8cc84-104">**Summary:** Configure Exchange Server Unified Messaging for Skype for Business Server voice mail.</span></span>
  
<span data-ttu-id="8cc84-105">商務用 Skype Server 可讓您在 Exchange Server 2016 或 Exchange Server 2013 中儲存語音信箱訊息;這些語音信箱訊息就會以電子郵件訊息的方式顯示在使用者的收件匣中。</span><span class="sxs-lookup"><span data-stu-id="8cc84-105">Skype for Business Server enables you to have voicemail messages stored in Exchange Server 2016 or Exchange Server 2013; those voicemail messages will then appear as email messages in your users' Inboxes.</span></span> 

> [!NOTE]
> <span data-ttu-id="8cc84-106">Exchange 2019 中已不再提供 exchange 整合訊息 (如前所述), 但是您仍然可以使用電話系統來錄製語音信箱訊息, 然後將錄製內容留在使用者的 Exchange 信箱中。</span><span class="sxs-lookup"><span data-stu-id="8cc84-106">Exchange Unified Messaging as previously known is no longer available in Exchange 2019, but you can still use Phone System to record voicemail messages and then leave the recording in a user's Exchange mailbox.</span></span> <span data-ttu-id="8cc84-107">如需詳細資訊, 請參閱[規劃雲端語音信箱服務](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md)。</span><span class="sxs-lookup"><span data-stu-id="8cc84-107">See [Plan Cloud Voicemail service](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) for more information.</span></span>
  
<span data-ttu-id="8cc84-108">如果您已在商務用 Skype Server 與 Exchange Server 2016 或 Exchange server 2013 之間設定了伺服器對伺服器驗證, 就表示您已準備好設定整合訊息。</span><span class="sxs-lookup"><span data-stu-id="8cc84-108">If you have already configured server-to-server authentication between Skype for Business Server and Exchange Server 2016 or Exchange Server 2013, then you are ready to setup unified messaging.</span></span> <span data-ttu-id="8cc84-109">若要這樣做, 您必須先在 Exchange 伺服器上建立並指派新的統一訊息撥號方案。</span><span class="sxs-lookup"><span data-stu-id="8cc84-109">To do so, you must first create and assign a new unified messaging dial plan on your Exchange Server.</span></span> <span data-ttu-id="8cc84-110">例如, 這兩個命令 (從 Exchange 管理命令介面內部執行) 會為 Exchange 設定新的3位數撥號方案:</span><span class="sxs-lookup"><span data-stu-id="8cc84-110">For example, these two commands (run from within the Exchange Management Shell) configure a new 3-digit dial plan for Exchange:</span></span>
  
```
New-UMDialPlan -Name "RedmondDialPlan" -VoIPSecurity "Secured" -NumberOfDigitsInExtension 3 -URIType "SipName" -CountryOrRegionCode 1
Set-UMDialPlan "RedmondDialPlan" -ConfiguredInCountryOrRegionGroups "Anywhere,*,*,*" -AllowedInCountryOrRegionGroups "Anywhere"
```

<span data-ttu-id="8cc84-111">在範例中的第一個命令中, VoIPSecurity 參數和參數值「受保護」, 表示信號通道是使用傳輸層安全性 (TLS) 來加密。</span><span class="sxs-lookup"><span data-stu-id="8cc84-111">In the first command in the example, the VoIPSecurity parameter, and the parameter value "Secured" indicates that the signaling channel is encrypted by using Transport Layer Security (TLS).</span></span> <span data-ttu-id="8cc84-112">URIType "SipName" 代表將使用 SIP 通訊協定來傳送和接收郵件, 而 CountryOrRegionCode 1 則表示您的撥號計畫適用于美國。</span><span class="sxs-lookup"><span data-stu-id="8cc84-112">The URIType "SipName" indicates that messages will be sent and received using the SIP protocol, and the CountryOrRegionCode of 1 indicates that the dial plan applies to the US.</span></span>
  
<span data-ttu-id="8cc84-113">在第二個命令中, 傳遞給 ConfiguredInCountryOrRegionGroups 參數的參數值會指定可與此撥號方案搭配使用的國家/地區群組。</span><span class="sxs-lookup"><span data-stu-id="8cc84-113">In the second command, the parameter value passed to the ConfiguredInCountryOrRegionGroups parameter specifies the in-country groups that can be used with this dial plan.</span></span> <span data-ttu-id="8cc84-114">參數值 "隨處,\*"\*,\*"會設定下列專案:</span><span class="sxs-lookup"><span data-stu-id="8cc84-114">The parameter value "Anywhere,\*,\*,\*" sets the following:</span></span>
  
- <span data-ttu-id="8cc84-115">組名 ("隨處")</span><span class="sxs-lookup"><span data-stu-id="8cc84-115">Group name ("Anywhere")</span></span>
    
- <span data-ttu-id="8cc84-116">AllowedNumberString (\*, 萬用字元代表允許的任何數位字串)</span><span class="sxs-lookup"><span data-stu-id="8cc84-116">AllowedNumberString (\*, a wildcard character indicating that any number string is allowed)</span></span>
    
- <span data-ttu-id="8cc84-117">DialNumberString (\*, 代表允許任何撥入號碼的萬用字元)</span><span class="sxs-lookup"><span data-stu-id="8cc84-117">DialNumberString (\*, a wildcard character indicating that any dialed number is allowed)</span></span>
    
- <span data-ttu-id="8cc84-118">TextComment (\*, 萬用字元代表允許使用任何文字命令)</span><span class="sxs-lookup"><span data-stu-id="8cc84-118">TextComment (\*, a wildcard character indicating that any text command is allowed)</span></span>
    
> [!NOTE]
> <span data-ttu-id="8cc84-119">建立新的撥號方案也會建立預設信箱原則。</span><span class="sxs-lookup"><span data-stu-id="8cc84-119">Creating a new dial plan will also create a Default Mailbox Policy.</span></span> 
  
<span data-ttu-id="8cc84-120">建立及設定新的撥號方案之後, 您必須將新的撥號方案新增至您的統一訊息伺服器, 然後修改該伺服器的啟動模式。特別是, 您必須將 [啟動模式] 設定為 "雙"。</span><span class="sxs-lookup"><span data-stu-id="8cc84-120">After creating and configuring the new dial plan you must add the new dial plan to your unified messaging server and then modify the startup mode of that server; in particular, you must set the startup mode to "Dual".</span></span> <span data-ttu-id="8cc84-121">您可以從 Exchange 管理命令介面內執行這兩項工作:</span><span class="sxs-lookup"><span data-stu-id="8cc84-121">You can perform both of these tasks from within the Exchange Management Shell:</span></span>
  
```
Set-UmService -Identity "atl-exchangeum-001.litwareinc.com" -DialPlans "RedmondDialPlan" -UMStartupMode "Dual"
```

<span data-ttu-id="8cc84-122">在已設定統一訊息伺服器之後, 您必須接著執行 ExchangeCertificate Cmdlet, 以確保您的 Exchange 憑證已套用到整合訊息服務:</span><span class="sxs-lookup"><span data-stu-id="8cc84-122">After the unified messaging server has been configured you should next run the Enable-ExchangeCertificate cmdlet to ensure that your Exchange certificate is applied to the unified messaging service:</span></span>
  
```
Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "EA5A332496CC05DA69B75B66111C0F78A110D22d" -Services "SMTP","IIS","UM"
```

<span data-ttu-id="8cc84-123">在正確指派憑證之後, 您必須停止並重新啟動統一訊息伺服器上的 MsExchangeUM 服務。</span><span class="sxs-lookup"><span data-stu-id="8cc84-123">After the certificate has been correctly assigned you must then stop and restart the MsExchangeUM service on the unified messaging server.</span></span> <span data-ttu-id="8cc84-124">每當您變更啟動模式時, 都必須停止並重新啟動此服務。</span><span class="sxs-lookup"><span data-stu-id="8cc84-124">This service must be stopped and restarted any time you change the startup mode.</span></span>
  
<span data-ttu-id="8cc84-125">完成整合郵件伺服器的設定之後, 您就可以設定 UM 呼叫路由器:</span><span class="sxs-lookup"><span data-stu-id="8cc84-125">After finishing configuration of the unified messaging server you can then configure the UM Call Router:</span></span>
  
```
Set-UMCallRouterSettings -Server "atl-exchange-001.litwareinc.com" -UMStartupMode "Dual" -DialPlans "RedmondDialPlan" 
Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "45BAA32496CC891169B75B9811320F78A1075DDA" -Services "IIS","UMCallRouter"
```

<span data-ttu-id="8cc84-126">因為啟動模式已變更, 所以您必須停止並重新啟動託管 UM 呼叫路由器的電腦上的 MsExchangeUMCR 服務。</span><span class="sxs-lookup"><span data-stu-id="8cc84-126">Because the startup mode has changed you must stop and restart the MsExchangeUMCR service on the computer hosting the UM Call Router.</span></span>
  
<span data-ttu-id="8cc84-127">若要完成統一訊息設定, 您必須建立 UM 信箱原則, 然後使用該原則來允許使用者使用整合訊息。</span><span class="sxs-lookup"><span data-stu-id="8cc84-127">To complete the unified messaging setup, you then need to create a UM mailbox policy and then use that policy to enable users for unified messaging.</span></span> <span data-ttu-id="8cc84-128">您可以使用類似以下的命令來建立信箱原則:</span><span class="sxs-lookup"><span data-stu-id="8cc84-128">You can create a mailbox policy by using a command similar to this:</span></span>
  
```
New-UMMailboxPolicy -Name "RedmondMailboxPolicy" -AllowedInCountryOrRegionGroups "Anywhere"
```

<span data-ttu-id="8cc84-129">而且, 您可以使用類似以下的命令, 讓使用者能夠使用整合訊息:</span><span class="sxs-lookup"><span data-stu-id="8cc84-129">And you can enable a user for unified messaging by using a command similar to this:</span></span>
  
```
Enable-UMMailbox -Extensions 100 -SIPResourceIdentifier "kenmyer@litwareinc.com" -Identity "litwareinc\kenmyer" -UMMailboxPolicy "RedmondMailboxPolicy"
```

<span data-ttu-id="8cc84-130">在上述命令中, Extensions 參數代表使用者的電話分機號碼。</span><span class="sxs-lookup"><span data-stu-id="8cc84-130">In the preceding command, the Extensions parameter represents the telephone extension number for the user.</span></span> <span data-ttu-id="8cc84-131">在這個範例中, 使用者的分機號碼是100。</span><span class="sxs-lookup"><span data-stu-id="8cc84-131">In this example, the user has the extension number 100.</span></span>
  
<span data-ttu-id="8cc84-132">在您啟用自己的信箱之後, 使用者 kenmyer@litwareinc.com 應該能夠使用 Exchange 整合訊息。</span><span class="sxs-lookup"><span data-stu-id="8cc84-132">After you have enabled his mailbox, the user kenmyer@litwareinc.com should be able to use Exchange unified messaging.</span></span> <span data-ttu-id="8cc84-133">您可以從商務用 Skype Server Management Shell 中執行[Test CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/test-csexumconnectivity?view=skype-ps) Cmdlet, 以確認使用者可以連線到 Exchange UM:</span><span class="sxs-lookup"><span data-stu-id="8cc84-133">You can verify that the user can connect to Exchange UM by running the [Test-CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/test-csexumconnectivity?view=skype-ps) cmdlet from within the Skype for Business Server Management Shell:</span></span>
  
```
$credential = Get-Credential "litwareinc\kenmyer"
Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential
```

<span data-ttu-id="8cc84-134">如果您有另一個已啟用整合訊息的使用者, 您可以使用[CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/test-csexumvoicemail?view=skype-ps) Cmdlet, 確認此第二位使用者可以為第一個使用者留下語音信箱訊息。</span><span class="sxs-lookup"><span data-stu-id="8cc84-134">If you have a second user who has been enabled for unified messaging you can use the [Test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/test-csexumvoicemail?view=skype-ps) cmdlet to verify that this second user can leave a voicemail message for the first user.</span></span>
  
```
$credential = Get-Credential "litwareinc\pilar"
Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential
```



## <a name="configuring-unified-messaging-on-microsoft-exchange-server"></a><span data-ttu-id="8cc84-135">在 Microsoft Exchange Server 上設定整合通訊</span><span class="sxs-lookup"><span data-stu-id="8cc84-135">Configuring Unified Messaging on Microsoft Exchange Server</span></span> 
> [!IMPORTANT]
> <span data-ttu-id="8cc84-136">如果您想要使用 Exchange 整合訊息 (UM) 來提供呼叫應答、Outlook Voice Access 或適用于企業語音使用者的自動助理服務, 請參閱[商務用 Skype 中的 Exchange 整合訊息整合規劃](../../plan-your-deployment/integrate-with-exchange/unified-messaging.md), 然後依照本節中的指示。</span><span class="sxs-lookup"><span data-stu-id="8cc84-136">If you want to use Exchange Unified Messaging (UM) to provide call answering, Outlook Voice Access, or auto-attendant services for Enterprise Voice users, read [Plan for Exchange Unified Messaging integration in Skype for Business](../../plan-your-deployment/integrate-with-exchange/unified-messaging.md), and then follow the instructions in this section.</span></span> 

<span data-ttu-id="8cc84-137">若要設定 Exchange 整合通訊 (UM) 以搭配企業語音使用, 您必須執行下列工作:</span><span class="sxs-lookup"><span data-stu-id="8cc84-137">To configure Exchange Unified Messaging (UM) to work with Enterprise Voice, you’ll need to perform the following tasks:</span></span>

- <span data-ttu-id="8cc84-138">在運行 Exchange 整合通訊 (UM) 服務的伺服器上設定憑證</span><span class="sxs-lookup"><span data-stu-id="8cc84-138">Configure certificates on the server running Exchange Unified Messaging (UM) services</span></span>
  > [!NOTE]
  > <span data-ttu-id="8cc84-139">將所有用戶端存取和信箱伺服器新增到所有 UM SIP URI 撥號方案。</span><span class="sxs-lookup"><span data-stu-id="8cc84-139">Add all Client Access and Mailbox servers to all UM SIP URI dial plans.</span></span> <span data-ttu-id="8cc84-140">如果不是, 傳出通話路由將無法如期運作。</span><span class="sxs-lookup"><span data-stu-id="8cc84-140">If not, outbound call routing won’t work as expected.</span></span> 
- <span data-ttu-id="8cc84-141">視需要建立一個或多個 UM SIP URI 撥號方案, 以及訂閱者的存取電話號碼, 然後建立對應的 L 撥號方案。</span><span class="sxs-lookup"><span data-stu-id="8cc84-141">Create one or more UM SIP URI dial plans, along with the subscriber access phone numbers, as needed, and then create corresponding L dial plans.</span></span>

- <span data-ttu-id="8cc84-142">使用 exchucutil. ps1 腳本來:</span><span class="sxs-lookup"><span data-stu-id="8cc84-142">Use the exchucutil.ps1 script to:</span></span>
    - <span data-ttu-id="8cc84-143">建立 UM IP 閘道。</span><span class="sxs-lookup"><span data-stu-id="8cc84-143">Create UM IP gateways.</span></span>
    - <span data-ttu-id="8cc84-144">建立 UM 查尋群組。</span><span class="sxs-lookup"><span data-stu-id="8cc84-144">Create UM hunt groups.</span></span>
    - <span data-ttu-id="8cc84-145">[授與商務用 Skype 伺服器] 許可權以讀取 UM Active Directory 網域服務物件。</span><span class="sxs-lookup"><span data-stu-id="8cc84-145">Grant Skype for Business Server permission to read UM Active Directory Domain Services objects.</span></span>
- <span data-ttu-id="8cc84-146">建立 UM 自動助理物件。</span><span class="sxs-lookup"><span data-stu-id="8cc84-146">Create a UM auto-attendant object.</span></span>
- <span data-ttu-id="8cc84-147">建立訂閱者存取物件。</span><span class="sxs-lookup"><span data-stu-id="8cc84-147">Create a subscriber access object.</span></span>
- <span data-ttu-id="8cc84-148">為每位使用者建立 SIP URI, 並將使用者與 UM SIP URI 撥號方案產生關聯。</span><span class="sxs-lookup"><span data-stu-id="8cc84-148">Create a SIP URI for each user and associating users with a UM SIP URI dial plan.</span></span>

### <a name="requirements-and-recommendations"></a><span data-ttu-id="8cc84-149">需求與建議</span><span class="sxs-lookup"><span data-stu-id="8cc84-149">Requirements and Recommendations</span></span>

<span data-ttu-id="8cc84-150">在開始之前, 本節中的檔假設您已部署下列 Exchange 角色: 用戶端存取和信箱。</span><span class="sxs-lookup"><span data-stu-id="8cc84-150">Before you begin, the documentation in this section assumes that you have deployed the following Exchange roles: Client Access and Mailbox.</span></span> <span data-ttu-id="8cc84-151">在 Microsoft Exchange Server 中, Exchange UM 在這些伺服器上以服務的方式執行。</span><span class="sxs-lookup"><span data-stu-id="8cc84-151">In Microsoft Exchange Server, Exchange UM runs as a service on these servers.</span></span>

<span data-ttu-id="8cc84-152">另請注意下列事項:</span><span class="sxs-lookup"><span data-stu-id="8cc84-152">Also note the following:</span></span>
- <span data-ttu-id="8cc84-153">如果 Exchange UM 安裝在多個目錄林中, 則必須針對每個 UM 林執行 Exchange Server 整合步驟。</span><span class="sxs-lookup"><span data-stu-id="8cc84-153">If Exchange UM is installed in multiple forests, the Exchange Server integration steps must be performed for each UM forest.</span></span> <span data-ttu-id="8cc84-154">此外, 每個 UM 目錄林都必須設定為信任在其中部署商務用 Skype 伺服器的林, 而商務用 whichSkype 中的林必須設定為信任每個 UM 目錄林。</span><span class="sxs-lookup"><span data-stu-id="8cc84-154">In addition, each UM forest must be configured to trust the forest in which Skype for Business Server is deployed, and the forest in whichSkype for Business Server is deployed must be configured to trust each UM forest.</span></span>
- <span data-ttu-id="8cc84-155">整合步驟是在執行整合訊息服務的 Exchange 伺服器角色, 以及在執行商務用 Skype Server 的伺服器上執行。</span><span class="sxs-lookup"><span data-stu-id="8cc84-155">Integration steps are performed on both the Exchange Server roles where Unified Messaging services are running, and on the server running Skype for Business Server.</span></span> <span data-ttu-id="8cc84-156">在執行 Lync Server 2013 整合步驟之前, 您應該執行 Exchange Server 整合訊息整合的步驟。</span><span class="sxs-lookup"><span data-stu-id="8cc84-156">You should perform the Exchange Server Unified Messaging integration steps before you perform the Lync Server 2013 integration steps.</span></span>
  > [!NOTE]
  > <span data-ttu-id="8cc84-157">若要查看要對哪些伺服器以及哪些系統管理員角色執行哪些整合步驟, 請參閱[整合內部部署整合訊息與商務用 Skype 的部署程式概覽](../../plan-your-deployment/integrate-with-exchange/deployment-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="8cc84-157">To see which integration steps are performed on which servers and by which administrator roles, see  [Deployment process overview for integrating on-premises Unified Messaging and Skype for Business](../../plan-your-deployment/integrate-with-exchange/deployment-overview.md).</span></span> 

<span data-ttu-id="8cc84-158">在執行 Exchange UM 的每個伺服器上, 都必須提供下列工具:</span><span class="sxs-lookup"><span data-stu-id="8cc84-158">The following tools must be available on each server running Exchange UM:</span></span>
- <span data-ttu-id="8cc84-159">Exchange 管理命令介面</span><span class="sxs-lookup"><span data-stu-id="8cc84-159">Exchange Management Shell</span></span>
- <span data-ttu-id="8cc84-160">腳本 exchucutil. ps1, 可執行下列任務:</span><span class="sxs-lookup"><span data-stu-id="8cc84-160">The script exchucutil.ps1, which performs the following tasks:</span></span>
    - <span data-ttu-id="8cc84-161">針對每個商務用 Skype 伺服器建立 UM IP 閘道。</span><span class="sxs-lookup"><span data-stu-id="8cc84-161">Creates a UM IP gateway for each Skype for Business Server.</span></span>
    - <span data-ttu-id="8cc84-162">為每個閘道建立一個 [查尋] 群組。</span><span class="sxs-lookup"><span data-stu-id="8cc84-162">Creates a hunt group for each gateway.</span></span> <span data-ttu-id="8cc84-163">每個查尋群組的先導識別碼, 會指定與閘道相關聯的前端池或標準版伺服器所使用的 UM SIP URI 撥號方案。</span><span class="sxs-lookup"><span data-stu-id="8cc84-163">The pilot identifier of each hunt group specifies the UM SIP URI dial plan used by the Front End pool or Standard Edition server that is associated with the gateway.</span></span>
    - <span data-ttu-id="8cc84-164">在 Active Directory 網域服務中, 授與商務用 Skype 伺服器的許可權, 以讀取 Exchange UM 物件。</span><span class="sxs-lookup"><span data-stu-id="8cc84-164">Grants Skype for Business Server permission to read Exchange UM objects in Active Directory Domain Services.</span></span>



### <a name="configure-unified-messaging-on-microsoft-exchange-with-exchucutilps1"></a><span data-ttu-id="8cc84-165">使用 ExchUCUtil 在 Microsoft Exchange 上設定整合通訊</span><span class="sxs-lookup"><span data-stu-id="8cc84-165">Configure Unified Messaging on Microsoft Exchange with ExchUCUtil.ps1</span></span> 

<span data-ttu-id="8cc84-166">當您將 Microsoft 商務用 Skype Server 與 Exchange 整合通訊 (UM) 整合在一起, 您必須在 Shell 中執行 ExchUcUtil 腳本。</span><span class="sxs-lookup"><span data-stu-id="8cc84-166">When you’re integrating Microsoft Skype for Business Server with Exchange Unified Messaging (UM), you have to run the ExchUcUtil.ps1 script in the Shell.</span></span> <span data-ttu-id="8cc84-167">ExchUcUtil. ps1 腳本會執行下列動作:</span><span class="sxs-lookup"><span data-stu-id="8cc84-167">The ExchUcUtil.ps1 script does the following:</span></span>

- <span data-ttu-id="8cc84-168">針對每個商務用 Skype 伺服器池建立 UM IP 閘道。</span><span class="sxs-lookup"><span data-stu-id="8cc84-168">Creates a UM IP gateway for each Skype for Business Server pool.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8cc84-169">ExchUcUtil. ps1 腳本會建立一個或多個 UM IP 閘道。</span><span class="sxs-lookup"><span data-stu-id="8cc84-169">The ExchUcUtil.ps1 script creates one or more UM IP gateways.</span></span> <span data-ttu-id="8cc84-170">您必須在所有 UM IP 閘道上停用撥出電話, 除了該腳本建立的一個閘道外。</span><span class="sxs-lookup"><span data-stu-id="8cc84-170">You must disable outgoing calls on all UM IP gateways except one gateway that the script created.</span></span> <span data-ttu-id="8cc84-171">這包括在執行腳本前, 在已建立的 UM IP 閘道上停用撥出通話。</span><span class="sxs-lookup"><span data-stu-id="8cc84-171">This includes disabling outgoing calls on UM IP gateways that were created before you ran the script.</span></span> 

- <span data-ttu-id="8cc84-172">針對每個 UM IP 閘道建立 UM 查尋群組。</span><span class="sxs-lookup"><span data-stu-id="8cc84-172">Creates a UM hunt group for each UM IP gateway.</span></span> <span data-ttu-id="8cc84-173">每個查尋群組的試驗識別碼, 會指定與 UM IP 閘道相關的商務用 Skype Server 前端池或標準版伺服器所使用的 UM SIP URI 撥號方案。</span><span class="sxs-lookup"><span data-stu-id="8cc84-173">The pilot identifier of each hunt group specifies the UM SIP URI dial plan used by the Skype for Business Server Front End pool or Standard Edition server that’s associated with the UM IP gateway.</span></span>
- <span data-ttu-id="8cc84-174">授與商務用 Skype 伺服器的許可權, 以讀取 Active Directory UM 容器物件 (例如 UM 撥號方案、自動語音應答、UM IP 閘道及 UM 查尋群組)。</span><span class="sxs-lookup"><span data-stu-id="8cc84-174">Grants Skype for Business Server permission to read Active Directory UM container objects such as UM dial plans, auto attendants, UM IP gateways, and UM hunt groups.</span></span>
  > [!IMPORTANT]
  > <span data-ttu-id="8cc84-175">每個 UM 林都必須設定為信任部署商務用 Skype Server 的林, 以及部署商務用 Skype Server 2013 的林必須設定為信任每個 UM 目錄林。</span><span class="sxs-lookup"><span data-stu-id="8cc84-175">Each UM forest must be configured to trust the forest in which Skype for Business Server is deployed, and the forest in which Skype for Business Server 2013 is deployed must be configured to trust each UM forest.</span></span> <span data-ttu-id="8cc84-176">如果 Exchange UM 是安裝在多個目錄林中, 則必須針對每個 UM 林執行 Exchange Server integration 步驟, 否則您必須指定商務用 Skype Server 網域。</span><span class="sxs-lookup"><span data-stu-id="8cc84-176">If Exchange UM is installed in multiple forests, the Exchange Server integration steps must be performed for each UM forest or you’ll have to specify the Skype for Business Server domain.</span></span> <span data-ttu-id="8cc84-177">例如, ExchUcUtil. ps1 –林: <lync-網域-控制器-fqdn>。</span><span class="sxs-lookup"><span data-stu-id="8cc84-177">For example, ExchUcUtil.ps1 –Forest:<lync-domain-controller-fqdn>.</span></span> 

### <a name="use-the-shell-to-run-the-exchucutilps1-script"></a><span data-ttu-id="8cc84-178">使用 Shell 執行 ExchUcUtil. ps1 腳本</span><span class="sxs-lookup"><span data-stu-id="8cc84-178">Use the Shell to run the ExchUcUtil.ps1 script</span></span>

<span data-ttu-id="8cc84-179">在貴組織中的任何 Exchange 伺服器上執行 ExchUcUtil 腳本, 這些伺服器與商務用 Skype Server 在相同的拓撲中。</span><span class="sxs-lookup"><span data-stu-id="8cc84-179">Run the ExchUcUtil.ps1 script on any Exchange server in your organization that’s in the same topology as Skype for Business Server.</span></span> <span data-ttu-id="8cc84-180">您可以使用 Shell 從信箱伺服器執行腳本, 或者您可以在用戶端存取伺服器上使用遠端 Windows PowerShell 來執行腳本。</span><span class="sxs-lookup"><span data-stu-id="8cc84-180">You can run the script from a Mailbox server using the Shell or you can run the script using Remote Windows PowerShell on a Client Access server.</span></span> <span data-ttu-id="8cc84-181">如果您在組織中的用戶端存取伺服器上執行腳本, 用戶端存取伺服器會將遠端 Windows PowerShell 會話 proxy 給組織中的信箱伺服器。</span><span class="sxs-lookup"><span data-stu-id="8cc84-181">If you run the script on a Client Access server in your organization, the Client Access server will proxy the Remote Windows PowerShell session to a Mailbox server in the organization.</span></span>
> [!IMPORTANT]
> <span data-ttu-id="8cc84-182">ExchUcUtil. ps1 腳本會建立一個或多個 UM IP 閘道。</span><span class="sxs-lookup"><span data-stu-id="8cc84-182">The ExchUcUtil.ps1 script creates one or more UM IP gateways.</span></span> <span data-ttu-id="8cc84-183">您必須在所有 UM IP 閘道上停用撥出電話, 除了該腳本建立的一個閘道外。</span><span class="sxs-lookup"><span data-stu-id="8cc84-183">You must disable outgoing calls on all UM IP gateways except one gateway that the script created.</span></span> <span data-ttu-id="8cc84-184">這包括在執行腳本前, 在已建立的 UM IP 閘道上停用撥出通話。</span><span class="sxs-lookup"><span data-stu-id="8cc84-184">This includes disabling outgoing calls on UM IP gateways that were created before you ran the script.</span></span> <span data-ttu-id="8cc84-185">若要在 UM IP 閘道停用撥出電話, 請參閱在 UM IP 閘道停用撥出電話。</span><span class="sxs-lookup"><span data-stu-id="8cc84-185">To disable outgoing calls on a UM IP gateway, see Disable outgoing calls on UM IP gateways.</span></span> 
> [!IMPORTANT]
> <span data-ttu-id="8cc84-186">您必須具備 Exchange 組織管理角色的許可權, 或是 Exchange 組織管理員安全性群組的成員, 才能執行腳本。</span><span class="sxs-lookup"><span data-stu-id="8cc84-186">You must have the permissions of the Exchange Organization Management role or be a member of the Exchange Organization Administrators security group to run the script.</span></span> 

1. <span data-ttu-id="8cc84-187">開啟 Exchange 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="8cc84-187">Open the Exchange Management Shell.</span></span>
2. <span data-ttu-id="8cc84-188">在 C:\Windows\System32 提示字元中,**輸入\<cd drive 字母>: \Program Files\Microsoft\Exchange Server\V15\Scripts>。ExchUcUtil......**.... ps1, 然後按 enter。</span><span class="sxs-lookup"><span data-stu-id="8cc84-188">At the C:\Windows\System32 prompt, type **cd \<drive letter>:\Program Files\Microsoft\Exchange Server\V15\Scripts>.ExchUcUtil.ps1**, and then press Enter.</span></span>

#### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="8cc84-189">如何知道這是正常運作的？</span><span class="sxs-lookup"><span data-stu-id="8cc84-189">How do you know this worked?</span></span>

<span data-ttu-id="8cc84-190">若要確認 ExchUcUtul 腳本已順利完成, 請執行下列動作:</span><span class="sxs-lookup"><span data-stu-id="8cc84-190">To verify that the ExchUcUtul.ps1 script completed successfully, do the following:</span></span>
- <span data-ttu-id="8cc84-191">使用 UMIPGateway Cmdlet 或 EAC 來查看已建立的新 UM IP 閘道或閘道。</span><span class="sxs-lookup"><span data-stu-id="8cc84-191">Use the Get-UMIPGateway cmdlet or the EAC to view the new UM IP gateway or gateways that were created.</span></span>
- <span data-ttu-id="8cc84-192">使用 UMHuntGroup Cmdlet 或 EAC 來查看新的 UM 查尋群組或已建立的群組。</span><span class="sxs-lookup"><span data-stu-id="8cc84-192">Use the Get-UMHuntGroup cmdlet or the EAC to view the new UM hunt group or groups that were created.</span></span>

### <a name="configure-certificates-on-the-server-running-exchange-server-unified-messaging"></a><span data-ttu-id="8cc84-193">在運行 Exchange Server 整合通訊的伺服器上設定憑證</span><span class="sxs-lookup"><span data-stu-id="8cc84-193">Configure certificates on the server running Exchange Server Unified Messaging</span></span>
 
<span data-ttu-id="8cc84-194">如果您已部署 Exchange 整合訊息 (UM), 請參閱規劃檔中的商務用 Skype Server 中的 Exchange 整合訊息整合規劃中所述, 而且您想要在您的電腦中為企業語音使用者提供 Exchange UM 功能組織中, 您可以使用下列程式來設定執行 Exchange UM 之伺服器上的憑證。</span><span class="sxs-lookup"><span data-stu-id="8cc84-194">If you have deployed Exchange Unified Messaging (UM), as described in Planning for Exchange Unified Messaging integration in Skype for Business Server in the Planning documentation, and you want to provide Exchange UM features to Enterprise Voice users in your organization, you can use the following procedures to configure the certificate on the server running Exchange UM.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8cc84-195">對於內部憑證, 執行商務用 Skype 伺服器的伺服器以及執行 Microsoft Exchange 的伺服器, 都必須有受信任的根授權憑證 (相互信任)。</span><span class="sxs-lookup"><span data-stu-id="8cc84-195">For internal certificates, both the servers running Skype for Business Server and the servers running Microsoft Exchange must have trusted root authority certificates that are mutually trusted.</span></span> <span data-ttu-id="8cc84-196">只要伺服器已在其受信任的根授權憑證存放區中註冊認證機構的根憑證, 憑證授權單位 (CA) 就可以是相同或不同的憑證授權單位。</span><span class="sxs-lookup"><span data-stu-id="8cc84-196">The certification authority (CA) can either be the same, or a different certification authority, as long as the servers have the certification authority’s root certificate registered in their trusted root authority certificate store.</span></span> 

<span data-ttu-id="8cc84-197">Exchange 伺服器必須使用伺服器憑證進行設定, 才能連線至商務用 Skype Server:</span><span class="sxs-lookup"><span data-stu-id="8cc84-197">The Exchange Server must be configured with a server certificate in order to connect to Skype for Business Server:</span></span>
1. <span data-ttu-id="8cc84-198">下載 Exchange 伺服器的 CA 憑證。</span><span class="sxs-lookup"><span data-stu-id="8cc84-198">Download the CA certificate for the Exchange Server.</span></span>
2. <span data-ttu-id="8cc84-199">安裝 Exchange 伺服器的 CA 憑證。</span><span class="sxs-lookup"><span data-stu-id="8cc84-199">Install the CA certificate for the Exchange Server.</span></span>
3. <span data-ttu-id="8cc84-200">確認 CA 位於 Exchange 伺服器的根信任 Ca 清單中。</span><span class="sxs-lookup"><span data-stu-id="8cc84-200">Verify that the CA is in the list of trusted root CAs of the Exchange Server.</span></span>
4. <span data-ttu-id="8cc84-201">建立 Exchange 伺服器的憑證要求並安裝證書。</span><span class="sxs-lookup"><span data-stu-id="8cc84-201">Create a certificate request for the Exchange Server and install the certificate.</span></span> 
5. <span data-ttu-id="8cc84-202">指派 Exchange 伺服器的憑證。</span><span class="sxs-lookup"><span data-stu-id="8cc84-202">Assign the certificate for the Exchange Server.</span></span>


<span data-ttu-id="8cc84-203">**若要下載 CA 憑證:**</span><span class="sxs-lookup"><span data-stu-id="8cc84-203">**To download the CA certificate:**</span></span>

1. <span data-ttu-id="8cc84-204">在執行 Exchange UM 的伺服器上, 按一下 [**開始**], 按一下 [**執行**], 輸入**您頒發 CA 伺服器的 HTTP://\<名稱>/certsrv**, 然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="8cc84-204">On the server running Exchange UM, click **Start**, click **Run**, type **http://\<name of your Issuing CA Server>/certsrv**, and then click **OK**.</span></span>
2. <span data-ttu-id="8cc84-205">在 [選取任務] 底下, 按一下 [**下載 CA 憑證、憑證鏈或 CRL**]。</span><span class="sxs-lookup"><span data-stu-id="8cc84-205">Under Select a task, click **Download a CA certificate, certificate chain, or CRL**.</span></span>
3. <span data-ttu-id="8cc84-206">在 [**下載 Ca 憑證、憑證連結或 CRL**] 底下, 選取 [**編碼方法至基本 64**], 然後按一下 [**下載 CA 憑證**]。</span><span class="sxs-lookup"><span data-stu-id="8cc84-206">Under **Download a CA Certificate, Certificate Chain, or CRL**, select **Encoding Method to Base 64**, and then click**Download CA certificate**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="8cc84-207">您也可以在此步驟指定可分辨編碼規則 (DER) 編碼。</span><span class="sxs-lookup"><span data-stu-id="8cc84-207">You can also specify Distinguished Encoding Rules (DER) encoding at this step.</span></span> <span data-ttu-id="8cc84-208">如果您選取 [DER 編碼], 此程式的下一個步驟中和**安裝 CA 憑證**的步驟10中的檔案類型是. p7b (而不是 .cer)。</span><span class="sxs-lookup"><span data-stu-id="8cc84-208">If you select DER encoding, the file type in the next step of this procedure and in step 10 of **To Install the CA certificate** is .p7b rather than .cer.</span></span> 
4. <span data-ttu-id="8cc84-209">在 [檔案**下載**] 對話方塊中, 按一下 [**儲存**], 然後將檔案儲存到伺服器上的硬碟。</span><span class="sxs-lookup"><span data-stu-id="8cc84-209">In the **File Download** dialog box, click **Save**, and then save the file to the hard disk on the server.</span></span> <span data-ttu-id="8cc84-210">(根據您在上一個步驟中選取的編碼, 該檔案將會有 .cer 或. p7b 檔案副檔名。)</span><span class="sxs-lookup"><span data-stu-id="8cc84-210">(The file will have either a .cer or a .p7b file extension, depending on the encoding that you selected in the previous step.)</span></span>

<span data-ttu-id="8cc84-211">**若要安裝 CA 憑證:**</span><span class="sxs-lookup"><span data-stu-id="8cc84-211">**To install the CA certificate:**</span></span>

1. <span data-ttu-id="8cc84-212">在執行 Exchange UM 的伺服器上, 按一下 [**開始**], 按一下 [**執行**], 在 [開啟] 方塊中輸入**MMC** , 然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="8cc84-212">On the server running Exchange UM, open Microsoft Management Console (MMC) by clicking **Start**, clicking **Run**, typing **mmc** in the Open box, and then clicking **OK**.</span></span>
2. <span data-ttu-id="8cc84-213">在 [ \*\*\*\* 檔案] 功能表上, 按一下 [**新增/移除管理單元**], 然後按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="8cc84-213">On the **File** menu, click **Add/Remove Snap-in**, and then click **Add**.</span></span>
3. <span data-ttu-id="8cc84-214">在 [**新增獨立的管理單元**] 方塊中, 按一下 [**憑證**], 然後按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="8cc84-214">In the **Add Standalone Snap-ins** box, click **Certificates**, and then click **Add**.</span></span>
4. <span data-ttu-id="8cc84-215">在 [**憑證管理單元**] 對話方塊中, 按一下 [**電腦帳戶**], 然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="8cc84-215">In the **Certificate snap-in** dialog box, click **Computer account**, and then click **Next**.</span></span>
5. <span data-ttu-id="8cc84-216">在 [**選取電腦**] 對話方塊中, 確認已選取 [**本機電腦 (執行此主控台的電腦)** ] 核取方塊, 然後按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="8cc84-216">In the **Select Computer** dialog box, verify that the **Local computer: (the computer this console is running on)** check box is selected, and then click **Finish**.</span></span>
6. <span data-ttu-id="8cc84-217">按一下 [**關閉**], 然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="8cc84-217">Click **Close**, and then click **OK**.</span></span> 
7. <span data-ttu-id="8cc84-218">在主控台樹中, 展開 [**憑證 (本機電腦)**], 展開 [**信任的根憑證授權單位**], 然後按一下 [**憑證**]。</span><span class="sxs-lookup"><span data-stu-id="8cc84-218">In the console tree, expand **Certificates (Local Computer)**, expand **Trusted Root Certification Authorities**, and then click **Certificates**.</span></span>
8. <span data-ttu-id="8cc84-219">以滑鼠右鍵按一下 [**憑證**], 按一下 [**所有任務**], 然後按一下 [匯**入**]。</span><span class="sxs-lookup"><span data-stu-id="8cc84-219">Right-click **Certificates**, click **All Tasks**, and click **Import**.</span></span>
9. <span data-ttu-id="8cc84-220">按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="8cc84-220">Click **Next**.</span></span> 
10. <span data-ttu-id="8cc84-221">按一下 **[流覽]** 找出檔案, 然後按一下 **[下一步**]。</span><span class="sxs-lookup"><span data-stu-id="8cc84-221">Click **Browse** to locate the file, and then click **Next**.</span></span> <span data-ttu-id="8cc84-222">(檔案將會有 .cer 或. p7b 副檔名, 視您在**下載 CA 憑證**的步驟3中所選取的編碼而定。</span><span class="sxs-lookup"><span data-stu-id="8cc84-222">(The file will have either a .cer or a .p7b file extension, depending on the encoding that you selected in step 3 of **To download the CA certificate**.</span></span>
11. <span data-ttu-id="8cc84-223">按一下 [**將所有憑證放**入下列存放區]。</span><span class="sxs-lookup"><span data-stu-id="8cc84-223">Click **Place All Certificates** in the following store.</span></span>
12. <span data-ttu-id="8cc84-224">按一下 **[流覽]**, 然後選取 [**信任的根憑證授權單位**]。</span><span class="sxs-lookup"><span data-stu-id="8cc84-224">Click **Browse**, and then select **Trusted Root Certification Authorities**.</span></span> 
13. <span data-ttu-id="8cc84-225">按一下 **[下一步**] 驗證設定, 然後按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="8cc84-225">Click **Next** to verify the settings, and then click **Finish**.</span></span> 


<span data-ttu-id="8cc84-226">**若要確認 CA 是否在受信任的根 Ca 清單中:**</span><span class="sxs-lookup"><span data-stu-id="8cc84-226">**To verify that the CA is in the list of trusted root CAs:**</span></span>

1. <span data-ttu-id="8cc84-227">在執行 Exchange UM 的伺服器上, 在 MMC 中展開 [憑證 (本機電腦)], 展開 [信任的根憑證授權單位], 然後按一下 [憑證]。</span><span class="sxs-lookup"><span data-stu-id="8cc84-227">On the server running Exchange UM, in MMC expand Certificates (Local Computer), expand Trusted Root Certification Authorities, and then click Certificates.</span></span>
2. <span data-ttu-id="8cc84-228">在 [詳細資料] 窗格中, 確認您的 CA 位於信任的 Ca 清單中。</span><span class="sxs-lookup"><span data-stu-id="8cc84-228">In the details pane, verify that your CA is on the list of trusted CAs.</span></span>


