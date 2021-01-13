---
title: 管理組織的外部存取原則
ms.reviewer: ''
ms:assetid: 5571811e-34c8-443a-b94c-1ab5d4275581
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520995(v=OCS.15)
ms:contentKeyID: 48184160
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 部署一或多部 Edge Server 之後，您必須為組織啟用將支援的外部存取類型。
ms.openlocfilehash: 71797e865860107d23095659461c1b02e6d47cd7
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817253"
---
# <a name="manage-external-access-policy-for-your-organization"></a><span data-ttu-id="d8cfc-103">管理組織的外部存取原則</span><span class="sxs-lookup"><span data-stu-id="d8cfc-103">Manage external access policy for your organization</span></span>

<span data-ttu-id="d8cfc-104">部署一或多部 Edge Server 之後，您必須為組織啟用將支援的外部存取類型。</span><span class="sxs-lookup"><span data-stu-id="d8cfc-104">After deploying one or more Edge Servers, you must enable the types of external access that will be supported for your organization.</span></span>

<span data-ttu-id="d8cfc-p101">依預設，不會將任何原則設定為支援外部使用者存取 (包括遠端使用者存取、同盟網域使用者存取)，即使您已經為組織啟用外部使用者存取支援也一樣。若要控制外部使用者存取的使用，您必須設定一或多個原則，並為每個原則指定支援的外部使用者存取類型。您可以使用下列原則範圍來進行建立和設定。預設會建立全域原則，但無法加以刪除。</span><span class="sxs-lookup"><span data-stu-id="d8cfc-p101">By default, there are no policies configured to support external user access, including remote user access, federated user access, even if you have already enabled external user access support for your organization. To control the use of external user access, you must configure one or more policies, specifying the type of external user access supported for each policy. The following policy scopes are available for creation and configuration. By default, the Global policy is created, but cannot be deleted.</span></span>

  - <span data-ttu-id="d8cfc-109">**全域原則**   當您部署 Edge Server 時，就會建立全域原則。</span><span class="sxs-lookup"><span data-stu-id="d8cfc-109">**Global policy**   The global policy is created when you deploy your Edge Servers.</span></span> <span data-ttu-id="d8cfc-110">根據預設，全域原則中不會啟用任何外部使用者存取選項。</span><span class="sxs-lookup"><span data-stu-id="d8cfc-110">By default, no external user access options are enabled in the global policy.</span></span> <span data-ttu-id="d8cfc-111">若要在全域層級支援外部使用者存取，您可以設定全域原則來支援一或多個類型的外部使用者存取選項。</span><span class="sxs-lookup"><span data-stu-id="d8cfc-111">To support external user access at the global level, you configure the global policy to support one or more types of external user access options.</span></span> <span data-ttu-id="d8cfc-112">全域原則適用於組織中的所有使用者，但是網站原則和使用者原則會覆寫全域原則。</span><span class="sxs-lookup"><span data-stu-id="d8cfc-112">The global policy applies to all users in your organization, but site policies and user policies override the global policy.</span></span> <span data-ttu-id="d8cfc-113">如果您刪除全域原則，不會將它移除。</span><span class="sxs-lookup"><span data-stu-id="d8cfc-113">If you delete the global policy, you do not remove it.</span></span> <span data-ttu-id="d8cfc-114">而是會將它重設為預設值。</span><span class="sxs-lookup"><span data-stu-id="d8cfc-114">Instead, you reset it to the default setting.</span></span>

  - <span data-ttu-id="d8cfc-115">**網站原則**   您可以建立及設定一或多個網站原則，以限制對特定網站的外部使用者存取的支援。</span><span class="sxs-lookup"><span data-stu-id="d8cfc-115">**Site policy**   You can create and configure one or more site policies to limit support for external user access to specific sites.</span></span> <span data-ttu-id="d8cfc-116">網站原則中的設定會覆寫全域原則，但僅限於該網站原則所涵蓋的特定網站。</span><span class="sxs-lookup"><span data-stu-id="d8cfc-116">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span> <span data-ttu-id="d8cfc-117">例如，如果您在全域原則中啟用了遠端使用者存取，您可以指定網站原則以對特定網站停用遠端使用者存取。</span><span class="sxs-lookup"><span data-stu-id="d8cfc-117">For example, if you enable remote user access in the global policy, you might specify a site policy that disables remote user access for a specific site.</span></span> <span data-ttu-id="d8cfc-118">根據預設，網站原則會套用至該網站的所有使用者，但您可以指派使用者原則給個別使用者，以覆寫網站原則設定。</span><span class="sxs-lookup"><span data-stu-id="d8cfc-118">By default, a site policy is applied to all users of that site, but you can assign a user policy to a user to override the site policy setting.</span></span>

  - <span data-ttu-id="d8cfc-119">**使用者原則**   您可以建立及設定一或多個使用者原則，以限制對特定使用者的遠端使用者存取的支援。</span><span class="sxs-lookup"><span data-stu-id="d8cfc-119">**User policy**   You can create and configure one or more user policies to limit support for remote user access to specific users.</span></span> <span data-ttu-id="d8cfc-120">使用者原則中的設定會覆寫全域與網站原則，但僅限於該使用者原則指派的特定使用者。</span><span class="sxs-lookup"><span data-stu-id="d8cfc-120">The configuration in the user policy overrides the global and site policy, but only for the specific users to whom the user policy is assigned.</span></span> <span data-ttu-id="d8cfc-121">例如，如果您在全域原則和網站原則中啟用了遠端使用者存取，您可以指定使用者原則以停用遠端使用者存取，然後將該使用者原則指派給特定使用者。</span><span class="sxs-lookup"><span data-stu-id="d8cfc-121">For example, if you enable remote user access in the global policy and site policy, you might specify a user policy that disables remote user access and then assign that user policy to specific users.</span></span> <span data-ttu-id="d8cfc-122">如果您建立使用者原則，必須將其套用至一或多個使用者，該原則才能生效。</span><span class="sxs-lookup"><span data-stu-id="d8cfc-122">If you create a user policy, you must apply it to one or more users before it takes effect.</span></span>


> [!IMPORTANT]  
> <span data-ttu-id="d8cfc-123">在一個原則層級套用的原則設定，可以覆寫在另一個原則層級套用的設定。</span><span class="sxs-lookup"><span data-stu-id="d8cfc-123">Policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="d8cfc-124">商務用 Skype Server 原則優先順序為：使用者原則 (影響最大) 會覆寫網站原則，然後網站原則會覆寫全域原則 (影響最小)。</span><span class="sxs-lookup"><span data-stu-id="d8cfc-124">Skype for Business Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="d8cfc-125">也就是說，原則設定愈接近原則影響的物件，對物件所造成的影響也越大。</span><span class="sxs-lookup"><span data-stu-id="d8cfc-125">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>


<span data-ttu-id="d8cfc-126">這些選項包括下列類型的外部存取：</span><span class="sxs-lookup"><span data-stu-id="d8cfc-126">These options include the following types of external access:</span></span>

  - <span data-ttu-id="d8cfc-127">**啟用與同盟使用者的通訊**   如果您想要支援使用者對同盟夥伴網域的存取，請啟用此功能。</span><span class="sxs-lookup"><span data-stu-id="d8cfc-127">**Enable communications with federated users**   Enable this if you want to support user access to federated partner domains.</span></span> <span data-ttu-id="d8cfc-128">此設定會設定使用者與其他 SIP 同盟網域通訊的能力，以及主控的提供者，如 Microsoft 365 或 Office 365。</span><span class="sxs-lookup"><span data-stu-id="d8cfc-128">This setting configures the ability for users to communicate with other SIP federated domains, as well as Hosted providers like Microsoft 365 or Office 365.</span></span> 


  - <span data-ttu-id="d8cfc-129">**啟用與遠端使用者的通訊**   如果您想要在您的組織中的使用者（如已旅行的遠端辦公和使用者）可以透過網際網路連線至商務用 Skype Server，請啟用此選項。</span><span class="sxs-lookup"><span data-stu-id="d8cfc-129">**Enable communications with remote users**   Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Skype for Business Server over the Internet.</span></span>

  - <span data-ttu-id="d8cfc-130">**啟用與公用使用者的通訊**   如果您希望內部使用者能夠與公用 IM 提供者連絡人通訊，請啟用此選項。</span><span class="sxs-lookup"><span data-stu-id="d8cfc-130">**Enable communications with public users**   Enable this option if you want internal users to be able to communicate with public IM provider contacts.</span></span>
   

> [!NOTE]  
> <span data-ttu-id="d8cfc-131">除了啟用外部使用者存取支援，您還必須設定相關原則以控制組織外部使用者存取的使用，接著再為使用者提供任何類型的外部使用者存取。</span><span class="sxs-lookup"><span data-stu-id="d8cfc-131">In addition to enabling external user access support, you must also configure policies to control the use of external user access in your organization before any type of external user access is available to users.</span></span> <span data-ttu-id="d8cfc-132">如需有關建立、設定及套用外部使用者存取原則的詳細資訊，請參閱[啟用或停用遠端使用者存取](../access-edge/enable-or-disable-remote-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="d8cfc-132">For details about creating, configuring, and applying policies for external user access see [Enable or disable remote user access](../access-edge/enable-or-disable-remote-user-access.md).</span></span>



<span data-ttu-id="d8cfc-133">**使用 Windows PowerShell Cmdlet 來檢視外部存取原則**</span><span class="sxs-lookup"><span data-stu-id="d8cfc-133">**To view external access policies by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="d8cfc-134">您可以使用商務用 Skype Server 管理命令介面和 **CsExternalAccessPolicy** Cmdlet 來檢視外部存取原則。</span><span class="sxs-lookup"><span data-stu-id="d8cfc-134">You can view external access policies by using Skype for Business Server Management Shell and the **Get-CsExternalAccessPolicy** cmdlet.</span></span> <span data-ttu-id="d8cfc-135">您可以從商務用 Skype Server 管理命令介面或從 Windows PowerShell 的遠端工作階段執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d8cfc-135">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 
    
    <span data-ttu-id="d8cfc-136">若要檢視關於您所有外部存取原則的資訊，請在 Lync Server 管理命令介面中輸入下列命令，然後按 ENTER 鍵：</span><span class="sxs-lookup"><span data-stu-id="d8cfc-136">To view information about all your external access policies, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
    `Get-CsExternalAccessPolicy`
    
    <span data-ttu-id="d8cfc-137">此命令會傳回與下列相似的資訊：</span><span class="sxs-lookup"><span data-stu-id="d8cfc-137">This command returns information similar to the following:</span></span>
    
    ```console
    Identity                          : Global
    Description                       :
    EnableFederationAccess            : False
    EnableXmppAccess                  : False
    EnablePublicCloudAccess           : False
    EnablePublicCloudAudioVideoAccess : False
    EnableOutsideAccess               : False
    ```
