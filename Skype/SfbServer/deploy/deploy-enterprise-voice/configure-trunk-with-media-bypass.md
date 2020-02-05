---
title: 在商務用 Skype Server 中使用 [旁路媒體] 設定主幹
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 99d729ea-5a4c-4ff2-a4a3-93a24368da6d
description: 摘要：針對商務用 Skype Server 啟用 [媒體旁路] 設定主幹。 這可讓您最小化中繼伺服器的數目，presuming 您的 SIP 幹線供應商支援它。
ms.openlocfilehash: 4f834a908f002e334fbad70a8c1c8c0617ca2189
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768096"
---
# <a name="configure-a-trunk-with-media-bypass-in-skype-for-business-server"></a><span data-ttu-id="e7ce4-104">在商務用 Skype Server 中使用 [旁路媒體] 設定主幹</span><span class="sxs-lookup"><span data-stu-id="e7ce4-104">Configure a trunk with media bypass in Skype for Business Server</span></span>

<span data-ttu-id="e7ce4-105">**摘要：** 針對商務用 Skype Server 啟用 [媒體旁路] 設定主幹。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-105">**Summary:** Configure a trunk with media bypass enabled for Skype for Business Server.</span></span> <span data-ttu-id="e7ce4-106">這可讓您最小化中繼伺服器的數目，presuming 您的 SIP 幹線供應商支援它。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-106">This will let you minimize the number of Mediation Servers, presuming your SIP trunk provider supports it.</span></span>

<span data-ttu-id="e7ce4-107">請依照下列步驟來設定已啟用媒體旁路的幹線。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-107">Follow these steps to configure a trunk with media bypass enabled.</span></span> <span data-ttu-id="e7ce4-108">若要設定停用媒體旁路的幹線，請參閱[在商務用 Skype Server 中設定幹線而不使用媒體旁路](configure-trunk-without-media-bypass.md)。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-108">To configure a trunk with media bypass disabled, see [Configure a trunk without media bypass in Skype for Business Server](configure-trunk-without-media-bypass.md).</span></span>

<span data-ttu-id="e7ce4-109">如果您想要將部署的中繼伺服器數量減至最少，則可以使用 [媒體旁路]。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-109">Media bypass is useful when you want to minimize the number of Mediation Servers deployed.</span></span> <span data-ttu-id="e7ce4-110">如需詳細資訊，請參閱[在商務用 Skype 中規劃媒體旁路](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)</span><span class="sxs-lookup"><span data-stu-id="e7ce4-110">For more information, see [Plan for media bypass in Skype for Business](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)</span></span>

<span data-ttu-id="e7ce4-111">我們強烈建議您啟用 [媒體旁路]。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-111">We strongly recommend that you enable media bypass.</span></span> <span data-ttu-id="e7ce4-112">不過，在 SIP 主幹上啟用媒體旁路之前，請確認您的合格 SIP 幹線提供者支援媒體旁路，且能夠滿足成功啟用該案例的需求。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-112">However, before you enable media bypass on a SIP trunk, confirm that your qualified SIP trunk provider supports media bypass and is able to accommodate the requirements for successfully enabling the scenario.</span></span> <span data-ttu-id="e7ce4-113">具體說來，提供者必須擁有貴組織內部網路中伺服器的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-113">Specifically, the provider must have the IP addresses of servers in your organization's internal network.</span></span>

> [!NOTE]
> <span data-ttu-id="e7ce4-114">媒體旁路將無法與每個公開交換電話網絡（PSTN）閘道、IP PBX 和會話邊界控制器（SBC）進行交互操作。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-114">Media bypass will not interoperate with every Public Switched Telephone Network (PSTN) gateway, IP-PBX, and Session Border Controller (SBC).</span></span> <span data-ttu-id="e7ce4-115">Microsoft 已使用認證的合作夥伴測試了一組 PSTN 閘道和 SBCs。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-115">Microsoft has tested a set of PSTN gateways and SBCs with certified partners.</span></span> <span data-ttu-id="e7ce4-116">只有在[商務用 Skype Server 頁面的電話結構](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways)上所列的產品和版本，才能支援媒體略過。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-116">Media bypass is supported only with products and versions that are listed on the [Telephony Infrastructure for Skype for Business Server](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways) page.</span></span>

<span data-ttu-id="e7ce4-117">下面所述的主幹設定會將套用至 trunks 指派這個幹線設定的一組參數組成。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-117">A trunk configuration as described below groups a set of parameters that are applied to trunks assigned this trunk configuration.</span></span> <span data-ttu-id="e7ce4-118">您可以將特定的主幹設定設為全域（所有 trunks，而不會有更具體的網站或池配置），或是到網站或池中。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-118">A particular trunk configuration can be scoped globally (to all trunks that do not have more specific site or pool configuration), or to a site, or to a pool.</span></span> <span data-ttu-id="e7ce4-119">[池層級中繼] 設定是用來將特定主幹設定的範圍限定在單一干線中。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-119">The pool-level trunk configuration is used to scope a specific trunk configuration to a single trunk.</span></span>

### <a name="to-configure-a-trunk-with-media-bypass"></a><span data-ttu-id="e7ce4-120">使用 [旁路媒體] 設定主幹</span><span class="sxs-lookup"><span data-stu-id="e7ce4-120">To configure a trunk with media bypass</span></span>

1. <span data-ttu-id="e7ce4-121">開啟商務用 Skype Server 的 [控制台]</span><span class="sxs-lookup"><span data-stu-id="e7ce4-121">Open Skype for Business Server Control Panel</span></span>

2. <span data-ttu-id="e7ce4-122">在左側導覽列中，按一下 [**語音路由**]，然後按一下 [**幹線**設定]。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-122">In the left navigation bar, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

3. <span data-ttu-id="e7ce4-123">在 [**幹線**設定] 頁面上，使用下列其中一種方法來設定幹線：</span><span class="sxs-lookup"><span data-stu-id="e7ce4-123">On the **Trunk Configuration** page, use one of the following methods to configure a trunk:</span></span>

   - <span data-ttu-id="e7ce4-124">按兩下現有的幹線（例如，**全域**幹線），以顯示 [**編輯主幹**設定] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-124">Double-click an existing trunk (for example, the **Global** trunk) to display the **Edit Trunk Configuration** dialog box.</span></span>

   - <span data-ttu-id="e7ce4-125">按一下 [**新增**]，然後選取新主幹設定的範圍：</span><span class="sxs-lookup"><span data-stu-id="e7ce4-125">Click **New**, and then select a scope for the new trunk configuration:</span></span>

   - <span data-ttu-id="e7ce4-126">**網站主幹**：從 [**選取網站**] 選擇此主幹設定的網站，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-126">**Site trunk**: Choose the site for this trunk configuration from **Select a Site**, and then click **OK**.</span></span> <span data-ttu-id="e7ce4-127">請注意，如果已為網站建立中繼設定，網站就不會出現在 [**選取網站**] 中。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-127">Note that if a trunk configuration has already been created for a site, the site does not appear in **Select a Site**.</span></span> <span data-ttu-id="e7ce4-128">此主幹設定將會套用至網站中的所有 trunks。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-128">This trunk configuration will be applied to all trunks in the site.</span></span>

   - <span data-ttu-id="e7ce4-129">[**池主幹**]：選擇此幹線設定適用的主幹名稱。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-129">**Pool trunk**: Choose the name of the trunk that this trunk configuration applies to.</span></span> <span data-ttu-id="e7ce4-130">這個幹線可以是根主幹或在拓撲建立器中定義的任何其他 trunks。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-130">This trunk can be the root trunk or any additional trunks defined in Topology Builder.</span></span> <span data-ttu-id="e7ce4-131">從 [**選取服務**] 中，按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-131">From **Select a Service**, click **OK**.</span></span> <span data-ttu-id="e7ce4-132">請注意，如果已為特定主幹建立幹線設定，主幹不會出現在 [**選取服務**] 中。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-132">Note that if a trunk configuration has already been created for a specific trunk, the trunk does not appear in **Select a Service**.</span></span>

      > [!NOTE]
      > <span data-ttu-id="e7ce4-133">在您選取主幹設定的範圍之後，就無法變更它。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-133">After you select the scope of the trunk configuration, it cannot be changed.</span></span> <span data-ttu-id="e7ce4-134">> [ **Name** ] （名稱）欄位已預先填入與幹線設定關聯的網站或服務名稱，且無法變更。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-134">> The **Name** field is prepopulated with the name of the trunk configuration's associated site or service and cannot be changed.</span></span>

4. <span data-ttu-id="e7ce4-135">在**支援的最大早期對話方塊**中指定值。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-135">Specify a value in **Maximum early dialogs supported**.</span></span> <span data-ttu-id="e7ce4-136">這是公用交換電話網絡（PSTN）閘道、IP PBX 或 ITSP 會話邊界控制器（SBC）可接收傳送給轉送伺服器的邀請的數目上限。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-136">This is the maximum number of forked responses a public switched telephone network (PSTN) gateway, IP-PBX, or ITSP Session Border Controller (SBC) can receive to an INVITE that it sent to the Mediation Server.</span></span> <span data-ttu-id="e7ce4-137">預設值為20。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-137">The default value is 20.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e7ce4-138">變更此值前，請諮詢您的服務提供者或設備製造商，以取得系統功能的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-138">Before you change this value, consult your service provider or equipment manufacturer for details about the capabilities of your system.</span></span>

5. <span data-ttu-id="e7ce4-139">選取下列其中一個**加密支援等級**選項：</span><span class="sxs-lookup"><span data-stu-id="e7ce4-139">Select one of the following **Encryption support level** options:</span></span>

   - <span data-ttu-id="e7ce4-140">**必要**：您必須使用安全的即時傳輸通訊協定（SRTP）加密，以協助保護中繼伺服器與閘道或私人分支 EXCHANGE （PBX）之間的流量。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-140">**Required**: Secure real-time transport protocol (SRTP) encryption must be used to help protect traffic between the Mediation Server and the gateway or private branch exchange (PBX).</span></span>

   - <span data-ttu-id="e7ce4-141">**選用**：如果服務提供者或設備製造商支援，則會使用 SRTP 加密。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-141">**Optional**: SRTP encryption will be used if the service provider or equipment manufacturer supports it.</span></span>

   - <span data-ttu-id="e7ce4-142">**不支援**：服務提供者或設備製造商不支援 SRTP 加密，因此將無法使用。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-142">**Not Supported**: SRTP encryption is not supported by the service provider or equipment manufacturer and therefore will not be used.</span></span>

6. <span data-ttu-id="e7ce4-143">如果您想要媒體略過中繼伺服器以進行中繼對等處理，請選取 [**啟用媒體旁路**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-143">Select the **Enable media bypass** check box if you want media to bypass the Mediation Server for processing by the trunk peer.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="e7ce4-144">若要讓媒體旁路功能順利運作，PSTN 閘道、IP PBX 或 ITSP 會話框線控制器必須支援某些功能。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-144">For media bypass to work successfully, the PSTN gateway, IP-PBX, or ITSP Session Border Controller must support certain capabilities.</span></span> <span data-ttu-id="e7ce4-145">如需詳細資訊，請參閱[在商務用 Skype 中規劃媒體旁路](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-145">For details, see [Plan for media bypass in Skype for Business](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span></span>

7. <span data-ttu-id="e7ce4-146">如果有已知的媒體端接點，請選取 [**集中式媒體處理**] 核取方塊（例如，媒體端接的 PSTN 閘道與 [信號終止] 一樣）。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-146">Select the **Centralized media processing** check box if there is a well-known media termination point (for example, a PSTN gateway where the media termination has the same IP as the signaling termination).</span></span> <span data-ttu-id="e7ce4-147">如果主幹沒有已知的媒體端接點，請清除此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-147">Clear this check box if the trunk does not have a well-known media termination point.</span></span>

8. <span data-ttu-id="e7ce4-148">如果乾線對等支援接收來自中繼伺服器的 SIP，請選取 [**啟用傳送參照至閘道**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-148">If the trunk peer supports receiving SIP REFER requests from the Mediation Server, select the **Enable sending refer to the gateway** check box.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e7ce4-149">如果您在已選取 [**啟用媒體旁路**] 選項時停用此選項，則需要其他設定。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-149">If you disable this option while the **Enable media bypass** option is selected, additional settings are required.</span></span> <span data-ttu-id="e7ce4-150">如果乾線對等不支援接收來自中繼伺服器和媒體旁路的 SIP 參照要求，您也必須執行**new-cstrunkconfiguration** Cmdlet 來停用使用中及保留通話的 RTCP，以支援媒體旁路的正確情況。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-150">If the trunk peer does not support receiving SIP REFER requests from the Mediation Server and media bypass is enabled, you must also run the **Set-CsTrunkConfiguration** cmdlet to disable RTCP for active and held calls in order to support proper conditions for media bypass.</span></span> <span data-ttu-id="e7ce4-151">或者，如果您想要將轉接來電轉接給媒體，且閘道不支援 SIP，請選取 [**使用協力廠商通話的參照**]。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-151">Alternatively, you can select **Enable refer using third-party-call control** if you want transferred calls to be media bypassed, and the gateway does not support SIP REFER requests.</span></span>

9. <span data-ttu-id="e7ce4-152">可選若要啟用站間路由，請將 PSTN 使用記錄關聯並設定為此主幹設定。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-152">(Optional) To enable inter-trunk routing, associate and configure PSTN usage records to this trunk configuration.</span></span> <span data-ttu-id="e7ce4-153">與此幹線設定關聯的 PSTN 用法，將會針對並非源自商務用 Skype 伺服器端點的主幹進行所有來電。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-153">The PSTN usages associated to this trunk configuration will be applied for all incoming calls through the trunk that is not originating from a Skype for Business Server endpoint.</span></span> <span data-ttu-id="e7ce4-154">若要管理與幹線設定相關聯的 PSTN 使用記錄，請使用下列其中一種方法：</span><span class="sxs-lookup"><span data-stu-id="e7ce4-154">To manage PSTN usage records associated to a trunk configuration, use one of the following methods:</span></span>

   - <span data-ttu-id="e7ce4-155">若要從企業語音部署中所有可用的 PSTN 使用記錄清單中選取一或多筆記錄，請按一下 [**選取**]。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-155">To select one or more records from a list of all PSTN usage records available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="e7ce4-156">醒目提示您要與此主幹設定關聯的記錄，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-156">Highlight the records you want to associate with this trunk configuration and then click **OK**.</span></span>

   - <span data-ttu-id="e7ce4-157">若要從此幹線設定中移除 PSTN 使用記錄，請選取該記錄，然後按一下 [**移除**]。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-157">To remove a PSTN usage record from this trunk configuration, select the record and click **Remove**.</span></span>

   - <span data-ttu-id="e7ce4-158">若要定義新的 PSTN 使用記錄，並將它與此幹線設定關聯，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="e7ce4-158">To define a new PSTN usage record and associate it with this trunk configuration, do the following:</span></span>

     <span data-ttu-id="e7ce4-159">是.</span><span class="sxs-lookup"><span data-stu-id="e7ce4-159">a.</span></span> <span data-ttu-id="e7ce4-160">按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-160">Click **New**.</span></span>

     <span data-ttu-id="e7ce4-161">乙.</span><span class="sxs-lookup"><span data-stu-id="e7ce4-161">b.</span></span> <span data-ttu-id="e7ce4-162">在 [**名稱**] 欄位中，為記錄指定唯一的描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-162">In the **Name** field, specify a descriptive name for the record that is unique.</span></span>

     > [!NOTE]
     > <span data-ttu-id="e7ce4-163">PSTN 使用記錄名稱在企業語音部署中必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-163">The PSTN usage record name must be unique within the Enterprise Voice deployment.</span></span> <span data-ttu-id="e7ce4-164">在儲存記錄之後，[**名稱**] 欄位就無法進行編輯。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-164">After the record is saved, the **Name** field cannot be edited.</span></span>

     <span data-ttu-id="e7ce4-165">c-clip.</span><span class="sxs-lookup"><span data-stu-id="e7ce4-165">c.</span></span> <span data-ttu-id="e7ce4-166">使用下列其中一種方法來關聯及設定此 PSTN 使用記錄的路線：</span><span class="sxs-lookup"><span data-stu-id="e7ce4-166">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>

     - <span data-ttu-id="e7ce4-167">若要從企業語音部署中所有可用路由的清單中選取一或多個路由，請按一下 [**選取**]。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-167">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="e7ce4-168">醒目提示您想要與此 PSTN 使用記錄產生關聯的路線，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-168">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span>

     - <span data-ttu-id="e7ce4-169">若要從 PSTN 使用量記錄移除路由，請選取路由，然後按一下 [**移除**]。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-169">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>

   - <span data-ttu-id="e7ce4-170">若要定義新的路由，並將它與此 PSTN 使用記錄建立關聯，請按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-170">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="e7ce4-171">如需詳細資訊，請參閱[在商務用 Skype 中建立或修改語音路線](create-or-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-171">For details, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span>

     - <span data-ttu-id="e7ce4-172">若要編輯與此 PSTN 使用記錄相關聯的路線，請選取該路線，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-172">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span>

     <span data-ttu-id="e7ce4-173">希望.</span><span class="sxs-lookup"><span data-stu-id="e7ce4-173">d.</span></span> <span data-ttu-id="e7ce4-174">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-174">Click **OK**.</span></span>

     - <span data-ttu-id="e7ce4-175">若要編輯已與此幹線設定關聯的 PSTN 使用記錄，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="e7ce4-175">To edit a PSTN usage record that is already associated with this trunk configuration, do the following:</span></span>

       <span data-ttu-id="e7ce4-176">是.</span><span class="sxs-lookup"><span data-stu-id="e7ce4-176">a.</span></span> <span data-ttu-id="e7ce4-177">選取您要編輯的 PSTN 使用量記錄，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-177">Select the PSTN usage record you want to edit, and click **Show details**.</span></span>

       <span data-ttu-id="e7ce4-178">乙.</span><span class="sxs-lookup"><span data-stu-id="e7ce4-178">b.</span></span> <span data-ttu-id="e7ce4-179">使用下列其中一種方法來關聯及設定此 PSTN 使用記錄的路線：</span><span class="sxs-lookup"><span data-stu-id="e7ce4-179">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>

   - <span data-ttu-id="e7ce4-180">若要從企業語音部署中所有可用路由的清單中選取一或多個路由，請按一下 [**選取**]。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-180">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="e7ce4-181">醒目提示您想要與此 PSTN 使用記錄產生關聯的路線，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-181">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span>

   - <span data-ttu-id="e7ce4-182">若要從 PSTN 使用量記錄移除路由，請選取路由，然後按一下 [**移除**]。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-182">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>

   - <span data-ttu-id="e7ce4-183">若要定義新的路由，並將它與此 PSTN 使用記錄建立關聯，請按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-183">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="e7ce4-184">如需詳細資訊，請參閱[在商務用 Skype 中建立或修改語音路線](create-or-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-184">For details, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span>

   - <span data-ttu-id="e7ce4-185">若要編輯與此 PSTN 使用記錄相關聯的路線，請選取該路線，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-185">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span>

     <span data-ttu-id="e7ce4-186">c-clip.</span><span class="sxs-lookup"><span data-stu-id="e7ce4-186">c.</span></span> <span data-ttu-id="e7ce4-187">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-187">Click **OK**.</span></span>

     > [!IMPORTANT]
     > <span data-ttu-id="e7ce4-188">請務必將 PSTN 使用記錄與所設定的幹線相關聯的中繼伺服器對進行關聯。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-188">It is important to associate PSTN usage records according to the Mediation Server peer that is associated to the trunk being configured.</span></span> <span data-ttu-id="e7ce4-189">如果中繼伺服器對等是 PSTN 閘道或會話邊界控制器（SBC），強烈建議您不要將幹線設定與路由至 PSTN 目的地或透過 Skype 連接的任何其他下游系統的 PSTN 使用記錄相關聯商務用伺服器。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-189">If the Mediation Server peer is a PSTN gateway or a Session Border Controller (SBC), it is strongly recommended that the trunk configuration is not associated to a PSTN usage record that routes to a PSTN destination or any other downstream systems connected via Skype for Business Server.</span></span>

10. <span data-ttu-id="e7ce4-190">排列 PSTN 使用狀況記錄，以獲得最佳效能。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-190">Arrange the PSTN usage records for optimum performance.</span></span> <span data-ttu-id="e7ce4-191">若要變更記錄在清單中的位置，請選取 PSTN 使用記錄，然後按一下向上或向下箭號。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-191">To change a record's position in the list, select the PSTN usage record, and click the up or down arrows.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="e7ce4-192">PSTN 使用記錄在幹線設定中的顯示順序非常重要。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-192">The order in which PSTN usage records are listed in the trunk configuration is significant.</span></span> <span data-ttu-id="e7ce4-193">商務用 Skype 伺服器會從上到下遍歷清單。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-193">Skype for Business Server traverses the list from top to down.</span></span>

11. <span data-ttu-id="e7ce4-194">應選取 [**啟用 RTP 閉鎖**]，以針對網路位址轉譯（NAT）或防火牆以及支援閂鎖的 SBC 啟用旁路媒體。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-194">**Enable RTP Latching** should be selected to enable bypass media for clients behind a network address translation (NAT) or firewall and an SBC that supports latching.</span></span>

12. <span data-ttu-id="e7ce4-195">應選取 [**啟用轉寄通話記錄**]，以允許將通話記錄資訊傳送到中繼伺服器的閘道對等。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-195">**Enable forward call history** should be selected to enable sending of call history information to the gateway peer of the Mediation Server.</span></span>

13. <span data-ttu-id="e7ce4-196">[**啟用前 p-已斷言身分識別的資料**] 請選取 [啟用 p 斷言身分識別（PAI）] 呼叫始發者資訊，以便在中繼伺服器端和閘道端（反之亦然）之間轉寄。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-196">**Enable forward P-Asserted-Identity data** should be selected to enable the P-Asserted-Identity (PAI) call originator information to be forwarded between the Mediation Server side and gateway side (and vice versa), when present.</span></span>

14. <span data-ttu-id="e7ce4-197">若要啟用快速容錯移轉，請選取 [**啟用輸出路由容錯移轉計時器**]。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-197">**Enable outbound routing failover timer** should be selected to enable fast failover.</span></span> <span data-ttu-id="e7ce4-198">與此幹線關聯的閘道可以在處理撥出通話的10秒內發出通知。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-198">The gateway associated with this trunk can give notification within 10 seconds that it is processing an outbound call.</span></span> <span data-ttu-id="e7ce4-199">如果中繼伺服器未收到此通知，就會將重新路由至另一個主幹。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-199">Rerouting to another trunk will occur if this notification is not received by the Mediation Server.</span></span> <span data-ttu-id="e7ce4-200">在延遲可能會延遲回應時間的網路上，或閘道需要10秒以上的時間才能回應，就應該停用 [快速容錯移轉]。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-200">On networks where latency may delay the response time or the gateway takes longer than 10 seconds to respond, the fast failover should be disabled.</span></span>

15. <span data-ttu-id="e7ce4-201">可選關聯並設定主幹的**通話數轉譯規則**。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-201">(Optional) Associate and configure **calling number translation rules** for the trunk.</span></span> <span data-ttu-id="e7ce4-202">這些翻譯規則會套用至撥出通話的電話號碼</span><span class="sxs-lookup"><span data-stu-id="e7ce4-202">These translation rules apply to the calling number for outbound calls</span></span>

    - <span data-ttu-id="e7ce4-203">若要從企業語音部署中提供的所有翻譯規則清單中選擇一或多個規則，請按一下 [**選取**]。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-203">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="e7ce4-204">在 [**選取翻譯規則**] 中，按一下您要與主幹建立關聯的規則，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-204">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>

    - <span data-ttu-id="e7ce4-205">若要定義新的翻譯規則，並將其與骨幹建立關聯，請按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-205">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="e7ce4-206">如需翻譯規則的詳細資訊，請參閱[商務用 Skype Server 中的翻譯規則](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-206">For details about translation rules, see [Translation rules in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md).</span></span>

    - <span data-ttu-id="e7ce4-207">若要編輯已經與主幹建立關聯的翻譯規則，請按一下規則名稱，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-207">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span>

    - <span data-ttu-id="e7ce4-208">若要複製現有的翻譯規則，以做為定義新規則的起點，請按一下規則名稱，然後按一下 [**複製**]，然後按一下 [**貼**上]。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-208">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span>

    - <span data-ttu-id="e7ce4-209">若要從主幹中移除翻譯規則，請將規則名稱醒目提示，然後按一下 [**移除**]。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-209">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>

    > [!CAUTION]
    > <span data-ttu-id="e7ce4-210">如果您已在關聯的中繼對等上設定翻譯規則，請不要將翻譯規則與幹線建立關聯，因為這兩個規則可能會衝突。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-210">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>

16. <span data-ttu-id="e7ce4-211">可選關聯並設定主幹的已**呼叫數位轉譯規則**。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-211">(Optional) Associate and configure **called number translation rules** for the trunk.</span></span> <span data-ttu-id="e7ce4-212">翻譯規則會套用至撥出通話中呼叫的號碼。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-212">The translation rules apply to the called number in an outbound call.</span></span>

    - <span data-ttu-id="e7ce4-213">若要從企業語音部署中提供的所有翻譯規則清單中選擇一或多個規則，請按一下 [**選取**]。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-213">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="e7ce4-214">在 [**選取翻譯規則**] 中，按一下您要與主幹建立關聯的規則，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-214">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>

    - <span data-ttu-id="e7ce4-215">若要定義新的翻譯規則，並將其與骨幹建立關聯，請按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-215">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="e7ce4-216">如需翻譯規則的詳細資訊，請參閱[商務用 Skype Server 中的翻譯規則](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-216">For details about translation rules, see [Translation rules in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md).</span></span>

    - <span data-ttu-id="e7ce4-217">若要編輯已經與主幹建立關聯的翻譯規則，請按一下規則名稱，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-217">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span>

    - <span data-ttu-id="e7ce4-218">若要複製現有的翻譯規則，以做為定義新規則的起點，請按一下規則名稱，然後按一下 [**複製**]，然後按一下 [**貼**上]。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-218">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span>

    - <span data-ttu-id="e7ce4-219">若要從主幹中移除翻譯規則，請將規則名稱醒目提示，然後按一下 [**移除**]。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-219">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>

    > [!CAUTION]
    > <span data-ttu-id="e7ce4-220">如果您已在關聯的中繼對等上設定翻譯規則，請不要將翻譯規則與幹線建立關聯，因為這兩個規則可能會衝突。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-220">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>

17. <span data-ttu-id="e7ce4-221">確定主幹的轉譯規則依正確順序排列。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-221">Make sure that the trunk's translation rules are arranged in the correct order.</span></span> <span data-ttu-id="e7ce4-222">若要變更規則在清單中的位置，請醒目提示 [規則名稱]，然後按一下向上或向下箭號。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-222">To change a rule's position in the list, highlight the rule name and then click the up or down arrow.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="e7ce4-223">商務用 Skype 伺服器會從上到下遍歷翻譯規則清單，並使用與撥打的號碼相符的第一個規則。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-223">Skype for Business Server traverses the translation rule list from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="e7ce4-224">如果您設定幹線，讓撥入的號碼可以符合多個翻譯規則，請確定更嚴格的規則，在限制性較低的規則之上排序。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-224">If you configure a trunk so that a dialed number can match more than one translation rule, be sure that the more restrictive rules are sorted above the less restrictive rules.</span></span> <span data-ttu-id="e7ce4-225">例如，如果您已包含符合任何11位數的翻譯規則，以及只符合以 + 1425 開頭的11位數的翻譯規則，請確定符合任何11位數的規則，以更嚴格的*規則排序。*</span><span class="sxs-lookup"><span data-stu-id="e7ce4-225">For example, if you have included a translation rule that matches any 11-digit number and a translation rule that matches only 11-digit numbers that start with +1425, be sure that the rule that matches any 11-digit number is sorted  *below*  the more restrictive rule.</span></span>

18. <span data-ttu-id="e7ce4-226">當您完成設定主幹時，請按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-226">When you are finished configuring the trunk, click **OK**.</span></span>

19. <span data-ttu-id="e7ce4-227">在 [**幹線**設定] 頁面上，按一下 [**認可**]，然後按一下 [**全部確認**]。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-227">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e7ce4-228">每當您建立或修改幹線設定時，您都必須執行 [**全部提交**] 命令才能發佈設定變更。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-228">Whenever you create or modify a trunk configuration, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="e7ce4-229">如需詳細資訊，請參閱在作業檔中[發佈商務用 Skype 中的語音路由設定的待處理變更](voice-route-config-changes.md)。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-229">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

<span data-ttu-id="e7ce4-230">在您設定主幹之後，請選擇 [全域媒體旁路] 選項，繼續設定媒體旁路，如在部署檔中的[商務用 Skype 伺服器中的 [部署媒體旁路](deploy-media-bypass.md)] 中所述。</span><span class="sxs-lookup"><span data-stu-id="e7ce4-230">After you have configured the trunk, continue configuring media bypass by choosing between global media bypass options, as described in [Deploy media bypass in Skype for Business Server](deploy-media-bypass.md) in the Deployment documentation.</span></span>
## <a name="see-also"></a><span data-ttu-id="e7ce4-231">另請參閱</span><span class="sxs-lookup"><span data-stu-id="e7ce4-231">See also</span></span>

[<span data-ttu-id="e7ce4-232">在商務用 Skype Server 中設定不使用媒體的主幹</span><span class="sxs-lookup"><span data-stu-id="e7ce4-232">Configure a trunk without media bypass in Skype for Business Server</span></span>](configure-trunk-without-media-bypass.md)

[<span data-ttu-id="e7ce4-233">在商務用 Skype Server 中部署媒體旁路</span><span class="sxs-lookup"><span data-stu-id="e7ce4-233">Deploy media bypass in Skype for Business Server</span></span>](deploy-media-bypass.md)

[<span data-ttu-id="e7ce4-234">定義翻譯規則</span><span class="sxs-lookup"><span data-stu-id="e7ce4-234">Defining Translation Rules</span></span>](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx)

[<span data-ttu-id="e7ce4-235">設定媒體旁路</span><span class="sxs-lookup"><span data-stu-id="e7ce4-235">Configure Media Bypass</span></span>](https://technet.microsoft.com/library/f50a7a13-c6a0-48f1-bee1-e45fa2b2f9b8.aspx)

