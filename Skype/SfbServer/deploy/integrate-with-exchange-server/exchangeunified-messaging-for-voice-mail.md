---
title: 為商務用 Skype Server 語音信箱設定 Exchange Server 整合通訊
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/11/2019
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1be9c4f4-fd8e-4d64-9798-f8737b12e2ab
description: 摘要：設定適用于商務用 Skype Server 語音信箱的 Exchange Server 整合通訊。
ms.openlocfilehash: 68cf4a11deccac9ad71bdb6216c4126362787498
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834033"
---
# <a name="configure-exchange-server-unified-messaging-for-skype-for-business-server-voice-mail"></a><span data-ttu-id="c550e-103">為商務用 Skype Server 語音信箱設定 Exchange Server 整合通訊</span><span class="sxs-lookup"><span data-stu-id="c550e-103">Configure Exchange Server Unified Messaging for Skype for Business Server voice mail</span></span>
 
<span data-ttu-id="c550e-104">**摘要：** 為商務用 Skype 伺服器語音信箱設定 Exchange Server 整合通訊。</span><span class="sxs-lookup"><span data-stu-id="c550e-104">**Summary:** Configure Exchange Server Unified Messaging for Skype for Business Server voice mail.</span></span>
  
<span data-ttu-id="c550e-105">商務用 Skype Server 可讓您將語音信箱訊息儲存在 Exchange Server 2016 或 Exchange Server 2013 中;這些語音信箱訊息會以電子郵件訊息的方式顯示在使用者的收件匣中。</span><span class="sxs-lookup"><span data-stu-id="c550e-105">Skype for Business Server enables you to have voicemail messages stored in Exchange Server 2016 or Exchange Server 2013; those voicemail messages will then appear as email messages in your users' Inboxes.</span></span> 

> [!NOTE]
> <span data-ttu-id="c550e-106">Exchange 2019 中已不再提供 exchange 整合通訊（如先前所知），但您仍然可以使用電話系統來錄製語音信箱訊息，然後在使用者的 Exchange 信箱中留下記錄。</span><span class="sxs-lookup"><span data-stu-id="c550e-106">Exchange Unified Messaging as previously known is no longer available in Exchange 2019, but you can still use Phone System to record voicemail messages and then leave the recording in a user's Exchange mailbox.</span></span> <span data-ttu-id="c550e-107">如需詳細資訊，請參閱 [Plan Cloud 語音信箱服務](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) 。</span><span class="sxs-lookup"><span data-stu-id="c550e-107">See [Plan Cloud Voicemail service](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) for more information.</span></span>
  
<span data-ttu-id="c550e-108">如果您已在商務用 Skype Server 與 Exchange Server 2016 或 Exchange Server 2013 之間設定伺服器對伺服器驗證，則可以安裝整合通訊。</span><span class="sxs-lookup"><span data-stu-id="c550e-108">If you have already configured server-to-server authentication between Skype for Business Server and Exchange Server 2016 or Exchange Server 2013, then you are ready to setup unified messaging.</span></span> <span data-ttu-id="c550e-109">若要這麼做，您必須先在 Exchange 伺服器上建立並指派新的整合通訊撥號對應表。</span><span class="sxs-lookup"><span data-stu-id="c550e-109">To do so, you must first create and assign a new unified messaging dial plan on your Exchange Server.</span></span> <span data-ttu-id="c550e-110">例如，在 Exchange 管理命令介面中 (執行這兩個命令) 設定 Exchange 的新3位數撥號對應表：</span><span class="sxs-lookup"><span data-stu-id="c550e-110">For example, these two commands (run from within the Exchange Management Shell) configure a new 3-digit dial plan for Exchange:</span></span>
  
```powershell
New-UMDialPlan -Name "RedmondDialPlan" -VoIPSecurity "Secured" -NumberOfDigitsInExtension 3 -URIType "SipName" -CountryOrRegionCode 1
Set-UMDialPlan "RedmondDialPlan" -ConfiguredInCountryOrRegionGroups "Anywhere,*,*,*" -AllowedInCountryOrRegionGroups "Anywhere"
```

<span data-ttu-id="c550e-111">在範例中的第一個命令中，VoIPSecurity 參數和參數值「安全」表示使用傳輸層安全性 (TLS) 加密信號通道。</span><span class="sxs-lookup"><span data-stu-id="c550e-111">In the first command in the example, the VoIPSecurity parameter, and the parameter value "Secured" indicates that the signaling channel is encrypted by using Transport Layer Security (TLS).</span></span> <span data-ttu-id="c550e-112">URIType "SipName" 指出會使用 SIP 通訊協定來傳送和接收訊息，而 CountryOrRegionCode 的 1 則指出撥號對應表是套用至美國。</span><span class="sxs-lookup"><span data-stu-id="c550e-112">The URIType "SipName" indicates that messages will be sent and received using the SIP protocol, and the CountryOrRegionCode of 1 indicates that the dial plan applies to the US.</span></span>
  
<span data-ttu-id="c550e-113">在第二個命令中，傳送至 ConfiguredInCountryOrRegionGroups 參數的參數值指定了可使用此撥號對應表的的國內群組。</span><span class="sxs-lookup"><span data-stu-id="c550e-113">In the second command, the parameter value passed to the ConfiguredInCountryOrRegionGroups parameter specifies the in-country groups that can be used with this dial plan.</span></span> <span data-ttu-id="c550e-114">參數值 "Anywhere，， \* \* \* " 設定下列專案：</span><span class="sxs-lookup"><span data-stu-id="c550e-114">The parameter value "Anywhere,\*,\*,\*" sets the following:</span></span>
  
- <span data-ttu-id="c550e-115">群組名稱 ("Anywhere")</span><span class="sxs-lookup"><span data-stu-id="c550e-115">Group name ("Anywhere")</span></span>
    
- <span data-ttu-id="c550e-116">AllowedNumberString (\* ，表示允許任何數位字串的萬用字元) </span><span class="sxs-lookup"><span data-stu-id="c550e-116">AllowedNumberString (\*, a wildcard character indicating that any number string is allowed)</span></span>
    
- <span data-ttu-id="c550e-117">DialNumberString (\* ，表示允許任何撥入號碼的通配字元) </span><span class="sxs-lookup"><span data-stu-id="c550e-117">DialNumberString (\*, a wildcard character indicating that any dialed number is allowed)</span></span>
    
- <span data-ttu-id="c550e-118">TextComment (\* ，表示允許任何文字命令的萬用字元) </span><span class="sxs-lookup"><span data-stu-id="c550e-118">TextComment (\*, a wildcard character indicating that any text command is allowed)</span></span>
    
> [!NOTE]
> <span data-ttu-id="c550e-119">建立新的撥號對應表也會建立預設信箱原則。</span><span class="sxs-lookup"><span data-stu-id="c550e-119">Creating a new dial plan will also create a Default Mailbox Policy.</span></span> 
  
<span data-ttu-id="c550e-120">建立並設定新的撥號對應表之後，您必須將新的撥號對應表新增至整合通訊伺服器，然後修改該伺服器的啟動模式；明確地說，您必須將啟動模式設定為「雙重」模式。</span><span class="sxs-lookup"><span data-stu-id="c550e-120">After creating and configuring the new dial plan you must add the new dial plan to your unified messaging server and then modify the startup mode of that server; in particular, you must set the startup mode to "Dual".</span></span> <span data-ttu-id="c550e-121">您可以在 Exchange 管理命令介面內執行下列兩項工作：</span><span class="sxs-lookup"><span data-stu-id="c550e-121">You can perform both of these tasks from within the Exchange Management Shell:</span></span>
  
```powershell
Set-UmService -Identity "atl-exchangeum-001.litwareinc.com" -DialPlans "RedmondDialPlan" -UMStartupMode "Dual"
```

<span data-ttu-id="c550e-122">設定整合通訊伺服器之後，您應該接下來執行 Enable-ExchangeCertificate Cmdlet，以確保您的 Exchange 憑證已套用至整合通訊服務：</span><span class="sxs-lookup"><span data-stu-id="c550e-122">After the unified messaging server has been configured you should next run the Enable-ExchangeCertificate cmdlet to ensure that your Exchange certificate is applied to the unified messaging service:</span></span>
  
```powershell
Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "EA5A332496CC05DA69B75B66111C0F78A110D22d" -Services "SMTP","IIS","UM"
```

<span data-ttu-id="c550e-p106">正確指派憑證之後，您就必須停止並重新啟動整合通訊伺服器上的 MsExchangeUM 服務。每當您變更啟動模式時，都必須停止並重新啟動此服務。</span><span class="sxs-lookup"><span data-stu-id="c550e-p106">After the certificate has been correctly assigned you must then stop and restart the MsExchangeUM service on the unified messaging server. This service must be stopped and restarted any time you change the startup mode.</span></span>
  
<span data-ttu-id="c550e-125">完成整合通訊伺服器的設定之後，您就可以開始設定 UM 通話路由器：</span><span class="sxs-lookup"><span data-stu-id="c550e-125">After finishing configuration of the unified messaging server you can then configure the UM Call Router:</span></span>
  
```powershell
Set-UMCallRouterSettings -Server "atl-exchange-001.litwareinc.com" -UMStartupMode "Dual" -DialPlans "RedmondDialPlan" 
Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "45BAA32496CC891169B75B9811320F78A1075DDA" -Services "IIS","UMCallRouter"
```

<span data-ttu-id="c550e-126">由於啟動模式已變更，因此您必須停止並重新啟動主控 UM 通話路由器之電腦上的 MsExchangeUMCR 服務。</span><span class="sxs-lookup"><span data-stu-id="c550e-126">Because the startup mode has changed you must stop and restart the MsExchangeUMCR service on the computer hosting the UM Call Router.</span></span>
  
<span data-ttu-id="c550e-p107">若要完成整合通訊設定，您還需要建立 UM 信箱原則，然後使用該原則來啟用使用者的整合通訊。您可使用類似下列的命令，來建立信箱原則：</span><span class="sxs-lookup"><span data-stu-id="c550e-p107">To complete the unified messaging setup, you then need to create a UM mailbox policy and then use that policy to enable users for unified messaging. You can create a mailbox policy by using a command similar to this:</span></span>
  
```powershell
New-UMMailboxPolicy -Name "RedmondMailboxPolicy" -AllowedInCountryOrRegionGroups "Anywhere"
```

<span data-ttu-id="c550e-129">您可使用類似下列的命令，來啟用使用者的整合通訊：</span><span class="sxs-lookup"><span data-stu-id="c550e-129">And you can enable a user for unified messaging by using a command similar to this:</span></span>
  
```powershell
Enable-UMMailbox -Extensions 100 -SIPResourceIdentifier "kenmyer@litwareinc.com" -Identity "litwareinc\kenmyer" -UMMailboxPolicy "RedmondMailboxPolicy"
```

<span data-ttu-id="c550e-p108">在上一個命令中，Extensions 參數代表使用者的電話分機號碼。在此範例中，使用者的分機號碼為 100。</span><span class="sxs-lookup"><span data-stu-id="c550e-p108">In the preceding command, the Extensions parameter represents the telephone extension number for the user. In this example, the user has the extension number 100.</span></span>
  
<span data-ttu-id="c550e-132">啟用 kenmyer@litwareinc.com 的信箱後，該使用者應該就能使用 Exchange 整合通訊。</span><span class="sxs-lookup"><span data-stu-id="c550e-132">After you have enabled his mailbox, the user kenmyer@litwareinc.com should be able to use Exchange unified messaging.</span></span> <span data-ttu-id="c550e-133">您可以從商務用 Skype Server 管理命令介面中執行 [Test-CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/test-csexumconnectivity?view=skype-ps) Cmdlet，以確認使用者可以連線至 Exchange UM：</span><span class="sxs-lookup"><span data-stu-id="c550e-133">You can verify that the user can connect to Exchange UM by running the [Test-CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/test-csexumconnectivity?view=skype-ps) cmdlet from within the Skype for Business Server Management Shell:</span></span>
  
```powershell
$credential = Get-Credential "litwareinc\kenmyer"
Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential
```

<span data-ttu-id="c550e-134">若您還有第二個啟用了整合通訊的使用者，您可使用 [Test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/test-csexumvoicemail?view=skype-ps) Cmdlet 來驗證第二個使用者是否能語音留言給第一個使用者。</span><span class="sxs-lookup"><span data-stu-id="c550e-134">If you have a second user who has been enabled for unified messaging you can use the [Test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/test-csexumvoicemail?view=skype-ps) cmdlet to verify that this second user can leave a voicemail message for the first user.</span></span>
  
```powershell
$credential = Get-Credential "litwareinc\pilar"
Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential
```



## <a name="configuring-unified-messaging-on-microsoft-exchange-server"></a><span data-ttu-id="c550e-135">在 Microsoft Exchange Server 上設定整合通訊</span><span class="sxs-lookup"><span data-stu-id="c550e-135">Configuring Unified Messaging on Microsoft Exchange Server</span></span> 
> [!IMPORTANT]
> <span data-ttu-id="c550e-136">如果您想要使用 Exchange 整合通訊 (UM) 提供適用于 Enterprise Voice 使用者的呼叫回應、Outlook Voice Access 或自動語音應答服務，請參閱 [商務用 Skype 中的 Exchange 整合通訊整合對應](../../plan-your-deployment/integrate-with-exchange/unified-messaging.md)，然後依照本節中的指示進行。</span><span class="sxs-lookup"><span data-stu-id="c550e-136">If you want to use Exchange Unified Messaging (UM) to provide call answering, Outlook Voice Access, or auto-attendant services for Enterprise Voice users, read [Plan for Exchange Unified Messaging integration in Skype for Business](../../plan-your-deployment/integrate-with-exchange/unified-messaging.md), and then follow the instructions in this section.</span></span> 

<span data-ttu-id="c550e-137">若要設定 Exchange 整合通訊 (UM) 以使用 Enterprise Voice，您必須執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="c550e-137">To configure Exchange Unified Messaging (UM) to work with Enterprise Voice, you’ll need to perform the following tasks:</span></span>

- <span data-ttu-id="c550e-138">在執行 Exchange 整合通訊 (UM) 服務的伺服器上設定憑證</span><span class="sxs-lookup"><span data-stu-id="c550e-138">Configure certificates on the server running Exchange Unified Messaging (UM) services</span></span>
  > [!NOTE]
  > <span data-ttu-id="c550e-139">將所有用戶端存取和信箱伺服器新增至所有 UM SIP URI 撥號對應表。</span><span class="sxs-lookup"><span data-stu-id="c550e-139">Add all Client Access and Mailbox servers to all UM SIP URI dial plans.</span></span> <span data-ttu-id="c550e-140">如果不是，則輸出通話路由不會如預期般運作。</span><span class="sxs-lookup"><span data-stu-id="c550e-140">If not, outbound call routing won’t work as expected.</span></span> 
- <span data-ttu-id="c550e-141">視需要建立一個或多個 UM SIP URI 撥號對應表，以及訂閱者存取電話號碼，然後建立對應的 L 撥號對應表。</span><span class="sxs-lookup"><span data-stu-id="c550e-141">Create one or more UM SIP URI dial plans, along with the subscriber access phone numbers, as needed, and then create corresponding L dial plans.</span></span>

- <span data-ttu-id="c550e-142">使用 exchucutil.ps1 腳本執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="c550e-142">Use the exchucutil.ps1 script to:</span></span>
    - <span data-ttu-id="c550e-143">建立 UM IP 閘道。</span><span class="sxs-lookup"><span data-stu-id="c550e-143">Create UM IP gateways.</span></span>
    - <span data-ttu-id="c550e-144">建立 UM 群組搜尋。</span><span class="sxs-lookup"><span data-stu-id="c550e-144">Create UM hunt groups.</span></span>
    - <span data-ttu-id="c550e-145">授與商務用 Skype Server 讀取 UM Active Directory 網域服務物件的許可權。</span><span class="sxs-lookup"><span data-stu-id="c550e-145">Grant Skype for Business Server permission to read UM Active Directory Domain Services objects.</span></span>
- <span data-ttu-id="c550e-146">建立 UM 自動語音應答物件。</span><span class="sxs-lookup"><span data-stu-id="c550e-146">Create a UM auto-attendant object.</span></span>
- <span data-ttu-id="c550e-147">建立訂閱者存取物件。</span><span class="sxs-lookup"><span data-stu-id="c550e-147">Create a subscriber access object.</span></span>
- <span data-ttu-id="c550e-148">為每個使用者建立 SIP URI，並將使用者與 UM SIP URI 撥號對應表相關聯。</span><span class="sxs-lookup"><span data-stu-id="c550e-148">Create a SIP URI for each user and associating users with a UM SIP URI dial plan.</span></span>

### <a name="requirements-and-recommendations"></a><span data-ttu-id="c550e-149">需求和建議</span><span class="sxs-lookup"><span data-stu-id="c550e-149">Requirements and Recommendations</span></span>

<span data-ttu-id="c550e-150">在您開始之前，本節中的檔會假設您已部署下列 Exchange 角色： Client Access 和信箱。</span><span class="sxs-lookup"><span data-stu-id="c550e-150">Before you begin, the documentation in this section assumes that you have deployed the following Exchange roles: Client Access and Mailbox.</span></span> <span data-ttu-id="c550e-151">在 Microsoft Exchange Server 中，Exchange UM 會在這些伺服器上以服務的身分執行。</span><span class="sxs-lookup"><span data-stu-id="c550e-151">In Microsoft Exchange Server, Exchange UM runs as a service on these servers.</span></span>

<span data-ttu-id="c550e-152">也請注意以下事項：</span><span class="sxs-lookup"><span data-stu-id="c550e-152">Also note the following:</span></span>
- <span data-ttu-id="c550e-153">如果已在多個樹系中安裝 Exchange UM，則必須針對每個 UM 樹系執行 Exchange Server 整合步驟。</span><span class="sxs-lookup"><span data-stu-id="c550e-153">If Exchange UM is installed in multiple forests, the Exchange Server integration steps must be performed for each UM forest.</span></span> <span data-ttu-id="c550e-154">此外，每個 UM 樹系必須設定為信任部署商務用 Skype 伺服器的樹系，而且部署 whichSkype for Business Server 的樹系必須設定為信任每個 UM 樹系。</span><span class="sxs-lookup"><span data-stu-id="c550e-154">In addition, each UM forest must be configured to trust the forest in which Skype for Business Server is deployed, and the forest in whichSkype for Business Server is deployed must be configured to trust each UM forest.</span></span>
- <span data-ttu-id="c550e-155">在執行整合通訊服務的 Exchange 伺服器角色，以及執行商務用 Skype 伺服器的伺服器上執行整合步驟。</span><span class="sxs-lookup"><span data-stu-id="c550e-155">Integration steps are performed on both the Exchange Server roles where Unified Messaging services are running, and on the server running Skype for Business Server.</span></span> <span data-ttu-id="c550e-156">在您執行 Lync Server 2013 整合步驟之前，您應該先執行 Exchange Server 整合通訊整合步驟。</span><span class="sxs-lookup"><span data-stu-id="c550e-156">You should perform the Exchange Server Unified Messaging integration steps before you perform the Lync Server 2013 integration steps.</span></span>
  > [!NOTE]
  > <span data-ttu-id="c550e-157">若要查看在哪些伺服器及系統管理員角色上執行哪些整合步驟，請參閱  [整合內部部署整合通訊和商務用 Skype 的部署程式概述](../../plan-your-deployment/integrate-with-exchange/deployment-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="c550e-157">To see which integration steps are performed on which servers and by which administrator roles, see  [Deployment process overview for integrating on-premises Unified Messaging and Skype for Business](../../plan-your-deployment/integrate-with-exchange/deployment-overview.md).</span></span> 

<span data-ttu-id="c550e-158">在執行 Exchange UM 的每一部伺服器上都必須提供下列工具：</span><span class="sxs-lookup"><span data-stu-id="c550e-158">The following tools must be available on each server running Exchange UM:</span></span>
- <span data-ttu-id="c550e-159">Exchange 管理命令介面</span><span class="sxs-lookup"><span data-stu-id="c550e-159">Exchange Management Shell</span></span>
- <span data-ttu-id="c550e-160">指令碼 exchucutil.ps1，它會執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="c550e-160">The script exchucutil.ps1, which performs the following tasks:</span></span>
    - <span data-ttu-id="c550e-161">為每個商務用 Skype 伺服器建立 UM IP 閘道。</span><span class="sxs-lookup"><span data-stu-id="c550e-161">Creates a UM IP gateway for each Skype for Business Server.</span></span>
    - <span data-ttu-id="c550e-162">為每一個閘道建立群組搜尋。</span><span class="sxs-lookup"><span data-stu-id="c550e-162">Creates a hunt group for each gateway.</span></span> <span data-ttu-id="c550e-163">每個群組搜尋的引導識別碼會指定與閘道相關聯之前端集區或 Standard Edition server 所使用的 UM SIP URI 撥號對應表。</span><span class="sxs-lookup"><span data-stu-id="c550e-163">The pilot identifier of each hunt group specifies the UM SIP URI dial plan used by the Front End pool or Standard Edition server that is associated with the gateway.</span></span>
    - <span data-ttu-id="c550e-164">授與商務用 Skype Server 許可權，以在 Active Directory 網域服務中讀取 Exchange UM 物件。</span><span class="sxs-lookup"><span data-stu-id="c550e-164">Grants Skype for Business Server permission to read Exchange UM objects in Active Directory Domain Services.</span></span>



### <a name="configure-unified-messaging-on-microsoft-exchange-with-exchucutilps1"></a><span data-ttu-id="c550e-165">在 Microsoft Exchange 上使用 ExchUCUtil.ps1 設定整合通訊</span><span class="sxs-lookup"><span data-stu-id="c550e-165">Configure Unified Messaging on Microsoft Exchange with ExchUCUtil.ps1</span></span> 

<span data-ttu-id="c550e-166">當您將 Microsoft 商務用 Skype Server 與 Exchange 整合通訊 (UM) 整合時，您必須在命令介面中執行 ExchUcUtil.ps1 腳本。</span><span class="sxs-lookup"><span data-stu-id="c550e-166">When you’re integrating Microsoft Skype for Business Server with Exchange Unified Messaging (UM), you have to run the ExchUcUtil.ps1 script in the Shell.</span></span> <span data-ttu-id="c550e-167">ExchUcUtil.ps1 指令碼可執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="c550e-167">The ExchUcUtil.ps1 script does the following:</span></span>

- <span data-ttu-id="c550e-168">為每個商務用 Skype 伺服器集區建立 UM IP 閘道。</span><span class="sxs-lookup"><span data-stu-id="c550e-168">Creates a UM IP gateway for each Skype for Business Server pool.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c550e-169">ExchUcUtil.ps1 指令碼可建立一或多個 UM IP 閘道。</span><span class="sxs-lookup"><span data-stu-id="c550e-169">The ExchUcUtil.ps1 script creates one or more UM IP gateways.</span></span> <span data-ttu-id="c550e-170">您必須在除了指令碼所建立的一個閘道以外的所有 UM IP 閘道上，停用撥出電話。</span><span class="sxs-lookup"><span data-stu-id="c550e-170">You must disable outgoing calls on all UM IP gateways except one gateway that the script created.</span></span> <span data-ttu-id="c550e-171">這包括在已於執行指令碼之前就建立的 UM IP 閘道上，停用撥出電話。</span><span class="sxs-lookup"><span data-stu-id="c550e-171">This includes disabling outgoing calls on UM IP gateways that were created before you ran the script.</span></span> 

- <span data-ttu-id="c550e-172">為每個 UM IP 閘道建立一個 UM 群組搜尋。</span><span class="sxs-lookup"><span data-stu-id="c550e-172">Creates a UM hunt group for each UM IP gateway.</span></span> <span data-ttu-id="c550e-173">每個群組搜尋的引導識別碼會指定與 UM IP 閘道相關聯之商務用 Skype Server 前端集區或 Standard Edition server 所使用的 UM SIP URI 撥號對應表。</span><span class="sxs-lookup"><span data-stu-id="c550e-173">The pilot identifier of each hunt group specifies the UM SIP URI dial plan used by the Skype for Business Server Front End pool or Standard Edition server that’s associated with the UM IP gateway.</span></span>
- <span data-ttu-id="c550e-174">授與商務用 Skype Server 許可權，以閱讀 Active Directory UM 容器物件，例如 UM 撥號對應表、自動語音應答、UM IP 閘道和 UM 群組搜尋。</span><span class="sxs-lookup"><span data-stu-id="c550e-174">Grants Skype for Business Server permission to read Active Directory UM container objects such as UM dial plans, auto attendants, UM IP gateways, and UM hunt groups.</span></span>
  > [!IMPORTANT]
  > <span data-ttu-id="c550e-175">每個 UM 樹系都必須設定為信任部署商務用 Skype 伺服器的樹系，而且部署商務用 Skype Server 2013 的樹系必須設定為信任每個 UM 樹系。</span><span class="sxs-lookup"><span data-stu-id="c550e-175">Each UM forest must be configured to trust the forest in which Skype for Business Server is deployed, and the forest in which Skype for Business Server 2013 is deployed must be configured to trust each UM forest.</span></span> <span data-ttu-id="c550e-176">如果 Exchange UM 已安裝在多個樹系中，則必須針對每個 UM 樹系執行 Exchange Server 整合步驟，否則您必須指定商務用 Skype Server 網域。</span><span class="sxs-lookup"><span data-stu-id="c550e-176">If Exchange UM is installed in multiple forests, the Exchange Server integration steps must be performed for each UM forest or you’ll have to specify the Skype for Business Server domain.</span></span> <span data-ttu-id="c550e-177">例如，ExchUcUtil.ps1 –樹系： <lync 域-controller-fqdn>。</span><span class="sxs-lookup"><span data-stu-id="c550e-177">For example, ExchUcUtil.ps1 –Forest:<lync-domain-controller-fqdn>.</span></span> 

### <a name="use-the-shell-to-run-the-exchucutilps1-script"></a><span data-ttu-id="c550e-178">使用命令介面來執行 ExchUcUtil.ps1 指令碼</span><span class="sxs-lookup"><span data-stu-id="c550e-178">Use the Shell to run the ExchUcUtil.ps1 script</span></span>

<span data-ttu-id="c550e-179">在組織中與商務用 Skype Server 位於相同拓撲的任何 Exchange 伺服器上，執行 ExchUcUtil.ps1 腳本。</span><span class="sxs-lookup"><span data-stu-id="c550e-179">Run the ExchUcUtil.ps1 script on any Exchange server in your organization that’s in the same topology as Skype for Business Server.</span></span> <span data-ttu-id="c550e-180">您可以在 Mailbox Server 中使用命令介面來執行指令碼，或者您可以在 Client Access Server 上使用遠端 Windows PowerShell 來執行指令碼。</span><span class="sxs-lookup"><span data-stu-id="c550e-180">You can run the script from a Mailbox server using the Shell or you can run the script using Remote Windows PowerShell on a Client Access server.</span></span> <span data-ttu-id="c550e-181">如果您在組織中的 Client Access Server 上執行指令碼，則 Client Access Server 會將遠端 Windows PowerShell 工作階段，Proxy 處理至組織中的 Mailbox Server。</span><span class="sxs-lookup"><span data-stu-id="c550e-181">If you run the script on a Client Access server in your organization, the Client Access server will proxy the Remote Windows PowerShell session to a Mailbox server in the organization.</span></span>
> [!IMPORTANT]
> <span data-ttu-id="c550e-182">ExchUcUtil.ps1 指令碼可建立一或多個 UM IP 閘道。</span><span class="sxs-lookup"><span data-stu-id="c550e-182">The ExchUcUtil.ps1 script creates one or more UM IP gateways.</span></span> <span data-ttu-id="c550e-183">您必須在除了指令碼所建立的一個閘道以外的所有 UM IP 閘道上，停用撥出電話。</span><span class="sxs-lookup"><span data-stu-id="c550e-183">You must disable outgoing calls on all UM IP gateways except one gateway that the script created.</span></span> <span data-ttu-id="c550e-184">這包括在已於執行指令碼之前就建立的 UM IP 閘道上，停用撥出電話。</span><span class="sxs-lookup"><span data-stu-id="c550e-184">This includes disabling outgoing calls on UM IP gateways that were created before you ran the script.</span></span> <span data-ttu-id="c550e-185">若要在 UM IP 閘道上停用撥出電話，請參閱停用 UM IP 閘道器上的撥出電話。</span><span class="sxs-lookup"><span data-stu-id="c550e-185">To disable outgoing calls on a UM IP gateway, see Disable outgoing calls on UM IP gateways.</span></span> 
> [!IMPORTANT]
> <span data-ttu-id="c550e-186">您必須具備「Exchange 組織管理」角色的權限或屬於 Exchange Organization Administrators 安全性群組的成員，才能執行此指令碼。</span><span class="sxs-lookup"><span data-stu-id="c550e-186">You must have the permissions of the Exchange Organization Management role or be a member of the Exchange Organization Administrators security group to run the script.</span></span> 

1. <span data-ttu-id="c550e-187">開啟 [Exchange 管理命令介面]。</span><span class="sxs-lookup"><span data-stu-id="c550e-187">Open the Exchange Management Shell.</span></span>
2. <span data-ttu-id="c550e-188">在 C:\Windows\System32 提示字元處，輸入 **cd \<drive letter> ： \Program Files\Microsoft\Exchange Server\V15\Scripts # C0.ExchUcUtil.ps1**，然後按 enter 鍵。</span><span class="sxs-lookup"><span data-stu-id="c550e-188">At the C:\Windows\System32 prompt, type **cd \<drive letter>:\Program Files\Microsoft\Exchange Server\V15\Scripts>.ExchUcUtil.ps1**, and then press Enter.</span></span>

#### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="c550e-189">如何知道這是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="c550e-189">How do you know this worked?</span></span>

<span data-ttu-id="c550e-190">若要確認是否已成功完成 ExchUcUtul.ps1 指令碼，請執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="c550e-190">To verify that the ExchUcUtul.ps1 script completed successfully, do the following:</span></span>
- <span data-ttu-id="c550e-191">使用 Get-UMIPGateway Cmdlet 或 EAC 來檢視所建立的新 UM IP 閘道。</span><span class="sxs-lookup"><span data-stu-id="c550e-191">Use the Get-UMIPGateway cmdlet or the EAC to view the new UM IP gateway or gateways that were created.</span></span>
- <span data-ttu-id="c550e-192">使用 Get-UMHuntGroup Cmdlet 或 EAC 來檢視所建立的新 UM 群組搜尋。</span><span class="sxs-lookup"><span data-stu-id="c550e-192">Use the Get-UMHuntGroup cmdlet or the EAC to view the new UM hunt group or groups that were created.</span></span>

### <a name="configure-certificates-on-the-server-running-exchange-server-unified-messaging"></a><span data-ttu-id="c550e-193">在執行 Exchange Server 整合通訊的伺服器上設定憑證</span><span class="sxs-lookup"><span data-stu-id="c550e-193">Configure certificates on the server running Exchange Server Unified Messaging</span></span>
 
<span data-ttu-id="c550e-194">如果您已部署 Exchange 整合通訊 (UM) （如規劃檔中的「在商務用 Skype Server 中規劃 Exchange 整合通訊整合」一節所述），而且想要將 Exchange UM 功能提供給組織中的 Enterprise Voice 使用者，您可以使用下列程式在執行 Exchange UM 的伺服器上設定憑證。</span><span class="sxs-lookup"><span data-stu-id="c550e-194">If you have deployed Exchange Unified Messaging (UM), as described in Planning for Exchange Unified Messaging integration in Skype for Business Server in the Planning documentation, and you want to provide Exchange UM features to Enterprise Voice users in your organization, you can use the following procedures to configure the certificate on the server running Exchange UM.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c550e-195">針對內部憑證，執行商務用 Skype 伺服器的伺服器和執行 Microsoft Exchange 的伺服器必須具有相互信任的根信任授權憑證。</span><span class="sxs-lookup"><span data-stu-id="c550e-195">For internal certificates, both the servers running Skype for Business Server and the servers running Microsoft Exchange must have trusted root authority certificates that are mutually trusted.</span></span> <span data-ttu-id="c550e-196">憑證授權單位單位 (CA) 可以相同或不同的憑證授權單位單位，只要伺服器在其受信任的根授權憑證存放區中註冊了憑證授權單位的根憑證。</span><span class="sxs-lookup"><span data-stu-id="c550e-196">The certification authority (CA) can either be the same, or a different certification authority, as long as the servers have the certification authority’s root certificate registered in their trusted root authority certificate store.</span></span> 

<span data-ttu-id="c550e-197">必須將 Exchange 伺服器設定為使用伺服器憑證，才能連線至商務用 Skype Server：</span><span class="sxs-lookup"><span data-stu-id="c550e-197">The Exchange Server must be configured with a server certificate in order to connect to Skype for Business Server:</span></span>
1. <span data-ttu-id="c550e-198">下載 Exchange Server 的 CA 憑證。</span><span class="sxs-lookup"><span data-stu-id="c550e-198">Download the CA certificate for the Exchange Server.</span></span>
2. <span data-ttu-id="c550e-199">安裝 Exchange Server 的 CA 憑證。</span><span class="sxs-lookup"><span data-stu-id="c550e-199">Install the CA certificate for the Exchange Server.</span></span>
3. <span data-ttu-id="c550e-200">確認 CA 在 Exchange Server 的受信任的根 CA 清單中。</span><span class="sxs-lookup"><span data-stu-id="c550e-200">Verify that the CA is in the list of trusted root CAs of the Exchange Server.</span></span>
4. <span data-ttu-id="c550e-201">建立 Exchange Server 的憑證要求並安裝憑證。</span><span class="sxs-lookup"><span data-stu-id="c550e-201">Create a certificate request for the Exchange Server and install the certificate.</span></span> 
5. <span data-ttu-id="c550e-202">指派 Exchange Server 的憑證。</span><span class="sxs-lookup"><span data-stu-id="c550e-202">Assign the certificate for the Exchange Server.</span></span>


<span data-ttu-id="c550e-203">**若要下載 CA 憑證：**</span><span class="sxs-lookup"><span data-stu-id="c550e-203">**To download the CA certificate:**</span></span>

1. <span data-ttu-id="c550e-204">在執行 Exchange UM 的伺服器上，按一下 [ **開始**]，按一下 [ **執行**]，輸入 **Http:// \<name of your Issuing CA Server> /Certsrv**，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="c550e-204">On the server running Exchange UM, click **Start**, click **Run**, type **http://\<name of your Issuing CA Server>/certsrv**, and then click **OK**.</span></span>
2. <span data-ttu-id="c550e-205">在 [選取任務] 底下，按一下 [ **下載 CA 憑證、憑證鏈或 CRL**]。</span><span class="sxs-lookup"><span data-stu-id="c550e-205">Under Select a task, click **Download a CA certificate, certificate chain, or CRL**.</span></span>
3. <span data-ttu-id="c550e-206">在 [ **下載 Ca 憑證、憑證鏈或 CRL**] 底下，選取 [ **編碼方式為 64**]，然後按一下 [**下載 CA 憑證**]。</span><span class="sxs-lookup"><span data-stu-id="c550e-206">Under **Download a CA Certificate, Certificate Chain, or CRL**, select **Encoding Method to Base 64**, and then click **Download CA certificate**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="c550e-207">您也可以在此步驟 (DER) 編碼中指定可辨識的編碼規則。</span><span class="sxs-lookup"><span data-stu-id="c550e-207">You can also specify Distinguished Encoding Rules (DER) encoding at this step.</span></span> <span data-ttu-id="c550e-208">如果您選取 DER 編碼，此程序下一個步驟中以及 **「若要安裝 CA 憑證」** 步驟 10 中的檔案類型會是 .p7b，而非 .cer。</span><span class="sxs-lookup"><span data-stu-id="c550e-208">If you select DER encoding, the file type in the next step of this procedure and in step 10 of **To Install the CA certificate** is .p7b rather than .cer.</span></span> 
4. <span data-ttu-id="c550e-p123">在 **[檔案下載]** 對話方塊中，按一下 **[儲存]**，然後將檔案儲存到伺服器的硬碟上 (視您在上一個步驟中選取的編碼而定，檔案的副檔名會是 .cer 或 .p7b)。</span><span class="sxs-lookup"><span data-stu-id="c550e-p123">In the **File Download** dialog box, click **Save**, and then save the file to the hard disk on the server. (The file will have either a .cer or a .p7b file extension, depending on the encoding that you selected in the previous step.)</span></span>

<span data-ttu-id="c550e-211">**若要安裝 CA 憑證：**</span><span class="sxs-lookup"><span data-stu-id="c550e-211">**To install the CA certificate:**</span></span>

1. <span data-ttu-id="c550e-212">在執行 Exchange UM 的伺服器上，按一下 [ **開始**]，按一下 [ **執行**]，然後在 [開啟] 方塊中輸入 **MMC** ，然後按一下 **[確定]**，以開啟 Microsoft Management Console (MMC) 。</span><span class="sxs-lookup"><span data-stu-id="c550e-212">On the server running Exchange UM, open Microsoft Management Console (MMC) by clicking **Start**, clicking **Run**, typing **mmc** in the Open box, and then clicking **OK**.</span></span>
2. <span data-ttu-id="c550e-213">在 **[檔案]** 功能表中，按一下 **[新增/移除嵌入式管理單元]**，然後按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="c550e-213">On the **File** menu, click **Add/Remove Snap-in**, and then click **Add**.</span></span>
3. <span data-ttu-id="c550e-214">在 **[新增獨立嵌入式管理單元]** 方塊中，按一下 **[憑證]**，然後按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="c550e-214">In the **Add Standalone Snap-ins** box, click **Certificates**, and then click **Add**.</span></span>
4. <span data-ttu-id="c550e-215">在 **[憑證嵌入式管理單元]** 對話方塊中，按一下 **[電腦帳戶]**，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="c550e-215">In the **Certificate snap-in** dialog box, click **Computer account**, and then click **Next**.</span></span>
5. <span data-ttu-id="c550e-216">在 [ **選取電腦** ] 對話方塊中，確認已選取 [ **本機電腦： (執行此主控台的電腦)** ] 核取方塊，然後按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="c550e-216">In the **Select Computer** dialog box, verify that the **Local computer: (the computer this console is running on)** check box is selected, and then click **Finish**.</span></span>
6. <span data-ttu-id="c550e-217">按一下 **[關閉]**，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="c550e-217">Click **Close**, and then click **OK**.</span></span> 
7. <span data-ttu-id="c550e-218">在主控台樹狀目錄中，依序展開 **[憑證 (本機電腦)]** 和 **[信任的根憑證授權]**，然後按一下 **[憑證]**。</span><span class="sxs-lookup"><span data-stu-id="c550e-218">In the console tree, expand **Certificates (Local Computer)**, expand **Trusted Root Certification Authorities**, and then click **Certificates**.</span></span>
8. <span data-ttu-id="c550e-219">以滑鼠右鍵按一下 **[憑證]**，按一下 **[所有工作]**，再按一下 **[匯入]**。</span><span class="sxs-lookup"><span data-stu-id="c550e-219">Right-click **Certificates**, click **All Tasks**, and click **Import**.</span></span>
9. <span data-ttu-id="c550e-220">按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="c550e-220">Click **Next**.</span></span> 
10. <span data-ttu-id="c550e-p124">按一下 **[瀏覽]**，找出檔案，然後按 **[下一步]** (視您在 **「若要下載 CA 憑證」** 步驟 3 中選取的編碼而定，檔案的副檔名會是 .cer 或 .p7b)。</span><span class="sxs-lookup"><span data-stu-id="c550e-p124">Click **Browse** to locate the file, and then click **Next**. (The file will have either a .cer or a .p7b file extension, depending on the encoding that you selected in step 3 of **To download the CA certificate**.</span></span>
11. <span data-ttu-id="c550e-223">按一下 [ **將所有憑證放** 入下列儲存區]。</span><span class="sxs-lookup"><span data-stu-id="c550e-223">Click **Place All Certificates** in the following store.</span></span>
12. <span data-ttu-id="c550e-224">按一下 **[瀏覽]**，然後選取 **[受信任的根憑證授權單位]**。</span><span class="sxs-lookup"><span data-stu-id="c550e-224">Click **Browse**, and then select **Trusted Root Certification Authorities**.</span></span> 
13. <span data-ttu-id="c550e-225">按 **[下一步]** 以驗證設定，然後按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="c550e-225">Click **Next** to verify the settings, and then click **Finish**.</span></span> 


<span data-ttu-id="c550e-226">**若要驗證 CA 是否在受信任的根 Ca 清單中：**</span><span class="sxs-lookup"><span data-stu-id="c550e-226">**To verify that the CA is in the list of trusted root CAs:**</span></span>

1. <span data-ttu-id="c550e-227">在執行 Exchange UM 的伺服器上，于 MMC 中展開 [憑證 (本機電腦]) 中，展開 [受信任的根憑證授權單位]，然後按一下 [憑證]。</span><span class="sxs-lookup"><span data-stu-id="c550e-227">On the server running Exchange UM, in MMC expand Certificates (Local Computer), expand Trusted Root Certification Authorities, and then click Certificates.</span></span>
2. <span data-ttu-id="c550e-228">在詳細資料窗格中，確認您的 CA 位於受信任的 CA 清單上。</span><span class="sxs-lookup"><span data-stu-id="c550e-228">In the details pane, verify that your CA is on the list of trusted CAs.</span></span>


