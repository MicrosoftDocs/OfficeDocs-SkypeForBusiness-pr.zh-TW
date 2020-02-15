---
title: Lync Server 2013： 主控的語音信箱原則
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
ms.openlocfilehash: 01e844e62934a697b12afa76d2e9c9405a30a4a4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043175"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-voice-mail-policies-in-lync-server-2013"></a><span data-ttu-id="e8e8a-102">Lync Server 2013 中的主控的語音信箱原則</span><span class="sxs-lookup"><span data-stu-id="e8e8a-102">Hosted voice mail policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e8e8a-103">_**主題上次修改日期：** 2012年-10-01_</span><span class="sxs-lookup"><span data-stu-id="e8e8a-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="e8e8a-104">*裝載語音信箱原則*提供資訊給 Lync Server 2013 ExUM Routing 應用程式的使用者信箱位於裝載 Exchange 服務的電話路由至何處。</span><span class="sxs-lookup"><span data-stu-id="e8e8a-104">A *hosted voice mail policy* provides information to the Lync Server 2013 ExUM Routing application about where to route calls for users whose mailboxes are located on a hosted Exchange service.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e8e8a-105">主控的語音信箱原則所需僅適用於 Lync Server 2013 整合與裝載 Exchange UM。</span><span class="sxs-lookup"><span data-stu-id="e8e8a-105">Hosted voice mail policies are required only for Lync Server 2013 integration with hosted Exchange UM.</span></span> <span data-ttu-id="e8e8a-106">不需要進行與內部部署 Exchange UM 整合。</span><span class="sxs-lookup"><span data-stu-id="e8e8a-106">They are not needed for integration with on-premises Exchange UM.</span></span>



</div>

<div>

## <a name="hosted-voice-mail-policy-scope"></a><span data-ttu-id="e8e8a-107">裝載的語音信箱原則範圍</span><span class="sxs-lookup"><span data-stu-id="e8e8a-107">Hosted Voice Mail Policy Scope</span></span>

<span data-ttu-id="e8e8a-108">裝載的語音信箱原則範圍會決定在套用原則的階層式層級。</span><span class="sxs-lookup"><span data-stu-id="e8e8a-108">Hosted voice mail policy scope determines the hierarchical level at which the policy applies.</span></span> <span data-ttu-id="e8e8a-109">您可以使用下列範圍層級設定主控的語音信箱原則：</span><span class="sxs-lookup"><span data-stu-id="e8e8a-109">You can configure hosted voice mail policies with the following scope levels:</span></span>

  - <span data-ttu-id="e8e8a-110">*全域*原則可能會影響在 Lync Server 2013 部署中的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="e8e8a-110">The *global* policy can potentially affect all users in the Lync Server 2013 deployment.</span></span> <span data-ttu-id="e8e8a-111">如果使用者的裝載 Exchange UM 存取已啟用，且未被指派個別使用者原則，且網站原則不已指派給使用者的網站，適用於全域原則。</span><span class="sxs-lookup"><span data-stu-id="e8e8a-111">If a user is enabled for hosted Exchange UM access and has not been assigned a per-user policy, and if a site policy has not been assigned to the user’s site, the global policy applies.</span></span> <span data-ttu-id="e8e8a-112">使用 Lync Server 2013 安裝的全域原則。</span><span class="sxs-lookup"><span data-stu-id="e8e8a-112">The global policy is installed with Lync Server 2013.</span></span> <span data-ttu-id="e8e8a-113">您可加以修改以符合您的需求，但您無法重新命名或刪除它。</span><span class="sxs-lookup"><span data-stu-id="e8e8a-113">You can modify it to meet your needs, but you cannot rename or delete it.</span></span>

  - <span data-ttu-id="e8e8a-114">*網站*原則可能會影響所有使用者都位於其定義原則的網站。</span><span class="sxs-lookup"><span data-stu-id="e8e8a-114">A *site* policy can affect all users that are homed on the site for which the policy is defined.</span></span> <span data-ttu-id="e8e8a-115">如果使用者的裝載 Exchange UM 存取設定，且未被指派個別使用者原則，適用於站台原則。</span><span class="sxs-lookup"><span data-stu-id="e8e8a-115">If a user is configured for hosted Exchange UM access and has not been assigned a per-user policy, the site policy applies.</span></span>

  - <span data-ttu-id="e8e8a-116">*每位使用者*的原則可能會影響僅限個別使用者或群組。</span><span class="sxs-lookup"><span data-stu-id="e8e8a-116">A *per-user* policy can affect only individual users or groups.</span></span> <span data-ttu-id="e8e8a-117">強制執行的每一使用者原則，您必須明確地將原則指派給個別使用者、 群組和連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="e8e8a-117">To enforce a per-user policy, you must explicitly assign the policy to individual users, groups, and contact objects.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e8e8a-118">在大多數情況下，只有一個裝載的語音信箱原則是必要的。</span><span class="sxs-lookup"><span data-stu-id="e8e8a-118">In most cases, only one hosted voice mail policy is required.</span></span> <span data-ttu-id="e8e8a-119">您通常可以修改全域原則以符合您的需求。</span><span class="sxs-lookup"><span data-stu-id="e8e8a-119">You can often modify the global policy to meet all your needs.</span></span> <span data-ttu-id="e8e8a-120">如果您部署多個託管的語音信箱原則時，所有這類原則有每個使用者範圍。</span><span class="sxs-lookup"><span data-stu-id="e8e8a-120">If you deploy multiple hosted voice mail policies, all such policies have per-user scope.</span></span>



</div>

</div>

<div>

## <a name="hosted-voice-mail-policy-attributes"></a><span data-ttu-id="e8e8a-121">裝載的語音信箱原則屬性</span><span class="sxs-lookup"><span data-stu-id="e8e8a-121">Hosted Voice Mail Policy Attributes</span></span>

<span data-ttu-id="e8e8a-122">「 語音信箱原則會定義 Lync Server 2013 ExUM Routing 應用程式插入要求 URI，傳送至裝載的 Exchange UM 實作此 INVITE 訊息中的兩個屬性：</span><span class="sxs-lookup"><span data-stu-id="e8e8a-122">A voice mail policy defines two attributes that the Lync Server 2013 ExUM Routing application inserts in the request URI of an INVITE message that is sent to the hosted Exchange UM implementation:</span></span>

  - <span data-ttu-id="e8e8a-123">**目的地：** 主控 Exchange UM 服務的完整的網域名稱 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="e8e8a-123">**Destination:** The fully qualified domain name (FQDN) of the hosted Exchange UM service.</span></span> <span data-ttu-id="e8e8a-124">這個值是由內部部署 Lync Server Edge Server 用於路由用途。</span><span class="sxs-lookup"><span data-stu-id="e8e8a-124">This value is used by the on-premises Lync Server Edge Server for routing purposes.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e8e8a-125">Exchange Online 的 FQDN 是 exap.um.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="e8e8a-125">The FQDN for Exchange Online is exap.um.outlook.com.</span></span>

    
    </div>

  - <span data-ttu-id="e8e8a-126">**組織：** 在主控 Exchange UM 服務所在 Lync Server 2013 使用者信箱上的租用戶 FQDN。</span><span class="sxs-lookup"><span data-stu-id="e8e8a-126">**Organization:** The FQDN of the tenant on the hosted Exchange UM service that homes your Lync Server 2013 users’ mailboxes.</span></span> <span data-ttu-id="e8e8a-127">「 語音信箱原則可以包含多個組織。</span><span class="sxs-lookup"><span data-stu-id="e8e8a-127">A voice mail policy can contain multiple organizations.</span></span> <span data-ttu-id="e8e8a-128">如果在原則中包含了一個以上的組織，這個屬性必須以逗號分隔清單中的 Exchange 伺服器 tenant 該首頁 Lync Server 2013 使用者信箱。</span><span class="sxs-lookup"><span data-stu-id="e8e8a-128">If more than one organization is included in the policy, this attribute must be a comma-separated list of the Exchange Server tenants that home your Lync Server 2013 user mailboxes.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e8e8a-129">您的託管式 Exchange UM 服務租用戶系統管理員會提供您的目的地和組織屬性設定必要的值。</span><span class="sxs-lookup"><span data-stu-id="e8e8a-129">The tenant administrator of your hosted Exchange UM service will provide the necessary values for your Destination and Organization attribute settings.</span></span> <span data-ttu-id="e8e8a-130">若要設定您的原則，您必須執行新增 CsHostedVoicemailPolicy 指令程式，或使用 Set-cshostedvoicemailpolicy cmdlet 來修改其中存在 （例如，全域原則）。</span><span class="sxs-lookup"><span data-stu-id="e8e8a-130">To configure your policy, you must run the New-CsHostedVoicemailPolicy cmdlet or use the Set-CsHostedVoicemailPolicy cmdlet to modify one that exists (for example, the global policy).</span></span>



</div>

<span data-ttu-id="e8e8a-131">如需管理裝載的語音信箱原則的詳細資訊，請參閱 Lync Server 管理命令介面文件的下列 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="e8e8a-131">For details about managing hosted voice mail policies, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="e8e8a-132">新 CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="e8e8a-132">New-CsHostedVoicemailPolicy</span></span>

  - <span data-ttu-id="e8e8a-133">Set-cshostedvoicemailpolicy</span><span class="sxs-lookup"><span data-stu-id="e8e8a-133">Set-CsHostedVoicemailPolicy</span></span>

  - <span data-ttu-id="e8e8a-134">Get-cshostedvoicemailpolicy</span><span class="sxs-lookup"><span data-stu-id="e8e8a-134">Get-CsHostedVoicemailPolicy</span></span>

</div>

<div>

## <a name="per-user-voice-mail-policy-assignment"></a><span data-ttu-id="e8e8a-135">每位使用者的語音信箱原則指派</span><span class="sxs-lookup"><span data-stu-id="e8e8a-135">Per-User Voice Mail Policy Assignment</span></span>

<span data-ttu-id="e8e8a-136">如果您的裝載的語音信箱原則定義每個使用者範圍，您必須明確地將授權指派。</span><span class="sxs-lookup"><span data-stu-id="e8e8a-136">If your hosted voice mail policy is defined with per-user scope, you must explicitly assign it.</span></span> <span data-ttu-id="e8e8a-137">您可以執行授與 CsHostedVoicemailPolicy 指令程式將原則指派給個別使用者或群組。</span><span class="sxs-lookup"><span data-stu-id="e8e8a-137">You can run the Grant-CsHostedVoicemailPolicy cmdlet to assign the policy to individual users or groups.</span></span>

<span data-ttu-id="e8e8a-138">如需指派或移除個別使用者裝載語音信箱原則的詳細資訊，請參閱 Lync Server 管理命令介面文件的下列 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="e8e8a-138">For details about assigning or removing a per-user hosted voice mail policy, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="e8e8a-139">授與 CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="e8e8a-139">Grant-CsHostedVoicemailPolicy</span></span>

  - <span data-ttu-id="e8e8a-140">移除 CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="e8e8a-140">Remove-CsHostedVoicemailPolicy</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

