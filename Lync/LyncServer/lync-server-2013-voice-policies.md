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
ms.openlocfilehash: 3998bd6f879b20b1a22f46818a22f26bbb2cc29a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758605"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="voice-policies-in-lync-server-2013"></a><span data-ttu-id="42f94-102">Lync Server 2013 中的語音原則</span><span class="sxs-lookup"><span data-stu-id="42f94-102">Voice policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="42f94-103">_**主題上次修改日期：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="42f94-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="42f94-104">Lync Server*語音原則*會針對指派原則的每個使用者、網站或組織定義下列專案：</span><span class="sxs-lookup"><span data-stu-id="42f94-104">Lync Server *voice policies* define the following for each user, site, or organization that is assigned the policy:</span></span>

  - <span data-ttu-id="42f94-105">可以啟用或停用的一組通話功能，以判斷使用者可以使用的企業語音功能。</span><span class="sxs-lookup"><span data-stu-id="42f94-105">A set of calling features that can be enabled or disabled to determine the Enterprise Voice functionality available to users.</span></span>

  - <span data-ttu-id="42f94-106">一組公用的交換電話網絡（PSTN）使用記錄，可定義授權的呼叫類型。</span><span class="sxs-lookup"><span data-stu-id="42f94-106">A set of public switched telephone network (PSTN) usage records that define what types of calls are authorized.</span></span>

<div>

## <a name="planning-for-voice-policies"></a><span data-ttu-id="42f94-107">語音原則規劃</span><span class="sxs-lookup"><span data-stu-id="42f94-107">Planning for Voice Policies</span></span>

<span data-ttu-id="42f94-108">下列步驟將協助您規劃企業語音部署所需的語音原則：</span><span class="sxs-lookup"><span data-stu-id="42f94-108">The following steps will help you plan the voice policies that you will need for your Enterprise Voice deployment:</span></span>

  - <span data-ttu-id="42f94-109">決定如何設定您的全域語音原則（與產品一起安裝的預設語音原則）。</span><span class="sxs-lookup"><span data-stu-id="42f94-109">Determine how you will configure your global voice policy (the default voice policy that is installed with the product).</span></span> <span data-ttu-id="42f94-110">此原則將套用至所有未明確指派網站層級或依使用者原則的企業語音使用者。</span><span class="sxs-lookup"><span data-stu-id="42f94-110">This policy will apply to all Enterprise Voice users who are not explicitly assigned a site-level or per-user policy.</span></span>

  - <span data-ttu-id="42f94-111">找出您可能需要的任何網站層級語音原則。</span><span class="sxs-lookup"><span data-stu-id="42f94-111">Identify any site-level voice policies that you might need.</span></span>

  - <span data-ttu-id="42f94-112">找出您可能需要的任何每使用者語音原則。</span><span class="sxs-lookup"><span data-stu-id="42f94-112">Identify any per-user voice policies that you might need.</span></span>

  - <span data-ttu-id="42f94-113">針對每個語音原則，決定要啟用哪些通話功能。</span><span class="sxs-lookup"><span data-stu-id="42f94-113">Decide which call features to enable for each voice policy.</span></span>

  - <span data-ttu-id="42f94-114">決定要為每個語音原則設定哪些 PSTN 使用記錄。</span><span class="sxs-lookup"><span data-stu-id="42f94-114">Determine what PSTN usage records to configure for each voice policy.</span></span>

<div>

## <a name="voice-policy-scope"></a><span data-ttu-id="42f94-115">語音原則範圍</span><span class="sxs-lookup"><span data-stu-id="42f94-115">Voice Policy Scope</span></span>

<span data-ttu-id="42f94-116">*語音原則範圍*決定原則可以套用的階層層級。</span><span class="sxs-lookup"><span data-stu-id="42f94-116">*Voice policy scope* determines the hierarchical level at which the policy can be applied.</span></span> <span data-ttu-id="42f94-117">在 Lync Server 中，您可以使用下列範圍階層來設定語音原則（依最具體到最一般的順序列出）。</span><span class="sxs-lookup"><span data-stu-id="42f94-117">In Lync Server, you can configure voice policies with the following scope levels (listed from the most specific to the most general).</span></span>

  - <span data-ttu-id="42f94-118">您可以將**使用者語音原則**指派給個別的使用者、群組或連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="42f94-118">**User voice policy** can be assigned to individual users, groups, or contact objects.</span></span> <span data-ttu-id="42f94-119">這是最低的層級原則。</span><span class="sxs-lookup"><span data-stu-id="42f94-119">This is the lowest level policy.</span></span> <span data-ttu-id="42f94-120">您可以部署使用者語音原則，以針對網站上的特定使用者或群組啟用功能，但不適用於同一網站中的其他使用者。</span><span class="sxs-lookup"><span data-stu-id="42f94-120">User voice policies can be deployed to enable features for certain users or groups at a site, but not for others in the same site.</span></span> <span data-ttu-id="42f94-121">例如，您可能會想要針對某些員工停用長途撥號。</span><span class="sxs-lookup"><span data-stu-id="42f94-121">For example, you may want to disable long distance dialing for some employees.</span></span> <span data-ttu-id="42f94-122">出於指派語音原則的目的，連絡人物件會被視為個別使用者。</span><span class="sxs-lookup"><span data-stu-id="42f94-122">For the purpose of assigning a voice policy, a contact object is treated as an individual user.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="42f94-123">我們建議您為分支網站企業語音原則部署使用者語音原則，這些使用者已在中央網站部署中註冊，或已在 Survivable 分支裝置上註冊的使用者。</span><span class="sxs-lookup"><span data-stu-id="42f94-123">We recommend that you deploy a user voice policy for branch site Enterprise Voice users who are registered with the central site deployment, or users who are registered on a Survivable Branch Appliance.</span></span>

    
    </div>

  - <span data-ttu-id="42f94-124">**網站語音原則**適用于整個網站，除了指派使用者語音原則的任何使用者、群組或連絡人物件外。</span><span class="sxs-lookup"><span data-stu-id="42f94-124">**Site voice policy** applies to an entire site, except for any users, groups, or contact objects that are assigned a user voice policy.</span></span> <span data-ttu-id="42f94-125">若要定義網站語音原則，您必須指定原則要套用的網站。</span><span class="sxs-lookup"><span data-stu-id="42f94-125">To define a site voice policy, you must specify the site to which the policy applies.</span></span> <span data-ttu-id="42f94-126">如果沒有指派使用者語音原則，就會使用網站語音原則。</span><span class="sxs-lookup"><span data-stu-id="42f94-126">If a user voice policy is not assigned, the site voice policy is used.</span></span>

  - <span data-ttu-id="42f94-127">[**全域語音原則**] 是隨產品一起安裝的預設語音原則。</span><span class="sxs-lookup"><span data-stu-id="42f94-127">**Global voice policy** is the default voice policy that is installed with the product.</span></span> <span data-ttu-id="42f94-128">您可以編輯全域語音原則，以符合貴組織的特定需求，但您無法重新命名或刪除。</span><span class="sxs-lookup"><span data-stu-id="42f94-128">You can edit the global voice policy to meet the specific needs of your organization, but you cannot rename or delete it.</span></span> <span data-ttu-id="42f94-129">除非您以更具體的範圍設定並指派語音原則，否則此語音原則會套用到您部署中的所有企業語音使用者、群組和連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="42f94-129">This voice policy applies to all Enterprise Voice users, groups, and contact objects in your deployment unless you configure and assign a voice policy with more specific scope.</span></span> <span data-ttu-id="42f94-130">如果您想要完全停用此原則，請確定所有網站和使用者都已獲指派自訂原則。</span><span class="sxs-lookup"><span data-stu-id="42f94-130">If you want to disable this policy entirely, be sure that all sites and users have custom policies assigned to them.</span></span>

</div>

<div>

## <a name="call-features"></a><span data-ttu-id="42f94-131">通話功能</span><span class="sxs-lookup"><span data-stu-id="42f94-131">Call Features</span></span>

<span data-ttu-id="42f94-132">您可以針對每個語音原則啟用或停用下列通話功能：</span><span class="sxs-lookup"><span data-stu-id="42f94-132">You can enable or disable the following call features for each voice policy:</span></span>

  - <span data-ttu-id="42f94-133">[**來電轉接**] 可讓使用者將來電轉接至其他電話與用戶端裝置。</span><span class="sxs-lookup"><span data-stu-id="42f94-133">**Call forwarding** enables users to forward calls to other phones and client devices.</span></span> <span data-ttu-id="42f94-134">預設為啟用。</span><span class="sxs-lookup"><span data-stu-id="42f94-134">Enabled by default.</span></span>

  - <span data-ttu-id="42f94-135">**委派**可讓使用者指定其他使用者代表自己傳送和接收來電。</span><span class="sxs-lookup"><span data-stu-id="42f94-135">**Delegation** enables users to specify other users to send and receive calls on their behalf.</span></span> <span data-ttu-id="42f94-136">預設為啟用。</span><span class="sxs-lookup"><span data-stu-id="42f94-136">Enabled by default.</span></span>

  - <span data-ttu-id="42f94-137">[**來電轉接**] 可讓使用者將來電轉接給其他使用者。</span><span class="sxs-lookup"><span data-stu-id="42f94-137">**Call transfer** enables users to transfer calls to other users.</span></span> <span data-ttu-id="42f94-138">預設為啟用。</span><span class="sxs-lookup"><span data-stu-id="42f94-138">Enabled by default.</span></span>

  - <span data-ttu-id="42f94-139">**通話寄存**可讓使用者撥出電話，然後從不同的電話或用戶端挑選通話。</span><span class="sxs-lookup"><span data-stu-id="42f94-139">**Call park** enables users to park calls and then pick up the call from a different phone or client.</span></span> <span data-ttu-id="42f94-140">預設為停用。</span><span class="sxs-lookup"><span data-stu-id="42f94-140">Disabled by default.</span></span>

  - <span data-ttu-id="42f94-141">**同時撥打**可讓來電撥打其他電話（例如行動電話）或其他端點裝置。</span><span class="sxs-lookup"><span data-stu-id="42f94-141">**Simultaneous ringing** enables incoming calls to ring on an additional phone (for example, a mobile phone) or other endpoint devices.</span></span> <span data-ttu-id="42f94-142">預設為啟用。</span><span class="sxs-lookup"><span data-stu-id="42f94-142">Enabled by default.</span></span>

  - <span data-ttu-id="42f94-143">**團隊通話**可讓已定義的小組中的使用者接聽小組其他成員的來電。</span><span class="sxs-lookup"><span data-stu-id="42f94-143">**Team call** enables users on a defined team to answer calls for other members of the team.</span></span> <span data-ttu-id="42f94-144">預設為啟用。</span><span class="sxs-lookup"><span data-stu-id="42f94-144">Enabled by default.</span></span>

  - <span data-ttu-id="42f94-145">**PSTN 重新路由**可讓指派此原則的使用者所做的呼叫能在 WAN 擁塞或無法使用時，在公用交換電話網絡（PSTN）上重新路由。</span><span class="sxs-lookup"><span data-stu-id="42f94-145">**PSTN reroute** enables calls made by users who are assigned this policy to other enterprise users to be rerouted on the public switched telephone network (PSTN) if the WAN is congested or unavailable.</span></span> <span data-ttu-id="42f94-146">預設為啟用。</span><span class="sxs-lookup"><span data-stu-id="42f94-146">Enabled by default.</span></span>

  - <span data-ttu-id="42f94-147">[**頻寬原則覆蓋**] 可讓系統管理員覆寫特定使用者的呼叫許可控制原則決定。</span><span class="sxs-lookup"><span data-stu-id="42f94-147">**Bandwidth policy override** enables administrators to override call admission control policy decisions for a particular user.</span></span> <span data-ttu-id="42f94-148">預設為停用。</span><span class="sxs-lookup"><span data-stu-id="42f94-148">Disabled by default.</span></span>

  - <span data-ttu-id="42f94-149">**惡意的通話追蹤功能**可讓使用者使用 Lync 用戶端來報告惡意通話，然後在通話詳細資料記錄中標示此類通話。</span><span class="sxs-lookup"><span data-stu-id="42f94-149">**Malicious call tracing** enables users to report malicious calls by using the Lync client, and then flags such calls in the call detail records.</span></span> <span data-ttu-id="42f94-150">預設為停用。</span><span class="sxs-lookup"><span data-stu-id="42f94-150">Disabled by default.</span></span>

  - <span data-ttu-id="42f94-151">當您設定同時撥打且電話已關閉、不在電池或超出範圍，且以計時器值為基礎時，**語音**轉換功能可防止呼叫立即路由到使用者的行動電話語音信箱系統。</span><span class="sxs-lookup"><span data-stu-id="42f94-151">**Voicemail escape** prevents calls from being immediately routed to the user’s mobile phone voicemail system when simultaneous ringing is configured and the phone is turned off, out of battery, or out of range, and is based on a timer value.</span></span> <span data-ttu-id="42f94-152">此設定會啟用及停用計時器，並設定計時器的值。</span><span class="sxs-lookup"><span data-stu-id="42f94-152">This setting enables and disables the timer and sets the value of the timer.</span></span> <span data-ttu-id="42f94-153">它只能使用 Lync Server 管理命令介面進行設定。</span><span class="sxs-lookup"><span data-stu-id="42f94-153">It can be configured only by using the Lync Server Management Shell.</span></span> <span data-ttu-id="42f94-154">預設為停用。</span><span class="sxs-lookup"><span data-stu-id="42f94-154">Disabled by default.</span></span>

  - <span data-ttu-id="42f94-155">**來電轉接和同時撥打 PSTN 使用**方式可讓系統管理員指定與來電轉接和同時撥打的語音原則相同的 PSTN 使用狀況，限制來電轉接及同時撥打給內部的 Lync 使用者，或指定自訂的 pstn 使用狀況，這與語音原則的 pstn 用法不同。</span><span class="sxs-lookup"><span data-stu-id="42f94-155">**Call forwarding and simultaneous ringing PSTN usages** enables administrators to specify the same PSTN usage as the voice policy for call forwarding and simultaneous ringing, restrict call forwarding and simultaneous ringing to internal Lync users only, or specify a custom PSTN usage that is different from the voice policy’s PSTN usage.</span></span> <span data-ttu-id="42f94-156">預設是使用與來電轉接和同時撥打的語音原則相同的 PSTN 使用量。</span><span class="sxs-lookup"><span data-stu-id="42f94-156">The default is to use the same PSTN usage as the voice policy for call forwarding and simultaneous ringing.</span></span>

</div>

<div>

## <a name="pstn-usage-records"></a><span data-ttu-id="42f94-157">PSTN 使用記錄</span><span class="sxs-lookup"><span data-stu-id="42f94-157">PSTN Usage Records</span></span>

<span data-ttu-id="42f94-158">每個語音原則都應該有一個或多個相關聯的 PSTN 使用記錄。</span><span class="sxs-lookup"><span data-stu-id="42f94-158">Each voice policy should have one or more associated PSTN usage records.</span></span> <span data-ttu-id="42f94-159">PSTN 用途可以與語音原則相關聯，以同時撥打和來電轉接。</span><span class="sxs-lookup"><span data-stu-id="42f94-159">PSTN usages can be associated with a voice policy for the purpose of simultaneous ringing and call forwarding only.</span></span> <span data-ttu-id="42f94-160">如需規劃 PSTN 使用記錄的詳細資料，請參閱[Lync Server 2013 中的 PSTN 使用記錄](lync-server-2013-pstn-usage-records.md)。</span><span class="sxs-lookup"><span data-stu-id="42f94-160">For details about planning PSTN usage records, see [PSTN usage records in Lync Server 2013](lync-server-2013-pstn-usage-records.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="42f94-161">PSTN 使用順序非常重要，因為在與路由相符的使用者中，傳出路由功能會將 PSTN 使用量從上而下。</span><span class="sxs-lookup"><span data-stu-id="42f94-161">PSTN usage order is critical because in matching users to routes, the outbound routing functionality compares PSTN usages from top to bottom.</span></span> <span data-ttu-id="42f94-162">如果第一個使用方式符合呼叫路線，就會使用該路線。</span><span class="sxs-lookup"><span data-stu-id="42f94-162">If the first usage matches the call route, that route is used.</span></span> <span data-ttu-id="42f94-163">如果不是，輸出路由功能會在清單中尋找下一個 PSTN 使用量，並持續到找到相符為止。</span><span class="sxs-lookup"><span data-stu-id="42f94-163">If not, the outbound routing functionality looks at the next PSTN usage on the list and continues until a match is found.</span></span> <span data-ttu-id="42f94-164">事實上，如果清單中的第一個用法無法使用，後續的 PSTN 用法就會提供備份。</span><span class="sxs-lookup"><span data-stu-id="42f94-164">In effect, the subsequent PSTN usages provide backup if the first one on the list is unavailable.</span></span>



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

