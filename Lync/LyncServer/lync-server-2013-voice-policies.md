---
title: Lync Server 2013：語音原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Voice policies
ms:assetid: b7433c62-9d8c-48af-89a0-19f0d34806ec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412891(v=OCS.15)
ms:contentKeyID: 48185223
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 986350a766716cc8a1fc35a734933f30b25a70ec
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211089"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="voice-policies-in-lync-server-2013"></a><span data-ttu-id="19769-102">Lync Server 2013 中的語音原則</span><span class="sxs-lookup"><span data-stu-id="19769-102">Voice policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="19769-103">_**主題上次修改日期：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="19769-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="19769-104">Lync Server*語音原則*針對指派原則的每個使用者、網站或組織，定義下列各項：</span><span class="sxs-lookup"><span data-stu-id="19769-104">Lync Server *voice policies* define the following for each user, site, or organization that is assigned the policy:</span></span>

  - <span data-ttu-id="19769-105">一組可啟用或停用的呼叫功能，可決定使用者可使用的 Enterprise Voice 功能。</span><span class="sxs-lookup"><span data-stu-id="19769-105">A set of calling features that can be enabled or disabled to determine the Enterprise Voice functionality available to users.</span></span>

  - <span data-ttu-id="19769-106">一組公用交換電話網路 (PSTN) 使用方式記錄，可定義授權的來電類型。</span><span class="sxs-lookup"><span data-stu-id="19769-106">A set of public switched telephone network (PSTN) usage records that define what types of calls are authorized.</span></span>

<div>

## <a name="planning-for-voice-policies"></a><span data-ttu-id="19769-107">規劃語音原則</span><span class="sxs-lookup"><span data-stu-id="19769-107">Planning for Voice Policies</span></span>

<span data-ttu-id="19769-108">下列步驟可協助您規劃企業語音部署所需的語音原則：</span><span class="sxs-lookup"><span data-stu-id="19769-108">The following steps will help you plan the voice policies that you will need for your Enterprise Voice deployment:</span></span>

  - <span data-ttu-id="19769-109">決定如何設定全域語音原則 (隨產品) 安裝的預設語音原則。</span><span class="sxs-lookup"><span data-stu-id="19769-109">Determine how you will configure your global voice policy (the default voice policy that is installed with the product).</span></span> <span data-ttu-id="19769-110">這個原則會套用至所有未明確指派網站層級或每位使用者原則的 Enterprise Voice 使用者。</span><span class="sxs-lookup"><span data-stu-id="19769-110">This policy will apply to all Enterprise Voice users who are not explicitly assigned a site-level or per-user policy.</span></span>

  - <span data-ttu-id="19769-111">識別您可能需要的任何網站層級語音原則。</span><span class="sxs-lookup"><span data-stu-id="19769-111">Identify any site-level voice policies that you might need.</span></span>

  - <span data-ttu-id="19769-112">識別您可能需要的任何個別使用者語音原則。</span><span class="sxs-lookup"><span data-stu-id="19769-112">Identify any per-user voice policies that you might need.</span></span>

  - <span data-ttu-id="19769-113">決定要針對每個語音原則啟用哪些通話功能。</span><span class="sxs-lookup"><span data-stu-id="19769-113">Decide which call features to enable for each voice policy.</span></span>

  - <span data-ttu-id="19769-114">決定要針對每個語音原則設定的 PSTN 使用方式記錄。</span><span class="sxs-lookup"><span data-stu-id="19769-114">Determine what PSTN usage records to configure for each voice policy.</span></span>

<div>

## <a name="voice-policy-scope"></a><span data-ttu-id="19769-115">語音原則範圍</span><span class="sxs-lookup"><span data-stu-id="19769-115">Voice Policy Scope</span></span>

<span data-ttu-id="19769-116">*語音原則範圍*決定原則可以套用的層級。</span><span class="sxs-lookup"><span data-stu-id="19769-116">*Voice policy scope* determines the hierarchical level at which the policy can be applied.</span></span> <span data-ttu-id="19769-117">在 Lync Server 中，您可以設定具有下列範圍層級的語音原則， (依最常見的) 列出。</span><span class="sxs-lookup"><span data-stu-id="19769-117">In Lync Server, you can configure voice policies with the following scope levels (listed from the most specific to the most general).</span></span>

  - <span data-ttu-id="19769-118">**使用者語音原則**可以指派給個別的使用者、群組或連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="19769-118">**User voice policy** can be assigned to individual users, groups, or contact objects.</span></span> <span data-ttu-id="19769-119">這是最低的層級原則。</span><span class="sxs-lookup"><span data-stu-id="19769-119">This is the lowest level policy.</span></span> <span data-ttu-id="19769-120">您可以部署使用者語音原則，以在網站上啟用特定使用者或群組的功能，而不是在相同網站中的其他使用者。</span><span class="sxs-lookup"><span data-stu-id="19769-120">User voice policies can be deployed to enable features for certain users or groups at a site, but not for others in the same site.</span></span> <span data-ttu-id="19769-121">例如，您可能想要對某些員工停用長途撥號。</span><span class="sxs-lookup"><span data-stu-id="19769-121">For example, you may want to disable long distance dialing for some employees.</span></span> <span data-ttu-id="19769-122">出於指派語音原則的目的，連絡人物件會被視為個別使用者。</span><span class="sxs-lookup"><span data-stu-id="19769-122">For the purpose of assigning a voice policy, a contact object is treated as an individual user.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="19769-123">建議您部署使用者語音原則，以供向中央網站部署註冊的分支網站 Enterprise Voice 使用者或已在 Survivable Branch 裝置上登錄的使用者。</span><span class="sxs-lookup"><span data-stu-id="19769-123">We recommend that you deploy a user voice policy for branch site Enterprise Voice users who are registered with the central site deployment, or users who are registered on a Survivable Branch Appliance.</span></span>

    
    </div>

  - <span data-ttu-id="19769-124">**網站語音原則**適用于整個網站，但不包括指派使用者語音原則的任何使用者、群組或連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="19769-124">**Site voice policy** applies to an entire site, except for any users, groups, or contact objects that are assigned a user voice policy.</span></span> <span data-ttu-id="19769-125">若要定義網站語音原則，您必須指定要套用原則的網站。</span><span class="sxs-lookup"><span data-stu-id="19769-125">To define a site voice policy, you must specify the site to which the policy applies.</span></span> <span data-ttu-id="19769-126">若未指派使用者語音原則，則會使用網站語音原則。</span><span class="sxs-lookup"><span data-stu-id="19769-126">If a user voice policy is not assigned, the site voice policy is used.</span></span>

  - <span data-ttu-id="19769-127">**Global voice policy**是隨產品一起安裝的預設語音原則。</span><span class="sxs-lookup"><span data-stu-id="19769-127">**Global voice policy** is the default voice policy that is installed with the product.</span></span> <span data-ttu-id="19769-128">您可以編輯全域語音原則，以符合組織的特定需求，但是您無法重新命名或刪除。</span><span class="sxs-lookup"><span data-stu-id="19769-128">You can edit the global voice policy to meet the specific needs of your organization, but you cannot rename or delete it.</span></span> <span data-ttu-id="19769-129">這個語音原則會套用至部署中的所有 Enterprise Voice 使用者、群組和連絡人物件，除非您設定並指派具有更特定範圍的語音原則。</span><span class="sxs-lookup"><span data-stu-id="19769-129">This voice policy applies to all Enterprise Voice users, groups, and contact objects in your deployment unless you configure and assign a voice policy with more specific scope.</span></span> <span data-ttu-id="19769-130">若要完全停用這個原則，請確定所有的網站和使用者都有指派的自訂原則。</span><span class="sxs-lookup"><span data-stu-id="19769-130">If you want to disable this policy entirely, be sure that all sites and users have custom policies assigned to them.</span></span>

</div>

<div>

## <a name="call-features"></a><span data-ttu-id="19769-131">通話功能</span><span class="sxs-lookup"><span data-stu-id="19769-131">Call Features</span></span>

<span data-ttu-id="19769-132">您可以針對每個語音原則啟用或停用下列通話功能：</span><span class="sxs-lookup"><span data-stu-id="19769-132">You can enable or disable the following call features for each voice policy:</span></span>

  - <span data-ttu-id="19769-133">**[來電轉接]** 可讓使用者將來電轉接到其他電話和用戶端裝置。</span><span class="sxs-lookup"><span data-stu-id="19769-133">**Call forwarding** enables users to forward calls to other phones and client devices.</span></span> <span data-ttu-id="19769-134">預設為啟用。</span><span class="sxs-lookup"><span data-stu-id="19769-134">Enabled by default.</span></span>

  - <span data-ttu-id="19769-135">**[委派]** 可讓使用者指定其他使用者，來代表他們撥號和接聽電話。</span><span class="sxs-lookup"><span data-stu-id="19769-135">**Delegation** enables users to specify other users to send and receive calls on their behalf.</span></span> <span data-ttu-id="19769-136">預設為啟用。</span><span class="sxs-lookup"><span data-stu-id="19769-136">Enabled by default.</span></span>

  - <span data-ttu-id="19769-137">**[通話轉接]** 可讓使用者將通話轉接給其他使用者。</span><span class="sxs-lookup"><span data-stu-id="19769-137">**Call transfer** enables users to transfer calls to other users.</span></span> <span data-ttu-id="19769-138">預設為啟用。</span><span class="sxs-lookup"><span data-stu-id="19769-138">Enabled by default.</span></span>

  - <span data-ttu-id="19769-139">**通話駐留**可讓使用者寄存通話，然後從不同的電話或用戶端挑選來電。</span><span class="sxs-lookup"><span data-stu-id="19769-139">**Call park** enables users to park calls and then pick up the call from a different phone or client.</span></span> <span data-ttu-id="19769-140">預設為停用。</span><span class="sxs-lookup"><span data-stu-id="19769-140">Disabled by default.</span></span>

  - <span data-ttu-id="19769-141">**同時震鈴**允許來電撥打額外的電話 (例如，行動電話) 或其他端點裝置。</span><span class="sxs-lookup"><span data-stu-id="19769-141">**Simultaneous ringing** enables incoming calls to ring on an additional phone (for example, a mobile phone) or other endpoint devices.</span></span> <span data-ttu-id="19769-142">預設為啟用。</span><span class="sxs-lookup"><span data-stu-id="19769-142">Enabled by default.</span></span>

  - <span data-ttu-id="19769-143">**[小組通話]** 可讓所定義小組的使用者接聽該小組其他成員的通話。</span><span class="sxs-lookup"><span data-stu-id="19769-143">**Team call** enables users on a defined team to answer calls for other members of the team.</span></span> <span data-ttu-id="19769-144">預設為啟用。</span><span class="sxs-lookup"><span data-stu-id="19769-144">Enabled by default.</span></span>

  - <span data-ttu-id="19769-145">**PSTN 重新路由**功能可讓指派此原則的使用者所撥打的使用者，在公用交換電話網路 (PSTN) （WAN 遭到擁塞或無法使用時）進行重新路由傳送。</span><span class="sxs-lookup"><span data-stu-id="19769-145">**PSTN reroute** enables calls made by users who are assigned this policy to other enterprise users to be rerouted on the public switched telephone network (PSTN) if the WAN is congested or unavailable.</span></span> <span data-ttu-id="19769-146">預設為啟用。</span><span class="sxs-lookup"><span data-stu-id="19769-146">Enabled by default.</span></span>

  - <span data-ttu-id="19769-147">**頻寬原則覆寫**可讓系統管理員覆寫特定使用者的通話許可控制原則決定。</span><span class="sxs-lookup"><span data-stu-id="19769-147">**Bandwidth policy override** enables administrators to override call admission control policy decisions for a particular user.</span></span> <span data-ttu-id="19769-148">預設為停用。</span><span class="sxs-lookup"><span data-stu-id="19769-148">Disabled by default.</span></span>

  - <span data-ttu-id="19769-149">**惡意的呼叫追蹤功能**可讓使用者使用 Lync 用戶端來報告惡意通話，然後在詳細通話記錄中旗標此通話。</span><span class="sxs-lookup"><span data-stu-id="19769-149">**Malicious call tracing** enables users to report malicious calls by using the Lync client, and then flags such calls in the call detail records.</span></span> <span data-ttu-id="19769-150">預設為停用。</span><span class="sxs-lookup"><span data-stu-id="19769-150">Disabled by default.</span></span>

  - <span data-ttu-id="19769-151">**語音信箱 escape**可在設定同時震鈴時，立即將來電路由傳送到使用者的行動電話語音信箱系統，而且電話會關閉、電池計量不足或範圍外，而且會以計時器值為基礎。</span><span class="sxs-lookup"><span data-stu-id="19769-151">**Voicemail escape** prevents calls from being immediately routed to the user’s mobile phone voicemail system when simultaneous ringing is configured and the phone is turned off, out of battery, or out of range, and is based on a timer value.</span></span> <span data-ttu-id="19769-152">這項設定可啟用及停用計時器，並設定計時器的值。</span><span class="sxs-lookup"><span data-stu-id="19769-152">This setting enables and disables the timer and sets the value of the timer.</span></span> <span data-ttu-id="19769-153">只能使用 Lync Server 管理命令介面來設定它。</span><span class="sxs-lookup"><span data-stu-id="19769-153">It can be configured only by using the Lync Server Management Shell.</span></span> <span data-ttu-id="19769-154">預設為停用。</span><span class="sxs-lookup"><span data-stu-id="19769-154">Disabled by default.</span></span>

  - <span data-ttu-id="19769-155">**來電轉接和同時響鈴 PSTN 使用**方式可讓系統管理員指定與來電轉接和同時響鈴之語音原則相同的 PSTN 使用方式，將來電轉接和同時響鈴限制為僅限內部 Lync 使用者，或指定不同于語音原則 pstn 使用方式的自訂 PSTN 使用方式。</span><span class="sxs-lookup"><span data-stu-id="19769-155">**Call forwarding and simultaneous ringing PSTN usages** enables administrators to specify the same PSTN usage as the voice policy for call forwarding and simultaneous ringing, restrict call forwarding and simultaneous ringing to internal Lync users only, or specify a custom PSTN usage that is different from the voice policy’s PSTN usage.</span></span> <span data-ttu-id="19769-156">預設值是使用與來電轉接和同時響鈴的語音原則相同的 PSTN 使用方式。</span><span class="sxs-lookup"><span data-stu-id="19769-156">The default is to use the same PSTN usage as the voice policy for call forwarding and simultaneous ringing.</span></span>

</div>

<div>

## <a name="pstn-usage-records"></a><span data-ttu-id="19769-157">PSTN 使用方式記錄</span><span class="sxs-lookup"><span data-stu-id="19769-157">PSTN Usage Records</span></span>

<span data-ttu-id="19769-158">每個語音原則都應有一或多個相關聯的 PSTN 使用方式記錄。</span><span class="sxs-lookup"><span data-stu-id="19769-158">Each voice policy should have one or more associated PSTN usage records.</span></span> <span data-ttu-id="19769-159">PSTN 使用方式可以與語音原則相關聯，以進行同時震鈴及來電轉接的目的。</span><span class="sxs-lookup"><span data-stu-id="19769-159">PSTN usages can be associated with a voice policy for the purpose of simultaneous ringing and call forwarding only.</span></span> <span data-ttu-id="19769-160">如需規劃 PSTN 使用方式記錄的詳細資訊，請參閱[Lync Server 2013 中的 PSTN 使用方式記錄](lync-server-2013-pstn-usage-records.md)。</span><span class="sxs-lookup"><span data-stu-id="19769-160">For details about planning PSTN usage records, see [PSTN usage records in Lync Server 2013](lync-server-2013-pstn-usage-records.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="19769-161">PSTN 使用順序很重要，因為在將使用者對應到路由時，輸出路由功能會比較 PSTN 使用方式，從上到下。</span><span class="sxs-lookup"><span data-stu-id="19769-161">PSTN usage order is critical because in matching users to routes, the outbound routing functionality compares PSTN usages from top to bottom.</span></span> <span data-ttu-id="19769-162">如果第一個使用方式符合通話路由，則會使用該路由。</span><span class="sxs-lookup"><span data-stu-id="19769-162">If the first usage matches the call route, that route is used.</span></span> <span data-ttu-id="19769-163">否則，輸出路由功能會查看清單中的下一個 PSTN 使用狀況，並繼續直到找到相符專案為止。</span><span class="sxs-lookup"><span data-stu-id="19769-163">If not, the outbound routing functionality looks at the next PSTN usage on the list and continues until a match is found.</span></span> <span data-ttu-id="19769-164">實際上，如果清單中的第一個無法使用，後續的 PSTN 使用方式也會提供備份。</span><span class="sxs-lookup"><span data-stu-id="19769-164">In effect, the subsequent PSTN usages provide backup if the first one on the list is unavailable.</span></span>



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

