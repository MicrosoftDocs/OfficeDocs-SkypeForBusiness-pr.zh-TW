---
title: Lync Server 2013：將使用者移至企業語音
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Moving users to Enterprise Voice
ms:assetid: a2df6d51-5cf2-4d3e-8f97-496af5fd5e5e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412758(v=OCS.15)
ms:contentKeyID: 48184958
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1127bd0c767da7f02df8aefb30fda41a64bd353a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40973999"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="moving-users-to-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="f49c9-102">在 Lync Server 2013 中將使用者移至企業語音</span><span class="sxs-lookup"><span data-stu-id="f49c9-102">Moving users to Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f49c9-103">_**主題上次修改日期：** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="f49c9-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="f49c9-104">如果您是將現有的 PBX 電話結構中的使用者移至企業語音，則部署程式會包含一些並非在[Lync Server 2013 規劃企業語音](lync-server-2013-planning-for-enterprise-voice.md)的規劃程式中所述的步驟。</span><span class="sxs-lookup"><span data-stu-id="f49c9-104">If you are moving users from an existing PBX telephony infrastructure to Enterprise Voice, the deployment process includes some steps that are not part of the planning process already described in [Planning for Enterprise Voice in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md).</span></span> <span data-ttu-id="f49c9-105">如需從舊版企業語音部署中遷移使用者的相關資訊，請參閱安裝媒體隨附的 [遷移檔]。</span><span class="sxs-lookup"><span data-stu-id="f49c9-105">For information about migrating users from an earlier Enterprise Voice deployment, see the migration documents that were included with your installation media.</span></span>

<span data-ttu-id="f49c9-106">將使用者從現有的電話架構移至企業語音的程式，包括下列步驟：</span><span class="sxs-lookup"><span data-stu-id="f49c9-106">The process of moving users from an existing telephony infrastructure to Enterprise Voice consists of the following steps:</span></span>

1.  <span data-ttu-id="f49c9-107">指定主要電話號碼。</span><span class="sxs-lookup"><span data-stu-id="f49c9-107">Designate primary phone numbers.</span></span>

2.  <span data-ttu-id="f49c9-108">允許使用者使用企業語音。</span><span class="sxs-lookup"><span data-stu-id="f49c9-108">Enable users for Enterprise Voice.</span></span>

3.  <span data-ttu-id="f49c9-109">為使用者準備撥號方案。</span><span class="sxs-lookup"><span data-stu-id="f49c9-109">Prepare dial plans for users.</span></span>

4.  <span data-ttu-id="f49c9-110">規劃使用者語音原則。</span><span class="sxs-lookup"><span data-stu-id="f49c9-110">Plan user voice policies.</span></span>

5.  <span data-ttu-id="f49c9-111">規劃通話路線。</span><span class="sxs-lookup"><span data-stu-id="f49c9-111">Plan call routes.</span></span>

6.  <span data-ttu-id="f49c9-112">設定 PBX 或 SIP 幹線來重新路由針對企業語音啟用的使用者的通話。</span><span class="sxs-lookup"><span data-stu-id="f49c9-112">Configure PBX or SIP Trunk to reroute calls for users enabled for Enterprise Voice.</span></span>

7.  <span data-ttu-id="f49c9-113">將使用者移至 Exchange 整合通訊（UM）（建議使用）。</span><span class="sxs-lookup"><span data-stu-id="f49c9-113">Move users to Exchange Unified Messaging (UM) (recommended).</span></span>

<span data-ttu-id="f49c9-114">本主題描述每個步驟所需的規劃。</span><span class="sxs-lookup"><span data-stu-id="f49c9-114">This topic describes the planning that is necessary for each of these steps.</span></span>

<div>

## <a name="step-1-designate-primary-phone-numbers"></a><span data-ttu-id="f49c9-115">步驟1。</span><span class="sxs-lookup"><span data-stu-id="f49c9-115">Step 1.</span></span> <span data-ttu-id="f49c9-116">指定主要電話號碼</span><span class="sxs-lookup"><span data-stu-id="f49c9-116">Designate primary phone numbers</span></span>

<span data-ttu-id="f49c9-117">企業語音會將語音與其他訊息媒體整合，在來電到達伺服器時，伺服器會將號碼對應至使用者的 SIP URI，然後將呼叫派生到與該 SIP URI 相關的所有用戶端端點。</span><span class="sxs-lookup"><span data-stu-id="f49c9-117">Enterprise Voice integrates voice with other messaging media, such that when an incoming call arrives at the server, the server maps the number to the user’s SIP-URI and then forks the call to all the client endpoints associated with that SIP-URI.</span></span> <span data-ttu-id="f49c9-118">這個程式要求每個使用者都要與主要電話號碼相關聯。</span><span class="sxs-lookup"><span data-stu-id="f49c9-118">This process requires that each user be associated with a primary phone number.</span></span>

<span data-ttu-id="f49c9-119">主要電話號碼必須是：</span><span class="sxs-lookup"><span data-stu-id="f49c9-119">A primary phone number must be:</span></span>

  - <span data-ttu-id="f49c9-120">全域唯一或（如果是內部擴充），在企業中則是唯一的。</span><span class="sxs-lookup"><span data-stu-id="f49c9-120">Globally unique or, in the case of internal extensions, unique in the enterprise.</span></span>

  - <span data-ttu-id="f49c9-121">在企業中擁有及路由。</span><span class="sxs-lookup"><span data-stu-id="f49c9-121">Owned by and routable in the enterprise.</span></span> <span data-ttu-id="f49c9-122">不應使用個人號碼。</span><span class="sxs-lookup"><span data-stu-id="f49c9-122">Personal numbers should not be used.</span></span>

<span data-ttu-id="f49c9-123">企業使用者可以在 Active Directory 網域服務中列出兩個或多個電話號碼。</span><span class="sxs-lookup"><span data-stu-id="f49c9-123">Enterprise users can have two or more telephone numbers listed for them in Active Directory Domain Services.</span></span> <span data-ttu-id="f49c9-124">在 Active Directory 使用者和電腦管理單元中，您可以在該使用者的屬性工作表上查看或變更所有與特定使用者相關聯的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="f49c9-124">All the telephone numbers associated with a particular user can be viewed or changed on the property sheet for that user in the Active Directory Users and Computers snap-in.</span></span>

<span data-ttu-id="f49c9-125">[**使用者屬性**] 對話方塊的 [**一般**] 索引標籤上的 [**電話號碼**] 方塊中應包含使用者的主要公司電話號碼。</span><span class="sxs-lookup"><span data-stu-id="f49c9-125">The **Telephone number** box on the **General** tab of the **User Properties** dialog box should contain the user’s main work number.</span></span> <span data-ttu-id="f49c9-126">這個數位通常會指定為使用者的主要電話號碼。</span><span class="sxs-lookup"><span data-stu-id="f49c9-126">This number will usually be designated as the user's Primary Phone Number.</span></span>

<span data-ttu-id="f49c9-127">有些使用者可能會有特殊需求（例如，想要讓所有來電都透過管理小幫手傳送），但這類例外狀況只會限制為需要清楚且不重要的那些例外狀況。</span><span class="sxs-lookup"><span data-stu-id="f49c9-127">Some users may have special requirements (for example, an executive who wants all incoming calls routed through an administrative assistant), but such exceptions should be limited only to those where the need is clear and critical.</span></span>

<span data-ttu-id="f49c9-128">選取主要數位之後，必須：</span><span class="sxs-lookup"><span data-stu-id="f49c9-128">After a primary number is chosen, it must be:</span></span>

  - <span data-ttu-id="f49c9-129">盡可能正常化為. 164 格式。</span><span class="sxs-lookup"><span data-stu-id="f49c9-129">Normalized to E.164 format, wherever possible.</span></span>

  - <span data-ttu-id="f49c9-130">已複製到 Active Directory **msRTCSIP line**屬性。</span><span class="sxs-lookup"><span data-stu-id="f49c9-130">Copied to the Active Directory **msRTCSIP-line** attribute.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f49c9-131"><STRONG>與遠端通話控制（RCC）共存</STRONG></span><span class="sxs-lookup"><span data-stu-id="f49c9-131"><STRONG>Coexisting with remote call control (RCC)</STRONG></span></span><BR><span data-ttu-id="f49c9-132">RCC 是使用 Lync Server 來監視及控制桌面 PBX 手機的功能。</span><span class="sxs-lookup"><span data-stu-id="f49c9-132">RCC is the ability to use Lync Server to monitor and control a desktop PBX phone.</span></span> <span data-ttu-id="f49c9-133">控制是透過伺服器路由的，可充當 PBX 的閘道。</span><span class="sxs-lookup"><span data-stu-id="f49c9-133">Control is routed through the server, which acts as a gateway to the PBX.</span></span> <span data-ttu-id="f49c9-134">雖然您無法同時設定 RCC 和企業語音的使用者，但 [列 URI] 設定會在任何情況下指定使用者的主要電話號碼。</span><span class="sxs-lookup"><span data-stu-id="f49c9-134">Although you cannot configure a user for both RCC and Enterprise Voice, the Line URI setting designates a user’s primary phone number in either case.</span></span><BR><span data-ttu-id="f49c9-135">如果您有您想要讓使用者繼續使用的現有 PBX 基礎結構，您可以將企業語音逐步引入您的組織。</span><span class="sxs-lookup"><span data-stu-id="f49c9-135">If you have an existing PBX infrastructure that you want selected users to continue using, you can introduce Enterprise Voice incrementally into your organization.</span></span> <span data-ttu-id="f49c9-136">如需此部署案例的詳細資訊，請參閱規劃檔中的<A href="lync-server-2013-direct-sip-deployment-options.md">Lync Server 2013 中的直接 SIP 部署選項</A>。</span><span class="sxs-lookup"><span data-stu-id="f49c9-136">For details about this deployment scenario, see <A href="lync-server-2013-direct-sip-deployment-options.md">Direct SIP deployment options in Lync Server 2013</A> in the Planning documentation.</span></span><BR><span data-ttu-id="f49c9-137">在前一個版本中，您可以為使用者啟用 RCC 和企業版語音，但只有當您同時設定雙重呼叫的使用者時，傳入通話會同時撥打使用者的 PBX 手機和 Communicator 的功能。</span><span class="sxs-lookup"><span data-stu-id="f49c9-137">In previous releases, you could enable both RCC and Enterprise Voice for a user, but only if you also configured the user for dual forking, a feature in which an incoming call will ring a user’s PBX phone and Communicator simultaneously.</span></span> <span data-ttu-id="f49c9-138">在 Lync Server 2010 中，不支援雙分叉。</span><span class="sxs-lookup"><span data-stu-id="f49c9-138">In Lync Server 2010, dual-forking is not supported.</span></span>

    
    </div>

<span data-ttu-id="f49c9-139">有三種方法可填充**msRTCSIP**屬性：</span><span class="sxs-lookup"><span data-stu-id="f49c9-139">There are three methods for populating the **msRTCSIP-line** attribute:</span></span>

  - <span data-ttu-id="f49c9-140">Microsoft 身分識別整合伺服器（建議使用）</span><span class="sxs-lookup"><span data-stu-id="f49c9-140">Microsoft Identity Integration Server (recommended)</span></span>

  - <span data-ttu-id="f49c9-141">Lync Server [控制台] 中的 [**使用者**] 頁面</span><span class="sxs-lookup"><span data-stu-id="f49c9-141">The **Users** page in the Lync Server Control Panel</span></span>

<span data-ttu-id="f49c9-142">在必須處理多個電話號碼的情況下，您組織所開發的腳本是比較好的選擇。</span><span class="sxs-lookup"><span data-stu-id="f49c9-142">Where many phone numbers must be processed, a script custom developed by your organization is the better choice.</span></span> <span data-ttu-id="f49c9-143">根據貴組織在 Active Directory 網域服務中代表電話號碼的方式，此腳本可能必須先將主要電話號碼標準化為 E. 164 格式，然後才能將其複製到**msRTCSIP**屬性。</span><span class="sxs-lookup"><span data-stu-id="f49c9-143">Depending on how your organization represents telephone numbers in Active Directory Domain Services, the script may have to normalize primary phone numbers to E.164 format before copying them to the **msRTCSIP-line** attribute.</span></span>

  - <span data-ttu-id="f49c9-144">如果您的組織以單一格式維護 Active Directory 網域服務中的所有電話號碼，而如果該格式是 E. 164，您的腳本只需要將每個主要電話號碼寫入**msRTCSIP**屬性。</span><span class="sxs-lookup"><span data-stu-id="f49c9-144">If your organization maintains all telephone numbers in Active Directory Domain Services in a single format, and if that format is E.164, your script only needs to write each Primary Telephone Number to the **msRTCSIP-line** attribute.</span></span>

  - <span data-ttu-id="f49c9-145">如果您的組織以單一格式維護 Active Directory 網域服務中的所有電話號碼，但該格式不是 E. 164，您的腳本應該定義適當的正常化規則，以便將主要電話號碼從其現有的格式轉換為 E.i，然後再將其寫入**msRTCSIP**屬性。</span><span class="sxs-lookup"><span data-stu-id="f49c9-145">If your organization maintains all telephone numbers in Active Directory Domain Services in a single format, but that format is not E.164, your script should define an appropriate normalization rule to convert Primary Telephone Numbers from their existing format to E.164 before writing them to the **msRTCSIP-line** attribute.</span></span>

  - <span data-ttu-id="f49c9-146">如果您的組織沒有在 Active Directory 網域服務中強制執行電話號碼的標準格式，您的腳本應該定義適當的正常化規則，將主要電話號碼從其各種格式轉換為 MsRTCSIP，然後再將主要電話號碼寫入\*\*\*\* 屬性。</span><span class="sxs-lookup"><span data-stu-id="f49c9-146">If your organization does not enforce a standard format for telephone numbers in Active Directory Domain Services, your script should define appropriate normalization rules to convert Primary Phone Numbers from their various formats to E.164 compliance before writing the Primary Telephone Numbers to the **msRTCSIP-line** attribute.</span></span>

<span data-ttu-id="f49c9-147">您的腳本也必須插入前置詞**電話：** 在將主要號碼寫入**msRTCSIP**屬性之前。</span><span class="sxs-lookup"><span data-stu-id="f49c9-147">Your script will also have to insert the prefix **Tel:** before each primary number before writing it to the **msRTCSIP-line** attribute.</span></span>

<span data-ttu-id="f49c9-148">這個屬性所指定之數位的預期格式為：</span><span class="sxs-lookup"><span data-stu-id="f49c9-148">The expected format of the number specified in this attribute is:</span></span>

  - <span data-ttu-id="f49c9-149">電話： + 14255550100; ext = 50100。</span><span class="sxs-lookup"><span data-stu-id="f49c9-149">Tel:+14255550100;ext=50100.</span></span>

  - <span data-ttu-id="f49c9-150">電話：5550100（適用于獨特的企業廣泛延伸）</span><span class="sxs-lookup"><span data-stu-id="f49c9-150">Tel:5550100 (for unique enterprise wide extensions)</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="f49c9-151">通訊錄服務（ABS）執行的正常化不會取代，也不需要在 Active Directory 網域服務中將每個使用者的主要電話號碼標準化，因為 ABS 沒有 Active Directory 網域服務的存取權，因此無法將主要數位複製到<STRONG>msRTCSIP</STRONG>屬性。</span><span class="sxs-lookup"><span data-stu-id="f49c9-151">The normalization performed by the Address Book Service (ABS) does not replace or otherwise eliminate the need to normalize each user's primary phone number in Active Directory Domain Services because ABS does not have access to Active Directory Domain Services and therefore cannot copy primary numbers to the <STRONG>msRTCSIP-line</STRONG> attribute.</span></span>

    
    </div>

</div>

<div>

## <a name="step-2-enable-users-for-enterprise-voice"></a><span data-ttu-id="f49c9-152">步驟2。</span><span class="sxs-lookup"><span data-stu-id="f49c9-152">Step 2.</span></span> <span data-ttu-id="f49c9-153">為使用者啟用企業語音</span><span class="sxs-lookup"><span data-stu-id="f49c9-153">Enable users for Enterprise Voice</span></span>

<span data-ttu-id="f49c9-154">除了識別要啟用的使用者之外，不需要進行特殊規劃，就能完成這個步驟。</span><span class="sxs-lookup"><span data-stu-id="f49c9-154">Other than identifying which users are to be enabled, no special planning is required to complete this step.</span></span>

</div>

<div>

## <a name="step-3-prepare-dial-plans-for-users"></a><span data-ttu-id="f49c9-155">步驟3。</span><span class="sxs-lookup"><span data-stu-id="f49c9-155">Step 3.</span></span> <span data-ttu-id="f49c9-156">為使用者準備撥號方案。</span><span class="sxs-lookup"><span data-stu-id="f49c9-156">Prepare dial plans for users.</span></span>

<span data-ttu-id="f49c9-157">已啟用企業語音的使用者將無法呼叫 PSTN，而不需撥號方案。</span><span class="sxs-lookup"><span data-stu-id="f49c9-157">Users who are enabled for Enterprise Voice will not be able to make calls to the PSTN without dial plans in place.</span></span> <span data-ttu-id="f49c9-158">撥號方案是一組命名的正常化規則，可將命名位置、個別使用者或連絡人物件的電話號碼轉換成單一標準（e. 164）格式，以用於手機授權及呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="f49c9-158">A dial plan is a named set of normalization rules that translates phone numbers for a named location, individual user, or contact object into a single standard (E.164) format for purposes of phone authorization and call routing.</span></span> <span data-ttu-id="f49c9-159">正常化規則定義以各種格式表示的電話號碼如何針對每一個指定的位置、使用者或連絡人物件進行路由。</span><span class="sxs-lookup"><span data-stu-id="f49c9-159">Normalization rules define how phone numbers expressed in various formats are to be routed for each specified location, user, or contact object.</span></span>

<span data-ttu-id="f49c9-160">如需有關準備撥號方案的詳細資訊，請參閱[Lync Server 2013 中的撥號方案和正常化規則](lync-server-2013-dial-plans-and-normalization-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="f49c9-160">For information about preparing dial plans, see [Dial plans and normalization rules in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md).</span></span>

</div>

<div>

## <a name="step-4-plan-user-voice-policies"></a><span data-ttu-id="f49c9-161">步驟4。</span><span class="sxs-lookup"><span data-stu-id="f49c9-161">Step 4.</span></span> <span data-ttu-id="f49c9-162">規劃使用者語音原則</span><span class="sxs-lookup"><span data-stu-id="f49c9-162">Plan user voice policies</span></span>

<span data-ttu-id="f49c9-163">在舊版 PBX （例如從公司手機撥打遠距離或國際電話）上的 [使用者類別] 設定，必須針對移至企業語音的使用者，將其重新配置為 VoIP 原則。</span><span class="sxs-lookup"><span data-stu-id="f49c9-163">User class-of-service settings on a legacy PBX, such as the right to make long-distance or international calls from company phones, must be reconfigured as VoIP policies for users moved to Enterprise Voice.</span></span> <span data-ttu-id="f49c9-164">如需規劃及建立企業語音原則的詳細資料，請參閱[Lync Server 2013 中的語音原則](lync-server-2013-voice-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="f49c9-164">For details about planning and creating policies for Enterprise Voice, see [Voice policies in Lync Server 2013](lync-server-2013-voice-policies.md).</span></span>

</div>

<div>

## <a name="step-5-plan-outbound-call-routes"></a><span data-ttu-id="f49c9-165">步驟5。</span><span class="sxs-lookup"><span data-stu-id="f49c9-165">Step 5.</span></span> <span data-ttu-id="f49c9-166">規劃出站通話路線</span><span class="sxs-lookup"><span data-stu-id="f49c9-166">Plan outbound call routes</span></span>

<span data-ttu-id="f49c9-167">[通話路線] 可指定 Lync Server 處理企業語音使用者所放的出站通話的方式。</span><span class="sxs-lookup"><span data-stu-id="f49c9-167">Call routes specify how Lync Server handles outbound calls placed by Enterprise Voice users.</span></span> <span data-ttu-id="f49c9-168">當使用者撥打電話號碼時，如有必要，伺服器會將撥號字串標準化為 E.i 格式，並嘗試將它與 SIP URI 相符。</span><span class="sxs-lookup"><span data-stu-id="f49c9-168">When a user dials a number, the server, if necessary, normalizes the dial string to E.164 format and attempts to match it to a SIP URI.</span></span> <span data-ttu-id="f49c9-169">如果伺服器無法進行相符，就會根據數位來套用撥出電話路由邏輯。</span><span class="sxs-lookup"><span data-stu-id="f49c9-169">If the server is unable to make the match, it applies outgoing call routing logic based on the number.</span></span> <span data-ttu-id="f49c9-170">定義該邏輯的最後一個步驟是為每一組在每個撥號計畫中列出的目的地電話號碼建立單獨的命名呼叫路線。</span><span class="sxs-lookup"><span data-stu-id="f49c9-170">The final step in defining that logic is creating a separate named call route for each set of destination phone numbers that are listed in each dial plan.</span></span>

<span data-ttu-id="f49c9-171">如需規劃通話路線的詳細資料，請參閱[Lync Server 2013 中的語音路由](lync-server-2013-voice-routes.md)。</span><span class="sxs-lookup"><span data-stu-id="f49c9-171">For details about planning call routes, see [Voice routes in Lync Server 2013](lync-server-2013-voice-routes.md).</span></span>

</div>

<div>

## <a name="step-6-configure-pbx-or-sip-trunk-to-reroute-calls-for-enterprise-voice-users"></a><span data-ttu-id="f49c9-172">步驟6。</span><span class="sxs-lookup"><span data-stu-id="f49c9-172">Step 6.</span></span> <span data-ttu-id="f49c9-173">設定 PBX 或 SIP 幹線來重新路由企業語音使用者的通話</span><span class="sxs-lookup"><span data-stu-id="f49c9-173">Configure PBX or SIP Trunk to reroute calls for Enterprise Voice users</span></span>

<span data-ttu-id="f49c9-174">在傳統 PBX 或 SIP 中繼連線中，原有的使用者是以網際網路電話服務提供者（ITSP）為宿主，在移動之後，就會保留他們的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="f49c9-174">Users who formerly were hosted on a traditional PBX or on a SIP Trunk connection to an Internet Telephony Service Provider (ITSP) retain their phone numbers after the move.</span></span> <span data-ttu-id="f49c9-175">唯一的需求是，在移動之後，必須重新配置 PBX 或 SIP 幹線，才能將企業語音使用者的來電路由到中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="f49c9-175">The only requirement is that after the move, the PBX or SIP Trunk must be reconfigured to route incoming calls for Enterprise Voice users to the Mediation Server.</span></span>

</div>

<div>

## <a name="step-7-move-users-to-exchange-unified-messaging-recommended"></a><span data-ttu-id="f49c9-176">步驟7。</span><span class="sxs-lookup"><span data-stu-id="f49c9-176">Step 7.</span></span> <span data-ttu-id="f49c9-177">將使用者移至 Exchange 整合訊息（建議使用）</span><span class="sxs-lookup"><span data-stu-id="f49c9-177">Move users to Exchange Unified Messaging (recommended)</span></span>

<span data-ttu-id="f49c9-178">將使用者移至 Exchange 整合訊息包含下列任務：</span><span class="sxs-lookup"><span data-stu-id="f49c9-178">Moving users to Exchange Unified Messaging consists of the following tasks:</span></span>

  - <span data-ttu-id="f49c9-179">設定 Exchange 整合訊息和 Lync 伺服器共同作業。</span><span class="sxs-lookup"><span data-stu-id="f49c9-179">Configure Exchange Unified Messaging and Lync Server to work together.</span></span>

  - <span data-ttu-id="f49c9-180">允許使用者使用 Exchange 整合訊息呼叫應答及 Outlook 語音存取。</span><span class="sxs-lookup"><span data-stu-id="f49c9-180">Enable users for Exchange Unified Messaging call answering and Outlook Voice Access.</span></span> <span data-ttu-id="f49c9-181">此工作是在 Exchange 整合通訊伺服器上執行。</span><span class="sxs-lookup"><span data-stu-id="f49c9-181">This task is performed on the Exchange Unified Messaging server.</span></span> <span data-ttu-id="f49c9-182">如需詳細資訊，請參閱 Exchange Server 2010 TechNet [http://go.microsoft.com/fwlink/p/?linkID=139372](http://go.microsoft.com/fwlink/p/?linkid=139372)文件庫。</span><span class="sxs-lookup"><span data-stu-id="f49c9-182">For details, see the Exchange Server 2010 TechNet Library at [http://go.microsoft.com/fwlink/p/?linkID=139372](http://go.microsoft.com/fwlink/p/?linkid=139372).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

