---
title: 管理組織的外部使用存取原則
ms.reviewer: ''
ms:assetid: 5571811e-34c8-443a-b94c-1ab5d4275581
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520995(v=OCS.15)
ms:contentKeyID: 48184160
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 部署一或多個 Edge 伺服器之後，您必須啟用貴組織所支援的外部存取類型。
ms.openlocfilehash: f1f9798907f70893601a5dfe05b5045e484911e0
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991748"
---
# <a name="manage-external-access-policy-for-your-organization"></a><span data-ttu-id="1beda-103">管理組織的外部使用存取原則</span><span class="sxs-lookup"><span data-stu-id="1beda-103">Manage external access policy for your organization</span></span>

<span data-ttu-id="1beda-104">部署一或多個 Edge 伺服器之後，您必須啟用貴組織所支援的外部存取類型。</span><span class="sxs-lookup"><span data-stu-id="1beda-104">After deploying one or more Edge Servers, you must enable the types of external access that will be supported for your organization.</span></span>

<span data-ttu-id="1beda-105">根據預設，沒有任何原則可設定支援外部使用者存取，包括遠端使用者存取、同盟使用者存取，即使您已為組織啟用外部使用者存取支援。</span><span class="sxs-lookup"><span data-stu-id="1beda-105">By default, there are no policies configured to support external user access, including remote user access, federated user access, even if you have already enabled external user access support for your organization.</span></span> <span data-ttu-id="1beda-106">若要控制外部使用者存取的使用方式，您必須設定一或多個原則，以指定每個原則支援的外部使用者存取類型。</span><span class="sxs-lookup"><span data-stu-id="1beda-106">To control the use of external user access, you must configure one or more policies, specifying the type of external user access supported for each policy.</span></span> <span data-ttu-id="1beda-107">下列原則作用中可供建立及設定。</span><span class="sxs-lookup"><span data-stu-id="1beda-107">The following policy scopes are available for creation and configuration.</span></span> <span data-ttu-id="1beda-108">根據預設，會建立全域原則，但無法刪除。</span><span class="sxs-lookup"><span data-stu-id="1beda-108">By default, the Global policy is created, but cannot be deleted.</span></span>

  - <span data-ttu-id="1beda-109">**全域原則**   當您部署邊緣伺服器時，就會建立全域原則。</span><span class="sxs-lookup"><span data-stu-id="1beda-109">**Global policy**   The global policy is created when you deploy your Edge Servers.</span></span> <span data-ttu-id="1beda-110">根據預設，全域原則中不會啟用任何外部使用者存取選項。</span><span class="sxs-lookup"><span data-stu-id="1beda-110">By default, no external user access options are enabled in the global policy.</span></span> <span data-ttu-id="1beda-111">若要支援全域層級的外部使用者存取，您可以將全域原則設定為支援一或多種類型的外部使用者存取選項。</span><span class="sxs-lookup"><span data-stu-id="1beda-111">To support external user access at the global level, you configure the global policy to support one or more types of external user access options.</span></span> <span data-ttu-id="1beda-112">全域原則會套用至貴組織中的所有使用者，但網站原則和使用者原則會覆寫全域原則。</span><span class="sxs-lookup"><span data-stu-id="1beda-112">The global policy applies to all users in your organization, but site policies and user policies override the global policy.</span></span> <span data-ttu-id="1beda-113">如果您刪除全域原則，就不會將它移除。</span><span class="sxs-lookup"><span data-stu-id="1beda-113">If you delete the global policy, you do not remove it.</span></span> <span data-ttu-id="1beda-114">相反地，您可以將其重設為預設設定。</span><span class="sxs-lookup"><span data-stu-id="1beda-114">Instead, you reset it to the default setting.</span></span>

  - <span data-ttu-id="1beda-115">**網站原則**   您可以建立並設定一或多個網站原則，以限制外部使用者存取特定網站的支援。</span><span class="sxs-lookup"><span data-stu-id="1beda-115">**Site policy**   You can create and configure one or more site policies to limit support for external user access to specific sites.</span></span> <span data-ttu-id="1beda-116">網站原則中的設定優先於全域原則，但僅限該網站原則所涵蓋的特定網站。</span><span class="sxs-lookup"><span data-stu-id="1beda-116">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span> <span data-ttu-id="1beda-117">例如，如果您在全域原則中啟用遠端使用者存取，您可以指定可停用特定網站之遠端使用者存取權的網站原則。</span><span class="sxs-lookup"><span data-stu-id="1beda-117">For example, if you enable remote user access in the global policy, you might specify a site policy that disables remote user access for a specific site.</span></span> <span data-ttu-id="1beda-118">根據預設，網站原則會套用至該網站的所有使用者，但您可以將使用者原則指派給使用者，以覆寫網站原則設定。</span><span class="sxs-lookup"><span data-stu-id="1beda-118">By default, a site policy is applied to all users of that site, but you can assign a user policy to a user to override the site policy setting.</span></span>

  - <span data-ttu-id="1beda-119">**使用者原則**   您可以建立及設定一或多個使用者原則，以限制對特定使用者的遠端使用者存取權的支援。</span><span class="sxs-lookup"><span data-stu-id="1beda-119">**User policy**   You can create and configure one or more user policies to limit support for remote user access to specific users.</span></span> <span data-ttu-id="1beda-120">使用者原則中的設定會覆寫全域和網站原則，但只適用于指派使用者原則的特定使用者。</span><span class="sxs-lookup"><span data-stu-id="1beda-120">The configuration in the user policy overrides the global and site policy, but only for the specific users to whom the user policy is assigned.</span></span> <span data-ttu-id="1beda-121">例如，如果您在全域原則和網站原則中啟用遠端使用者存取，您可以指定可停用遠端使用者存取的使用者原則，然後將該使用者原則指派給特定的使用者。</span><span class="sxs-lookup"><span data-stu-id="1beda-121">For example, if you enable remote user access in the global policy and site policy, you might specify a user policy that disables remote user access and then assign that user policy to specific users.</span></span> <span data-ttu-id="1beda-122">如果您建立使用者原則，您必須先將其套用至一或多個使用者，才會生效。</span><span class="sxs-lookup"><span data-stu-id="1beda-122">If you create a user policy, you must apply it to one or more users before it takes effect.</span></span>


> [!IMPORTANT]  
> <span data-ttu-id="1beda-123">在一個策略層級套用的原則設定可以覆寫在其他原則層級套用的設定。</span><span class="sxs-lookup"><span data-stu-id="1beda-123">Policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="1beda-124">商務用 Skype Server 原則優先順序為：使用者原則（最具影響力）會覆寫網站原則，然後網站原則會覆寫全域原則（最小的影響）。</span><span class="sxs-lookup"><span data-stu-id="1beda-124">Skype for Business Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="1beda-125">這表示原則設定越接近策略設定的物件，就會受到對物件的影響。</span><span class="sxs-lookup"><span data-stu-id="1beda-125">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>


<span data-ttu-id="1beda-126">這些選項包括下列外部存取類型：</span><span class="sxs-lookup"><span data-stu-id="1beda-126">These options include the following types of external access:</span></span>

  - <span data-ttu-id="1beda-127">\*\*\*\*    如果您想要支援使用者存取聯盟夥伴網域，請啟用與同盟使用者進行通訊。</span><span class="sxs-lookup"><span data-stu-id="1beda-127">**Enable communications with federated users**   Enable this if you want to support user access to federated partner domains.</span></span> <span data-ttu-id="1beda-128">此設定會設定使用者與其他 SIP 聯盟網域通訊的能力，以及 Microsoft Office 365 等主機提供者。</span><span class="sxs-lookup"><span data-stu-id="1beda-128">This setting configures the ability for users to communicate with other SIP federated domains, as well as Hosted providers like Microsoft Office 365.</span></span> 


  - <span data-ttu-id="1beda-129">\*\*\*\*    如果您想讓組織中的使用者（例如正在旅行的遠端電腦和使用者）能夠透過網際網路連線到商務用 Skype Server，請啟用 [與遠端使用者進行通訊] 選項。</span><span class="sxs-lookup"><span data-stu-id="1beda-129">**Enable communications with remote users**   Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Skype for Business Server over the Internet.</span></span>

  - <span data-ttu-id="1beda-130">\*\*\*\*    如果您希望內部使用者能夠與公用 IM 提供者連絡人通訊，請啟用 [與公用使用者通訊]。</span><span class="sxs-lookup"><span data-stu-id="1beda-130">**Enable communications with public users**   Enable this option if you want internal users to be able to communicate with public IM provider contacts.</span></span>
   

> [!NOTE]  
> <span data-ttu-id="1beda-131">除了啟用外部使用者存取支援之外，您也必須先設定原則，以控制在您的組織中使用外部使用者存取權，才能供使用者使用任何類型的外部使用者存取。</span><span class="sxs-lookup"><span data-stu-id="1beda-131">In addition to enabling external user access support, you must also configure policies to control the use of external user access in your organization before any type of external user access is available to users.</span></span> <span data-ttu-id="1beda-132">如需建立、設定及套用外部使用者存取原則的詳細資料，請參閱[啟用或停用遠端使用者存取](../access-edge/enable-or-disable-remote-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="1beda-132">For details about creating, configuring, and applying policies for external user access see [Enable or disable remote user access](../access-edge/enable-or-disable-remote-user-access.md).</span></span>



<span data-ttu-id="1beda-133">**使用 Windows PowerShell Cmdlet 來查看外部存取原則**</span><span class="sxs-lookup"><span data-stu-id="1beda-133">**To view external access policies by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="1beda-134">您可以使用商務用 Skype Server Management 命令介面和**CsExternalAccessPolicy** Cmdlet 來查看外部存取原則。</span><span class="sxs-lookup"><span data-stu-id="1beda-134">You can view external access policies by using Skype for Business Server Management Shell and the **Get-CsExternalAccessPolicy** cmdlet.</span></span> <span data-ttu-id="1beda-135">您可以從商務用 Skype Server Management 命令介面或從 Windows PowerShell 遠端會話執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1beda-135">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 
    
    <span data-ttu-id="1beda-136">若要查看所有外部存取原則的相關資訊，請在 Lync Server 管理命令介面中輸入下列命令，然後按 ENTER 鍵：</span><span class="sxs-lookup"><span data-stu-id="1beda-136">To view information about all your external access policies, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
    `Get-CsExternalAccessPolicy`
    
    <span data-ttu-id="1beda-137">這個命令會傳回如下所示的資訊：</span><span class="sxs-lookup"><span data-stu-id="1beda-137">This command returns information similar to the following:</span></span>
    
    ```console
    Identity                          : Global
    Description                       :
    EnableFederationAccess            : False
    EnableXmppAccess                  : False
    EnablePublicCloudAccess           : False
    EnablePublicCloudAudioVideoAccess : False
    EnableOutsideAccess               : False
    ```
