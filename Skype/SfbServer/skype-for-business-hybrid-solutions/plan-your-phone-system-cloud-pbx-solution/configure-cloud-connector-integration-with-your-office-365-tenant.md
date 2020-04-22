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
description: 瞭解如何設定雲端連接器與 Office 365 組織的整合。
ms.openlocfilehash: 1fecf017f614fc8bdf0f38b5f51c29e4b2774357
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780642"
---
# <a name="configure-cloud-connector-integration-with-your-microsoft-365-or-office-365-organization"></a><span data-ttu-id="ae0e5-103">設定與您的 Microsoft 365 或 Office 365 組織的雲端連接器整合</span><span class="sxs-lookup"><span data-stu-id="ae0e5-103">Configure Cloud Connector integration with your Microsoft 365 or Office 365 organization</span></span>
 
<span data-ttu-id="ae0e5-104">瞭解如何設定雲端連接器與 Office 365 組織的整合。</span><span class="sxs-lookup"><span data-stu-id="ae0e5-104">Learn how to configure Cloud Connector integration with your Office 365 organization.</span></span>
  
<span data-ttu-id="ae0e5-105">完成商務用 Skype Cloud Connector Edition 安裝之後，請執行本節中的步驟來設定您的部署，並將其連線至您的 Office 365 組織。</span><span class="sxs-lookup"><span data-stu-id="ae0e5-105">Once the Skype for Business Cloud Connector Edition installation is complete, perform the steps in this section to configure your deployment and connect it to your Office 365 organization.</span></span>
  
## <a name="configure-firewall-settings"></a><span data-ttu-id="ae0e5-106">設定防火牆設定</span><span class="sxs-lookup"><span data-stu-id="ae0e5-106">Configure firewall settings</span></span>

<span data-ttu-id="ae0e5-107">為周邊網路設定內部和外部防火牆設定的防火牆設定，以開啟[計畫商務用 Skype 雲端連接器 Edition](plan-skype-for-business-cloud-connector-edition.md)的[埠和通訊協定](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports)中所述的必要端口。</span><span class="sxs-lookup"><span data-stu-id="ae0e5-107">Configure the firewall settings for your internal and external firewall settings for you perimeter network to open the required ports as described in [Ports and protocols](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports) in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span>
  
## <a name="set-up-public-switched-telephone-network-pstn-gateways"></a><span data-ttu-id="ae0e5-108">設定公用交換電話網路（PSTN）閘道</span><span class="sxs-lookup"><span data-stu-id="ae0e5-108">Set up Public Switched Telephone Network (PSTN) gateways</span></span>

<span data-ttu-id="ae0e5-109">在每個 PSTN 閘道上設定主幹，以指向所有裝置的轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="ae0e5-109">Set up trunks on each PSTN gateway to point back to Mediation Servers for all appliances.</span></span> <span data-ttu-id="ae0e5-110">因為集區中所有伺服器的集區 FQDN 都是相同的，所以每個主幹應該指向一個轉送伺服器 FQDN 或 IP 位址，而非轉送伺服器集區 FQDN。</span><span class="sxs-lookup"><span data-stu-id="ae0e5-110">Because the pool FQDN is the same for all servers in the pool, each trunk should point to one Mediation Server FQDN or IP address instead of the Mediation Server pool FQDN.</span></span> <span data-ttu-id="ae0e5-111">主幹應以相同的優先順序加以設定。</span><span class="sxs-lookup"><span data-stu-id="ae0e5-111">Trunks should be set in the same priority.</span></span>
  
<span data-ttu-id="ae0e5-112">如果您使用的是轉送伺服器和閘道之間的 TLS，您必須將閘道和轉送伺服器設定為支援 MTLS，如下所示：</span><span class="sxs-lookup"><span data-stu-id="ae0e5-112">If you are using TLS between Mediation Servers and gateways, you will need to configure the gateways and Mediation Servers to support MTLS as follows:</span></span>
  
1. <span data-ttu-id="ae0e5-113">從雲端連接器 Active Directory 電腦匯出根 CA。</span><span class="sxs-lookup"><span data-stu-id="ae0e5-113">Export the Root CA from the Cloud Connector Active Directory computer.</span></span>
    
2. <span data-ttu-id="ae0e5-114">依照 PSTN 閘道廠商的指示，匯入根 CA。</span><span class="sxs-lookup"><span data-stu-id="ae0e5-114">Follow the PSTN gateway vendor instructions for importing the Root CA.</span></span>
    
3. <span data-ttu-id="ae0e5-115">在轉送伺服器上，匯入發給您閘道之憑證的根 CA 憑證。</span><span class="sxs-lookup"><span data-stu-id="ae0e5-115">Import the Root CA certificate for the certificate issued to your gateway on the Mediation Servers.</span></span> <span data-ttu-id="ae0e5-116">如果您需要取得閘道的 SSL 憑證，您可以使用雲端連接器 Active Directory 電腦上所執行的憑證授權單位服務，如下所示：</span><span class="sxs-lookup"><span data-stu-id="ae0e5-116">If you need to obtain an SSL certificate for the gateway, you may do this using the Certificate Authority service running on the Cloud Connector Active Directory computer as follows:</span></span>
    
   - <span data-ttu-id="ae0e5-117">修改現有的 Web 服務器範本，讓已驗證的使用者能夠註冊，或是建立新的網頁伺服器範本以設定其他屬性，並讓已驗證的使用者能夠進行註冊。</span><span class="sxs-lookup"><span data-stu-id="ae0e5-117">Modify the existing Web Server template to enable Authenticated users to enroll, or create a new Web Server template to configure other properties and enable Authenticated users to enroll.</span></span> <span data-ttu-id="ae0e5-118">如需詳細指示，請參閱[憑證範本](https://technet.microsoft.com/library/cc730705.aspx)。</span><span class="sxs-lookup"><span data-stu-id="ae0e5-118">For detailed instructions, see [Certificate Templates](https://technet.microsoft.com/library/cc730705.aspx).</span></span>
    
   - <span data-ttu-id="ae0e5-119">使用憑證嵌入式管理單元要求憑證選取您已啟用的 Web 服務器範本。</span><span class="sxs-lookup"><span data-stu-id="ae0e5-119">Request a certificate using Certificate snap-in selecting the Web Server template that you have enabled.</span></span> <span data-ttu-id="ae0e5-120">請務必在 [替代名稱] 中，使用「閘道的 FQDN」來新增 Subject 和 DNS 名稱中的 [一般名稱]，然後在 [主要選項] 下，確認已選取 [可匯出私密金鑰] 的私密金鑰。</span><span class="sxs-lookup"><span data-stu-id="ae0e5-120">Be sure to add Common name in Subject and DNS name in Alternative name with FQDN of the gateway, and confirm on the Private Key that Make private key exportable is selected under key options.</span></span> 
    
4. <span data-ttu-id="ae0e5-121">使用私密金鑰匯出 SSL 憑證，並遵循您的 PSTN 閘道廠商的指示，以匯入憑證。</span><span class="sxs-lookup"><span data-stu-id="ae0e5-121">Export the SSL certificate with Private key and follow the instructions from your PSTN gateway vendor for importing the certificate.</span></span>
    
## <a name="update-the-domain-for-your-tenant"></a><span data-ttu-id="ae0e5-122">更新租使用者的網域</span><span class="sxs-lookup"><span data-stu-id="ae0e5-122">Update the domain for your tenant</span></span>

<span data-ttu-id="ae0e5-123">請確認您已完成在 Office 365 更新您的網域的步驟，並且具備新增 DNS 記錄的能力。</span><span class="sxs-lookup"><span data-stu-id="ae0e5-123">Make sure that you've completed the steps to update your domain in Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="ae0e5-124">如需如何在 Office 365 中設定網域的相關資訊，請參閱[Add a domain To Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)。</span><span class="sxs-lookup"><span data-stu-id="ae0e5-124">For more information about how to set up your domain in Office 365, see [Add a domain to Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
  
## <a name="add-dns-records-in-office-365-for-your-edge"></a><span data-ttu-id="ae0e5-125">在 Office 365 中新增您 Edge 的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="ae0e5-125">Add DNS records in Office 365 for your Edge</span></span>

<span data-ttu-id="ae0e5-126">將下列 DNS 記錄新增至您的 Office 365 組織。</span><span class="sxs-lookup"><span data-stu-id="ae0e5-126">Add the following DNS records to your Office 365 organization.</span></span> <span data-ttu-id="ae0e5-127">如需如何將 DNS 記錄新增至 Office 365 組織的詳細資訊，請參閱[在 office 365 中新增或編輯自訂 DNS 記錄](https://support.office.com/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1)。</span><span class="sxs-lookup"><span data-stu-id="ae0e5-127">For information about how to add DNS records to your Office 365 organization, see [Add or edit custom DNS records in Office 365](https://support.office.com/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1).</span></span>
  
1. <span data-ttu-id="ae0e5-128">新增 Access Edge 的 DNS A 記錄。</span><span class="sxs-lookup"><span data-stu-id="ae0e5-128">Add a DNS A record for Access Edge.</span></span>
    
2. <span data-ttu-id="ae0e5-129">Office 365 和部署腳本會自動建立 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="ae0e5-129">SRV records will automatically be created by Office 365 and the deployment scripts.</span></span> <span data-ttu-id="ae0e5-130">請確認您可以在 Edge 上查詢下列兩種 SIP 服務： _sip 和 _sipfederationtls。</span><span class="sxs-lookup"><span data-stu-id="ae0e5-130">Confirm that you can look up the following two SIP services on the Edge: _sip and _sipfederationtls.</span></span>
    
     ![SRV 記錄確認](../../media/3c353a29-6dcc-4ed3-98db-3a6bed3e929e.png)
  
## <a name="set-up-hybrid-connectivity-between-cloud-connector-edition-and-office-365"></a><span data-ttu-id="ae0e5-132">設定 Cloud Connector Edition 與 Office 365 之間的混合式連線</span><span class="sxs-lookup"><span data-stu-id="ae0e5-132">Set up hybrid connectivity between Cloud Connector Edition and Office 365</span></span>

<span data-ttu-id="ae0e5-133">若要設定商務用 Skype Cloud Connector Edition 部署與 Office 365 組織之間的混合式連線，請在遠端 PowerShell 會話中執行下列 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ae0e5-133">To configure hybrid connectivity between your Skype for Business Cloud Connector Edition deployment and your Office 365 organization, run the following cmdlet in a remote PowerShell session.</span></span> <span data-ttu-id="ae0e5-134">若要瞭解如何建立遠端 PowerShell 會話，請參閱：[設定您的電腦 Windows PowerShell](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="ae0e5-134">To learn how to establish a remote PowerShell session, see: [Set up your computer for Windows PowerShell](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx).</span></span>
  
<span data-ttu-id="ae0e5-135">Cmdlet 會設定 Access Edge 的外部 FQDN。</span><span class="sxs-lookup"><span data-stu-id="ae0e5-135">The cmdlet sets the Access Edge external FQDN.</span></span> <span data-ttu-id="ae0e5-136">在第一個命令中， \<外部訪問 edge FQDN 應該是\> SIP ACCESS edge role 的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="ae0e5-136">In the first of the commands, the \<External Access Edge FQDN\> should be the one for the SIP Access Edge role.</span></span> <span data-ttu-id="ae0e5-137">根據預設，此值應為 ap\<。功能變數名稱\>。</span><span class="sxs-lookup"><span data-stu-id="ae0e5-137">By default, this should be ap.\<Domain Name\>.</span></span>
  
```powershell
Set-CsTenantHybridConfiguration -PeerDestination <External Access Edge FQDN> -UseOnPremDialPlan $false
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True
```

> [!NOTE]
> <span data-ttu-id="ae0e5-138">用於對等目的地的外部存取 Edge FQDN 應該設定為 PSTN 網站，只有當使用者未被指派給 PSTN 網站時，才會將其當作回退使用。</span><span class="sxs-lookup"><span data-stu-id="ae0e5-138">The External Access Edge FQDN used for Peer Destination should be set to a PSTN site that will only be used as a fallback in case a user isn't assigned to a PSTN site.</span></span> <span data-ttu-id="ae0e5-139">如需詳細資訊，請參閱[deploy a site In Cloud connector](deploy-a-single-site-in-cloud-connector.md)和[Deploy in cloud connector 中的多個網站](deploy-multiple-sites-in-cloud-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="ae0e5-139">For more information, see [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md) and [Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span></span> 
  
## <a name="set-up-pstn-gateways"></a><span data-ttu-id="ae0e5-140">設定 PSTN 閘道</span><span class="sxs-lookup"><span data-stu-id="ae0e5-140">Set up PSTN gateways</span></span>

<span data-ttu-id="ae0e5-141">在每個 PSTN 閘道上設定主幹，以指向所有裝置的轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="ae0e5-141">Set up trunks on each PSTN gateway to point back to Mediation Servers for all appliances.</span></span> <span data-ttu-id="ae0e5-142">每個主幹應該指向一個轉送伺服器 FQDN 或 IP 位址，而非轉送伺服器集區 FQDN，因為集區中所有伺服器的集區 FQDN 都相同。</span><span class="sxs-lookup"><span data-stu-id="ae0e5-142">Each trunk should point to one Mediation Server FQDN or IP address instead of the Mediation Server pool FQDN because the pool FQDN is the same for all servers in the pool.</span></span> <span data-ttu-id="ae0e5-143">主幹應以相同的優先順序加以設定。</span><span class="sxs-lookup"><span data-stu-id="ae0e5-143">Trunks should be set in the same priority.</span></span>
  
<span data-ttu-id="ae0e5-144">如果您使用的是轉送伺服器和閘道之間的 TLS，您必須將閘道和轉送伺服器設定為支援 MTLS，如下所示：</span><span class="sxs-lookup"><span data-stu-id="ae0e5-144">If you are using TLS between Mediation Servers and gateways, you will need to configure the gateways and Mediation Servers to support MTLS as follows:</span></span>
  
1. <span data-ttu-id="ae0e5-145">從雲端連接器 Active Directory 電腦匯出根 CA。</span><span class="sxs-lookup"><span data-stu-id="ae0e5-145">Export the Root CA from the Cloud Connector Active Directory computer.</span></span>
    
2. <span data-ttu-id="ae0e5-146">依照 PSTN 閘道廠商的指示，匯入根 CA。</span><span class="sxs-lookup"><span data-stu-id="ae0e5-146">Follow the PSTN gateway vendor instructions for importing the Root CA.</span></span>
    
3. <span data-ttu-id="ae0e5-147">在轉送伺服器上，匯入發給您閘道之憑證的根 CA 憑證。</span><span class="sxs-lookup"><span data-stu-id="ae0e5-147">Import the Root CA certificate for the certificate issued to your gateway on the Mediation Servers.</span></span> <span data-ttu-id="ae0e5-148">如果您需要取得閘道的 SSL 憑證，您可以使用雲端連接器 Active Directory 電腦上所執行的憑證授權單位服務，如下所示：</span><span class="sxs-lookup"><span data-stu-id="ae0e5-148">If you need to obtain an SSL certificate for the gateway, you may do this using the Certificate Authority service running on the Cloud Connector Active Directory computer as follows:</span></span>
    
   - <span data-ttu-id="ae0e5-149">修改現有的 Web 服務器範本，讓已驗證的使用者能夠註冊，或是建立新的網頁伺服器範本以設定其他屬性，並讓已驗證的使用者能夠進行註冊。</span><span class="sxs-lookup"><span data-stu-id="ae0e5-149">Modify the existing Web Server template to enable Authenticated users to Enroll, or create a new Web Server template to configure other properties and enable Authenticated users to enroll.</span></span> <span data-ttu-id="ae0e5-150">如需詳細指示，請參閱[憑證範本](https://technet.microsoft.com/library/cc730705.aspx)。</span><span class="sxs-lookup"><span data-stu-id="ae0e5-150">For detailed instructions, see [Certificate Templates](https://technet.microsoft.com/library/cc730705.aspx).</span></span>
    
   - <span data-ttu-id="ae0e5-151">使用憑證嵌入式管理單元要求憑證選取您已啟用的 Web 服務器範本。</span><span class="sxs-lookup"><span data-stu-id="ae0e5-151">Request a certificate using Certificate snap-in selecting the Web Server template that you have enabled.</span></span> <span data-ttu-id="ae0e5-152">請務必在 [替代名稱] 中，使用「閘道的 FQDN」來新增 Subject 和 DNS 名稱中的 [一般名稱]，然後在 [主要選項] 下，確認已選取 [可匯出私密金鑰] 的私密金鑰。</span><span class="sxs-lookup"><span data-stu-id="ae0e5-152">Be sure to add Common name in Subject and DNS name in Alternative name with FQDN of the gateway, and confirm on the Private Key that Make private key exportable is selected under key options.</span></span> 
    
4. <span data-ttu-id="ae0e5-153">使用私密金鑰匯出 SSL 憑證，並遵循您的 PSTN 閘道廠商的指示，以匯入憑證。</span><span class="sxs-lookup"><span data-stu-id="ae0e5-153">Export the SSL certificate with Private key and follow the instructions from your PSTN gateway vendor for importing the certificate.</span></span>
    
5. <span data-ttu-id="ae0e5-154">一個 PSTN 網站中的 PSTN 閘道應該只會連接至相同網站的轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="ae0e5-154">PSTN gateway(s) in one PSTN site should only connect to the Mediation Server(s) in the same site.</span></span>
    
## <a name="set-up-your-users-in-office-365"></a><span data-ttu-id="ae0e5-155">在 Office 365 中設定使用者</span><span class="sxs-lookup"><span data-stu-id="ae0e5-155">Set up your users in Office 365</span></span>

<span data-ttu-id="ae0e5-156">登入 Microsoft 365 系統管理中心，新增將為線上語音服務啟用的使用者，並在 Office 365 附加元件中指派 E5 授權或電話系統給這些使用者的 E3 授權。</span><span class="sxs-lookup"><span data-stu-id="ae0e5-156">Log in to the Microsoft 365 admin center, add the users that will be enabled for online voice services, and assign an E5 license or Phone System in Office 365 add-on to the E3 license to these users.</span></span> <span data-ttu-id="ae0e5-157">如需新增使用者的詳細資訊，請參閱[將使用者新增至 Office 365 for business](https://support.office.com/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc)。</span><span class="sxs-lookup"><span data-stu-id="ae0e5-157">For information about adding users, see [Add users to Office 365 for business](https://support.office.com/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc).</span></span>
  
## <a name="enable-users-for-phone-system-in-office-365-voice-and-voicemail-services"></a><span data-ttu-id="ae0e5-158">在 Office 365 語音及語音信箱服務中啟用使用者的電話系統</span><span class="sxs-lookup"><span data-stu-id="ae0e5-158">Enable users for Phone System in Office 365 voice and voicemail services</span></span>

<span data-ttu-id="ae0e5-159">將使用者新增至 Office 365 之後，請在 Office 365 語音服務（包括語音信箱）中啟用其電話系統帳戶。</span><span class="sxs-lookup"><span data-stu-id="ae0e5-159">After adding your users to Office 365, enable their accounts for Phone System in Office 365 voice services, including voicemail.</span></span> <span data-ttu-id="ae0e5-160">若要啟用這些功能，您必須以全域系統管理員角色的帳戶登入 Office 365 組織，並且能夠執行遠端 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="ae0e5-160">To enable these capabilities, you must log in to your Office 365 organization with an account that is a Global Administrator role, and be able to run remote PowerShell.</span></span> <span data-ttu-id="ae0e5-161">若要瞭解如何建立遠端 PowerShell 會話，請參閱：[設定電腦的 Windows PowerShell](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ae0e5-161">To learn how to establish a remote PowerShell session, see: [Set up your computer for Windows PowerShell](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx)</span></span>
  
- <span data-ttu-id="ae0e5-162">將原則指派給您的使用者，並設定使用者的商務語音電話號碼，並以**Identity**參數的值來指定：</span><span class="sxs-lookup"><span data-stu-id="ae0e5-162">Assign the policy to your user and configure the user's business voice phone number, which you specify with the value of the **Identity** parameter:</span></span>
    
  ```powershell
  Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI <tel:+phonenumber>
  ```

    > [!NOTE]
    > <span data-ttu-id="ae0e5-163">使用者身分識別可以使用使用者的 SIP 位址、使用者主體名稱（UPN）或使用者的 Active Directory 顯示名稱來指定（例如，「Bob 凱利」）。</span><span class="sxs-lookup"><span data-stu-id="ae0e5-163">A user identity can be specified using the user's SIP address, user principal name (UPN), or the user's Active Directory display name (for example, "Bob Kelly").</span></span> <span data-ttu-id="ae0e5-164">星號（\*）字元也可以使用顯示名稱做為使用者身分識別。</span><span class="sxs-lookup"><span data-stu-id="ae0e5-164">The asterisk (\*) character can also be used with the Display Name as the user Identity.</span></span> <span data-ttu-id="ae0e5-165">例如，身分識別 "\*smith" 會傳回顯示名稱結尾為字串值 "Smith" 的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="ae0e5-165">For example, the Identity "\*Smith" returns all the users who have a display name that ends with the string value "Smith".</span></span>
  
<span data-ttu-id="ae0e5-166">然後，您可以使用下列腳本確認使用者已新增及啟用：</span><span class="sxs-lookup"><span data-stu-id="ae0e5-166">You can then verify that the users were added and enabled using the following script:</span></span>
  
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

<span data-ttu-id="ae0e5-167">您必須決定您的使用者是否應該能夠撥打國際電話。</span><span class="sxs-lookup"><span data-stu-id="ae0e5-167">You'll need to decide whether your users should be able to make international calls.</span></span> <span data-ttu-id="ae0e5-168">依預設，會啟用國際通話。</span><span class="sxs-lookup"><span data-stu-id="ae0e5-168">By default, international calling is enabled.</span></span> <span data-ttu-id="ae0e5-169">您可以使用線上商務用 Skype 系統管理中心，停用或啟用使用者進行國際撥號的功能。</span><span class="sxs-lookup"><span data-stu-id="ae0e5-169">You can disable or enable users for international dialing using the online Skype for Business admin center.</span></span>
  
<span data-ttu-id="ae0e5-170">若要以每位使用者為基礎停用國際電話，請在商務用 Skype Online 中執行下列 Cmdlet PowerShell:</span><span class="sxs-lookup"><span data-stu-id="ae0e5-170">To disable international calling on a per user basis, run the following cmdlet in Skype for Business Online PowerShell:</span></span>
  
```powershell
Grant-CsVoiceRoutingPolicy -PolicyName InternationalCallsDisallowed -Identity $user
```

<span data-ttu-id="ae0e5-171">若要在每一使用者停用時以每個使用者為基礎重新啟用國際電話，請執行相同的 Cmdlet，但將**PolicyName**的值變更為*InternationalCallsAllowed* 。</span><span class="sxs-lookup"><span data-stu-id="ae0e5-171">To re-enable international calling on a per user basis after it has been disabled, run the same cmdlet, but change the value for **PolicyName** to *InternationalCallsAllowed*  .</span></span>
  
## <a name="assign-users-to-pstn-sites"></a><span data-ttu-id="ae0e5-172">將使用者指派至 PSTN 網站</span><span class="sxs-lookup"><span data-stu-id="ae0e5-172">Assign users to PSTN sites</span></span>

<span data-ttu-id="ae0e5-173">使用租使用者遠端 PowerShell 將網站指派給使用者，即使您只部署了單一網站也是一樣。</span><span class="sxs-lookup"><span data-stu-id="ae0e5-173">Use tenant remote PowerShell to assign a site to users even if you only deployed a single site.</span></span> <span data-ttu-id="ae0e5-174">若要瞭解如何建立遠端 PowerShell 會話，請參閱：[設定您的電腦 Windows PowerShell](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="ae0e5-174">To learn how to establish a remote PowerShell session, see: [Set up your computer for Windows PowerShell](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx).</span></span>
  
```powershell
# Set the site to users
Set-CsUserPstnSettings -Identity <User Name> -HybridPstnSite <PSTN Site Name>

# Review the site setting for a user
Get-CsUserPstnSettings -Identity <User Name> 

# See all the user settings in one tenant
Get-CsOnlineUser | Get-CsUserPstnSettings
```

> [!NOTE]
> <span data-ttu-id="ae0e5-175">如果沒有 PSTN 網站指派給使用者，則您的商務用 Skype 雲端連接器 Edition 部署和 Office 365 組織之間的混合式連線將會回復為使用租使用者層級的預設值（對等目的地），這樣通話才能完成。</span><span class="sxs-lookup"><span data-stu-id="ae0e5-175">If no PSTN site is assigned to a user, hybrid connectivity between your Skype for Business Cloud Connector Edition deployment and your Office 365 organization will fall back to use the tenant level default one (Peer Destination) so that calls can be completed.</span></span> 
  
## <a name="configure-online-hybrid-mediation-server-settings"></a><span data-ttu-id="ae0e5-176">設定線上混合轉送伺服器設定</span><span class="sxs-lookup"><span data-stu-id="ae0e5-176">Configure online hybrid Mediation Server Settings</span></span>
<span data-ttu-id="ae0e5-177"><a name="BKMK_ConfigureMediationServer"> </a></span><span class="sxs-lookup"><span data-stu-id="ae0e5-177"><a name="BKMK_ConfigureMediationServer"> </a></span></span>

<span data-ttu-id="ae0e5-178">當 P2P 呼叫呈報給 PSTN 會議時，商務用 Skype Online 會議服務器會將邀請傳送至雲端連接器轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="ae0e5-178">When a P2P call is escalated to a PSTN conference, the Skype for Business Online conferencing server will send an invite to the Cloud Connector Mediation Server.</span></span> <span data-ttu-id="ae0e5-179">為了確保 Office 365 可順利路由傳送此邀請，您必須為每個雲端連接器轉送伺服器設定您線上承租人中的設定，如下所示：</span><span class="sxs-lookup"><span data-stu-id="ae0e5-179">To ensure that Office 365 can route this invite successfully, you need to configure a setting in your online tenant for each Cloud Connector Mediation Server as follows:</span></span> 
  
1. <span data-ttu-id="ae0e5-180">在 Microsoft 365 admin center 中建立使用者。</span><span class="sxs-lookup"><span data-stu-id="ae0e5-180">Create a user in the Microsoft 365 admin center.</span></span> <span data-ttu-id="ae0e5-181">使用任何您想要的使用者名稱，例如 "MediationServer1"。</span><span class="sxs-lookup"><span data-stu-id="ae0e5-181">Use any user name you want, such as "MediationServer1."</span></span>
    
    <span data-ttu-id="ae0e5-182">使用雲端連接器的預設 SIP 網域（.ini 檔案中的第一個 SIP 網域）做為使用者網域。</span><span class="sxs-lookup"><span data-stu-id="ae0e5-182">Use the default SIP domain of Cloud Connector (the first SIP domain in the .ini file) as the user domain.</span></span>
    
    <span data-ttu-id="ae0e5-183">請注意，使用者必須將授權指派傳播至商務用 Skype online 目錄。</span><span class="sxs-lookup"><span data-stu-id="ae0e5-183">Please note that license assignment is only required for the user propagation into the Skype for Business online directory.</span></span> <span data-ttu-id="ae0e5-184">將 Office 365 授權（例如 E5）指派給您所建立的帳戶，最多允許一小時若要傳播變更，請透過執行下列 Cmdlet，將使用者帳戶正確布建至商務用 Skype online 目錄，然後從此帳戶中移除授權。</span><span class="sxs-lookup"><span data-stu-id="ae0e5-184">Assign an Office 365 licenses (such as E5) to the account you create, allow up to one hour for the changes to propagate,verify the user accounts has been provisioned correctly to the Skype for Business online directory by running following cmdlet, then remove the license from this account.</span></span>
    ```powershell
   Get-CsOnlineUser -Identity <UserPrincipalName>
   ```
    
2. <span data-ttu-id="ae0e5-185">使用您的全域或使用者系統管理員認證來啟動租 Azure AD remote PowerShell 會話，然後執行下列 Cmdlet，將步驟1中設定之 Azure AD 使用者帳戶的部門設定為 "HybridMediationServer"：</span><span class="sxs-lookup"><span data-stu-id="ae0e5-185">Start a tenant Azure AD remote PowerShell session using your global or user admin credentials, and then run the following cmdlet to set the department for the Azure AD user account configured in step 1 to "HybridMediationServer":</span></span>

   ```powershell
   Set-MsolUser -UserPrincipalName <UserPrincipalName> -Department "HybridMediationServer"
   ```

3. <span data-ttu-id="ae0e5-186">使用您的商務用 Skype 租使用者系統管理員認證來啟動租使用者商務用 Skype 遠端 PowerShell 會話，然後執行下列 Cmdlet，將轉送伺服器和 Edge Server FQDN 設定為該使用者帳戶\<，\>並將 DisplayName 取代為您在步驟1中建立之帳戶的使用者顯示名稱：</span><span class="sxs-lookup"><span data-stu-id="ae0e5-186">Start a tenant Skype for Business remote PowerShell session using your Skype for Business tenant admin credentials, and then run the following cmdlet to set the Mediation Server and Edge Server FQDN to that user account, replacing \<DisplayName\> with the Display Name of the user for the account you created in step 1:</span></span>
    
   ```powershell
   Set-CsHybridMediationServer -Identity <DisplayName> -Fqdn <MediationServerFQDN> -AccessProxyExternalFqdn <EdgeServerExternalFQDN>
   ```

    <span data-ttu-id="ae0e5-187">針對 [身分識別]，使用您為此轉送伺服器建立的使用者帳戶顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="ae0e5-187">For Identity, use the Display Name of the user account you created for this Mediation Server.</span></span>
    
    <span data-ttu-id="ae0e5-188">針對*MediationServerFQDN* ，使用為您的轉送伺服器定義的內部 FQDN。</span><span class="sxs-lookup"><span data-stu-id="ae0e5-188">For  *MediationServerFQDN*  , use the internal FQDN defined for your Mediation Server.</span></span>
    
    <span data-ttu-id="ae0e5-189">針對*EdgeServerExternalFQDN* ，使用為 Edge Server Access Proxy 定義的外部 FQDN。</span><span class="sxs-lookup"><span data-stu-id="ae0e5-189">For  *EdgeServerExternalFQDN*  , use the external FQDN defined for Edge Server Access Proxy.</span></span> <span data-ttu-id="ae0e5-190">如果有多個雲端連接器 PSTN 網站，請選擇指派給轉送伺服器所在之網站的 Edge Server Access Proxy FQDN。</span><span class="sxs-lookup"><span data-stu-id="ae0e5-190">If there are multiple Cloud Connector PSTN sites, choose the Edge Server Access Proxy FQDN assigned to the site where the Mediation Server is located.</span></span>
    
4. <span data-ttu-id="ae0e5-191">如果有多個 Cloud Connector 轉送伺服器（多個網站，HA），請為每個轉送伺服器重複先前的步驟。</span><span class="sxs-lookup"><span data-stu-id="ae0e5-191">If there are multiple Cloud Connector Mediation Servers (multiple-site, HA), please repeat the previous steps for each of them.</span></span>
    

