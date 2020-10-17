---
title: Lync Server 2013：主控語音信箱原則
description: Lync Server 2013：主控語音信箱原則。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted voice mail policies
ms:assetid: d62a35ed-cbe2-4f06-86b4-e192c18435c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398932(v=OCS.15)
ms:contentKeyID: 48185506
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 57461f4ffd2c6f2cd733dd7ec2c945c9e7b801c2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550099"
---
# <a name="hosted-voice-mail-policies-in-lync-server-2013"></a><span data-ttu-id="262c7-103">Lync Server 2013 中的主控語音信箱原則</span><span class="sxs-lookup"><span data-stu-id="262c7-103">Hosted voice mail policies in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="262c7-104">_**主題上次修改日期：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="262c7-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="262c7-105">「裝載 *語音信箱原則* 」會為 Lync Server 2013 ExUM 路由應用程式提供資訊，告知其信箱位於裝載 Exchange 服務上之使用者的通話位置。</span><span class="sxs-lookup"><span data-stu-id="262c7-105">A *hosted voice mail policy* provides information to the Lync Server 2013 ExUM Routing application about where to route calls for users whose mailboxes are located on a hosted Exchange service.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="262c7-106">主控的語音信箱原則只有在 Lync Server 2013 與主控 Exchange UM 的整合時才需要。</span><span class="sxs-lookup"><span data-stu-id="262c7-106">Hosted voice mail policies are required only for Lync Server 2013 integration with hosted Exchange UM.</span></span> <span data-ttu-id="262c7-107">與內部部署 Exchange UM 的整合不需要這些功能。</span><span class="sxs-lookup"><span data-stu-id="262c7-107">They are not needed for integration with on-premises Exchange UM.</span></span>



</div>

<div>

## <a name="hosted-voice-mail-policy-scope"></a><span data-ttu-id="262c7-108">主控語音信箱原則範圍</span><span class="sxs-lookup"><span data-stu-id="262c7-108">Hosted Voice Mail Policy Scope</span></span>

<span data-ttu-id="262c7-109">「主控語音信箱原則」範圍決定原則適用的階層層級。</span><span class="sxs-lookup"><span data-stu-id="262c7-109">Hosted voice mail policy scope determines the hierarchical level at which the policy applies.</span></span> <span data-ttu-id="262c7-110">您可以設定具有下列範圍層級的主控語音信箱原則：</span><span class="sxs-lookup"><span data-stu-id="262c7-110">You can configure hosted voice mail policies with the following scope levels:</span></span>

  - <span data-ttu-id="262c7-111">*全域*原則可能會影響 Lync Server 2013 部署中的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="262c7-111">The *global* policy can potentially affect all users in the Lync Server 2013 deployment.</span></span> <span data-ttu-id="262c7-112">如果使用者已啟用主控 Exchange UM 存取，但尚未被指派個別使用者原則，而且尚未將網站原則指派給使用者的網站，則會套用全域原則。</span><span class="sxs-lookup"><span data-stu-id="262c7-112">If a user is enabled for hosted Exchange UM access and has not been assigned a per-user policy, and if a site policy has not been assigned to the user’s site, the global policy applies.</span></span> <span data-ttu-id="262c7-113">通用原則是隨 Lync Server 2013 一起安裝。</span><span class="sxs-lookup"><span data-stu-id="262c7-113">The global policy is installed with Lync Server 2013.</span></span> <span data-ttu-id="262c7-114">您可以修改它以符合您的需求，但是您無法重新命名或刪除。</span><span class="sxs-lookup"><span data-stu-id="262c7-114">You can modify it to meet your needs, but you cannot rename or delete it.</span></span>

  - <span data-ttu-id="262c7-115">*網站*原則可能會影響位於已定義原則之網站上的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="262c7-115">A *site* policy can affect all users that are homed on the site for which the policy is defined.</span></span> <span data-ttu-id="262c7-116">若使用者已設定為主控 Exchange UM 存取，但尚未指派個別使用者原則，則會套用網站原則。</span><span class="sxs-lookup"><span data-stu-id="262c7-116">If a user is configured for hosted Exchange UM access and has not been assigned a per-user policy, the site policy applies.</span></span>

  - <span data-ttu-id="262c7-117">*每一使用者*原則只會影響個別的使用者或群組。</span><span class="sxs-lookup"><span data-stu-id="262c7-117">A *per-user* policy can affect only individual users or groups.</span></span> <span data-ttu-id="262c7-118">若要強制執行個別使用者原則，您必須將原則明確指派給個別的使用者、群組和連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="262c7-118">To enforce a per-user policy, you must explicitly assign the policy to individual users, groups, and contact objects.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="262c7-119">在大多數情況下，只需要一個主控語音信箱原則。</span><span class="sxs-lookup"><span data-stu-id="262c7-119">In most cases, only one hosted voice mail policy is required.</span></span> <span data-ttu-id="262c7-120">您通常可以修改全域原則，以符合您的所有需求。</span><span class="sxs-lookup"><span data-stu-id="262c7-120">You can often modify the global policy to meet all your needs.</span></span> <span data-ttu-id="262c7-121">如果您部署多個主控的語音信箱原則，則所有此類原則都具有每一使用者範圍。</span><span class="sxs-lookup"><span data-stu-id="262c7-121">If you deploy multiple hosted voice mail policies, all such policies have per-user scope.</span></span>



</div>

</div>

<div>

## <a name="hosted-voice-mail-policy-attributes"></a><span data-ttu-id="262c7-122">主控語音信箱原則屬性</span><span class="sxs-lookup"><span data-stu-id="262c7-122">Hosted Voice Mail Policy Attributes</span></span>

<span data-ttu-id="262c7-123">語音信箱原則定義兩個屬性，Lync Server 2013 ExUM 路由應用程式會在傳送至主控 Exchange UM 實現的 INVITE 郵件要求 URI 中插入：</span><span class="sxs-lookup"><span data-stu-id="262c7-123">A voice mail policy defines two attributes that the Lync Server 2013 ExUM Routing application inserts in the request URI of an INVITE message that is sent to the hosted Exchange UM implementation:</span></span>

  - <span data-ttu-id="262c7-124">**目的地：** 主控 Exchange UM 服務的完整功能變數名稱 (FQDN) 。</span><span class="sxs-lookup"><span data-stu-id="262c7-124">**Destination:** The fully qualified domain name (FQDN) of the hosted Exchange UM service.</span></span> <span data-ttu-id="262c7-125">內部部署 Lync Server Edge Server 會使用此值進行路由傳送。</span><span class="sxs-lookup"><span data-stu-id="262c7-125">This value is used by the on-premises Lync Server Edge Server for routing purposes.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="262c7-126">Exchange Online 的 FQDN 是 exap.um.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="262c7-126">The FQDN for Exchange Online is exap.um.outlook.com.</span></span>

    
    </div>

  - <span data-ttu-id="262c7-127">**組織：** 主控您的 Lync Server 2013 使用者信箱之主控 Exchange UM 服務上租使用者的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="262c7-127">**Organization:** The FQDN of the tenant on the hosted Exchange UM service that homes your Lync Server 2013 users’ mailboxes.</span></span> <span data-ttu-id="262c7-128">語音信箱原則可以包含多個組織。</span><span class="sxs-lookup"><span data-stu-id="262c7-128">A voice mail policy can contain multiple organizations.</span></span> <span data-ttu-id="262c7-129">若原則中包含多個組織，此屬性必須是以逗號分隔的 Exchange 伺服器租使用者，該清單會家用您的 Lync Server 2013 使用者信箱。</span><span class="sxs-lookup"><span data-stu-id="262c7-129">If more than one organization is included in the policy, this attribute must be a comma-separated list of the Exchange Server tenants that home your Lync Server 2013 user mailboxes.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="262c7-130">您裝載的 Exchange UM 服務的租使用者系統管理員會提供必要的目的地和組織屬性設定值。</span><span class="sxs-lookup"><span data-stu-id="262c7-130">The tenant administrator of your hosted Exchange UM service will provide the necessary values for your Destination and Organization attribute settings.</span></span> <span data-ttu-id="262c7-131">若要設定原則，您必須執行 New-CsHostedVoicemailPolicy Cmdlet，或使用 Set-CsHostedVoicemailPolicy Cmdlet 來修改存在 (例如，全域原則) 。</span><span class="sxs-lookup"><span data-stu-id="262c7-131">To configure your policy, you must run the New-CsHostedVoicemailPolicy cmdlet or use the Set-CsHostedVoicemailPolicy cmdlet to modify one that exists (for example, the global policy).</span></span>



</div>

<span data-ttu-id="262c7-132">如需管理主控語音信箱原則的詳細資訊，請參閱 Lync Server 管理命令介面檔中的下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="262c7-132">For details about managing hosted voice mail policies, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="262c7-133">New-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="262c7-133">New-CsHostedVoicemailPolicy</span></span>

  - <span data-ttu-id="262c7-134">Set-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="262c7-134">Set-CsHostedVoicemailPolicy</span></span>

  - <span data-ttu-id="262c7-135">Get-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="262c7-135">Get-CsHostedVoicemailPolicy</span></span>

</div>

<div>

## <a name="per-user-voice-mail-policy-assignment"></a><span data-ttu-id="262c7-136">Per-User 語音信箱原則指派</span><span class="sxs-lookup"><span data-stu-id="262c7-136">Per-User Voice Mail Policy Assignment</span></span>

<span data-ttu-id="262c7-137">如果您裝載的語音信箱原則是以每個使用者範圍定義，您必須明確指派它。</span><span class="sxs-lookup"><span data-stu-id="262c7-137">If your hosted voice mail policy is defined with per-user scope, you must explicitly assign it.</span></span> <span data-ttu-id="262c7-138">您可以執行 Grant-CsHostedVoicemailPolicy Cmdlet，將原則指派給個別使用者或群組。</span><span class="sxs-lookup"><span data-stu-id="262c7-138">You can run the Grant-CsHostedVoicemailPolicy cmdlet to assign the policy to individual users or groups.</span></span>

<span data-ttu-id="262c7-139">如需指派或移除個別使用者的主控語音信箱原則的詳細資訊，請參閱 Lync Server 管理命令介面檔中的下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="262c7-139">For details about assigning or removing a per-user hosted voice mail policy, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="262c7-140">Grant-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="262c7-140">Grant-CsHostedVoicemailPolicy</span></span>

  - <span data-ttu-id="262c7-141">Remove-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="262c7-141">Remove-CsHostedVoicemailPolicy</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

