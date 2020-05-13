---
title: 設定內部部署 Lync Server 與 Exchange Online 整合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring on-premises Lync Server integration with Exchange Online
ms:assetid: 95a20117-2064-43c4-94fe-cac892cadb6f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh533880(v=OCS.15)
ms:contentKeyID: 48184900
ms.date: 03/30/2018
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60cfa8caa0aa2cb7dac704123f2a099bd305aed5
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/13/2020
ms.locfileid: "44219663"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-on-premises-lync-server-2013-integration-with-exchange-online"></a><span data-ttu-id="8270f-102">設定內部部署 Lync Server 2013 與 Exchange Online 整合</span><span class="sxs-lookup"><span data-stu-id="8270f-102">Configuring on-premises Lync Server 2013 integration with Exchange Online</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8270f-103">_**主題上次修改日期：** 2018-03-30_</span><span class="sxs-lookup"><span data-stu-id="8270f-103">_**Topic Last Modified:** 2018-03-30_</span></span>

<span data-ttu-id="8270f-104">使用內部部署 Lync Server 2013 部署的客戶可以在混合式部署模式中，設定 microsoft Exchange Online 中 Microsoft Outlook Web App 的互通性。</span><span class="sxs-lookup"><span data-stu-id="8270f-104">Customers who are using on-premises Lync Server 2013 deployments can configure interoperability with Microsoft Outlook Web App in Microsoft Exchange Online in a hybrid deployment mode.</span></span> <span data-ttu-id="8270f-105">互通性功能包括 Outlook Web App 介面的單一登入和立即訊息（IM）和目前狀態整合。</span><span class="sxs-lookup"><span data-stu-id="8270f-105">Interoperability features include single sign on and instant messaging (IM) and presence integration with the Outlook Web App interface.</span></span> <span data-ttu-id="8270f-106">若要啟用此整合，您必須完成下列工作，以在您的內部部署 Lync Server 部署中設定 Edge Server：</span><span class="sxs-lookup"><span data-stu-id="8270f-106">To enable this integration, you must configure the Edge Server in your on-premises Lync Server deployment by completing the following tasks:</span></span>

  - <span data-ttu-id="8270f-107">設定共用 SIP 位址空間</span><span class="sxs-lookup"><span data-stu-id="8270f-107">Configure a shared SIP address space</span></span>

  - <span data-ttu-id="8270f-108">在 Edge Server 上設定裝載提供者</span><span class="sxs-lookup"><span data-stu-id="8270f-108">Configure a hosting provider on the Edge Server</span></span>

  - <span data-ttu-id="8270f-109">驗證更新的中央管理存放區複寫</span><span class="sxs-lookup"><span data-stu-id="8270f-109">Verify replication of the updated Central Management store</span></span>

<span data-ttu-id="8270f-110">如果 Lync Server 2013 與 Exchange Online 整合，嘗試從 OWA 登入 IM 的使用者被視為遠端或外部使用者。</span><span class="sxs-lookup"><span data-stu-id="8270f-110">If Lync Server 2013 is integrated with Exchange Online, a user who is trying to sign in to IM from OWA is considered a remote or external user.</span></span> <span data-ttu-id="8270f-111">在此案例中，此使用者必須已被指派具有下列選項的外部存取原則：</span><span class="sxs-lookup"><span data-stu-id="8270f-111">In this scenario, this user must have an external access policy assigned that has the following option selected:</span></span>

<span data-ttu-id="8270f-112">**啟用與遠端使用者的通訊**</span><span class="sxs-lookup"><span data-stu-id="8270f-112">**Enable communications with remote users**</span></span>

<span data-ttu-id="8270f-113">如果您想要在您的組織中的使用者（例如出差的遠端辦公和使用者）可以透過網際網路連線至 Lync Server，請啟用此選項。</span><span class="sxs-lookup"><span data-stu-id="8270f-113">Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Lync Server over the Internet.</span></span>

<span data-ttu-id="8270f-114">如需詳細資訊，請參閱[Manage external access policy In Lync Server 2013](lync-server-2013-manage-external-access-policy-for-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="8270f-114">For more information, see [Manage external access policy in Lync Server 2013](lync-server-2013-manage-external-access-policy-for-your-organization.md).</span></span>

<div>

## <a name="configure-a-shared-sip-address-space"></a><span data-ttu-id="8270f-115">設定共用 SIP 位址空間</span><span class="sxs-lookup"><span data-stu-id="8270f-115">Configure a Shared SIP Address Space</span></span>

<span data-ttu-id="8270f-116">若要將內部部署的 Lync Server 2013 與 Exchange Online 整合，您必須設定共用 SIP 位址空間。</span><span class="sxs-lookup"><span data-stu-id="8270f-116">To integrate on-premises Lync Server 2013 with Exchange Online, you must configure a shared SIP address space.</span></span> <span data-ttu-id="8270f-117">Lync Server 和 Exchange Online 服務都支援相同的 SIP 網域位址空間。</span><span class="sxs-lookup"><span data-stu-id="8270f-117">The same SIP domain address space is supported by both Lync Server and the Exchange Online service.</span></span>

<span data-ttu-id="8270f-118">使用 Lync Server 管理命令介面，使用下列範例所示的參數執行**Set-CSAccessEdgeConfiguration** Cmdlet，以設定 Edge server 以進行同盟：</span><span class="sxs-lookup"><span data-stu-id="8270f-118">Using the Lync Server Management Shell, configure the Edge Server for federation by running the **Set-CSAccessEdgeConfiguration** cmdlet, using the parameters that are displayed in the following example:</span></span>

    Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

  - <span data-ttu-id="8270f-119">**AllowFederatedUsers** 指定是否允許內部使用者與同盟網域的使用者進行通訊。</span><span class="sxs-lookup"><span data-stu-id="8270f-119">**AllowFederatedUsers** specifies whether internal users are allowed to communicate with users from federated domains.</span></span> <span data-ttu-id="8270f-120">此屬性也會判斷內部使用者是否可以使用 Lync Server 和 Exchange Online，與共享 SIP 位址空間案例中的使用者進行通訊。</span><span class="sxs-lookup"><span data-stu-id="8270f-120">This property also determines whether internal users can communicate with users in a shared SIP address space scenario with Lync Server and Exchange Online.</span></span>

<span data-ttu-id="8270f-121">如需如何使用 Lync Server 管理命令介面的詳細資訊，請參閱[Lync server 2013 管理命令](lync-server-2013-lync-server-management-shell.md)介面。</span><span class="sxs-lookup"><span data-stu-id="8270f-121">For details about how to use the Lync Server Management Shell, see [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).</span></span>

</div>

<div>

## <a name="configure-a-hosting-provider-on-the-edge-server"></a><span data-ttu-id="8270f-122">在 Edge Server 上設定裝載提供者</span><span class="sxs-lookup"><span data-stu-id="8270f-122">Configure a Hosting Provider on the Edge Server</span></span>

<span data-ttu-id="8270f-123">使用 Lync Server 管理命令介面，在 Edge Server 上設定裝載提供者。</span><span class="sxs-lookup"><span data-stu-id="8270f-123">Use the Lync Server Management Shell to configure a hosting provider on the Edge Server.</span></span> <span data-ttu-id="8270f-124">若要這麼做，請使用下列範例中的參數執行**New-CsHostingProvider** Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="8270f-124">To do this, run the **New-CsHostingProvider** cmdlet, using the parameters in the following example:</span></span>

    New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification

<div>


> [!NOTE]
> <span data-ttu-id="8270f-125">如果您使用中國運作的 Office 365，請將此範例（"exap.um.outlook.com"）中的<STRONG>ProxyFqdn</STRONG>參數值取代為世紀所運作之服務的 FQDN： "exap.um.partner.outlook.cn"。</span><span class="sxs-lookup"><span data-stu-id="8270f-125">If you are using Office 365 operated by 21Vianet in China, replace the value for the <STRONG>ProxyFqdn</STRONG> parameter in this example ("exap.um.outlook.com") with the FQDN for the service operated by 21Vianet: "exap.um.partner.outlook.cn".</span></span>



</div>

  - <span data-ttu-id="8270f-126">**Identity**為所建立的裝載提供者指定唯一的字串值識別碼（例如，「Exchange Online」）。</span><span class="sxs-lookup"><span data-stu-id="8270f-126">**Identity** specifies a unique string value identifier for the hosting provider that you are creating (for example, "Exchange Online").</span></span> <span data-ttu-id="8270f-127">包含空格的值必須用雙引號括住。</span><span class="sxs-lookup"><span data-stu-id="8270f-127">Values that contain spaces must be in double quotation marks.</span></span>

  - <span data-ttu-id="8270f-128">**Enabled** 會指出網域和裝載提供者之間的網路連線是否已啟用。</span><span class="sxs-lookup"><span data-stu-id="8270f-128">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled.</span></span> <span data-ttu-id="8270f-129">這必須設定為**True**。</span><span class="sxs-lookup"><span data-stu-id="8270f-129">This must be set to **True**.</span></span>

  - <span data-ttu-id="8270f-130">**EnabledSharedAddressSpace** 指出是否將以共用 SIP 位址空間案例使用裝載提供者。</span><span class="sxs-lookup"><span data-stu-id="8270f-130">**EnabledSharedAddressSpace** indicates whether the hosting provider will be used in a shared SIP address space scenario.</span></span> <span data-ttu-id="8270f-131">這必須設定為**True**。</span><span class="sxs-lookup"><span data-stu-id="8270f-131">This must be set to **True**.</span></span>

  - <span data-ttu-id="8270f-132">**HostsOCSUsers**會指出裝載提供者是否是用來主控 Office 通訊伺服器或 Lync server。</span><span class="sxs-lookup"><span data-stu-id="8270f-132">**HostsOCSUsers** indicates whether the hosting provider is used to host Office Communications Server or Lync Server.</span></span> <span data-ttu-id="8270f-133">這必須設定為**False**。</span><span class="sxs-lookup"><span data-stu-id="8270f-133">This must be set to **False**.</span></span>

  - <span data-ttu-id="8270f-134">**ProxyFQDN** 會指定裝載提供者所使用 Proxy 伺服器的完整網域名稱 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="8270f-134">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider.</span></span> <span data-ttu-id="8270f-135">針對 Exchange Online，FQDN 是 exap.um.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="8270f-135">For Exchange Online, the FQDN is exap.um.outlook.com.</span></span>

  - <span data-ttu-id="8270f-136">**IsLocal**指出主控提供者所使用的 proxy 伺服器是否包含在 Lync server 拓撲中。</span><span class="sxs-lookup"><span data-stu-id="8270f-136">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Lync Server topology.</span></span> <span data-ttu-id="8270f-137">這必須設定為**False**。</span><span class="sxs-lookup"><span data-stu-id="8270f-137">This must be set to **False**.</span></span>

  - <span data-ttu-id="8270f-138">**VerificationLevel**表示所傳送的郵件所允許的驗證層級提供者。</span><span class="sxs-lookup"><span data-stu-id="8270f-138">**VerificationLevel** indicates the verification level allowed for messages that are sent to and from the hosted provider.</span></span> <span data-ttu-id="8270f-139">指定**UseSourceVerification**。</span><span class="sxs-lookup"><span data-stu-id="8270f-139">Specify **UseSourceVerification**.</span></span> <span data-ttu-id="8270f-140">此選項取決於從裝載提供者傳送的郵件中所包含的驗證層級。</span><span class="sxs-lookup"><span data-stu-id="8270f-140">This option relies on the verification level that is included in messages that are sent from the hosting provider.</span></span> <span data-ttu-id="8270f-141">若未指定此層級，郵件將被拒絕為無法驗證。</span><span class="sxs-lookup"><span data-stu-id="8270f-141">If this level is not specified, the message will be rejected as being unverifiable.</span></span>

</div>

<div>

## <a name="verify-replication-of-the-updated-central-management-store"></a><span data-ttu-id="8270f-142">驗證更新的中央管理存放區複寫</span><span class="sxs-lookup"><span data-stu-id="8270f-142">Verify Replication of the Updated Central Management Store</span></span>

<span data-ttu-id="8270f-143">您使用上述各節中的 Cmdlet 所做的變更，會自動套用至 Edge Server，而且通常會在一分鐘內進行複製。</span><span class="sxs-lookup"><span data-stu-id="8270f-143">The changes that you made by using the cmdlets in the preceding sections are automatically applied to the Edge Server, and generally take less than one minute to replicate.</span></span> <span data-ttu-id="8270f-144">您可以使用下列 Cmdlet 來驗證複寫狀態，以及是否已將變更套用至 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="8270f-144">You can verify the replication status and that the changes were applied to your Edge Server by using the following cmdlets.</span></span>

<span data-ttu-id="8270f-145">若要驗證 Lync Server 部署中內部伺服器的複寫更新，請執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="8270f-145">To verify replication updates on a server internal in your Lync Server deployment, run the following cmdlet:</span></span>

    Get-CsManagementStoreReplicationStatus

<span data-ttu-id="8270f-146">若要確認是否已套用變更，請在 Edge Server 上執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="8270f-146">To verify that the changes were applied, run the following cmdlet on the Edge Server:</span></span>

    Get-CsHostingProvider -LocalStore

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8270f-147">另請參閱</span><span class="sxs-lookup"><span data-stu-id="8270f-147">See Also</span></span>


[<span data-ttu-id="8270f-148">在主控 Exchange UM 上提供 Lync Server 2013 使用者語音信箱</span><span class="sxs-lookup"><span data-stu-id="8270f-148">Providing Lync Server 2013 users voice mail on hosted Exchange UM</span></span>](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md)  
[<span data-ttu-id="8270f-149">Lync Server 2013 中的主控 Exchange 整合通訊整合</span><span class="sxs-lookup"><span data-stu-id="8270f-149">Hosted Exchange Unified Messaging integration in Lync Server 2013</span></span>](lync-server-2013-hosted-exchange-unified-messaging-integration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>
