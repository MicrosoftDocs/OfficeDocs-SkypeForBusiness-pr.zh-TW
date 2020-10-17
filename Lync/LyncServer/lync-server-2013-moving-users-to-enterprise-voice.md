---
title: Lync Server 2013：將使用者移至企業語音
description: Lync Server 2013：將使用者移至 Enterprise Voice。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Moving users to Enterprise Voice
ms:assetid: a2df6d51-5cf2-4d3e-8f97-496af5fd5e5e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412758(v=OCS.15)
ms:contentKeyID: 48184958
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 41b075f916f4d81d8d3c24c24c7393be58e10a92
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542009"
---
# <a name="moving-users-to-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="35467-103">在 Lync Server 2013 中將使用者移至企業語音</span><span class="sxs-lookup"><span data-stu-id="35467-103">Moving users to Enterprise Voice in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="35467-104">_**主題上次修改日期：** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="35467-104">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="35467-105">如果您要將使用者從現有的 PBX 電話語音基礎結構移至 Enterprise Voice，部署程式會包含一些步驟，這些步驟並非在 [Lync Server 2013 中規劃 Enterprise Voice](lync-server-2013-planning-for-enterprise-voice.md)時所述的規劃程式中的部分。</span><span class="sxs-lookup"><span data-stu-id="35467-105">If you are moving users from an existing PBX telephony infrastructure to Enterprise Voice, the deployment process includes some steps that are not part of the planning process already described in [Planning for Enterprise Voice in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md).</span></span> <span data-ttu-id="35467-106">如需從舊版 Enterprise Voice 部署遷移使用者的詳細資訊，請參閱安裝媒體隨附的遷移檔。</span><span class="sxs-lookup"><span data-stu-id="35467-106">For information about migrating users from an earlier Enterprise Voice deployment, see the migration documents that were included with your installation media.</span></span>

<span data-ttu-id="35467-107">將使用者從現有電話語音基礎結構移至 Enterprise Voice 的套裝程式含下列步驟：</span><span class="sxs-lookup"><span data-stu-id="35467-107">The process of moving users from an existing telephony infrastructure to Enterprise Voice consists of the following steps:</span></span>

1.  <span data-ttu-id="35467-108">指定主要電話號碼。</span><span class="sxs-lookup"><span data-stu-id="35467-108">Designate primary phone numbers.</span></span>

2.  <span data-ttu-id="35467-109">啟用使用者的企業語音。</span><span class="sxs-lookup"><span data-stu-id="35467-109">Enable users for Enterprise Voice.</span></span>

3.  <span data-ttu-id="35467-110">為使用者準備撥號對應表。</span><span class="sxs-lookup"><span data-stu-id="35467-110">Prepare dial plans for users.</span></span>

4.  <span data-ttu-id="35467-111">規劃使用者語音原則。</span><span class="sxs-lookup"><span data-stu-id="35467-111">Plan user voice policies.</span></span>

5.  <span data-ttu-id="35467-112">規劃通話路由。</span><span class="sxs-lookup"><span data-stu-id="35467-112">Plan call routes.</span></span>

6.  <span data-ttu-id="35467-113">設定 PBX 或 SIP 主幹以為已啟用 Enterprise Voice 的使用者重新路由通話。</span><span class="sxs-lookup"><span data-stu-id="35467-113">Configure PBX or SIP Trunk to reroute calls for users enabled for Enterprise Voice.</span></span>

7.  <span data-ttu-id="35467-114">將使用者移至 Exchange 整合通訊 (UM)  (建議) 。</span><span class="sxs-lookup"><span data-stu-id="35467-114">Move users to Exchange Unified Messaging (UM) (recommended).</span></span>

<span data-ttu-id="35467-115">本主題說明上述每個步驟所需的規劃。</span><span class="sxs-lookup"><span data-stu-id="35467-115">This topic describes the planning that is necessary for each of these steps.</span></span>

<div>

## <a name="step-1-designate-primary-phone-numbers"></a><span data-ttu-id="35467-116">步驟 1：</span><span class="sxs-lookup"><span data-stu-id="35467-116">Step 1.</span></span> <span data-ttu-id="35467-117">指定主要電話號碼</span><span class="sxs-lookup"><span data-stu-id="35467-117">Designate primary phone numbers</span></span>

<span data-ttu-id="35467-118">Enterprise Voice 會與其他郵件媒體整合語音，如此一來，當來電到達伺服器時，伺服器會將該號碼對應至使用者的 SIP-URI，然後將該呼叫派生至與該 SIP-URI 相關聯的所有用戶端端點。</span><span class="sxs-lookup"><span data-stu-id="35467-118">Enterprise Voice integrates voice with other messaging media, such that when an incoming call arrives at the server, the server maps the number to the user’s SIP-URI and then forks the call to all the client endpoints associated with that SIP-URI.</span></span> <span data-ttu-id="35467-119">此程式需要每一位使用者都與主要電話號碼相關聯。</span><span class="sxs-lookup"><span data-stu-id="35467-119">This process requires that each user be associated with a primary phone number.</span></span>

<span data-ttu-id="35467-120">主要電話號碼必須：</span><span class="sxs-lookup"><span data-stu-id="35467-120">A primary phone number must be:</span></span>

  - <span data-ttu-id="35467-121">全域唯一或內部分機的情況，在企業中是唯一的。</span><span class="sxs-lookup"><span data-stu-id="35467-121">Globally unique or, in the case of internal extensions, unique in the enterprise.</span></span>

  - <span data-ttu-id="35467-122">企業中的擁有和路由傳送。</span><span class="sxs-lookup"><span data-stu-id="35467-122">Owned by and routable in the enterprise.</span></span> <span data-ttu-id="35467-123">不應該使用個人號碼。</span><span class="sxs-lookup"><span data-stu-id="35467-123">Personal numbers should not be used.</span></span>

<span data-ttu-id="35467-124">企業使用者可在 Active Directory 網域服務中列出兩個以上的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="35467-124">Enterprise users can have two or more telephone numbers listed for them in Active Directory Domain Services.</span></span> <span data-ttu-id="35467-125">在 [Active Directory 使用者及電腦] 嵌入式管理單元中，您可以在該使用者的屬性工作表上查看或變更所有與特定使用者相關聯的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="35467-125">All the telephone numbers associated with a particular user can be viewed or changed on the property sheet for that user in the Active Directory Users and Computers snap-in.</span></span>

<span data-ttu-id="35467-126">[**使用者屬性**] 對話方塊的 [**一般**] 索引標籤上的 [**電話號碼**] 方塊應包含使用者的主要工作號碼。</span><span class="sxs-lookup"><span data-stu-id="35467-126">The **Telephone number** box on the **General** tab of the **User Properties** dialog box should contain the user’s main work number.</span></span> <span data-ttu-id="35467-127">此號碼通常會指定為使用者的主要電話號碼。</span><span class="sxs-lookup"><span data-stu-id="35467-127">This number will usually be designated as the user's Primary Phone Number.</span></span>

<span data-ttu-id="35467-128">有些使用者可能會有特殊需求 (例如，想要讓所有來電都透過系統管理助理) 傳送，但例外狀況應只局限于需要明確且嚴重的情況。</span><span class="sxs-lookup"><span data-stu-id="35467-128">Some users may have special requirements (for example, an executive who wants all incoming calls routed through an administrative assistant), but such exceptions should be limited only to those where the need is clear and critical.</span></span>

<span data-ttu-id="35467-129">選取主要號碼後，必須：</span><span class="sxs-lookup"><span data-stu-id="35467-129">After a primary number is chosen, it must be:</span></span>

  - <span data-ttu-id="35467-130">盡可能正常化為 e.164 格式。</span><span class="sxs-lookup"><span data-stu-id="35467-130">Normalized to E.164 format, wherever possible.</span></span>

  - <span data-ttu-id="35467-131">複製到 Active Directory **msRTCSIP-line** 屬性。</span><span class="sxs-lookup"><span data-stu-id="35467-131">Copied to the Active Directory **msRTCSIP-line** attribute.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="35467-132"><STRONG>與遠端呼叫控制共存 (RCC) </STRONG></span><span class="sxs-lookup"><span data-stu-id="35467-132"><STRONG>Coexisting with remote call control (RCC)</STRONG></span></span><BR><span data-ttu-id="35467-133">RCC 是使用 Lync Server 來監控及控制桌面 PBX 電話的功能。</span><span class="sxs-lookup"><span data-stu-id="35467-133">RCC is the ability to use Lync Server to monitor and control a desktop PBX phone.</span></span> <span data-ttu-id="35467-134">控制是透過伺服器進行路由傳送，其充當 PBX 的閘道。</span><span class="sxs-lookup"><span data-stu-id="35467-134">Control is routed through the server, which acts as a gateway to the PBX.</span></span> <span data-ttu-id="35467-135">雖然您無法同時為 RCC 和 Enterprise Voice 設定使用者，但是行 URI 設定會指定使用者的主要電話號碼（以任一種情況為單位）。</span><span class="sxs-lookup"><span data-stu-id="35467-135">Although you cannot configure a user for both RCC and Enterprise Voice, the Line URI setting designates a user’s primary phone number in either case.</span></span><BR><span data-ttu-id="35467-136">如果您有現有的 PBX 基礎結構，讓選取的使用者繼續使用，您可以將企業語音逐步引入您的組織。</span><span class="sxs-lookup"><span data-stu-id="35467-136">If you have an existing PBX infrastructure that you want selected users to continue using, you can introduce Enterprise Voice incrementally into your organization.</span></span> <span data-ttu-id="35467-137">如需此部署案例的詳細資訊，請參閱規劃檔中的 <A href="lync-server-2013-direct-sip-deployment-options.md">Lync Server 2013 中的直銷 SIP 部署選項</A> 。</span><span class="sxs-lookup"><span data-stu-id="35467-137">For details about this deployment scenario, see <A href="lync-server-2013-direct-sip-deployment-options.md">Direct SIP deployment options in Lync Server 2013</A> in the Planning documentation.</span></span><BR><span data-ttu-id="35467-138">在舊版中，您可以為使用者同時啟用 RCC 和 Enterprise Voice，但只有在您也為雙重分叉設定使用者時，撥入電話會同時撥打使用者 PBX 電話和 Communicator 的功能。</span><span class="sxs-lookup"><span data-stu-id="35467-138">In previous releases, you could enable both RCC and Enterprise Voice for a user, but only if you also configured the user for dual forking, a feature in which an incoming call will ring a user’s PBX phone and Communicator simultaneously.</span></span> <span data-ttu-id="35467-139">在 Lync Server 2010 中，不支援雙重分叉。</span><span class="sxs-lookup"><span data-stu-id="35467-139">In Lync Server 2010, dual-forking is not supported.</span></span>

    
    </div>

<span data-ttu-id="35467-140">可用於填入 **msRTCSIP-line** 屬性的方法有三種：</span><span class="sxs-lookup"><span data-stu-id="35467-140">There are three methods for populating the **msRTCSIP-line** attribute:</span></span>

  - <span data-ttu-id="35467-141">建議的 Microsoft Identity Integration Server () </span><span class="sxs-lookup"><span data-stu-id="35467-141">Microsoft Identity Integration Server (recommended)</span></span>

  - <span data-ttu-id="35467-142">Lync Server 控制台中的 [ **使用者** ] 頁面</span><span class="sxs-lookup"><span data-stu-id="35467-142">The **Users** page in the Lync Server Control Panel</span></span>

<span data-ttu-id="35467-143">必須處理的電話號碼數目，組織所開發的腳本是比較好的選擇。</span><span class="sxs-lookup"><span data-stu-id="35467-143">Where many phone numbers must be processed, a script custom developed by your organization is the better choice.</span></span> <span data-ttu-id="35467-144">根據您的組織在 Active Directory 網域服務中表示電話號碼的方式，腳本可能必須先將主要電話號碼正常化為 e.164 格式，再將其複製到 **msRTCSIP-line** 屬性。</span><span class="sxs-lookup"><span data-stu-id="35467-144">Depending on how your organization represents telephone numbers in Active Directory Domain Services, the script may have to normalize primary phone numbers to E.164 format before copying them to the **msRTCSIP-line** attribute.</span></span>

  - <span data-ttu-id="35467-145">如果您的組織在 Active Directory 網域服務中以單一格式維護所有的電話號碼，且該格式為 e.164，則您的腳本只需要將每個主要電話號碼寫入 **msRTCSIP-line** 屬性。</span><span class="sxs-lookup"><span data-stu-id="35467-145">If your organization maintains all telephone numbers in Active Directory Domain Services in a single format, and if that format is E.164, your script only needs to write each Primary Telephone Number to the **msRTCSIP-line** attribute.</span></span>

  - <span data-ttu-id="35467-146">如果您的組織在 Active Directory 網域服務中以單一格式維護所有的電話號碼，但該格式不是 e.164，您的腳本應定義適當的正規化規則，以便將主要電話號碼從現有的格式轉換為 e.164，然後再將主要電話號碼寫入 **msRTCSIP-line** 屬性。</span><span class="sxs-lookup"><span data-stu-id="35467-146">If your organization maintains all telephone numbers in Active Directory Domain Services in a single format, but that format is not E.164, your script should define an appropriate normalization rule to convert Primary Telephone Numbers from their existing format to E.164 before writing them to the **msRTCSIP-line** attribute.</span></span>

  - <span data-ttu-id="35467-147">如果您的組織未在 Active Directory 網域服務中強制使用電話號碼的標準格式，則您的腳本應該定義適當的正規化規則，以便將主要電話號碼從其各種格式轉換為 e.164 相容性，然後再將主要電話號碼寫入 **msRTCSIP-line** 屬性。</span><span class="sxs-lookup"><span data-stu-id="35467-147">If your organization does not enforce a standard format for telephone numbers in Active Directory Domain Services, your script should define appropriate normalization rules to convert Primary Phone Numbers from their various formats to E.164 compliance before writing the Primary Telephone Numbers to the **msRTCSIP-line** attribute.</span></span>

<span data-ttu-id="35467-148">您的腳本也必須先插入首碼 **電話：** 在每個主要號碼之前，再將它寫入 **msRTCSIP-line** 屬性。</span><span class="sxs-lookup"><span data-stu-id="35467-148">Your script will also have to insert the prefix **Tel:** before each primary number before writing it to the **msRTCSIP-line** attribute.</span></span>

<span data-ttu-id="35467-149">此屬性中指定的數位預期格式為：</span><span class="sxs-lookup"><span data-stu-id="35467-149">The expected format of the number specified in this attribute is:</span></span>

  - <span data-ttu-id="35467-150">電話： + 14255550100; ext = 50100。</span><span class="sxs-lookup"><span data-stu-id="35467-150">Tel:+14255550100;ext=50100.</span></span>

  - <span data-ttu-id="35467-151">電話：針對獨特 enterprise wide 擴充的 5550100 () </span><span class="sxs-lookup"><span data-stu-id="35467-151">Tel:5550100 (for unique enterprise wide extensions)</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="35467-152">由 Address Book Service () ABS 所執行的正規化，不會取代或不再需要正常化 Active Directory 網域服務中每個使用者的主要電話號碼，因為 ABS 沒有 Active Directory 網域服務的存取權，因此無法將主要號碼複製到 <STRONG>msRTCSIP-line</STRONG> 屬性。</span><span class="sxs-lookup"><span data-stu-id="35467-152">The normalization performed by the Address Book Service (ABS) does not replace or otherwise eliminate the need to normalize each user's primary phone number in Active Directory Domain Services because ABS does not have access to Active Directory Domain Services and therefore cannot copy primary numbers to the <STRONG>msRTCSIP-line</STRONG> attribute.</span></span>

    
    </div>

</div>

<div>

## <a name="step-2-enable-users-for-enterprise-voice"></a><span data-ttu-id="35467-153">步驟 2：</span><span class="sxs-lookup"><span data-stu-id="35467-153">Step 2.</span></span> <span data-ttu-id="35467-154">為使用者啟用企業語音</span><span class="sxs-lookup"><span data-stu-id="35467-154">Enable users for Enterprise Voice</span></span>

<span data-ttu-id="35467-155">除了識別要啟用的使用者之外，不需要進行特殊規劃，即可完成此步驟。</span><span class="sxs-lookup"><span data-stu-id="35467-155">Other than identifying which users are to be enabled, no special planning is required to complete this step.</span></span>

</div>

<div>

## <a name="step-3-prepare-dial-plans-for-users"></a><span data-ttu-id="35467-156">步驟 3：</span><span class="sxs-lookup"><span data-stu-id="35467-156">Step 3.</span></span> <span data-ttu-id="35467-157">為使用者準備撥號對應表。</span><span class="sxs-lookup"><span data-stu-id="35467-157">Prepare dial plans for users.</span></span>

<span data-ttu-id="35467-158">已啟用 Enterprise Voice 的使用者將無法在未設定撥號對應表的情況下撥打 PSTN 電話。</span><span class="sxs-lookup"><span data-stu-id="35467-158">Users who are enabled for Enterprise Voice will not be able to make calls to the PSTN without dial plans in place.</span></span> <span data-ttu-id="35467-159">撥號對應表是一個具名的正規化規則集，可將具名位置、個別使用者或連絡人物件的電話號碼轉譯成單一標準 (E.164) 格式，以便進行電話授權和電話路由傳送。</span><span class="sxs-lookup"><span data-stu-id="35467-159">A dial plan is a named set of normalization rules that translates phone numbers for a named location, individual user, or contact object into a single standard (E.164) format for purposes of phone authorization and call routing.</span></span> <span data-ttu-id="35467-160">正規化規則會針對每個指定位置、使用者或連絡人物件，定義要如何路由傳送以各種格式表達的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="35467-160">Normalization rules define how phone numbers expressed in various formats are to be routed for each specified location, user, or contact object.</span></span>

<span data-ttu-id="35467-161">如需有關準備撥號對應表的詳細資訊，請參閱 [Lync Server 2013 中的撥號對應表和正常化規則](lync-server-2013-dial-plans-and-normalization-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="35467-161">For information about preparing dial plans, see [Dial plans and normalization rules in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md).</span></span>

</div>

<div>

## <a name="step-4-plan-user-voice-policies"></a><span data-ttu-id="35467-162">步驟 4：</span><span class="sxs-lookup"><span data-stu-id="35467-162">Step 4.</span></span> <span data-ttu-id="35467-163">規劃使用者語音原則</span><span class="sxs-lookup"><span data-stu-id="35467-163">Plan user voice policies</span></span>

<span data-ttu-id="35467-164">在舊版 PBX 上的服務類別設定（例如從公司電話撥打長途電話或國際電話的權利）必須重新設定為 VoIP 原則，以供使用者移至 Enterprise Voice。</span><span class="sxs-lookup"><span data-stu-id="35467-164">User class-of-service settings on a legacy PBX, such as the right to make long-distance or international calls from company phones, must be reconfigured as VoIP policies for users moved to Enterprise Voice.</span></span> <span data-ttu-id="35467-165">如需規劃及建立 Enterprise Voice 之原則的詳細資訊，請參閱 [Lync Server 2013 中的語音原則](lync-server-2013-voice-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="35467-165">For details about planning and creating policies for Enterprise Voice, see [Voice policies in Lync Server 2013](lync-server-2013-voice-policies.md).</span></span>

</div>

<div>

## <a name="step-5-plan-outbound-call-routes"></a><span data-ttu-id="35467-166">步驟 5：</span><span class="sxs-lookup"><span data-stu-id="35467-166">Step 5.</span></span> <span data-ttu-id="35467-167">規劃撥出電話路由</span><span class="sxs-lookup"><span data-stu-id="35467-167">Plan outbound call routes</span></span>

<span data-ttu-id="35467-168">通話路由會指定 Lync Server 如何處理 Enterprise Voice 使用者撥出的電話。</span><span class="sxs-lookup"><span data-stu-id="35467-168">Call routes specify how Lync Server handles outbound calls placed by Enterprise Voice users.</span></span> <span data-ttu-id="35467-169">當使用者撥打號碼時，如果有必要，伺服器會將撥號字串標準化為 e.164 格式，並嘗試將撥號字串與 SIP URI 相符。</span><span class="sxs-lookup"><span data-stu-id="35467-169">When a user dials a number, the server, if necessary, normalizes the dial string to E.164 format and attempts to match it to a SIP URI.</span></span> <span data-ttu-id="35467-170">如果伺服器無法進行相符，它會根據數目來套用傳出的呼叫路由邏輯。</span><span class="sxs-lookup"><span data-stu-id="35467-170">If the server is unable to make the match, it applies outgoing call routing logic based on the number.</span></span> <span data-ttu-id="35467-171">定義該邏輯的最後一個步驟是針對每一組每個撥號對應表中所列的目的地電話號碼，建立個別的命名呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="35467-171">The final step in defining that logic is creating a separate named call route for each set of destination phone numbers that are listed in each dial plan.</span></span>

<span data-ttu-id="35467-172">如需規劃通話路由的詳細資訊，請參閱 [Lync Server 2013 中的語音路由](lync-server-2013-voice-routes.md)。</span><span class="sxs-lookup"><span data-stu-id="35467-172">For details about planning call routes, see [Voice routes in Lync Server 2013](lync-server-2013-voice-routes.md).</span></span>

</div>

<div>

## <a name="step-6-configure-pbx-or-sip-trunk-to-reroute-calls-for-enterprise-voice-users"></a><span data-ttu-id="35467-173">步驟 6：</span><span class="sxs-lookup"><span data-stu-id="35467-173">Step 6.</span></span> <span data-ttu-id="35467-174">設定 PBX 或 SIP 主幹以重新路由傳送 Enterprise Voice 使用者的通話</span><span class="sxs-lookup"><span data-stu-id="35467-174">Configure PBX or SIP Trunk to reroute calls for Enterprise Voice users</span></span>

<span data-ttu-id="35467-175">先前是裝載在傳統 PBX 上的使用者，或是在網際網路電話語音服務提供者的 SIP 主幹連線上， (ITSP) 會在移動之後保留其電話號碼。</span><span class="sxs-lookup"><span data-stu-id="35467-175">Users who formerly were hosted on a traditional PBX or on a SIP Trunk connection to an Internet Telephony Service Provider (ITSP) retain their phone numbers after the move.</span></span> <span data-ttu-id="35467-176">唯一的需求是在移動之後，必須重新設定 PBX 或 SIP 主幹，才能將 Enterprise Voice 使用者的來電路由傳送至轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="35467-176">The only requirement is that after the move, the PBX or SIP Trunk must be reconfigured to route incoming calls for Enterprise Voice users to the Mediation Server.</span></span>

</div>

<div>

## <a name="step-7-move-users-to-exchange-unified-messaging-recommended"></a><span data-ttu-id="35467-177">步驟7。</span><span class="sxs-lookup"><span data-stu-id="35467-177">Step 7.</span></span> <span data-ttu-id="35467-178">將使用者移至 Exchange 整合通訊 (建議) </span><span class="sxs-lookup"><span data-stu-id="35467-178">Move users to Exchange Unified Messaging (recommended)</span></span>

<span data-ttu-id="35467-179">將使用者移至 Exchange 整合通訊包含下列工作：</span><span class="sxs-lookup"><span data-stu-id="35467-179">Moving users to Exchange Unified Messaging consists of the following tasks:</span></span>

  - <span data-ttu-id="35467-180">將 Exchange 整合通訊和 Lync 伺服器設定為一起運作。</span><span class="sxs-lookup"><span data-stu-id="35467-180">Configure Exchange Unified Messaging and Lync Server to work together.</span></span>

  - <span data-ttu-id="35467-181">為使用者啟用 Exchange 整合通訊呼叫應答和 Outlook Voice Access。</span><span class="sxs-lookup"><span data-stu-id="35467-181">Enable users for Exchange Unified Messaging call answering and Outlook Voice Access.</span></span> <span data-ttu-id="35467-182">這種工作是在 Exchange 整合通訊伺服器上執行。</span><span class="sxs-lookup"><span data-stu-id="35467-182">This task is performed on the Exchange Unified Messaging server.</span></span> <span data-ttu-id="35467-183">如需詳細資訊，請參閱 Exchange Server 2010 TechNet 程式庫，網址為 [https://go.microsoft.com/fwlink/p/?linkID=139372](https://go.microsoft.com/fwlink/p/?linkid=139372) 。</span><span class="sxs-lookup"><span data-stu-id="35467-183">For details, see the Exchange Server 2010 TechNet Library at [https://go.microsoft.com/fwlink/p/?linkID=139372](https://go.microsoft.com/fwlink/p/?linkid=139372).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

