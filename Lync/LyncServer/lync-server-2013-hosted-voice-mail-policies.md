---
title: Lync Server 2013：主控語音信箱原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Hosted voice mail policies
ms:assetid: d62a35ed-cbe2-4f06-86b4-e192c18435c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398932(v=OCS.15)
ms:contentKeyID: 48185506
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a23f5fa67a34d479bbc5b9d5c9bf55071b187c1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981775"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-voice-mail-policies-in-lync-server-2013"></a><span data-ttu-id="5d22e-102">Lync Server 2013 中的主控語音信箱原則</span><span class="sxs-lookup"><span data-stu-id="5d22e-102">Hosted voice mail policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5d22e-103">_**主題上次修改日期：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="5d22e-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="5d22e-104">已*託管的語音信箱原則*會提供資訊給 Lync Server 2013 ExUM 路由應用程式，讓您在何處路由其信箱位於託管 Exchange 服務的使用者。</span><span class="sxs-lookup"><span data-stu-id="5d22e-104">A *hosted voice mail policy* provides information to the Lync Server 2013 ExUM Routing application about where to route calls for users whose mailboxes are located on a hosted Exchange service.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5d22e-105">只有在與託管 Exchange UM 整合 Lync Server 2013 時，才需要託管語音信箱原則。</span><span class="sxs-lookup"><span data-stu-id="5d22e-105">Hosted voice mail policies are required only for Lync Server 2013 integration with hosted Exchange UM.</span></span> <span data-ttu-id="5d22e-106">它們不是與內部部署 Exchange UM 的整合所需要的。</span><span class="sxs-lookup"><span data-stu-id="5d22e-106">They are not needed for integration with on-premises Exchange UM.</span></span>



</div>

<div>

## <a name="hosted-voice-mail-policy-scope"></a><span data-ttu-id="5d22e-107">已託管的語音信箱原則範圍</span><span class="sxs-lookup"><span data-stu-id="5d22e-107">Hosted Voice Mail Policy Scope</span></span>

<span data-ttu-id="5d22e-108">已託管的語音信箱原則範圍會決定原則的層次結構層級。</span><span class="sxs-lookup"><span data-stu-id="5d22e-108">Hosted voice mail policy scope determines the hierarchical level at which the policy applies.</span></span> <span data-ttu-id="5d22e-109">您可以將託管的語音信箱原則設定為下列範圍層級：</span><span class="sxs-lookup"><span data-stu-id="5d22e-109">You can configure hosted voice mail policies with the following scope levels:</span></span>

  - <span data-ttu-id="5d22e-110">*全域*原則可能會影響 Lync Server 2013 部署中的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="5d22e-110">The *global* policy can potentially affect all users in the Lync Server 2013 deployment.</span></span> <span data-ttu-id="5d22e-111">如果使用者已啟用託管 Exchange UM 存取，而且尚未獲指派每個使用者的原則，且尚未將網站原則指派給使用者的網站，則會套用全域原則。</span><span class="sxs-lookup"><span data-stu-id="5d22e-111">If a user is enabled for hosted Exchange UM access and has not been assigned a per-user policy, and if a site policy has not been assigned to the user’s site, the global policy applies.</span></span> <span data-ttu-id="5d22e-112">使用 Lync Server 2013 安裝全域原則。</span><span class="sxs-lookup"><span data-stu-id="5d22e-112">The global policy is installed with Lync Server 2013.</span></span> <span data-ttu-id="5d22e-113">您可以對其進行修改以符合您的需求，但無法重新命名或刪除該檔案。</span><span class="sxs-lookup"><span data-stu-id="5d22e-113">You can modify it to meet your needs, but you cannot rename or delete it.</span></span>

  - <span data-ttu-id="5d22e-114">*網站*原則可能會影響託管在已定義策略之網站上的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="5d22e-114">A *site* policy can affect all users that are homed on the site for which the policy is defined.</span></span> <span data-ttu-id="5d22e-115">如果使用者是針對託管 Exchange UM 存取進行設定，且尚未獲指派每個使用者的原則，則會套用網站原則。</span><span class="sxs-lookup"><span data-stu-id="5d22e-115">If a user is configured for hosted Exchange UM access and has not been assigned a per-user policy, the site policy applies.</span></span>

  - <span data-ttu-id="5d22e-116">*每個使用者*的原則只會影響個別的使用者或群組。</span><span class="sxs-lookup"><span data-stu-id="5d22e-116">A *per-user* policy can affect only individual users or groups.</span></span> <span data-ttu-id="5d22e-117">若要強制執行每個使用者的原則，您必須將原則明確指派給個別的使用者、群組和連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="5d22e-117">To enforce a per-user policy, you must explicitly assign the policy to individual users, groups, and contact objects.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5d22e-118">在大多數情況下，只需要一個寄宿的語音信箱原則。</span><span class="sxs-lookup"><span data-stu-id="5d22e-118">In most cases, only one hosted voice mail policy is required.</span></span> <span data-ttu-id="5d22e-119">您通常可以修改全域原則，以符合您的需求。</span><span class="sxs-lookup"><span data-stu-id="5d22e-119">You can often modify the global policy to meet all your needs.</span></span> <span data-ttu-id="5d22e-120">如果您部署多個託管的語音信箱原則，所有這類原則都會有每個使用者的範圍。</span><span class="sxs-lookup"><span data-stu-id="5d22e-120">If you deploy multiple hosted voice mail policies, all such policies have per-user scope.</span></span>



</div>

</div>

<div>

## <a name="hosted-voice-mail-policy-attributes"></a><span data-ttu-id="5d22e-121">託管的語音信箱原則屬性</span><span class="sxs-lookup"><span data-stu-id="5d22e-121">Hosted Voice Mail Policy Attributes</span></span>

<span data-ttu-id="5d22e-122">語音信箱原則定義了兩個屬性，Lync Server 2013 ExUM 路由應用程式會在傳送到託管 Exchange UM 實現的邀請郵件的要求 URI 中插入：</span><span class="sxs-lookup"><span data-stu-id="5d22e-122">A voice mail policy defines two attributes that the Lync Server 2013 ExUM Routing application inserts in the request URI of an INVITE message that is sent to the hosted Exchange UM implementation:</span></span>

  - <span data-ttu-id="5d22e-123">**目的地：** 託管 Exchange UM 服務的完整功能變數名稱（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="5d22e-123">**Destination:** The fully qualified domain name (FQDN) of the hosted Exchange UM service.</span></span> <span data-ttu-id="5d22e-124">此值是由內部部署的 Lync Server Edge 伺服器用來進行路由的目的。</span><span class="sxs-lookup"><span data-stu-id="5d22e-124">This value is used by the on-premises Lync Server Edge Server for routing purposes.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5d22e-125">Exchange Online 的 FQDN 是 exap.um.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="5d22e-125">The FQDN for Exchange Online is exap.um.outlook.com.</span></span>

    
    </div>

  - <span data-ttu-id="5d22e-126">**組織：** 寄存您的 Lync Server 2013 使用者信箱的託管 Exchange UM 服務上的租使用者 FQDN。</span><span class="sxs-lookup"><span data-stu-id="5d22e-126">**Organization:** The FQDN of the tenant on the hosted Exchange UM service that homes your Lync Server 2013 users’ mailboxes.</span></span> <span data-ttu-id="5d22e-127">語音信箱原則可以包含多個組織。</span><span class="sxs-lookup"><span data-stu-id="5d22e-127">A voice mail policy can contain multiple organizations.</span></span> <span data-ttu-id="5d22e-128">如果原則中包含多個組織，此屬性必須是家用 Lync Server 2013 使用者信箱之 Exchange 伺服器租使用者的逗號分隔清單。</span><span class="sxs-lookup"><span data-stu-id="5d22e-128">If more than one organization is included in the policy, this attribute must be a comma-separated list of the Exchange Server tenants that home your Lync Server 2013 user mailboxes.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5d22e-129">您託管 Exchange UM 服務的租使用者系統管理員會針對您的目的地和組織屬性設定提供必要的值。</span><span class="sxs-lookup"><span data-stu-id="5d22e-129">The tenant administrator of your hosted Exchange UM service will provide the necessary values for your Destination and Organization attribute settings.</span></span> <span data-ttu-id="5d22e-130">若要設定您的原則，您必須執行新的 CsHostedVoicemailPolicy Cmdlet，或使用 CsHostedVoicemailPolicy Cmdlet 來修改現有的（例如，全域原則）。</span><span class="sxs-lookup"><span data-stu-id="5d22e-130">To configure your policy, you must run the New-CsHostedVoicemailPolicy cmdlet or use the Set-CsHostedVoicemailPolicy cmdlet to modify one that exists (for example, the global policy).</span></span>



</div>

<span data-ttu-id="5d22e-131">如需管理託管語音信箱原則的詳細資訊，請參閱下列 Cmdlet 的 Lync Server 管理命令介面檔：</span><span class="sxs-lookup"><span data-stu-id="5d22e-131">For details about managing hosted voice mail policies, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="5d22e-132">新-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="5d22e-132">New-CsHostedVoicemailPolicy</span></span>

  - <span data-ttu-id="5d22e-133">Set-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="5d22e-133">Set-CsHostedVoicemailPolicy</span></span>

  - <span data-ttu-id="5d22e-134">CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="5d22e-134">Get-CsHostedVoicemailPolicy</span></span>

</div>

<div>

## <a name="per-user-voice-mail-policy-assignment"></a><span data-ttu-id="5d22e-135">每個使用者的語音信箱原則指派</span><span class="sxs-lookup"><span data-stu-id="5d22e-135">Per-User Voice Mail Policy Assignment</span></span>

<span data-ttu-id="5d22e-136">如果您託管的語音信箱原則是由每個使用者的範圍所定義，則您必須明確指派它。</span><span class="sxs-lookup"><span data-stu-id="5d22e-136">If your hosted voice mail policy is defined with per-user scope, you must explicitly assign it.</span></span> <span data-ttu-id="5d22e-137">您可以執行授與 CsHostedVoicemailPolicy Cmdlet，將原則指派給個別的使用者或群組。</span><span class="sxs-lookup"><span data-stu-id="5d22e-137">You can run the Grant-CsHostedVoicemailPolicy cmdlet to assign the policy to individual users or groups.</span></span>

<span data-ttu-id="5d22e-138">如需指派或移除依使用者裝載的語音信箱原則的詳細資料，請參閱下列 Cmdlet 的 Lync Server 管理命令介面檔：</span><span class="sxs-lookup"><span data-stu-id="5d22e-138">For details about assigning or removing a per-user hosted voice mail policy, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="5d22e-139">授與 CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="5d22e-139">Grant-CsHostedVoicemailPolicy</span></span>

  - <span data-ttu-id="5d22e-140">移除-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="5d22e-140">Remove-CsHostedVoicemailPolicy</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

