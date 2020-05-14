---
title: 設定內部部署商務用 Skype Server 和 Outlook Web App 之間的整合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/7/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 95a20117-2064-43c4-94fe-cac892cadb6f
description: 摘要：整合商務用 Skype Server 和 Outlook Web App。
ms.openlocfilehash: ee5676c0dbe88568af78a1c278eea8a46457cb5c
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221183"
---
# <a name="configure-integration-between-on-premises-skype-for-business-server-and-outlook-web-app"></a><span data-ttu-id="34c7e-103">設定內部部署商務用 Skype Server 和 Outlook Web App 之間的整合</span><span class="sxs-lookup"><span data-stu-id="34c7e-103">Configure integration between on-premises Skype for Business Server and Outlook Web App</span></span>

<span data-ttu-id="34c7e-104">**摘要：** 整合商務用 Skype Server 和 Outlook Web App。</span><span class="sxs-lookup"><span data-stu-id="34c7e-104">**Summary:** Integrate Skype for Business Server and Outlook Web App.</span></span>

<span data-ttu-id="34c7e-105">使用內部部署商務用 Skype 伺服器部署的客戶，可在混合式部署模式中，設定 microsoft Exchange Online 中 Microsoft Outlook Web App 的互通性。</span><span class="sxs-lookup"><span data-stu-id="34c7e-105">Customers who are using on-premises Skype for Business Server deployments can configure interoperability with Microsoft Outlook Web App in Microsoft Exchange Online in a hybrid deployment mode.</span></span> <span data-ttu-id="34c7e-106">互通性功能包括 Outlook Web App 介面的單一登入和立即訊息（IM）和目前狀態整合。</span><span class="sxs-lookup"><span data-stu-id="34c7e-106">Interoperability features include single sign on and instant messaging (IM) and presence integration with the Outlook Web App interface.</span></span> <span data-ttu-id="34c7e-107">若要啟用此整合，您必須完成下列工作，以在內部部署商務用 Skype Server 部署中設定 Edge Server：</span><span class="sxs-lookup"><span data-stu-id="34c7e-107">To enable this integration, you must configure the Edge Server in your on-premises Skype for Business Server deployment by completing the following tasks:</span></span>

- <span data-ttu-id="34c7e-108">設定共用 SIP 位址空間</span><span class="sxs-lookup"><span data-stu-id="34c7e-108">Configure a shared SIP address space</span></span>

- <span data-ttu-id="34c7e-109">在 Edge Server 上設定裝載提供者</span><span class="sxs-lookup"><span data-stu-id="34c7e-109">Configure a hosting provider on the Edge Server</span></span>

- <span data-ttu-id="34c7e-110">驗證更新的中央管理存放區複寫</span><span class="sxs-lookup"><span data-stu-id="34c7e-110">Verify replication of the updated Central Management store</span></span>

## <a name="configure-a-shared-sip-address-space"></a><span data-ttu-id="34c7e-111">設定共用 SIP 位址空間</span><span class="sxs-lookup"><span data-stu-id="34c7e-111">Configure a Shared SIP Address Space</span></span>

<span data-ttu-id="34c7e-112">若要將內部部署商務用 Skype Server 與 Exchange Online 整合，您必須設定共用 SIP 位址空間。</span><span class="sxs-lookup"><span data-stu-id="34c7e-112">To integrate on-premises Skype for Business Server with Exchange Online, you must configure a shared SIP address space.</span></span> <span data-ttu-id="34c7e-113">商務用 Skype 伺服器和 Exchange Online 服務都支援相同的 SIP 網域位址空間。</span><span class="sxs-lookup"><span data-stu-id="34c7e-113">The same SIP domain address space is supported by both Skype for Business Server and the Exchange Online service.</span></span>

<span data-ttu-id="34c7e-114">使用商務用 Skype Server 管理命令介面，使用下列範例所示的參數執行**Set-CSAccessEdgeConfiguration** Cmdlet，以設定 Edge server 以進行同盟：</span><span class="sxs-lookup"><span data-stu-id="34c7e-114">Using the Skype for Business Server Management Shell, configure the Edge Server for federation by running the **Set-CSAccessEdgeConfiguration** cmdlet, using the parameters displayed in the following example:</span></span>

```powershell
Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
```

- <span data-ttu-id="34c7e-115">**AllowFederatedUsers**參數會指定是否允許內部使用者與來自同盟網域的使用者進行通訊。</span><span class="sxs-lookup"><span data-stu-id="34c7e-115">**AllowFederatedUsers** parameter specifies whether internal users are allowed to communicate with users from federated domains.</span></span> <span data-ttu-id="34c7e-116">此屬性也會判斷內部使用者是否可以使用商務用 Skype 伺服器和 Exchange Online，與共享 SIP 位址空間案例中的使用者進行通訊。</span><span class="sxs-lookup"><span data-stu-id="34c7e-116">This property also determines whether internal users can communicate with users in a shared SIP address space scenario with Skype for Business Server and Exchange Online.</span></span>

<span data-ttu-id="34c7e-117">如需使用商務用 Skype Server 管理命令介面的詳細資訊，請參閱[商務用 Skype Server 管理命令](../../manage/management-shell.md)介面。</span><span class="sxs-lookup"><span data-stu-id="34c7e-117">For details about using the Skype for Business Server Management Shell, see [Skype for Business Server Management Shell](../../manage/management-shell.md).</span></span>

## <a name="configure-a-hosting-provider-on-the-edge-server"></a><span data-ttu-id="34c7e-118">在 Edge Server 上設定裝載提供者</span><span class="sxs-lookup"><span data-stu-id="34c7e-118">Configure a Hosting Provider on the Edge Server</span></span>

<span data-ttu-id="34c7e-119">使用商務用 Skype Server 管理命令介面，使用下列範例中的參數執行**New-CsHostingProvider** Cmdlet，以在 Edge Server 上設定裝載提供者：</span><span class="sxs-lookup"><span data-stu-id="34c7e-119">Using the Skype for Business Server Management Shell, configure a hosting provider on the Edge Server by running the **New-CsHostingProvider** cmdlet, using the parameters in the following example:</span></span>

```powershell
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

> [!NOTE]
> <span data-ttu-id="34c7e-120">如果您使用的是中國在中國運作的 Microsoft 365 或 Office 365，請將此範例（"exap.um.outlook.com"）中的 ProxyFqdn 參數值取代為世紀所運作之服務的 FQDN： "exap.um.partner.outlook.cn"。</span><span class="sxs-lookup"><span data-stu-id="34c7e-120">If you are using Microsoft 365 or Office 365 operated by 21Vianet in China, replace the value for the ProxyFqdn parameter in this example ("exap.um.outlook.com") with the FQDN for the service operated by 21Vianet: "exap.um.partner.outlook.cn".</span></span> <span data-ttu-id="34c7e-121">如果您使用 Microsoft 365 或 Office 365 GCC High，請將此範例（"exap.um.outlook.com"）中的 ProxyFqdn 參數值取代為 [exap.um.office365.us] 的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="34c7e-121">If you are using Microsoft 365 or Office 365 GCC High, replace the value for the ProxyFqdn parameter in this example ("exap.um.outlook.com") with the FQDN for GCC High: “exap.um.office365.us”.</span></span>

- <span data-ttu-id="34c7e-122">**Identity**為所建立的裝載提供者指定唯一的字串值識別碼（例如，「Exchange Online」）。</span><span class="sxs-lookup"><span data-stu-id="34c7e-122">**Identity** specifies a unique string value identifier for the hosting provider that you are creating (for example, "Exchange Online").</span></span> <span data-ttu-id="34c7e-123">包含空格的值必須用雙引號括住。</span><span class="sxs-lookup"><span data-stu-id="34c7e-123">Values that contain spaces must be in double quotes.</span></span>

- <span data-ttu-id="34c7e-124">**Enabled** 會指出網域和裝載提供者之間的網路連線是否已啟用。</span><span class="sxs-lookup"><span data-stu-id="34c7e-124">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled.</span></span> <span data-ttu-id="34c7e-125">這必須設定為 True。</span><span class="sxs-lookup"><span data-stu-id="34c7e-125">This must be set to True.</span></span>

- <span data-ttu-id="34c7e-126">**EnabledSharedAddressSpace** 指出是否將以共用 SIP 位址空間案例使用裝載提供者。</span><span class="sxs-lookup"><span data-stu-id="34c7e-126">**EnabledSharedAddressSpace** indicates whether the hosting provider will be used in a shared SIP address space scenario.</span></span> <span data-ttu-id="34c7e-127">這必須設定為 True。</span><span class="sxs-lookup"><span data-stu-id="34c7e-127">This must be set to True.</span></span>

- <span data-ttu-id="34c7e-128">**HostsOCSUsers**會指出裝載提供者是否是用來主控 Office 通訊伺服器或商務用 Skype 伺服器。</span><span class="sxs-lookup"><span data-stu-id="34c7e-128">**HostsOCSUsers** indicates whether the hosting provider is used to host Office Communications Server or Skype for Business Server.</span></span> <span data-ttu-id="34c7e-129">這必須設定為 False。</span><span class="sxs-lookup"><span data-stu-id="34c7e-129">This must be set to False.</span></span>

- <span data-ttu-id="34c7e-130">**ProxyFQDN** 會指定裝載提供者所使用 Proxy 伺服器的完整網域名稱 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="34c7e-130">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider.</span></span> <span data-ttu-id="34c7e-131">針對 Exchange Online，FQDN 是 exap.um.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="34c7e-131">For Exchange Online, the FQDN is exap.um.outlook.com.</span></span>

- <span data-ttu-id="34c7e-132">**IsLocal**會指出裝載提供者所使用的 proxy 伺服器是否包含在商務用 Skype 伺服器拓撲中。</span><span class="sxs-lookup"><span data-stu-id="34c7e-132">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Skype for Business Server topology.</span></span> <span data-ttu-id="34c7e-133">這必須設定為 False。</span><span class="sxs-lookup"><span data-stu-id="34c7e-133">This must be set to False.</span></span>

- <span data-ttu-id="34c7e-134">**VerificationLevel**會指出所傳送至及傳送自裝載提供者的郵件所允許的驗證層級。</span><span class="sxs-lookup"><span data-stu-id="34c7e-134">**VerificationLevel** Indicates the verification level allowed for messages that are sent to and from the hosted provider.</span></span> <span data-ttu-id="34c7e-135">指定**UseSourceVerification**，取決於從裝載提供者傳送的郵件中所包含的驗證層級。</span><span class="sxs-lookup"><span data-stu-id="34c7e-135">Specify **UseSourceVerification**, which relies on the verification level included in messages sent from the hosting provider.</span></span> <span data-ttu-id="34c7e-136">若未指定此層級，郵件將被拒絕為無法驗證。</span><span class="sxs-lookup"><span data-stu-id="34c7e-136">If this level is not specified, the message will be rejected as being unverifiable.</span></span>

## <a name="verify-replication-of-the-updated-central-management-store"></a><span data-ttu-id="34c7e-137">驗證更新的中央管理存放區複寫</span><span class="sxs-lookup"><span data-stu-id="34c7e-137">Verify Replication of the Updated Central Management Store</span></span>

<span data-ttu-id="34c7e-138">您在上述各節中使用 Cmdlet 所做的變更，會自動套用至 Edge Server，通常需要不到一分鐘才能進行複製。</span><span class="sxs-lookup"><span data-stu-id="34c7e-138">The changes you made by using the cmdlets in the preceding sections are automatically applied to the Edge Server, and generally take less than a minute to replicate.</span></span> <span data-ttu-id="34c7e-139">您可以驗證複寫狀態，然後使用下列 Cmdlet，確認是否已將變更套用至 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="34c7e-139">You can validate replication status, and then confirm that the changes were applied to your Edge Server by using the following cmdlets.</span></span>

<span data-ttu-id="34c7e-140">若要驗證複寫更新，請在商務用 Skype Server 部署的內部伺服器上，執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="34c7e-140">To verify replication updates, on a server internal in your Skype for Business Server deployment, run the following cmdlet:</span></span>

```powershell
Get-CsManagementStoreReplicationStatus
```
<span data-ttu-id="34c7e-141">檢查是否所有複本的 UpToDate 值都顯示為 TRUE。</span><span class="sxs-lookup"><span data-stu-id="34c7e-141">Check if UpToDate value is showing TRUE for all Replicas.</span></span>

<span data-ttu-id="34c7e-142">若要確認是否已套用變更，請在 Edge Server 上執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="34c7e-142">To confirm that the changes were applied, on the Edge Server, run the following cmdlet:</span></span>

```powershell
Get-CsHostingProvider -LocalStore
```
<span data-ttu-id="34c7e-143">請仔細檢查所顯示的資訊是否符合先前步驟中認可的變更。</span><span class="sxs-lookup"><span data-stu-id="34c7e-143">Double check if the information shown matches the changes committed in the previous steps.</span></span>

## <a name="see-also"></a><span data-ttu-id="34c7e-144">另請參閱</span><span class="sxs-lookup"><span data-stu-id="34c7e-144">See also</span></span>

[<span data-ttu-id="34c7e-145">在主控 Exchange UM 上供應商務用 Skype Server 使用者語音信箱</span><span class="sxs-lookup"><span data-stu-id="34c7e-145">Providing Skype for Business Server users voice mail on hosted Exchange UM</span></span>](https://technet.microsoft.com/library/306d3fb5-231b-4f0b-b8d8-0d9083b5ed77.aspx)

[<span data-ttu-id="34c7e-146">商務用 Skype Server 中的主控 Exchange 整合通訊整合</span><span class="sxs-lookup"><span data-stu-id="34c7e-146">Hosted Exchange Unified Messaging integration in Skype for Business Server</span></span>](https://technet.microsoft.com/library/f4de0165-da3b-499e-98fc-28ddd0db02d5.aspx)
