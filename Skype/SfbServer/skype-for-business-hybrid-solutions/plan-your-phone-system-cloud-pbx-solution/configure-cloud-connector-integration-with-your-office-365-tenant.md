---
title: 設定 Cloud Connector 與 Office 365 租用戶的整合
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0e2f2395-b890-4d16-aa2d-99d52438b89c
description: 瞭解如何設定雲端連接器與您的 Office 365 租使用者整合。
ms.openlocfilehash: ed9437026ddbae07aadbe81585886ed0cb5cb0cc
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002853"
---
# <a name="configure-cloud-connector-integration-with-your-office-365-tenant"></a><span data-ttu-id="997ef-103">設定 Cloud Connector 與 Office 365 租用戶的整合</span><span class="sxs-lookup"><span data-stu-id="997ef-103">Configure Cloud Connector integration with your Office 365 tenant</span></span>
 
<span data-ttu-id="997ef-104">瞭解如何設定雲端連接器與您的 Office 365 租使用者整合。</span><span class="sxs-lookup"><span data-stu-id="997ef-104">Learn how to configure Cloud Connector integration with your Office 365 tenant.</span></span>
  
<span data-ttu-id="997ef-105">在商務用 Skype 雲端連接器版本安裝完成後，請執行本節中的步驟來設定您的部署，並將其連線至您的 Office 365 租使用者。</span><span class="sxs-lookup"><span data-stu-id="997ef-105">Once the Skype for Business Cloud Connector Edition installation is complete, perform the steps in this section to configure your deployment and connect it to your Office 365 tenant.</span></span>
  
## <a name="configure-firewall-settings"></a><span data-ttu-id="997ef-106">設定防火牆設定</span><span class="sxs-lookup"><span data-stu-id="997ef-106">Configure firewall settings</span></span>

<span data-ttu-id="997ef-107">針對您的周邊網路設定您的內部和外部防火牆設定的防火牆設定，以開啟 [[商務用 Skype 雲端連接器版本規劃](plan-skype-for-business-cloud-connector-edition.md)中的[埠和通訊協定](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports)] 中所述的必要端口。</span><span class="sxs-lookup"><span data-stu-id="997ef-107">Configure the firewall settings for your internal and external firewall settings for you perimeter network to open the required ports as described in [Ports and protocols](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports) in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span>
  
## <a name="set-up-public-switched-telephone-network-pstn-gateways"></a><span data-ttu-id="997ef-108">設定公用交換電話網絡（PSTN）閘道</span><span class="sxs-lookup"><span data-stu-id="997ef-108">Set up Public Switched Telephone Network (PSTN) gateways</span></span>

<span data-ttu-id="997ef-109">在每個 PSTN 閘道設定 trunks，以指向所有裝置的中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="997ef-109">Set up trunks on each PSTN gateway to point back to Mediation Servers for all appliances.</span></span> <span data-ttu-id="997ef-110">因為對於池中的所有伺服器而言，池 FQDN 都是相同的，所以每個幹線都應該指向一個中繼伺服器 FQDN 或 IP 位址，而不是中繼伺服器池 FQDN。</span><span class="sxs-lookup"><span data-stu-id="997ef-110">Because the pool FQDN is the same for all servers in the pool, each trunk should point to one Mediation Server FQDN or IP address instead of the Mediation Server pool FQDN.</span></span> <span data-ttu-id="997ef-111">Trunks 應設定為相同的優先順序。</span><span class="sxs-lookup"><span data-stu-id="997ef-111">Trunks should be set in the same priority.</span></span>
  
<span data-ttu-id="997ef-112">如果您使用的是在中繼伺服器和閘道之間的 TLS，您必須設定閘道和中繼伺服器來支援 MTLS，如下所示：</span><span class="sxs-lookup"><span data-stu-id="997ef-112">If you are using TLS between Mediation Servers and gateways, you will need to configure the gateways and Mediation Servers to support MTLS as follows:</span></span>
  
1. <span data-ttu-id="997ef-113">從雲端連接器 Active Directory 電腦匯出根 CA。</span><span class="sxs-lookup"><span data-stu-id="997ef-113">Export the Root CA from the Cloud Connector Active Directory computer.</span></span>
    
2. <span data-ttu-id="997ef-114">請依照 PSTN 閘道供應商的說明進行，以匯入根 CA。</span><span class="sxs-lookup"><span data-stu-id="997ef-114">Follow the PSTN gateway vendor instructions for importing the Root CA.</span></span>
    
3. <span data-ttu-id="997ef-115">匯入您在中繼伺服器上頒發給閘道之憑證的根 CA 憑證。</span><span class="sxs-lookup"><span data-stu-id="997ef-115">Import the Root CA certificate for the certificate issued to your gateway on the Mediation Servers.</span></span> <span data-ttu-id="997ef-116">如果您需要取得閘道的 SSL 憑證，您可以使用在雲端連接器 Active Directory 電腦上執行的憑證授權單位服務來執行此動作，如下所示：</span><span class="sxs-lookup"><span data-stu-id="997ef-116">If you need to obtain an SSL certificate for the gateway, you may do this using the Certificate Authority service running on the Cloud Connector Active Directory computer as follows:</span></span>
    
   - <span data-ttu-id="997ef-117">修改現有的 Web 服務器範本，讓經過驗證的使用者可以進行註冊，或建立新的 Web 服務器範本來設定其他屬性，並讓經過驗證的使用者可以進行註冊。</span><span class="sxs-lookup"><span data-stu-id="997ef-117">Modify the existing Web Server template to enable Authenticated users to enroll, or create a new Web Server template to configure other properties and enable Authenticated users to enroll.</span></span> <span data-ttu-id="997ef-118">如需詳細指示，請參閱[憑證範本](https://technet.microsoft.com/en-us/library/cc730705.aspx)。</span><span class="sxs-lookup"><span data-stu-id="997ef-118">For detailed instructions, see [Certificate Templates](https://technet.microsoft.com/en-us/library/cc730705.aspx).</span></span>
    
   - <span data-ttu-id="997ef-119">使用 [憑證] 管理單元來申請憑證，選取您已啟用的 Web 服務器範本。</span><span class="sxs-lookup"><span data-stu-id="997ef-119">Request a certificate using Certificate snap-in selecting the Web Server template that you have enabled.</span></span> <span data-ttu-id="997ef-120">請務必在 [主題] 和 [DNS 名稱] 中的 [Subject] 和 [DNS 名稱] 中新增常見名稱，並在 [主要選項] 底下選取 [可匯出私密金鑰] 的 [私人金鑰]。</span><span class="sxs-lookup"><span data-stu-id="997ef-120">Be sure to add Common name in Subject and DNS name in Alternative name with FQDN of the gateway, and confirm on the Private Key that Make private key exportable is selected under key options.</span></span> 
    
4. <span data-ttu-id="997ef-121">使用私人金鑰匯出 SSL 憑證，然後依照 PSTN 閘道廠商的指示匯入憑證。</span><span class="sxs-lookup"><span data-stu-id="997ef-121">Export the SSL certificate with Private key and follow the instructions from your PSTN gateway vendor for importing the certificate.</span></span>
    
## <a name="update-the-domain-for-your-tenant"></a><span data-ttu-id="997ef-122">為您的租使用者更新網域</span><span class="sxs-lookup"><span data-stu-id="997ef-122">Update the domain for your tenant</span></span>

<span data-ttu-id="997ef-123">請確定您已完成 Office 365 中更新網域的步驟，並具備新增 DNS 記錄的功能。</span><span class="sxs-lookup"><span data-stu-id="997ef-123">Make sure that you've completed the steps to update your domain in Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="997ef-124">如需如何在 Office 365 中設定網域的詳細資訊，請參閱[將網域新增至 office 365](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)。</span><span class="sxs-lookup"><span data-stu-id="997ef-124">For more information about how to set up your domain in Office 365, see [Add a domain to Office 365](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
  
## <a name="add-dns-records-in-office-365-for-your-edge"></a><span data-ttu-id="997ef-125">在 Office 365 中新增您 Edge 的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="997ef-125">Add DNS records in Office 365 for your Edge</span></span>

<span data-ttu-id="997ef-126">將下列 DNS 記錄新增至您的 Office 365 租使用者。</span><span class="sxs-lookup"><span data-stu-id="997ef-126">Add the following DNS records to your Office 365 tenant.</span></span> <span data-ttu-id="997ef-127">如需如何將 DNS 記錄新增至您的 Office 365 租使用者的相關資訊，請參閱[在 office 365 中新增或編輯自訂 DNS 記錄](https://support.office.com/en-us/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1)。</span><span class="sxs-lookup"><span data-stu-id="997ef-127">For information about how to add DNS records to your Office 365 tenant, see [Add or edit custom DNS records in Office 365](https://support.office.com/en-us/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1).</span></span>
  
1. <span data-ttu-id="997ef-128">新增 Access Edge 的 DNS A 記錄。</span><span class="sxs-lookup"><span data-stu-id="997ef-128">Add a DNS A record for Access Edge.</span></span>
    
2. <span data-ttu-id="997ef-129">您可以透過 Office 365 和部署腳本來自動建立 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="997ef-129">SRV records will automatically be created by Office 365 and the deployment scripts.</span></span> <span data-ttu-id="997ef-130">確認您可以在 Edge 上查詢下列兩個 SIP 服務： [_sip] 和 [_sipfederationtls]。</span><span class="sxs-lookup"><span data-stu-id="997ef-130">Confirm that you can look up the following two SIP services on the Edge: _sip and _sipfederationtls.</span></span>
    
     ![已確認 SRV 記錄](../../media/3c353a29-6dcc-4ed3-98db-3a6bed3e929e.png)
  
## <a name="set-up-hybrid-connectivity-between-cloud-connector-edition-and-office-365"></a><span data-ttu-id="997ef-132">在雲端連接器版本與 Office 365 之間設定混合式連接</span><span class="sxs-lookup"><span data-stu-id="997ef-132">Set up hybrid connectivity between Cloud Connector Edition and Office 365</span></span>

<span data-ttu-id="997ef-133">若要設定您的商務用 Skype 雲端連接器版本部署與您的 Office 365 租使用者之間的混合式連線性，請在遠端 PowerShell 會話中執行下列 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="997ef-133">To configure hybrid connectivity between your Skype for Business Cloud Connector Edition deployment and your Office 365 tenant, run the following cmdlet in a remote PowerShell session.</span></span> <span data-ttu-id="997ef-134">若要瞭解如何建立遠端 PowerShell 會話，請參閱：[設定您的 Windows PowerShell 電腦](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="997ef-134">To learn how to establish a remote PowerShell session, see: [Set up your computer for Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx).</span></span>
  
<span data-ttu-id="997ef-135">這個 Cmdlet 會設定存取邊緣外部 FQDN。</span><span class="sxs-lookup"><span data-stu-id="997ef-135">The cmdlet sets the Access Edge external FQDN.</span></span> <span data-ttu-id="997ef-136">在第一個命令中， \<外部存取邊緣 FQDN 應該是\> SIP 存取邊緣角色的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="997ef-136">In the first of the commands, the \<External Access Edge FQDN\> should be the one for the SIP Access Edge role.</span></span> <span data-ttu-id="997ef-137">根據預設，這應該是 [ap\<. 功能變數名稱\>]。</span><span class="sxs-lookup"><span data-stu-id="997ef-137">By default, this should be ap.\<Domain Name\>.</span></span>
  
```powershell
Set-CsTenantHybridConfiguration -PeerDestination <External Access Edge FQDN> -UseOnPremDialPlan $false
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True
```

> [!NOTE]
> <span data-ttu-id="997ef-138">針對對等目的地使用的外部存取邊緣 FQDN 應該設定為 PSTN 網站，只有當使用者未指派給 PSTN 網站時，才會將它當作備用物件使用。</span><span class="sxs-lookup"><span data-stu-id="997ef-138">The External Access Edge FQDN used for Peer Destination should be set to a PSTN site that will only be used as a fallback in case a user isn't assigned to a PSTN site.</span></span> <span data-ttu-id="997ef-139">如需詳細資訊，請參閱[在雲端連接器中部署單一網站](deploy-a-single-site-in-cloud-connector.md)，並[在雲端連接器中部署多個網站](deploy-multiple-sites-in-cloud-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="997ef-139">For more information, see [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md) and [Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span></span> 
  
## <a name="set-up-pstn-gateways"></a><span data-ttu-id="997ef-140">設定 PSTN 閘道</span><span class="sxs-lookup"><span data-stu-id="997ef-140">Set up PSTN gateways</span></span>

<span data-ttu-id="997ef-141">在每個 PSTN 閘道設定 trunks，以指向所有裝置的中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="997ef-141">Set up trunks on each PSTN gateway to point back to Mediation Servers for all appliances.</span></span> <span data-ttu-id="997ef-142">每個幹線都應該指向一個中繼伺服器 FQDN 或 IP 位址（而非轉送轉送伺服器池 FQDN），因為對於池中的所有伺服器而言，該池 FQDN 都是相同的。</span><span class="sxs-lookup"><span data-stu-id="997ef-142">Each trunk should point to one Mediation Server FQDN or IP address instead of the Mediation Server pool FQDN because the pool FQDN is the same for all servers in the pool.</span></span> <span data-ttu-id="997ef-143">Trunks 應設定為相同的優先順序。</span><span class="sxs-lookup"><span data-stu-id="997ef-143">Trunks should be set in the same priority.</span></span>
  
<span data-ttu-id="997ef-144">如果您使用的是在中繼伺服器和閘道之間的 TLS，您必須設定閘道和中繼伺服器來支援 MTLS，如下所示：</span><span class="sxs-lookup"><span data-stu-id="997ef-144">If you are using TLS between Mediation Servers and gateways, you will need to configure the gateways and Mediation Servers to support MTLS as follows:</span></span>
  
1. <span data-ttu-id="997ef-145">從雲端連接器 Active Directory 電腦匯出根 CA。</span><span class="sxs-lookup"><span data-stu-id="997ef-145">Export the Root CA from the Cloud Connector Active Directory computer.</span></span>
    
2. <span data-ttu-id="997ef-146">請依照 PSTN 閘道供應商的說明進行，以匯入根 CA。</span><span class="sxs-lookup"><span data-stu-id="997ef-146">Follow the PSTN gateway vendor instructions for importing the Root CA.</span></span>
    
3. <span data-ttu-id="997ef-147">匯入您在中繼伺服器上頒發給閘道之憑證的根 CA 憑證。</span><span class="sxs-lookup"><span data-stu-id="997ef-147">Import the Root CA certificate for the certificate issued to your gateway on the Mediation Servers.</span></span> <span data-ttu-id="997ef-148">如果您需要取得閘道的 SSL 憑證，您可以使用在雲端連接器 Active Directory 電腦上執行的憑證授權單位服務來執行此動作，如下所示：</span><span class="sxs-lookup"><span data-stu-id="997ef-148">If you need to obtain an SSL certificate for the gateway, you may do this using the Certificate Authority service running on the Cloud Connector Active Directory computer as follows:</span></span>
    
   - <span data-ttu-id="997ef-149">修改現有的 Web 服務器範本，讓經過驗證的使用者可以進行註冊，或建立新的 Web 服務器範本來設定其他屬性，並讓經過驗證的使用者可以進行註冊。</span><span class="sxs-lookup"><span data-stu-id="997ef-149">Modify the existing Web Server template to enable Authenticated users to Enroll, or create a new Web Server template to configure other properties and enable Authenticated users to enroll.</span></span> <span data-ttu-id="997ef-150">如需詳細指示，請參閱[憑證範本](https://technet.microsoft.com/library/cc730705.aspx)。</span><span class="sxs-lookup"><span data-stu-id="997ef-150">For detailed instructions, see [Certificate Templates](https://technet.microsoft.com/library/cc730705.aspx).</span></span>
    
   - <span data-ttu-id="997ef-151">使用 [憑證] 管理單元來申請憑證，選取您已啟用的 Web 服務器範本。</span><span class="sxs-lookup"><span data-stu-id="997ef-151">Request a certificate using Certificate snap-in selecting the Web Server template that you have enabled.</span></span> <span data-ttu-id="997ef-152">請務必在 [主題] 和 [DNS 名稱] 中的 [Subject] 和 [DNS 名稱] 中新增常見名稱，並在 [主要選項] 底下選取 [可匯出私密金鑰] 的 [私人金鑰]。</span><span class="sxs-lookup"><span data-stu-id="997ef-152">Be sure to add Common name in Subject and DNS name in Alternative name with FQDN of the gateway, and confirm on the Private Key that Make private key exportable is selected under key options.</span></span> 
    
4. <span data-ttu-id="997ef-153">使用私人金鑰匯出 SSL 憑證，然後依照 PSTN 閘道廠商的指示匯入憑證。</span><span class="sxs-lookup"><span data-stu-id="997ef-153">Export the SSL certificate with Private key and follow the instructions from your PSTN gateway vendor for importing the certificate.</span></span>
    
5. <span data-ttu-id="997ef-154">一個 PSTN 網站中的 PSTN 閘道應該只會連接到相同網站中的中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="997ef-154">PSTN gateway(s) in one PSTN site should only connect to the Mediation Server(s) in the same site.</span></span>
    
## <a name="set-up-your-users-in-office-365"></a><span data-ttu-id="997ef-155">在 Office 365 中設定您的使用者</span><span class="sxs-lookup"><span data-stu-id="997ef-155">Set up your users in Office 365</span></span>

<span data-ttu-id="997ef-156">登入 Office 365 系統管理入口網站，新增將可供線上語音服務使用的使用者，並在 Office 365 附加元件中將 E5 授權或電話系統指派給這些使用者的 E3 授權。</span><span class="sxs-lookup"><span data-stu-id="997ef-156">Log in to the Office 365 admin portal, add the users that will be enabled for online voice services, and assign an E5 license or Phone System in Office 365 add-on to the E3 license to these users.</span></span> <span data-ttu-id="997ef-157">如需新增使用者的相關資訊，請參閱[將使用者新增至商務用 Office 365](https://support.office.com/en-US/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc)。</span><span class="sxs-lookup"><span data-stu-id="997ef-157">For information about adding users, see [Add users to Office 365 for business](https://support.office.com/en-US/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc).</span></span>
  
## <a name="enable-users-for-phone-system-in-office-365-voice-and-voicemail-services"></a><span data-ttu-id="997ef-158">在 Office 365 語音及語音信箱服務中啟用手機系統使用者</span><span class="sxs-lookup"><span data-stu-id="997ef-158">Enable users for Phone System in Office 365 voice and voicemail services</span></span>

<span data-ttu-id="997ef-159">將使用者新增至 Office 365 之後，在 Office 365 語音服務（包括語音信箱）中啟用其電話系統帳戶。</span><span class="sxs-lookup"><span data-stu-id="997ef-159">After adding your users to Office 365, enable their accounts for Phone System in Office 365 voice services, including voicemail.</span></span> <span data-ttu-id="997ef-160">若要啟用這些功能，您必須使用 Office 365 全域系統管理員角色的帳戶登入 Office 365 租使用者，並且能夠執行遠端 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="997ef-160">To enable these capabilities, you must log in to your Office 365 tenant with an account that is an Office 365 Global Administrator role, and be able to run remote PowerShell.</span></span> <span data-ttu-id="997ef-161">若要瞭解如何建立遠端 PowerShell 會話，請參閱：[設定您的 Windows PowerShell 電腦](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="997ef-161">To learn how to establish a remote PowerShell session, see: [Set up your computer for Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx)</span></span>
  
- <span data-ttu-id="997ef-162">將原則指派給您的使用者，並設定使用者的商務語音電話號碼，並以身分**識別**參數的值來指定：</span><span class="sxs-lookup"><span data-stu-id="997ef-162">Assign the policy to your user and configure the user's business voice phone number, which you specify with the value of the **Identity** parameter:</span></span>
    
  ```powershell
  Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI <tel:+phonenumber>
  ```

    > [!NOTE]
    > <span data-ttu-id="997ef-163">您可以使用使用者的 SIP 位址、使用者主體名稱（UPN）或使用者的 Active Directory 顯示名稱（例如「Bob 凱利」）來指定使用者身分識別。</span><span class="sxs-lookup"><span data-stu-id="997ef-163">A user identity can be specified using the user's SIP address, user principal name (UPN), or the user's Active Directory display name (for example, "Bob Kelly").</span></span> <span data-ttu-id="997ef-164">星號（\*）字元也可以搭配顯示名稱來作為使用者身分識別。</span><span class="sxs-lookup"><span data-stu-id="997ef-164">The asterisk (\*) character can also be used with the Display Name as the user Identity.</span></span> <span data-ttu-id="997ef-165">例如，身分識別「\*smith」會傳回其顯示名稱以字串值「Smith」結尾的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="997ef-165">For example, the Identity "\*Smith" returns all the users who have a display name that ends with the string value "Smith".</span></span>
  
<span data-ttu-id="997ef-166">然後，您可以使用下列腳本確認已新增並啟用使用者：</span><span class="sxs-lookup"><span data-stu-id="997ef-166">You can then verify that the users were added and enabled using the following script:</span></span>
  
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

<span data-ttu-id="997ef-167">您必須決定您的使用者是否可以進行國際通話。</span><span class="sxs-lookup"><span data-stu-id="997ef-167">You'll need to decide whether your users should be able to make international calls.</span></span> <span data-ttu-id="997ef-168">根據預設，國際通話是啟用的。</span><span class="sxs-lookup"><span data-stu-id="997ef-168">By default, international calling is enabled.</span></span> <span data-ttu-id="997ef-169">您可以使用線上商務用 Skype 系統管理中心來停用或啟用使用者的國際撥號。</span><span class="sxs-lookup"><span data-stu-id="997ef-169">You can disable or enable users for international dialing using the online Skype for Business admin center.</span></span>
  
<span data-ttu-id="997ef-170">若要針對每位使用者停用國際通話，請在商務用 Skype Online PowerShell 中執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="997ef-170">To disable international calling on a per user basis, run the following cmdlet in Skype for Business Online PowerShell:</span></span>
  
```powershell
Grant-CsVoiceRoutingPolicy -PolicyName InternationalCallsDisallowed -Identity $user
```

<span data-ttu-id="997ef-171">若要在已停用每個使用者的情況下，針對每個使用者重新啟用國際通話，請執行相同的 Cmdlet，但將**PolicyName**的值變更為*InternationalCallsAllowed* 。</span><span class="sxs-lookup"><span data-stu-id="997ef-171">To re-enable international calling on a per user basis after it has been disabled, run the same cmdlet, but change the value for **PolicyName** to *InternationalCallsAllowed*  .</span></span>
  
## <a name="assign-users-to-pstn-sites"></a><span data-ttu-id="997ef-172">將使用者指派至 PSTN 網站</span><span class="sxs-lookup"><span data-stu-id="997ef-172">Assign users to PSTN sites</span></span>

<span data-ttu-id="997ef-173">即使您只部署單一網站，也可以使用租使用者遠端 PowerShell 將網站指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="997ef-173">Use tenant remote PowerShell to assign a site to users even if you only deployed a single site.</span></span> <span data-ttu-id="997ef-174">若要瞭解如何建立遠端 PowerShell 會話，請參閱：[設定您的 Windows PowerShell 電腦](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="997ef-174">To learn how to establish a remote PowerShell session, see: [Set up your computer for Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx).</span></span>
  
```powershell
# Set the site to users
Set-CsUserPstnSettings -Identity <User Name> -HybridPstnSite <PSTN Site Name>

# Review the site setting for a user
Get-CsUserPstnSettings -Identity <User Name> 

# See all the user settings in one tenant
Get-CsOnlineUser | Get-CsUserPstnSettings
```

> [!NOTE]
> <span data-ttu-id="997ef-175">如果沒有 PSTN 網站指派給使用者，您的商務用 Skype 雲端連接器版本部署與您的 Office 365 租使用者之間的混合式連接，就會回到使用租使用者層級預設值（對等目的地），以便完成通話。</span><span class="sxs-lookup"><span data-stu-id="997ef-175">If no PSTN site is assigned to a user, hybrid connectivity between your Skype for Business Cloud Connector Edition deployment and your Office 365 tenant will fall back to use the tenant level default one (Peer Destination) so that calls can be completed.</span></span> 
  
## <a name="configure-online-hybrid-mediation-server-settings"></a><span data-ttu-id="997ef-176">設定線上混合式轉送轉送伺服器設定</span><span class="sxs-lookup"><span data-stu-id="997ef-176">Configure online hybrid Mediation Server Settings</span></span>
<span data-ttu-id="997ef-177"><a name="BKMK_ConfigureMediationServer"> </a></span><span class="sxs-lookup"><span data-stu-id="997ef-177"></span></span>

<span data-ttu-id="997ef-178">當 P2P 通話升級至 PSTN 會議時，商務用 Skype Online 會議服務器會將邀請傳送給雲端連接器中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="997ef-178">When a P2P call is escalated to a PSTN conference, the Skype for Business Online conferencing server will send an invite to the Cloud Connector Mediation Server.</span></span> <span data-ttu-id="997ef-179">若要確保 Office 365 能成功地路由此邀請，您需要針對每個雲端連接器中繼伺服器設定線上租使用者的設定，如下所示：</span><span class="sxs-lookup"><span data-stu-id="997ef-179">To ensure that Office 365 can route this invite successfully, you need to configure a setting in your online tenant for each Cloud Connector Mediation Server as follows:</span></span> 
  
1. <span data-ttu-id="997ef-180">在 Office 365 系統管理入口網站中建立使用者。</span><span class="sxs-lookup"><span data-stu-id="997ef-180">Create a user in the Office 365 admin portal.</span></span> <span data-ttu-id="997ef-181">使用任何您想要的使用者名稱，例如 "MediationServer1"。</span><span class="sxs-lookup"><span data-stu-id="997ef-181">Use any user name you want, such as "MediationServer1."</span></span>
    
    <span data-ttu-id="997ef-182">使用雲端連接器的預設 SIP 網域（.ini 檔案中的第一個 SIP 網域）作為使用者網域。</span><span class="sxs-lookup"><span data-stu-id="997ef-182">Use the default SIP domain of Cloud Connector (the first SIP domain in the .ini file) as the user domain.</span></span>
    
    <span data-ttu-id="997ef-183">請注意，只有在使用者傳播到商務用 Skype online 目錄時，才需要授權指派。</span><span class="sxs-lookup"><span data-stu-id="997ef-183">Please note that license assignment is only required for the user propagation into the Skype for Business online directory.</span></span> <span data-ttu-id="997ef-184">將 Office 365 授權（例如 E5）指派給您所建立的帳戶，最多允許一個小時來傳播變更，確認使用者帳戶已透過執行下列 Cmdlet 正確地提供給商務用 Skype online 目錄，然後移除此帳戶的授權。</span><span class="sxs-lookup"><span data-stu-id="997ef-184">Assign an Office 365 licenses (such as E5) to the account you create, allow up to one hour for the changes to propagate,verify the user accounts has been provisioned correctly to the Skype for Business online directory by running following cmdlet, then remove the license from this account.</span></span>
    ```powershell
   Get-CsOnlineUser -Identity <UserPrincipalName>
   ```
    
2. <span data-ttu-id="997ef-185">使用您的全域或使用者管理員認證啟動租使用者 Azure AD 遠端 PowerShell 會話，然後執行下列 Cmdlet，將步驟1中設定的 Azure AD 使用者帳戶設定為「HybridMediationServer」：</span><span class="sxs-lookup"><span data-stu-id="997ef-185">Start a tenant Azure AD remote PowerShell session using your global or user admin credentials, and then run the following cmdlet to set the department for the Azure AD user account configured in step 1 to "HybridMediationServer":</span></span>

   ```powershell
   Set-MsolUser -UserPrincipalName <UserPrincipalName> -Department "HybridMediationServer"
   ```

3. <span data-ttu-id="997ef-186">使用您的商務用 Skype 租使用者系統管理員認證啟動租使用者商務用 Skype 遠端 PowerShell 會話，然後執行下列 Cmdlet，將轉送伺服器和 Edge 伺服器 FQDN 設定為該使用者帳戶， \<將\> DisplayName 替換為您在步驟1中建立的帳戶顯示名稱：</span><span class="sxs-lookup"><span data-stu-id="997ef-186">Start a tenant Skype for Business remote PowerShell session using your Skype for Business tenant admin credentials, and then run the following cmdlet to set the Mediation Server and Edge Server FQDN to that user account, replacing \<DisplayName\> with the Display Name of the user for the account you created in step 1:</span></span>
    
   ```powershell
   Set-CsHybridMediationServer -Identity <DisplayName> -Fqdn <MediationServerFQDN> -AccessProxyExternalFqdn <EdgeServerExternalFQDN>
   ```

    <span data-ttu-id="997ef-187">針對 [身分識別]，請使用您為此中繼伺服器建立的 Office 365 使用者帳戶的顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="997ef-187">For Identity, use the Display Name of the Office 365 user account you created for this Mediation Server.</span></span>
    
    <span data-ttu-id="997ef-188">若是*MediationServerFQDN* ，請使用針對您的中繼伺服器定義的內部 FQDN。</span><span class="sxs-lookup"><span data-stu-id="997ef-188">For  *MediationServerFQDN*  , use the internal FQDN defined for your Mediation Server.</span></span>
    
    <span data-ttu-id="997ef-189">若是*EdgeServerExternalFQDN* ，請使用針對 Edge 伺服器訪問 Proxy 定義的外部 FQDN。</span><span class="sxs-lookup"><span data-stu-id="997ef-189">For  *EdgeServerExternalFQDN*  , use the external FQDN defined for Edge Server Access Proxy.</span></span> <span data-ttu-id="997ef-190">如果有多個雲端連接器 PSTN 網站，請選擇指派給中繼伺服器所在之網站的邊緣伺服器訪問 Proxy FQDN。</span><span class="sxs-lookup"><span data-stu-id="997ef-190">If there are multiple Cloud Connector PSTN sites, choose the Edge Server Access Proxy FQDN assigned to the site where the Mediation Server is located.</span></span>
    
4. <span data-ttu-id="997ef-191">如果有多個雲端連接器中繼伺服器（多個網站、HA），請針對每個伺服器重複上述步驟。</span><span class="sxs-lookup"><span data-stu-id="997ef-191">If there are multiple Cloud Connector Mediation Servers (multiple-site, HA), please repeat the previous steps for each of them.</span></span>
    

