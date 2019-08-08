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
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 95a20117-2064-43c4-94fe-cac892cadb6f
description: '摘要: 整合商務用 Skype Server 和 Outlook Web App。'
ms.openlocfilehash: b7c279dc41515d9613d8c000ab9e81164a1ccaa6
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244207"
---
# <a name="configure-integration-between-on-premises-skype-for-business-server-and-outlook-web-app"></a><span data-ttu-id="cf730-103">設定內部部署商務用 Skype Server 和 Outlook Web App 之間的整合</span><span class="sxs-lookup"><span data-stu-id="cf730-103">Configure integration between on-premises Skype for Business Server and Outlook Web App</span></span>

<span data-ttu-id="cf730-104">**摘要:** 整合商務用 Skype Server 和 Outlook Web App。</span><span class="sxs-lookup"><span data-stu-id="cf730-104">**Summary:** Integrate Skype for Business Server and Outlook Web App.</span></span>

<span data-ttu-id="cf730-105">使用內部部署商務用 Skype 伺服器部署的客戶, 可以使用混合式部署模式, 在 Microsoft Exchange Online 的 microsoft Outlook Web App 中設定互通性。</span><span class="sxs-lookup"><span data-stu-id="cf730-105">Customers who are using on-premises Skype for Business Server deployments can configure interoperability with Microsoft Outlook Web App in Microsoft Exchange Online in a hybrid deployment mode.</span></span> <span data-ttu-id="cf730-106">互通性功能包括單一登入與立即訊息 (IM), 以及與 Outlook Web App 介面的目前狀態整合。</span><span class="sxs-lookup"><span data-stu-id="cf730-106">Interoperability features include single sign on and instant messaging (IM) and presence integration with the Outlook Web App interface.</span></span> <span data-ttu-id="cf730-107">若要啟用此整合, 您必須完成下列工作, 才能在內部部署商務用 Skype Server 部署中設定 Edge 伺服器:</span><span class="sxs-lookup"><span data-stu-id="cf730-107">To enable this integration, you must configure the Edge Server in your on-premises Skype for Business Server deployment by completing the following tasks:</span></span>

- <span data-ttu-id="cf730-108">設定共用的 SIP 位址空間</span><span class="sxs-lookup"><span data-stu-id="cf730-108">Configure a shared SIP address space</span></span>

- <span data-ttu-id="cf730-109">在 Edge 伺服器上設定主機服務提供者</span><span class="sxs-lookup"><span data-stu-id="cf730-109">Configure a hosting provider on the Edge Server</span></span>

- <span data-ttu-id="cf730-110">驗證已更新的中央管理存放區的複製</span><span class="sxs-lookup"><span data-stu-id="cf730-110">Verify replication of the updated Central Management store</span></span>

## <a name="configure-a-shared-sip-address-space"></a><span data-ttu-id="cf730-111">設定共用的 SIP 位址空間</span><span class="sxs-lookup"><span data-stu-id="cf730-111">Configure a Shared SIP Address Space</span></span>

<span data-ttu-id="cf730-112">若要將內部部署商務用 Skype 伺服器與 Exchange Online 整合, 您必須設定共用的 SIP 位址空間。</span><span class="sxs-lookup"><span data-stu-id="cf730-112">To integrate on-premises Skype for Business Server with Exchange Online, you must configure a shared SIP address space.</span></span> <span data-ttu-id="cf730-113">商務用 Skype Server 和 Exchange Online 服務都支援相同的 SIP 網域位址空間。</span><span class="sxs-lookup"><span data-stu-id="cf730-113">The same SIP domain address space is supported by both Skype for Business Server and the Exchange Online service.</span></span>

<span data-ttu-id="cf730-114">使用商務用 Skype Server Management Shell, 透過執行**CSAccessEdgeConfiguration** Cmdlet 來設定同盟的 Edge 伺服器, 方法是使用下列範例所示的參數:</span><span class="sxs-lookup"><span data-stu-id="cf730-114">Using the Skype for Business Server Management Shell, configure the Edge Server for federation by running the **Set-CSAccessEdgeConfiguration** cmdlet, using the parameters displayed in the following example:</span></span>

```
Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
```

- <span data-ttu-id="cf730-115">**AllowFederatedUsers**參數指定是否允許內部使用者與來自聯盟網域的使用者進行通訊。</span><span class="sxs-lookup"><span data-stu-id="cf730-115">**AllowFederatedUsers** parameter specifies whether internal users are allowed to communicate with users from federated domains.</span></span> <span data-ttu-id="cf730-116">這個屬性也會判斷內部使用者是否可以使用商務用 Skype Server 和 Exchange Online, 在共用的 SIP 位址空間案例中與使用者進行通訊。</span><span class="sxs-lookup"><span data-stu-id="cf730-116">This property also determines whether internal users can communicate with users in a shared SIP address space scenario with Skype for Business Server and Exchange Online.</span></span>

<span data-ttu-id="cf730-117">如需使用商務用 Skype Server Management 命令介面的詳細資料, 請參閱[商務用 Skype Server 管理命令](../../manage/management-shell.md)介面。</span><span class="sxs-lookup"><span data-stu-id="cf730-117">For details about using the Skype for Business Server Management Shell, see [Skype for Business Server Management Shell](../../manage/management-shell.md).</span></span>

## <a name="configure-a-hosting-provider-on-the-edge-server"></a><span data-ttu-id="cf730-118">在 Edge 伺服器上設定主機服務提供者</span><span class="sxs-lookup"><span data-stu-id="cf730-118">Configure a Hosting Provider on the Edge Server</span></span>

<span data-ttu-id="cf730-119">使用商務用 Skype Server Management Shell, 透過執行**CsHostingProvider** Cmdlet, 在 Edge 伺服器上設定主機服務提供者, 方法是使用下列範例中的參數:</span><span class="sxs-lookup"><span data-stu-id="cf730-119">Using the Skype for Business Server Management Shell, configure a hosting provider on the Edge Server by running the **New-CsHostingProvider** cmdlet, using the parameters in the following example:</span></span>

```
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

> [!NOTE]
> <span data-ttu-id="cf730-120">如果您使用的是中國由世紀運營的 Office 365, 請將此範例 ("exap.um.outlook.com") 中 ProxyFqdn 參數的值, 以由世紀運營的服務 FQDN 取代 ("exap.um.partner.outlook.cn")。</span><span class="sxs-lookup"><span data-stu-id="cf730-120">If you are using Office 365 operated by 21Vianet in China, replace the value for the ProxyFqdn parameter in this example ("exap.um.outlook.com") with the FQDN for the service operated by 21Vianet: "exap.um.partner.outlook.cn".</span></span> <span data-ttu-id="cf730-121">如果您使用的是 Office 365 GCC 高版, 請將此範例 ("exap.um.outlook.com") 中的 ProxyFqdn 參數值取代為 [exap.um.office365.us] 的 FQDN: ""。</span><span class="sxs-lookup"><span data-stu-id="cf730-121">If you are using Office 365 GCC High, replace the value for the ProxyFqdn parameter in this example ("exap.um.outlook.com") with the FQDN for GCC High: “exap.um.office365.us”.</span></span>

- <span data-ttu-id="cf730-122">身分**識別**會為您建立的主機服務提供者指定唯一的字串值識別碼 (例如, 「Exchange Online」)。</span><span class="sxs-lookup"><span data-stu-id="cf730-122">**Identity** specifies a unique string value identifier for the hosting provider that you are creating (for example, "Exchange Online").</span></span> <span data-ttu-id="cf730-123">包含空格的值必須以雙引號括住。</span><span class="sxs-lookup"><span data-stu-id="cf730-123">Values that contain spaces must be in double quotes.</span></span>

- <span data-ttu-id="cf730-124">\*\*Enabled \*\* 指出網域與裝載提供者之間的網路連線是否已啟用。</span><span class="sxs-lookup"><span data-stu-id="cf730-124">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled.</span></span> <span data-ttu-id="cf730-125">這必須設定為 True。</span><span class="sxs-lookup"><span data-stu-id="cf730-125">This must be set to True.</span></span>

- <span data-ttu-id="cf730-126">**EnabledSharedAddressSpace**表示主機服務提供者是否將用於共用的 SIP 位址空間案例中。</span><span class="sxs-lookup"><span data-stu-id="cf730-126">**EnabledSharedAddressSpace** indicates whether the hosting provider will be used in a shared SIP address space scenario.</span></span> <span data-ttu-id="cf730-127">這必須設定為 True。</span><span class="sxs-lookup"><span data-stu-id="cf730-127">This must be set to True.</span></span>

- <span data-ttu-id="cf730-128">**HostsOCSUsers**表示主機服務提供者是用來託管 Office 通訊伺服器或商務用 Skype 伺服器。</span><span class="sxs-lookup"><span data-stu-id="cf730-128">**HostsOCSUsers** indicates whether the hosting provider is used to host Office Communications Server or Skype for Business Server.</span></span> <span data-ttu-id="cf730-129">必須將它設為 False。</span><span class="sxs-lookup"><span data-stu-id="cf730-129">This must be set to False.</span></span>

- <span data-ttu-id="cf730-130">**ProxyFQDN**指定主機提供者所使用之 proxy 伺服器的完整功能變數名稱 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="cf730-130">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider.</span></span> <span data-ttu-id="cf730-131">針對 Exchange Online, FQDN 是 exap.um.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="cf730-131">For Exchange Online, the FQDN is exap.um.outlook.com.</span></span>

- <span data-ttu-id="cf730-132">**IsLocal**表示主機服務提供者所使用的 proxy 伺服器是否包含在您的商務用 Skype 伺服器拓撲中。</span><span class="sxs-lookup"><span data-stu-id="cf730-132">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Skype for Business Server topology.</span></span> <span data-ttu-id="cf730-133">必須將它設為 False。</span><span class="sxs-lookup"><span data-stu-id="cf730-133">This must be set to False.</span></span>

- <span data-ttu-id="cf730-134">**VerificationLevel**表示傳送到託管提供者的訊息所允許的驗證層級。</span><span class="sxs-lookup"><span data-stu-id="cf730-134">**VerificationLevel** Indicates the verification level allowed for messages that are sent to and from the hosted provider.</span></span> <span data-ttu-id="cf730-135">指定 **UseSourceVerification**，其依賴包含在裝載提供者發出之訊息內的驗證層級。</span><span class="sxs-lookup"><span data-stu-id="cf730-135">Specify **UseSourceVerification**, which relies on the verification level included in messages sent from the hosting provider.</span></span> <span data-ttu-id="cf730-136">如果未指定此等級, 郵件將會因無法驗證而遭到拒絕。</span><span class="sxs-lookup"><span data-stu-id="cf730-136">If this level is not specified, the message will be rejected as being unverifiable.</span></span>

## <a name="verify-replication-of-the-updated-central-management-store"></a><span data-ttu-id="cf730-137">驗證已更新的中央管理存放區的複製</span><span class="sxs-lookup"><span data-stu-id="cf730-137">Verify Replication of the Updated Central Management Store</span></span>

<span data-ttu-id="cf730-138">您在前面章節中使用 Cmdlet 所做的變更, 會自動套用至 Edge 伺服器, 且通常需要不到一分鐘的時間來複製。</span><span class="sxs-lookup"><span data-stu-id="cf730-138">The changes you made by using the cmdlets in the preceding sections are automatically applied to the Edge Server, and generally take less than a minute to replicate.</span></span> <span data-ttu-id="cf730-139">您可以驗證複製狀態, 然後使用下列 Cmdlet 確認已將變更套用至 Edge 伺服器。</span><span class="sxs-lookup"><span data-stu-id="cf730-139">You can validate replication status, and then confirm that the changes were applied to your Edge Server by using the following cmdlets.</span></span>

<span data-ttu-id="cf730-140">若要驗證複製更新, 請在商務用 Skype Server 部署的內部伺服器上, 執行下列 Cmdlet:</span><span class="sxs-lookup"><span data-stu-id="cf730-140">To verify replication updates, on a server internal in your Skype for Business Server deployment, run the following cmdlet:</span></span>

```
Get-CsManagementStoreReplicationStatus
```
<span data-ttu-id="cf730-141">檢查 UpToDate 值是否針對所有複本顯示 TRUE。</span><span class="sxs-lookup"><span data-stu-id="cf730-141">Check if UpToDate value is showing TRUE for all Replicas.</span></span>

<span data-ttu-id="cf730-142">若要確認已套用變更, 請在 Edge 伺服器上執行下列 Cmdlet:</span><span class="sxs-lookup"><span data-stu-id="cf730-142">To confirm that the changes were applied, on the Edge Server, run the following cmdlet:</span></span>

```
Get-CsHostingProvider -LocalStore
```
<span data-ttu-id="cf730-143">請仔細檢查所顯示的資訊是否符合先前步驟中所提交的變更。</span><span class="sxs-lookup"><span data-stu-id="cf730-143">Double check if the information shown matches the changes committed in the previous steps.</span></span>

## <a name="see-also"></a><span data-ttu-id="cf730-144">另請參閱</span><span class="sxs-lookup"><span data-stu-id="cf730-144">See also</span></span>

[<span data-ttu-id="cf730-145">供應商務用 Skype Server 使用者在託管 Exchange UM 上的語音信箱</span><span class="sxs-lookup"><span data-stu-id="cf730-145">Providing Skype for Business Server users voice mail on hosted Exchange UM</span></span>](https://technet.microsoft.com/library/306d3fb5-231b-4f0b-b8d8-0d9083b5ed77.aspx)

[<span data-ttu-id="cf730-146">商務用 Skype Server 中的託管 Exchange 整合訊息整合</span><span class="sxs-lookup"><span data-stu-id="cf730-146">Hosted Exchange Unified Messaging integration in Skype for Business Server</span></span>](https://technet.microsoft.com/library/f4de0165-da3b-499e-98fc-28ddd0db02d5.aspx)
