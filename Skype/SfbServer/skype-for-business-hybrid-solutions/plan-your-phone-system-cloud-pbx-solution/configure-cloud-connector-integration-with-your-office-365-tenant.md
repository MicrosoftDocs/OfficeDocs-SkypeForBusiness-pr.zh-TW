---
title: 設定與您的 Microsoft 365 或 Office 365 組織的雲端連接器整合
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0e2f2395-b890-4d16-aa2d-99d52438b89c
description: 瞭解如何設定 Cloud Connector 整合與您的 Microsoft 365 或 Office 365 組織。
ms.openlocfilehash: bf5d8c4fb9684a205670701428fa8db30835a871
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359069"
---
# <a name="configure-cloud-connector-integration-with-your-microsoft-365-or-office-365-organization"></a><span data-ttu-id="ee8dc-103">設定與您的 Microsoft 365 或 Office 365 組織的雲端連接器整合</span><span class="sxs-lookup"><span data-stu-id="ee8dc-103">Configure Cloud Connector integration with your Microsoft 365 or Office 365 organization</span></span>

> [!Important] 
> <span data-ttu-id="ee8dc-104">雲端連接器 Edition 會于2021年7月31日和商務用 Skype Online 終止。</span><span class="sxs-lookup"><span data-stu-id="ee8dc-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="ee8dc-105">當您的組織升級至小組後，請瞭解如何使用 [直接路由](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)將您的內部部署電話語音網路連線到小組。</span><span class="sxs-lookup"><span data-stu-id="ee8dc-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="ee8dc-106">瞭解如何設定 Cloud Connector 整合與您的 Microsoft 365 或 Office 365 組織。</span><span class="sxs-lookup"><span data-stu-id="ee8dc-106">Learn how to configure Cloud Connector integration with your Microsoft 365 or Office 365 organization.</span></span>
  
<span data-ttu-id="ee8dc-107">完成商務用 Skype Cloud Connector Edition 安裝之後，請執行本節中的步驟來設定您的部署，並將其連線至您的 Microsoft 365 或 Office 365 組織。</span><span class="sxs-lookup"><span data-stu-id="ee8dc-107">Once the Skype for Business Cloud Connector Edition installation is complete, perform the steps in this section to configure your deployment and connect it to your Microsoft 365 or Office 365 organization.</span></span>
  
## <a name="configure-firewall-settings"></a><span data-ttu-id="ee8dc-108">設定防火牆設定</span><span class="sxs-lookup"><span data-stu-id="ee8dc-108">Configure firewall settings</span></span>

<span data-ttu-id="ee8dc-109">為周邊網路設定內部和外部防火牆設定的防火牆設定，以開啟[計畫商務用 Skype 雲端連接器 Edition](plan-skype-for-business-cloud-connector-edition.md)的[埠和通訊協定](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports)中所述的必要端口。</span><span class="sxs-lookup"><span data-stu-id="ee8dc-109">Configure the firewall settings for your internal and external firewall settings for you perimeter network to open the required ports as described in [Ports and protocols](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports) in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span>
  
## <a name="set-up-public-switched-telephone-network-pstn-gateways"></a><span data-ttu-id="ee8dc-110">設定公用交換電話網路 (PSTN) 閘道</span><span class="sxs-lookup"><span data-stu-id="ee8dc-110">Set up Public Switched Telephone Network (PSTN) gateways</span></span>

<span data-ttu-id="ee8dc-111">在每個 PSTN 閘道上設定主幹，以指向所有裝置的轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="ee8dc-111">Set up trunks on each PSTN gateway to point back to Mediation Servers for all appliances.</span></span> <span data-ttu-id="ee8dc-112">因為集區中所有伺服器的集區 FQDN 都是相同的，所以每個主幹應該指向一個轉送伺服器 FQDN 或 IP 位址，而非轉送伺服器集區 FQDN。</span><span class="sxs-lookup"><span data-stu-id="ee8dc-112">Because the pool FQDN is the same for all servers in the pool, each trunk should point to one Mediation Server FQDN or IP address instead of the Mediation Server pool FQDN.</span></span> <span data-ttu-id="ee8dc-113">主幹應以相同的優先順序加以設定。</span><span class="sxs-lookup"><span data-stu-id="ee8dc-113">Trunks should be set in the same priority.</span></span>
  
<span data-ttu-id="ee8dc-114">如果您使用的是轉送伺服器和閘道之間的 TLS，您必須將閘道和轉送伺服器設定為支援 MTLS，如下所示：</span><span class="sxs-lookup"><span data-stu-id="ee8dc-114">If you are using TLS between Mediation Servers and gateways, you will need to configure the gateways and Mediation Servers to support MTLS as follows:</span></span>
  
1. <span data-ttu-id="ee8dc-115">從雲端連接器 Active Directory 電腦匯出根 CA。</span><span class="sxs-lookup"><span data-stu-id="ee8dc-115">Export the Root CA from the Cloud Connector Active Directory computer.</span></span>
    
2. <span data-ttu-id="ee8dc-116">依照 PSTN 閘道廠商的指示，匯入根 CA。</span><span class="sxs-lookup"><span data-stu-id="ee8dc-116">Follow the PSTN gateway vendor instructions for importing the Root CA.</span></span>
    
3. <span data-ttu-id="ee8dc-117">在轉送伺服器上，匯入發給您閘道之憑證的根 CA 憑證。</span><span class="sxs-lookup"><span data-stu-id="ee8dc-117">Import the Root CA certificate for the certificate issued to your gateway on the Mediation Servers.</span></span> <span data-ttu-id="ee8dc-118">如果您需要取得閘道的 SSL 憑證，您可以使用雲端連接器 Active Directory 電腦上所執行的憑證授權單位服務，如下所示：</span><span class="sxs-lookup"><span data-stu-id="ee8dc-118">If you need to obtain an SSL certificate for the gateway, you may do this using the Certificate Authority service running on the Cloud Connector Active Directory computer as follows:</span></span>
    
   - <span data-ttu-id="ee8dc-119">修改現有的 Web 服務器範本，讓已驗證的使用者能夠註冊，或是建立新的網頁伺服器範本以設定其他屬性，並讓已驗證的使用者能夠進行註冊。</span><span class="sxs-lookup"><span data-stu-id="ee8dc-119">Modify the existing Web Server template to enable Authenticated users to enroll, or create a new Web Server template to configure other properties and enable Authenticated users to enroll.</span></span> <span data-ttu-id="ee8dc-120">如需詳細指示，請參閱 [憑證範本](https://technet.microsoft.com/library/cc730705.aspx)。</span><span class="sxs-lookup"><span data-stu-id="ee8dc-120">For detailed instructions, see [Certificate Templates](https://technet.microsoft.com/library/cc730705.aspx).</span></span>
    
   - <span data-ttu-id="ee8dc-121">使用憑證嵌入式管理單元要求憑證選取您已啟用的 Web 服務器範本。</span><span class="sxs-lookup"><span data-stu-id="ee8dc-121">Request a certificate using Certificate snap-in selecting the Web Server template that you have enabled.</span></span> <span data-ttu-id="ee8dc-122">請務必在 [替代名稱] 中，使用「閘道的 FQDN」來新增 Subject 和 DNS 名稱中的 [一般名稱]，然後在 [主要選項] 下，確認已選取 [可匯出私密金鑰] 的私密金鑰。</span><span class="sxs-lookup"><span data-stu-id="ee8dc-122">Be sure to add Common name in Subject and DNS name in Alternative name with FQDN of the gateway, and confirm on the Private Key that Make private key exportable is selected under key options.</span></span> 
    
4. <span data-ttu-id="ee8dc-123">使用私密金鑰匯出 SSL 憑證，並遵循您的 PSTN 閘道廠商的指示，以匯入憑證。</span><span class="sxs-lookup"><span data-stu-id="ee8dc-123">Export the SSL certificate with Private key and follow the instructions from your PSTN gateway vendor for importing the certificate.</span></span>
    
## <a name="update-the-domain-for-your-tenant"></a><span data-ttu-id="ee8dc-124">更新租使用者的網域</span><span class="sxs-lookup"><span data-stu-id="ee8dc-124">Update the domain for your tenant</span></span>

<span data-ttu-id="ee8dc-125">請確定您已完成在 Microsoft 365 或 Office 365 中更新網域的步驟，並具備新增 DNS 記錄的能力。</span><span class="sxs-lookup"><span data-stu-id="ee8dc-125">Make sure that you've completed the steps to update your domain in Microsoft 365 or Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="ee8dc-126">如需如何在 Microsoft 365 或 Office 365 中設定網域的詳細資訊，請參閱 [Add a domain To Microsoft 365 Or Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)。</span><span class="sxs-lookup"><span data-stu-id="ee8dc-126">For more information about how to set up your domain in Microsoft 365 or Office 365, see [Add a domain to Microsoft 365 or Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
  
## <a name="add-dns-records-for-your-edge"></a><span data-ttu-id="ee8dc-127">新增您 Edge 的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="ee8dc-127">Add DNS records for your Edge</span></span>

<span data-ttu-id="ee8dc-128">將下列 DNS 記錄新增至您的 Microsoft 365 或 Office 365 組織。</span><span class="sxs-lookup"><span data-stu-id="ee8dc-128">Add the following DNS records to your Microsoft 365 or Office 365 organization.</span></span> <span data-ttu-id="ee8dc-129">如需如何新增 DNS 記錄的相關資訊，請參閱 [在 Microsoft 365 或 Office 365 中新增或編輯自訂 DNS 記錄](https://support.office.com/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1)。</span><span class="sxs-lookup"><span data-stu-id="ee8dc-129">For information about how to add DNS records, see [Add or edit custom DNS records in Microsoft 365 or Office 365](https://support.office.com/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1).</span></span>
  
1. <span data-ttu-id="ee8dc-130">新增 Access Edge 的 DNS A 記錄。</span><span class="sxs-lookup"><span data-stu-id="ee8dc-130">Add a DNS A record for Access Edge.</span></span>
    
2. <span data-ttu-id="ee8dc-131">SRV 記錄會自動由 Microsoft 365 或 Office 365 及部署腳本建立。</span><span class="sxs-lookup"><span data-stu-id="ee8dc-131">SRV records will automatically be created by Microsoft 365 or Office 365 and the deployment scripts.</span></span> <span data-ttu-id="ee8dc-132">請確認您可以在 Edge： sip 和 sipfederationtls 查看下列兩種 SIP 服務 \_ \_ 。</span><span class="sxs-lookup"><span data-stu-id="ee8dc-132">Confirm that you can look up the following two SIP services on the Edge: \_sip and \_sipfederationtls.</span></span>
    
     ![SRV 記錄確認](../../media/3c353a29-6dcc-4ed3-98db-3a6bed3e929e.png)
  
## <a name="set-up-hybrid-connectivity-between-cloud-connector-edition-and-microsoft-365-or-office-365"></a><span data-ttu-id="ee8dc-134">設定 Cloud Connector Edition 和 Microsoft 365 或 Office 365 之間的混合式連線</span><span class="sxs-lookup"><span data-stu-id="ee8dc-134">Set up hybrid connectivity between Cloud Connector Edition and Microsoft 365 or Office 365</span></span>

<span data-ttu-id="ee8dc-135">若要設定商務用 Skype Cloud Connector Edition 部署和您的 Microsoft 365 或 Office 365 組織之間的混合式連線，請在遠端 PowerShell 會話中執行下列 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ee8dc-135">To configure hybrid connectivity between your Skype for Business Cloud Connector Edition deployment and your Microsoft 365 or Office 365 organization, run the following cmdlet in a remote PowerShell session.</span></span> <span data-ttu-id="ee8dc-136">若要瞭解如何建立遠端 PowerShell 會話，請參閱： [設定您的電腦 Windows PowerShell](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="ee8dc-136">To learn how to establish a remote PowerShell session, see: [Set up your computer for Windows PowerShell](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx).</span></span>
  
<span data-ttu-id="ee8dc-137">Cmdlet 會設定 Access Edge 的外部 FQDN。</span><span class="sxs-lookup"><span data-stu-id="ee8dc-137">The cmdlet sets the Access Edge external FQDN.</span></span> <span data-ttu-id="ee8dc-138">在第一個命令中， \<External Access Edge FQDN\> 應該是 SIP Access Edge role 的一個。</span><span class="sxs-lookup"><span data-stu-id="ee8dc-138">In the first of the commands, the \<External Access Edge FQDN\> should be the one for the SIP Access Edge role.</span></span> <span data-ttu-id="ee8dc-139">根據預設，這應該是 \<Domain Name\> ap。</span><span class="sxs-lookup"><span data-stu-id="ee8dc-139">By default, this should be ap.\<Domain Name\>.</span></span>
  
```powershell
Set-CsTenantHybridConfiguration -PeerDestination <External Access Edge FQDN> -UseOnPremDialPlan $false
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True
```

> [!NOTE]
> <span data-ttu-id="ee8dc-140">用於對等目的地的外部存取 Edge FQDN 應該設定為 PSTN 網站，只有當使用者未被指派給 PSTN 網站時，才會將其當作回退使用。</span><span class="sxs-lookup"><span data-stu-id="ee8dc-140">The External Access Edge FQDN used for Peer Destination should be set to a PSTN site that will only be used as a fallback in case a user isn't assigned to a PSTN site.</span></span> <span data-ttu-id="ee8dc-141">如需詳細資訊，請參閱 [deploy a site In Cloud connector](deploy-a-single-site-in-cloud-connector.md) 和 [Deploy in cloud connector 中的多個網站](deploy-multiple-sites-in-cloud-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="ee8dc-141">For more information, see [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md) and [Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span></span> 
  
## <a name="set-up-pstn-gateways"></a><span data-ttu-id="ee8dc-142">設定 PSTN 閘道</span><span class="sxs-lookup"><span data-stu-id="ee8dc-142">Set up PSTN gateways</span></span>

<span data-ttu-id="ee8dc-143">在每個 PSTN 閘道上設定主幹，以指向所有裝置的轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="ee8dc-143">Set up trunks on each PSTN gateway to point back to Mediation Servers for all appliances.</span></span> <span data-ttu-id="ee8dc-144">每個主幹應該指向一個轉送伺服器 FQDN 或 IP 位址，而非轉送伺服器集區 FQDN，因為集區中所有伺服器的集區 FQDN 都相同。</span><span class="sxs-lookup"><span data-stu-id="ee8dc-144">Each trunk should point to one Mediation Server FQDN or IP address instead of the Mediation Server pool FQDN because the pool FQDN is the same for all servers in the pool.</span></span> <span data-ttu-id="ee8dc-145">主幹應以相同的優先順序加以設定。</span><span class="sxs-lookup"><span data-stu-id="ee8dc-145">Trunks should be set in the same priority.</span></span>
  
<span data-ttu-id="ee8dc-146">如果您使用的是轉送伺服器和閘道之間的 TLS，您必須將閘道和轉送伺服器設定為支援 MTLS，如下所示：</span><span class="sxs-lookup"><span data-stu-id="ee8dc-146">If you are using TLS between Mediation Servers and gateways, you will need to configure the gateways and Mediation Servers to support MTLS as follows:</span></span>
  
1. <span data-ttu-id="ee8dc-147">從雲端連接器 Active Directory 電腦匯出根 CA。</span><span class="sxs-lookup"><span data-stu-id="ee8dc-147">Export the Root CA from the Cloud Connector Active Directory computer.</span></span>
    
2. <span data-ttu-id="ee8dc-148">依照 PSTN 閘道廠商的指示，匯入根 CA。</span><span class="sxs-lookup"><span data-stu-id="ee8dc-148">Follow the PSTN gateway vendor instructions for importing the Root CA.</span></span>
    
3. <span data-ttu-id="ee8dc-149">在轉送伺服器上，匯入發給您閘道之憑證的根 CA 憑證。</span><span class="sxs-lookup"><span data-stu-id="ee8dc-149">Import the Root CA certificate for the certificate issued to your gateway on the Mediation Servers.</span></span> <span data-ttu-id="ee8dc-150">如果您需要取得閘道的 SSL 憑證，您可以使用雲端連接器 Active Directory 電腦上所執行的憑證授權單位服務，如下所示：</span><span class="sxs-lookup"><span data-stu-id="ee8dc-150">If you need to obtain an SSL certificate for the gateway, you may do this using the Certificate Authority service running on the Cloud Connector Active Directory computer as follows:</span></span>
    
   - <span data-ttu-id="ee8dc-151">修改現有的 Web 服務器範本，讓已驗證的使用者能夠註冊，或是建立新的網頁伺服器範本以設定其他屬性，並讓已驗證的使用者能夠進行註冊。</span><span class="sxs-lookup"><span data-stu-id="ee8dc-151">Modify the existing Web Server template to enable Authenticated users to Enroll, or create a new Web Server template to configure other properties and enable Authenticated users to enroll.</span></span> <span data-ttu-id="ee8dc-152">如需詳細指示，請參閱 [憑證範本](https://technet.microsoft.com/library/cc730705.aspx)。</span><span class="sxs-lookup"><span data-stu-id="ee8dc-152">For detailed instructions, see [Certificate Templates](https://technet.microsoft.com/library/cc730705.aspx).</span></span>
    
   - <span data-ttu-id="ee8dc-153">使用憑證嵌入式管理單元要求憑證選取您已啟用的 Web 服務器範本。</span><span class="sxs-lookup"><span data-stu-id="ee8dc-153">Request a certificate using Certificate snap-in selecting the Web Server template that you have enabled.</span></span> <span data-ttu-id="ee8dc-154">請務必在 [替代名稱] 中，使用「閘道的 FQDN」來新增 Subject 和 DNS 名稱中的 [一般名稱]，然後在 [主要選項] 下，確認已選取 [可匯出私密金鑰] 的私密金鑰。</span><span class="sxs-lookup"><span data-stu-id="ee8dc-154">Be sure to add Common name in Subject and DNS name in Alternative name with FQDN of the gateway, and confirm on the Private Key that Make private key exportable is selected under key options.</span></span> 
    
4. <span data-ttu-id="ee8dc-155">使用私密金鑰匯出 SSL 憑證，並遵循您的 PSTN 閘道廠商的指示，以匯入憑證。</span><span class="sxs-lookup"><span data-stu-id="ee8dc-155">Export the SSL certificate with Private key and follow the instructions from your PSTN gateway vendor for importing the certificate.</span></span>
    
5. <span data-ttu-id="ee8dc-156">PSTN 閘道 (s) 在一個 PSTN 網站中應該只會連線至同一個網站中 (s) 的轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="ee8dc-156">PSTN gateway(s) in one PSTN site should only connect to the Mediation Server(s) in the same site.</span></span>
    
## <a name="set-up-your-users"></a><span data-ttu-id="ee8dc-157">設定使用者</span><span class="sxs-lookup"><span data-stu-id="ee8dc-157">Set up your users</span></span>

<span data-ttu-id="ee8dc-158">登入 Microsoft 365 系統管理中心，新增將為線上語音服務啟用的使用者，並將 E5 授權或電話系統附加元件指派給這些使用者的 E3 授權。</span><span class="sxs-lookup"><span data-stu-id="ee8dc-158">Log in to the Microsoft 365 admin center, add the users that will be enabled for online voice services, and assign an E5 license or Phone System add-on to the E3 license to these users.</span></span> <span data-ttu-id="ee8dc-159">如需新增使用者的詳細資訊，請參閱 [將使用者新增至 Microsoft 365 for business](https://support.office.com/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc)。</span><span class="sxs-lookup"><span data-stu-id="ee8dc-159">For information about adding users, see [Add users to Microsoft 365 for business](https://support.office.com/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc).</span></span>
  
## <a name="enable-users-for-phone-system-voice-and-voicemail-services"></a><span data-ttu-id="ee8dc-160">為使用者啟用電話語音系統語音和語音信箱服務</span><span class="sxs-lookup"><span data-stu-id="ee8dc-160">Enable users for Phone System voice and voicemail services</span></span>
 
<span data-ttu-id="ee8dc-161">將使用者新增至 Microsoft 365 或 Office 365 後，請啟用其帳戶的電話語音服務（包括語音信箱）。</span><span class="sxs-lookup"><span data-stu-id="ee8dc-161">After adding your users to Microsoft 365 or Office 365, enable their accounts for Phone System voice services, including voicemail.</span></span> <span data-ttu-id="ee8dc-162">若要啟用這些功能，您必須以全域系統管理員角色的帳戶登入您的 Microsoft 365 或 Office 365 組織，並且能夠執行遠端 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="ee8dc-162">To enable these capabilities, you must log in to your Microsoft 365 or Office 365 organization with an account that is a Global Administrator role, and be able to run remote PowerShell.</span></span> <span data-ttu-id="ee8dc-163">若要瞭解如何建立遠端 PowerShell 會話，請參閱： [設定電腦的 Windows PowerShell](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ee8dc-163">To learn how to establish a remote PowerShell session, see: [Set up your computer for Windows PowerShell](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx)</span></span>
  
- <span data-ttu-id="ee8dc-164">將原則指派給您的使用者，並設定使用者的商務語音電話號碼，並以 **Identity** 參數的值來指定：</span><span class="sxs-lookup"><span data-stu-id="ee8dc-164">Assign the policy to your user and configure the user's business voice phone number, which you specify with the value of the **Identity** parameter:</span></span>
    
  ```powershell
  Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI <tel:+phonenumber>
  ```

    > [!NOTE]
    > <span data-ttu-id="ee8dc-165">使用者身分識別可以使用使用者的 SIP 位址、使用者主體名稱 (UPN) 或使用者的 Active Directory 顯示名稱來指定 (例如，「小明凱利」 ) 。</span><span class="sxs-lookup"><span data-stu-id="ee8dc-165">A user identity can be specified using the user's SIP address, user principal name (UPN), or the user's Active Directory display name (for example, "Bob Kelly").</span></span> <span data-ttu-id="ee8dc-166">星號 (\*) 字元也可以與使用者身分識別的顯示名稱搭配使用。</span><span class="sxs-lookup"><span data-stu-id="ee8dc-166">The asterisk (\*) character can also be used with the Display Name as the user Identity.</span></span> <span data-ttu-id="ee8dc-167">例如，身分識別 " \* smith" 會傳回顯示名稱結尾為字串值 "Smith" 的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="ee8dc-167">For example, the Identity "\*Smith" returns all the users who have a display name that ends with the string value "Smith".</span></span>
  
<span data-ttu-id="ee8dc-168">然後，您可以使用下列腳本確認使用者已新增及啟用：</span><span class="sxs-lookup"><span data-stu-id="ee8dc-168">You can then verify that the users were added and enabled using the following script:</span></span>
  
```powershell
# Input the user name you want to verify
$user = Get-CsOnlineUser <User name>

# For a hybrid user, the value of $user.EnterpriseVoiceEnabled should be True
$user.EnterpriseVoiceEnabled

# For a hybrid user, the value of $user.HostedVoiceMail should be True
$user.HostedVoiceMail

# For a hybrid user, the value of $user.VoicePolicy should be "HybridVoice"
$user.VoicePolicy
```

<span data-ttu-id="ee8dc-169">您必須決定您的使用者是否應該能夠撥打國際電話。</span><span class="sxs-lookup"><span data-stu-id="ee8dc-169">You'll need to decide whether your users should be able to make international calls.</span></span> <span data-ttu-id="ee8dc-170">依預設，會啟用國際通話。</span><span class="sxs-lookup"><span data-stu-id="ee8dc-170">By default, international calling is enabled.</span></span> <span data-ttu-id="ee8dc-171">您可以使用線上商務用 Skype 系統管理中心，停用或啟用使用者進行國際撥號的功能。</span><span class="sxs-lookup"><span data-stu-id="ee8dc-171">You can disable or enable users for international dialing using the online Skype for Business admin center.</span></span>
  
<span data-ttu-id="ee8dc-172">若要以每位使用者為基礎停用國際電話，請在商務用 Skype Online 中執行下列 Cmdlet PowerShell:</span><span class="sxs-lookup"><span data-stu-id="ee8dc-172">To disable international calling on a per user basis, run the following cmdlet in Skype for Business Online PowerShell:</span></span>
  
```powershell
Grant-CsVoiceRoutingPolicy -PolicyName InternationalCallsDisallowed -Identity $user
```

<span data-ttu-id="ee8dc-173">若要在每一使用者停用時以每個使用者為基礎重新啟用國際電話，請執行相同的 Cmdlet，但將 **PolicyName** 的值變更為 *InternationalCallsAllowed*  。</span><span class="sxs-lookup"><span data-stu-id="ee8dc-173">To re-enable international calling on a per user basis after it has been disabled, run the same cmdlet, but change the value for **PolicyName** to *InternationalCallsAllowed*  .</span></span>
  
## <a name="assign-users-to-pstn-sites"></a><span data-ttu-id="ee8dc-174">將使用者指派至 PSTN 網站</span><span class="sxs-lookup"><span data-stu-id="ee8dc-174">Assign users to PSTN sites</span></span>

<span data-ttu-id="ee8dc-175">使用租使用者遠端 PowerShell 將網站指派給使用者，即使您只部署了單一網站也是一樣。</span><span class="sxs-lookup"><span data-stu-id="ee8dc-175">Use tenant remote PowerShell to assign a site to users even if you only deployed a single site.</span></span> <span data-ttu-id="ee8dc-176">若要瞭解如何建立遠端 PowerShell 會話，請參閱： [設定您的電腦 Windows PowerShell](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="ee8dc-176">To learn how to establish a remote PowerShell session, see: [Set up your computer for Windows PowerShell](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx).</span></span>
  
```powershell
# Set the site to users
Set-CsUserPstnSettings -Identity <User Name> -HybridPstnSite <PSTN Site Name>

# Review the site setting for a user
Get-CsUserPstnSettings -Identity <User Name> 

# See all the user settings in one tenant
Get-CsOnlineUser | Get-CsUserPstnSettings
```

> [!NOTE]
> <span data-ttu-id="ee8dc-177">如果沒有 PSTN 網站指派給使用者，則您的商務用 Skype 雲端連接器版本部署和您的 Microsoft 365 或 Office 365 組織之間的混合式連線將會回退，使用 (對等目的地) 的承租人層級預設值，即可完成呼叫。</span><span class="sxs-lookup"><span data-stu-id="ee8dc-177">If no PSTN site is assigned to a user, hybrid connectivity between your Skype for Business Cloud Connector Edition deployment and your Microsoft 365 or Office 365 organization will fall back to use the tenant level default one (Peer Destination) so that calls can be completed.</span></span> 
  
## <a name="configure-online-hybrid-mediation-server-settings"></a><span data-ttu-id="ee8dc-178">設定線上混合轉送伺服器設定</span><span class="sxs-lookup"><span data-stu-id="ee8dc-178">Configure online hybrid Mediation Server Settings</span></span>
<span data-ttu-id="ee8dc-179"><a name="BKMK_ConfigureMediationServer"> </a></span><span class="sxs-lookup"><span data-stu-id="ee8dc-179"><a name="BKMK_ConfigureMediationServer"> </a></span></span>

<span data-ttu-id="ee8dc-180">當 P2P 呼叫呈報給 PSTN 會議時，商務用 Skype Online 會議服務器會將邀請傳送至雲端連接器轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="ee8dc-180">When a P2P call is escalated to a PSTN conference, the Skype for Business Online conferencing server will send an invite to the Cloud Connector Mediation Server.</span></span> <span data-ttu-id="ee8dc-181">為了確保 Microsoft 365 或 Office 365 能夠成功路由傳送此邀請，您必須為每個雲端連接器轉送伺服器設定您線上承租人中的設定，如下所示：</span><span class="sxs-lookup"><span data-stu-id="ee8dc-181">To ensure that Microsoft 365 or Office 365 can route this invite successfully, you need to configure a setting in your online tenant for each Cloud Connector Mediation Server as follows:</span></span> 
  
1. <span data-ttu-id="ee8dc-182">在 Microsoft 365 admin center 中建立使用者。</span><span class="sxs-lookup"><span data-stu-id="ee8dc-182">Create a user in the Microsoft 365 admin center.</span></span> <span data-ttu-id="ee8dc-183">使用任何您想要的使用者名稱，例如 "MediationServer1"。</span><span class="sxs-lookup"><span data-stu-id="ee8dc-183">Use any user name you want, such as "MediationServer1."</span></span>
    
    <span data-ttu-id="ee8dc-184">使用雲端連接器的預設 SIP 網域 (.ini 檔案中的第一個 SIP 網域) 做為使用者網域。</span><span class="sxs-lookup"><span data-stu-id="ee8dc-184">Use the default SIP domain of Cloud Connector (the first SIP domain in the .ini file) as the user domain.</span></span>
    
    <span data-ttu-id="ee8dc-185">請注意，使用者必須將授權指派傳播至商務用 Skype online 目錄。</span><span class="sxs-lookup"><span data-stu-id="ee8dc-185">Please note that license assignment is only required for the user propagation into the Skype for Business online directory.</span></span> <span data-ttu-id="ee8dc-186">指派 Microsoft 365 或 Office 365 授權 (例如，E5) 至您所建立的帳戶，最多允許一小時來傳播變更，請執行下列 Cmdlet，以確認使用者帳戶已正確布建至商務用 Skype online 目錄。請執行下列 Cmdlet，然後從此帳戶中移除授權。</span><span class="sxs-lookup"><span data-stu-id="ee8dc-186">Assign a Microsoft 365 or Office 365 license (such as E5) to the account you create, allow up to one hour for the changes to propagate,verify the user accounts has been provisioned correctly to the Skype for Business online directory by running following cmdlet, then remove the license from this account.</span></span>
    ```powershell
   Get-CsOnlineUser -Identity <UserPrincipalName>
   ```
    
2. <span data-ttu-id="ee8dc-187">使用您的全域或使用者系統管理員認證來啟動租 Azure AD remote PowerShell 會話，然後執行下列 Cmdlet，將步驟1中設定之 Azure AD 使用者帳戶的部門設定為 "HybridMediationServer"：</span><span class="sxs-lookup"><span data-stu-id="ee8dc-187">Start a tenant Azure AD remote PowerShell session using your global or user admin credentials, and then run the following cmdlet to set the department for the Azure AD user account configured in step 1 to "HybridMediationServer":</span></span>

   ```powershell
   Set-MsolUser -UserPrincipalName <UserPrincipalName> -Department "HybridMediationServer"
   ```

3. <span data-ttu-id="ee8dc-188">使用您的商務用 Skype 租使用者系統管理員認證來啟動租使用者商務用 Skype 遠端 PowerShell 會話，然後執行下列 Cmdlet，將轉送伺服器和 Edge Server FQDN 設定為該使用者帳戶，並以 \<DisplayName\> 您在步驟1中建立之帳戶的使用者顯示名稱取代：</span><span class="sxs-lookup"><span data-stu-id="ee8dc-188">Start a tenant Skype for Business remote PowerShell session using your Skype for Business tenant admin credentials, and then run the following cmdlet to set the Mediation Server and Edge Server FQDN to that user account, replacing \<DisplayName\> with the Display Name of the user for the account you created in step 1:</span></span>
    
   ```powershell
   Set-CsHybridMediationServer -Identity <DisplayName> -Fqdn <MediationServerFQDN> -AccessProxyExternalFqdn <EdgeServerExternalFQDN>
   ```

    <span data-ttu-id="ee8dc-189">針對 [身分識別]，使用您為此轉送伺服器建立的使用者帳戶顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="ee8dc-189">For Identity, use the Display Name of the user account you created for this Mediation Server.</span></span>
    
    <span data-ttu-id="ee8dc-190">針對  *MediationServerFQDN*  ，使用為您的轉送伺服器定義的內部 FQDN。</span><span class="sxs-lookup"><span data-stu-id="ee8dc-190">For  *MediationServerFQDN*  , use the internal FQDN defined for your Mediation Server.</span></span>
    
    <span data-ttu-id="ee8dc-191">針對  *EdgeServerExternalFQDN*  ，使用為 Edge Server Access Proxy 定義的外部 FQDN。</span><span class="sxs-lookup"><span data-stu-id="ee8dc-191">For  *EdgeServerExternalFQDN*  , use the external FQDN defined for Edge Server Access Proxy.</span></span> <span data-ttu-id="ee8dc-192">如果有多個雲端連接器 PSTN 網站，請選擇指派給轉送伺服器所在之網站的 Edge Server Access Proxy FQDN。</span><span class="sxs-lookup"><span data-stu-id="ee8dc-192">If there are multiple Cloud Connector PSTN sites, choose the Edge Server Access Proxy FQDN assigned to the site where the Mediation Server is located.</span></span>
    
4. <span data-ttu-id="ee8dc-193">如果有多個 Cloud Connector 轉送伺服器 (多個網站的 HA) ，請對每個伺服器重複上述步驟。</span><span class="sxs-lookup"><span data-stu-id="ee8dc-193">If there are multiple Cloud Connector Mediation Servers (multiple-site, HA), please repeat the previous steps for each of them.</span></span>
    
