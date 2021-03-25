---
title: 在商務用 Skype Server 中設定含媒體旁路的主幹
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 摘要：使用啟用商務用 Skype 伺服器的媒體旁路來設定主幹。 這可讓您將轉送伺服器的數目降至最低，presuming 您的 SIP 主幹提供者支援該伺服器。
ms.openlocfilehash: 12f9abc49830e0af9c1934f4da56fe29be861114
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51106389"
---
# <a name="configure-a-trunk-with-media-bypass-in-skype-for-business-server"></a><span data-ttu-id="238b2-104">在商務用 Skype Server 中設定含媒體旁路的主幹</span><span class="sxs-lookup"><span data-stu-id="238b2-104">Configure a trunk with media bypass in Skype for Business Server</span></span>

<span data-ttu-id="238b2-105">**摘要：** 使用啟用商務用 Skype Server 的媒體旁路來設定主幹。</span><span class="sxs-lookup"><span data-stu-id="238b2-105">**Summary:** Configure a trunk with media bypass enabled for Skype for Business Server.</span></span> <span data-ttu-id="238b2-106">這可讓您將轉送伺服器的數目降至最低，presuming 您的 SIP 主幹提供者支援該伺服器。</span><span class="sxs-lookup"><span data-stu-id="238b2-106">This will let you minimize the number of Mediation Servers, presuming your SIP trunk provider supports it.</span></span>

<span data-ttu-id="238b2-107">請遵循下列步驟，設定啟用媒體旁路的主幹。</span><span class="sxs-lookup"><span data-stu-id="238b2-107">Follow these steps to configure a trunk with media bypass enabled.</span></span> <span data-ttu-id="238b2-108">若要設定停用媒體旁路的主幹，請參閱 [在商務用 Skype Server 中設定無媒體旁路的主幹](configure-trunk-without-media-bypass.md)。</span><span class="sxs-lookup"><span data-stu-id="238b2-108">To configure a trunk with media bypass disabled, see [Configure a trunk without media bypass in Skype for Business Server](configure-trunk-without-media-bypass.md).</span></span>

<span data-ttu-id="238b2-109">當您想要將已部署的轉送伺服器數目降至最低時，媒體旁路很有用。</span><span class="sxs-lookup"><span data-stu-id="238b2-109">Media bypass is useful when you want to minimize the number of Mediation Servers deployed.</span></span> <span data-ttu-id="238b2-110">如需詳細資訊，請參閱 [在商務用 Skype 中規劃媒體旁路](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)</span><span class="sxs-lookup"><span data-stu-id="238b2-110">For more information, see [Plan for media bypass in Skype for Business](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)</span></span>

<span data-ttu-id="238b2-111">強烈建議您啟用媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="238b2-111">We strongly recommend that you enable media bypass.</span></span> <span data-ttu-id="238b2-112">不過，在 SIP 主幹上啟用媒體旁路之前，請先確認您合格的 SIP 主幹提供者支援媒體旁路，而且能夠滿足成功啟用此案例的需求。</span><span class="sxs-lookup"><span data-stu-id="238b2-112">However, before you enable media bypass on a SIP trunk, confirm that your qualified SIP trunk provider supports media bypass and is able to accommodate the requirements for successfully enabling the scenario.</span></span> <span data-ttu-id="238b2-113">具體而言，提供者必須具有組織內部網路中伺服器的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="238b2-113">Specifically, the provider must have the IP addresses of servers in your organization's internal network.</span></span>

> [!NOTE]
> <span data-ttu-id="238b2-114">媒體旁路不會與每一部公用交換電話網路 (PSTN) 閘道、IP-PBX 和會話邊界控制器 (SBC) 互動。</span><span class="sxs-lookup"><span data-stu-id="238b2-114">Media bypass will not interoperate with every Public Switched Telephone Network (PSTN) gateway, IP-PBX, and Session Border Controller (SBC).</span></span> <span data-ttu-id="238b2-115">Microsoft 已測試過一組 PSTN 閘道和認證合作夥伴的 SBCs。</span><span class="sxs-lookup"><span data-stu-id="238b2-115">Microsoft has tested a set of PSTN gateways and SBCs with certified partners.</span></span> <span data-ttu-id="238b2-116">只有產品和 [商務用 Skype Server 頁面的電話語音基礎結構](../../../SfbPartnerCertification/certification/infra-gateways.md) 中所列的版本，才支援媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="238b2-116">Media bypass is supported only with products and versions that are listed on the [Telephony Infrastructure for Skype for Business Server](../../../SfbPartnerCertification/certification/infra-gateways.md) page.</span></span>

<span data-ttu-id="238b2-117">如下所述的主幹設定群組一組套用至主幹指派此主幹設定的參數。</span><span class="sxs-lookup"><span data-stu-id="238b2-117">A trunk configuration as described below groups a set of parameters that are applied to trunks assigned this trunk configuration.</span></span> <span data-ttu-id="238b2-118">特定的主幹組態可涵蓋全域 (涵蓋至不具更明確網站或集區組態的所有主幹)，或涵蓋至網站或集區。</span><span class="sxs-lookup"><span data-stu-id="238b2-118">A particular trunk configuration can be scoped globally (to all trunks that do not have more specific site or pool configuration), or to a site, or to a pool.</span></span> <span data-ttu-id="238b2-119">集區層級組態是用於將明確主幹組態涵蓋至單一主幹。</span><span class="sxs-lookup"><span data-stu-id="238b2-119">The pool-level trunk configuration is used to scope a specific trunk configuration to a single trunk.</span></span>

### <a name="to-configure-a-trunk-with-media-bypass"></a><span data-ttu-id="238b2-120">使用媒體旁路設定主幹</span><span class="sxs-lookup"><span data-stu-id="238b2-120">To configure a trunk with media bypass</span></span>

1. <span data-ttu-id="238b2-121">開啟商務用 Skype Server 控制台</span><span class="sxs-lookup"><span data-stu-id="238b2-121">Open Skype for Business Server Control Panel</span></span>

2. <span data-ttu-id="238b2-122">在左導覽列中，按一下 **[語音路由]**，再按一下 **[主幹組態]**。</span><span class="sxs-lookup"><span data-stu-id="238b2-122">In the left navigation bar, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

3. <span data-ttu-id="238b2-123">在 **[主幹組態]** 頁面上，使用下列其中一個方法設定主幹：</span><span class="sxs-lookup"><span data-stu-id="238b2-123">On the **Trunk Configuration** page, use one of the following methods to configure a trunk:</span></span>

   - <span data-ttu-id="238b2-124">按兩下現有主幹 (例如 **[通用]** 主幹)，顯示 **[編輯主幹組態]** 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="238b2-124">Double-click an existing trunk (for example, the **Global** trunk) to display the **Edit Trunk Configuration** dialog box.</span></span>

   - <span data-ttu-id="238b2-125">按一下 **[新增]**，然後選取新主幹組態：</span><span class="sxs-lookup"><span data-stu-id="238b2-125">Click **New**, and then select a scope for the new trunk configuration:</span></span>

   - <span data-ttu-id="238b2-126">**網站主幹**：從 [ **選取網站**] 選擇此主幹設定的網站，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="238b2-126">**Site trunk**: Choose the site for this trunk configuration from **Select a Site**, and then click **OK**.</span></span> <span data-ttu-id="238b2-127">請注意，如果已為某個網站建立主幹組態，則該網站不會出現在 **[選取站台]** 中。</span><span class="sxs-lookup"><span data-stu-id="238b2-127">Note that if a trunk configuration has already been created for a site, the site does not appear in **Select a Site**.</span></span> <span data-ttu-id="238b2-128">此主幹組態將套用至網站中的所有主幹。</span><span class="sxs-lookup"><span data-stu-id="238b2-128">This trunk configuration will be applied to all trunks in the site.</span></span>

   - <span data-ttu-id="238b2-129">**集區主幹**：選擇此主幹設定適用的主幹名稱。</span><span class="sxs-lookup"><span data-stu-id="238b2-129">**Pool trunk**: Choose the name of the trunk that this trunk configuration applies to.</span></span> <span data-ttu-id="238b2-130">這個主幹可以是根主幹或在拓撲產生器中定義的任何其他主幹。</span><span class="sxs-lookup"><span data-stu-id="238b2-130">This trunk can be the root trunk or any additional trunks defined in Topology Builder.</span></span> <span data-ttu-id="238b2-131">從 [ **選取服務**] 中，按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="238b2-131">From **Select a Service**, click **OK**.</span></span> <span data-ttu-id="238b2-132">請注意，如果已經針對特定主幹建立主幹組態，則該主幹就不會顯示在 **[選取服務]** 中。</span><span class="sxs-lookup"><span data-stu-id="238b2-132">Note that if a trunk configuration has already been created for a specific trunk, the trunk does not appear in **Select a Service**.</span></span>

      > [!NOTE]
      > <span data-ttu-id="238b2-133">一旦選取主幹組態的範圍後，就無法變更。</span><span class="sxs-lookup"><span data-stu-id="238b2-133">After you select the scope of the trunk configuration, it cannot be changed.</span></span> <span data-ttu-id="238b2-134">> [ **名稱** ] 欄位會預先填入主幹設定的關聯網站或服務的名稱，而且無法變更。</span><span class="sxs-lookup"><span data-stu-id="238b2-134">> The **Name** field is prepopulated with the name of the trunk configuration's associated site or service and cannot be changed.</span></span>

4. <span data-ttu-id="238b2-135">在 **支援的最大早期對話方塊** 中指定一個值。</span><span class="sxs-lookup"><span data-stu-id="238b2-135">Specify a value in **Maximum early dialogs supported**.</span></span> <span data-ttu-id="238b2-136">這是公用交換電話網路 (PSTN) 閘道、IP-PBX 或 ITSP 會話邊界控制器 (SBC) 可以接收到它傳送給轉送伺服器的邀請數目上限。</span><span class="sxs-lookup"><span data-stu-id="238b2-136">This is the maximum number of forked responses a public switched telephone network (PSTN) gateway, IP-PBX, or ITSP Session Border Controller (SBC) can receive to an INVITE that it sent to the Mediation Server.</span></span> <span data-ttu-id="238b2-137">預設值是 20。</span><span class="sxs-lookup"><span data-stu-id="238b2-137">The default value is 20.</span></span>

    > [!NOTE]
    > <span data-ttu-id="238b2-138">變更此值之前，請諮詢服務提供者或設備製造商，以取得系統功能的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="238b2-138">Before you change this value, consult your service provider or equipment manufacturer for details about the capabilities of your system.</span></span>

5. <span data-ttu-id="238b2-139">選取下列其中一個 **[加密支援等級]** 選項：</span><span class="sxs-lookup"><span data-stu-id="238b2-139">Select one of the following **Encryption support level** options:</span></span>

   - <span data-ttu-id="238b2-140">**必要**：必須使用安全即時傳輸通訊協定 (SRTP) 加密來保護中繼伺服器和閘道或專用交換機 (PBX) 之間的流量。</span><span class="sxs-lookup"><span data-stu-id="238b2-140">**Required**: Secure real-time transport protocol (SRTP) encryption must be used to help protect traffic between the Mediation Server and the gateway or private branch exchange (PBX).</span></span>

   - <span data-ttu-id="238b2-141">**選用**：如果服務提供者或設備製造商支援 SRTP，則使用 SRTP 加密。</span><span class="sxs-lookup"><span data-stu-id="238b2-141">**Optional**: SRTP encryption will be used if the service provider or equipment manufacturer supports it.</span></span>

   - <span data-ttu-id="238b2-142">**不支援**：服務提供者或設備製造商不支援 SRTP 加密，因此不使用 SRTP 加密。</span><span class="sxs-lookup"><span data-stu-id="238b2-142">**Not Supported**: SRTP encryption is not supported by the service provider or equipment manufacturer and therefore will not be used.</span></span>

6. <span data-ttu-id="238b2-143">如果您想讓媒體略過轉送伺服器，以供主幹對等處理，請選取 [ **啟用媒體旁路** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="238b2-143">Select the **Enable media bypass** check box if you want media to bypass the Mediation Server for processing by the trunk peer.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="238b2-144">若要讓媒體旁路順利運作，PSTN 閘道、IP-PBX 或 ITSP 會話邊界控制器必須支援某些功能。</span><span class="sxs-lookup"><span data-stu-id="238b2-144">For media bypass to work successfully, the PSTN gateway, IP-PBX, or ITSP Session Border Controller must support certain capabilities.</span></span> <span data-ttu-id="238b2-145">如需詳細資訊，請參閱 [Plan for media 旁路 In 商務用 Skype](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)。</span><span class="sxs-lookup"><span data-stu-id="238b2-145">For details, see [Plan for media bypass in Skype for Business](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span></span>

7. <span data-ttu-id="238b2-146">如果有已知的媒體終端 (點，請選取 [ **集中式媒體處理** ] 核取方塊（例如，媒體端接系的 IP 位址與「終止」) 相同）。</span><span class="sxs-lookup"><span data-stu-id="238b2-146">Select the **Centralized media processing** check box if there is a well-known media termination point (for example, a PSTN gateway where the media termination has the same IP as the signaling termination).</span></span> <span data-ttu-id="238b2-147">如果主幹沒有已知的媒體終端點，請清除此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="238b2-147">Clear this check box if the trunk does not have a well-known media termination point.</span></span>

8. <span data-ttu-id="238b2-148">如果主幹對等支援從轉送伺服器接收 SIP 參考要求，請選取 [ **啟用傳送參照至閘道** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="238b2-148">If the trunk peer supports receiving SIP REFER requests from the Mediation Server, select the **Enable sending refer to the gateway** check box.</span></span>

    > [!NOTE]
    > <span data-ttu-id="238b2-149">如果在選取 [ **啟用媒體旁路** ] 選項時停用此選項，則需要其他設定。</span><span class="sxs-lookup"><span data-stu-id="238b2-149">If you disable this option while the **Enable media bypass** option is selected, additional settings are required.</span></span> <span data-ttu-id="238b2-150">若主幹對等不支援從轉送伺服器接收 SIP 參考要求和媒體旁路，您也必須執行 **Set-CsTrunkConfiguration** Cmdlet 以停用使用中和保留通話的 RTCP，以便支援媒體旁路的適當狀況。</span><span class="sxs-lookup"><span data-stu-id="238b2-150">If the trunk peer does not support receiving SIP REFER requests from the Mediation Server and media bypass is enabled, you must also run the **Set-CsTrunkConfiguration** cmdlet to disable RTCP for active and held calls in order to support proper conditions for media bypass.</span></span> <span data-ttu-id="238b2-151">或者，您也可以選取 [ **使用協力廠商通話控制啟用參考** ]，如果您想要將轉接來電轉接到媒體略過，而閘道不支援 SIP 參考要求。</span><span class="sxs-lookup"><span data-stu-id="238b2-151">Alternatively, you can select **Enable refer using third-party-call control** if you want transferred calls to be media bypassed, and the gateway does not support SIP REFER requests.</span></span>

9. <span data-ttu-id="238b2-152">(選用) 若要啟用主幹間的路由，請關聯至此主幹組態並設定其 PSTN 使用方式記錄。</span><span class="sxs-lookup"><span data-stu-id="238b2-152">(Optional) To enable inter-trunk routing, associate and configure PSTN usage records to this trunk configuration.</span></span> <span data-ttu-id="238b2-153">與此主幹設定相關聯的 PSTN 使用方式，會透過主幹（並非來自商務用 Skype 伺服器端點）進行所有來電的應用程式。</span><span class="sxs-lookup"><span data-stu-id="238b2-153">The PSTN usages associated to this trunk configuration will be applied for all incoming calls through the trunk that is not originating from a Skype for Business Server endpoint.</span></span> <span data-ttu-id="238b2-154">若要管理與主幹組態關聯的 PSTN 使用方式記錄，請使用下列其中一種方法：</span><span class="sxs-lookup"><span data-stu-id="238b2-154">To manage PSTN usage records associated to a trunk configuration, use one of the following methods:</span></span>

   - <span data-ttu-id="238b2-155">若要從 Enterprise Voice 部署中所有可用的 PSTN 使用方式記錄清單中選取一或多筆記錄，請按一下 [ **選取**]。</span><span class="sxs-lookup"><span data-stu-id="238b2-155">To select one or more records from a list of all PSTN usage records available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="238b2-156">反白顯示您要與此主幹組態建立關聯的記錄，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="238b2-156">Highlight the records you want to associate with this trunk configuration and then click **OK**.</span></span>

   - <span data-ttu-id="238b2-157">若要從此主幹組態移除 PSTN 使用方式記錄，請選取該記錄然後按一下 **[移除]**。</span><span class="sxs-lookup"><span data-stu-id="238b2-157">To remove a PSTN usage record from this trunk configuration, select the record and click **Remove**.</span></span>

   - <span data-ttu-id="238b2-158">若要定義新的 PSTN 使用方式記錄，並建立與此主幹組態的關聯，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="238b2-158">To define a new PSTN usage record and associate it with this trunk configuration, do the following:</span></span>

     <span data-ttu-id="238b2-159">a.</span><span class="sxs-lookup"><span data-stu-id="238b2-159">a.</span></span> <span data-ttu-id="238b2-160">按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="238b2-160">Click **New**.</span></span>

     <span data-ttu-id="238b2-161">b.</span><span class="sxs-lookup"><span data-stu-id="238b2-161">b.</span></span> <span data-ttu-id="238b2-162">在 **[名稱]** 欄位中，指定該記錄的唯一描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="238b2-162">In the **Name** field, specify a descriptive name for the record that is unique.</span></span>

     > [!NOTE]
     > <span data-ttu-id="238b2-p119">PSTN 使用方式記錄名稱必須是 Enterprise Voice 部署內的唯一名稱。儲存記錄之後，就無法編輯 **[名稱]** 欄位。</span><span class="sxs-lookup"><span data-stu-id="238b2-p119">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the **Name** field cannot be edited.</span></span>

     <span data-ttu-id="238b2-165">c.</span><span class="sxs-lookup"><span data-stu-id="238b2-165">c.</span></span> <span data-ttu-id="238b2-166">使用下列其中一種方法，關聯至此 PSTN 使用方式記錄並設定其路由：</span><span class="sxs-lookup"><span data-stu-id="238b2-166">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>

     - <span data-ttu-id="238b2-167">若要從 Enterprise Voice 部署中所有可用路由的清單中選取一個或多個路由，請按一下 [ **選取**]。</span><span class="sxs-lookup"><span data-stu-id="238b2-167">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="238b2-168">反白顯示您要與此 PSTN 使用方式記錄相關聯的路由，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="238b2-168">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span>

     - <span data-ttu-id="238b2-169">若要從 PSTN 使用方式記錄移除路由，請選取該路由，然後按一下 **[移除]**。</span><span class="sxs-lookup"><span data-stu-id="238b2-169">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>

   - <span data-ttu-id="238b2-170">若要定義新路由，並將其關聯至此 PSTN 使用記錄，請按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="238b2-170">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="238b2-171">如需詳細資訊，請參閱 [Create or modify voice route In 商務用 Skype](create-or-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="238b2-171">For details, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span>

     - <span data-ttu-id="238b2-172">若要編輯與此 PSTN 使用方式記錄相關聯的路由，請選取該路由，然後按一下 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="238b2-172">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span>

     <span data-ttu-id="238b2-173">d.</span><span class="sxs-lookup"><span data-stu-id="238b2-173">d.</span></span> <span data-ttu-id="238b2-174">按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="238b2-174">Click **OK**.</span></span>

     - <span data-ttu-id="238b2-175">若要編輯已經與此主幹組態建立關聯的 PSTN 使用方式記錄，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="238b2-175">To edit a PSTN usage record that is already associated with this trunk configuration, do the following:</span></span>

       <span data-ttu-id="238b2-176">a.</span><span class="sxs-lookup"><span data-stu-id="238b2-176">a.</span></span> <span data-ttu-id="238b2-177">選取您要編輯的 PSTN 使用方式記錄，然後按一下 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="238b2-177">Select the PSTN usage record you want to edit, and click **Show details**.</span></span>

       <span data-ttu-id="238b2-178">b.</span><span class="sxs-lookup"><span data-stu-id="238b2-178">b.</span></span> <span data-ttu-id="238b2-179">使用下列其中一種方法，關聯至此 PSTN 使用方式記錄並設定其路由：</span><span class="sxs-lookup"><span data-stu-id="238b2-179">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>

   - <span data-ttu-id="238b2-180">若要從 Enterprise Voice 部署中所有可用路由的清單中選取一個或多個路由，請按一下 [ **選取**]。</span><span class="sxs-lookup"><span data-stu-id="238b2-180">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="238b2-181">反白顯示您要與此 PSTN 使用方式記錄相關聯的路由，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="238b2-181">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span>

   - <span data-ttu-id="238b2-182">若要從 PSTN 使用方式記錄移除路由，請選取該路由，然後按一下 **[移除]**。</span><span class="sxs-lookup"><span data-stu-id="238b2-182">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>

   - <span data-ttu-id="238b2-183">若要定義新路由，並將其關聯至此 PSTN 使用記錄，請按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="238b2-183">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="238b2-184">如需詳細資訊，請參閱 [Create or modify voice route In 商務用 Skype](create-or-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="238b2-184">For details, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span>

   - <span data-ttu-id="238b2-185">若要編輯與此 PSTN 使用方式記錄相關聯的路由，請選取該路由，然後按一下 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="238b2-185">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span>

     <span data-ttu-id="238b2-186">c.</span><span class="sxs-lookup"><span data-stu-id="238b2-186">c.</span></span> <span data-ttu-id="238b2-187">按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="238b2-187">Click **OK**.</span></span>

     > [!IMPORTANT]
     > <span data-ttu-id="238b2-188">請務必將 PSTN 使用方式記錄與所設定之主幹相關聯的轉送伺服器對等相關聯。</span><span class="sxs-lookup"><span data-stu-id="238b2-188">It is important to associate PSTN usage records according to the Mediation Server peer that is associated to the trunk being configured.</span></span> <span data-ttu-id="238b2-189">若轉送伺服器對等是 PSTN 閘道或會話邊界控制器 (SBC) ，強烈建議您不要將主幹設定相關聯至 pstn 使用方式記錄，該記錄會路由傳送至 PSTN 目的地或透過商務用 Skype Server 所連接的任何其他下游系統。</span><span class="sxs-lookup"><span data-stu-id="238b2-189">If the Mediation Server peer is a PSTN gateway or a Session Border Controller (SBC), it is strongly recommended that the trunk configuration is not associated to a PSTN usage record that routes to a PSTN destination or any other downstream systems connected via Skype for Business Server.</span></span>

10. <span data-ttu-id="238b2-190">排列 PSTN 使用方式記錄，以獲得最佳效能。</span><span class="sxs-lookup"><span data-stu-id="238b2-190">Arrange the PSTN usage records for optimum performance.</span></span> <span data-ttu-id="238b2-191">若要變更記錄在清單中的位置，請選取 PSTN 使用方式記錄，然後按一下向上或向下箭號。</span><span class="sxs-lookup"><span data-stu-id="238b2-191">To change a record's position in the list, select the PSTN usage record, and click the up or down arrows.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="238b2-192">PSTN 使用方式記錄列示在主幹組態中的順序非常重要。</span><span class="sxs-lookup"><span data-stu-id="238b2-192">The order in which PSTN usage records are listed in the trunk configuration is significant.</span></span> <span data-ttu-id="238b2-193">商務用 Skype 伺服器從上到上，從上到上來遍歷清單。</span><span class="sxs-lookup"><span data-stu-id="238b2-193">Skype for Business Server traverses the list from top to down.</span></span>

11. <span data-ttu-id="238b2-194">應該選取 [**啟用 RTP** 鎖定]，以啟用網路位址轉譯之後用戶端的旁路媒體（ (NAT) 或防火牆，以及支援閉鎖的 SBC）。</span><span class="sxs-lookup"><span data-stu-id="238b2-194">**Enable RTP Latching** should be selected to enable bypass media for clients behind a network address translation (NAT) or firewall and an SBC that supports latching.</span></span>

12. <span data-ttu-id="238b2-195">應該選取 [**啟用轉接來電記錄**]，以啟用將通話記錄資訊傳送至轉送伺服器的閘道對等功能。</span><span class="sxs-lookup"><span data-stu-id="238b2-195">**Enable forward call history** should be selected to enable sending of call history information to the gateway peer of the Mediation Server.</span></span>

13. <span data-ttu-id="238b2-196">您應該選取 [**啟用轉寄 P-Asserted-Identity 資料**]，以啟用 P-ASSERTED-IDENTITY (PAI) 呼叫發信方資訊，以便在轉送伺服器端與閘道端 (之間轉送，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="238b2-196">**Enable forward P-Asserted-Identity data** should be selected to enable the P-Asserted-Identity (PAI) call originator information to be forwarded between the Mediation Server side and gateway side (and vice versa), when present.</span></span>

14. <span data-ttu-id="238b2-197">您應選取 **[啟用輸出路由容錯移轉計時器]** 才能啟用快速容錯移轉。</span><span class="sxs-lookup"><span data-stu-id="238b2-197">**Enable outbound routing failover timer** should be selected to enable fast failover.</span></span> <span data-ttu-id="238b2-198">由於與此主幹相關聯的閘道正在處理撥出電話，所以可以在 10 秒內發出通知。</span><span class="sxs-lookup"><span data-stu-id="238b2-198">The gateway associated with this trunk can give notification within 10 seconds that it is processing an outbound call.</span></span> <span data-ttu-id="238b2-199">若轉送伺服器未收到此通知，則會進行重新路由至另一個主幹。</span><span class="sxs-lookup"><span data-stu-id="238b2-199">Rerouting to another trunk will occur if this notification is not received by the Mediation Server.</span></span> <span data-ttu-id="238b2-200">在延遲可能遞延回應時間的網路上或是閘道回應時間在 10 秒以上者，應停用快速容錯移轉。</span><span class="sxs-lookup"><span data-stu-id="238b2-200">On networks where latency may delay the response time or the gateway takes longer than 10 seconds to respond, the fast failover should be disabled.</span></span>

15. <span data-ttu-id="238b2-201">(選用) 建立與主幹的關聯並設定其 **[撥號轉譯規則]**。</span><span class="sxs-lookup"><span data-stu-id="238b2-201">(Optional) Associate and configure **calling number translation rules** for the trunk.</span></span> <span data-ttu-id="238b2-202">這些轉譯規則適用於撥出電話的撥打號碼</span><span class="sxs-lookup"><span data-stu-id="238b2-202">These translation rules apply to the calling number for outbound calls</span></span>

    - <span data-ttu-id="238b2-203">若要從 Enterprise Voice 部署中所有可用轉譯規則的清單中選擇一個或多個規則，請按一下 [ **選取**]。</span><span class="sxs-lookup"><span data-stu-id="238b2-203">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="238b2-204">在 **[選取轉譯規則]** 中，按一下您要建立關聯的主幹，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="238b2-204">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>

    - <span data-ttu-id="238b2-205">若要定義新的轉譯規則並建立其與主幹的關聯，請按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="238b2-205">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="238b2-206">如需有關轉譯規則的詳細資訊，請參閱 [商務用 Skype Server 中的轉譯規則](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="238b2-206">For details about translation rules, see [Translation rules in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md).</span></span>

    - <span data-ttu-id="238b2-207">若要編輯已與主幹建立關聯的轉譯規則，按一下規則名稱，然後按一下 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="238b2-207">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span>

    - <span data-ttu-id="238b2-208">若要複製現有轉譯規則，以用來作為定義新規則時的起點，請按一下規則名稱，再按一下 **[複製]**，然後按一下 **[貼上]**。</span><span class="sxs-lookup"><span data-stu-id="238b2-208">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span>

    - <span data-ttu-id="238b2-209">若要從主幹移除轉譯規則，請反白顯示該規則名稱並按一下 **[移除]**。</span><span class="sxs-lookup"><span data-stu-id="238b2-209">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>

    > [!CAUTION]
    > <span data-ttu-id="238b2-210">如果您已在關聯的主幹對等上設定轉譯規則，請勿再將轉譯規則與主幹建立關聯，因為這兩個規則可能會產生衝突。</span><span class="sxs-lookup"><span data-stu-id="238b2-210">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>

16. <span data-ttu-id="238b2-p136">(選用) 建立與主幹的關聯並設定其 **[撥號轉譯規則]**。這些轉譯規則適用於撥出電話的撥打號碼。</span><span class="sxs-lookup"><span data-stu-id="238b2-p136">(Optional) Associate and configure **called number translation rules** for the trunk. The translation rules apply to the called number in an outbound call.</span></span>

    - <span data-ttu-id="238b2-213">若要從 Enterprise Voice 部署中所有可用轉譯規則的清單中選擇一個或多個規則，請按一下 [ **選取**]。</span><span class="sxs-lookup"><span data-stu-id="238b2-213">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="238b2-214">在 **[選取轉譯規則]** 中，按一下您要建立關聯的主幹，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="238b2-214">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>

    - <span data-ttu-id="238b2-215">若要定義新的轉譯規則並建立其與主幹的關聯，請按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="238b2-215">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="238b2-216">如需有關轉譯規則的詳細資訊，請參閱 [商務用 Skype Server 中的轉譯規則](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="238b2-216">For details about translation rules, see [Translation rules in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md).</span></span>

    - <span data-ttu-id="238b2-217">若要編輯已與主幹建立關聯的轉譯規則，按一下規則名稱，然後按一下 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="238b2-217">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span>

    - <span data-ttu-id="238b2-218">若要複製現有轉譯規則，以用來作為定義新規則時的起點，請按一下規則名稱，再按一下 **[複製]**，然後按一下 **[貼上]**。</span><span class="sxs-lookup"><span data-stu-id="238b2-218">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span>

    - <span data-ttu-id="238b2-219">若要從主幹移除轉譯規則，請反白顯示該規則名稱並按一下 **[移除]**。</span><span class="sxs-lookup"><span data-stu-id="238b2-219">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>

    > [!CAUTION]
    > <span data-ttu-id="238b2-220">如果您已在相關聯的主幹對等上設定轉譯規則，則請勿將轉譯規則與主幹建立關聯，因為兩種規則可能會衝突。</span><span class="sxs-lookup"><span data-stu-id="238b2-220">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>

17. <span data-ttu-id="238b2-221">請確定主幹的轉譯規則依正確的順序排列。</span><span class="sxs-lookup"><span data-stu-id="238b2-221">Make sure that the trunk's translation rules are arranged in the correct order.</span></span> <span data-ttu-id="238b2-222">若要變更規則在清單中的位置，請反白顯示規則名稱，然後按一下向上或向下箭號。</span><span class="sxs-lookup"><span data-stu-id="238b2-222">To change a rule's position in the list, highlight the rule name and then click the up or down arrow.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="238b2-223">商務用 Skype 伺服器會從左上部開始轉譯規則清單，並使用符合撥號號碼的第一個規則。</span><span class="sxs-lookup"><span data-stu-id="238b2-223">Skype for Business Server traverses the translation rule list from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="238b2-224">如果您設定的主幹會使撥號號碼符合不只一個轉譯規則，請確定限制較多的規則排在限制較少的規則上方。</span><span class="sxs-lookup"><span data-stu-id="238b2-224">If you configure a trunk so that a dialed number can match more than one translation rule, be sure that the more restrictive rules are sorted above the less restrictive rules.</span></span> <span data-ttu-id="238b2-225">例如，如果您已包含符合任何11位數的轉譯規則和轉譯規則，且符合以 + 1425 開頭的11位數，請確定符合任何11位數數位的規則，會依限制性更為嚴格的 *規則排序。*</span><span class="sxs-lookup"><span data-stu-id="238b2-225">For example, if you have included a translation rule that matches any 11-digit number and a translation rule that matches only 11-digit numbers that start with +1425, be sure that the rule that matches any 11-digit number is sorted  *below*  the more restrictive rule.</span></span>

18. <span data-ttu-id="238b2-226">完成主幹的設定時，請按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="238b2-226">When you are finished configuring the trunk, click **OK**.</span></span>

19. <span data-ttu-id="238b2-227">在 **[主幹組態]** 頁面上，按一下 **[認可]**，再按一下 **[全部認可]**。</span><span class="sxs-lookup"><span data-stu-id="238b2-227">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="238b2-228">只要建立或修改主幹組態後，都應執行 **[全部認可]** 命令以發行組態變更。</span><span class="sxs-lookup"><span data-stu-id="238b2-228">Whenever you create or modify a trunk configuration, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="238b2-229">如需詳細資訊，請參閱 Operations 檔中的在 [商務用 Skype 中發佈待定的變更至語音路由](voice-route-config-changes.md) 設定。</span><span class="sxs-lookup"><span data-stu-id="238b2-229">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

<span data-ttu-id="238b2-230">設定主幹之後，請選擇通用媒體旁路選項，繼續設定媒體旁路，如部署檔中的 [在 [商務用 Skype Server 中部署媒體旁路](deploy-media-bypass.md) ] 中所述。</span><span class="sxs-lookup"><span data-stu-id="238b2-230">After you have configured the trunk, continue configuring media bypass by choosing between global media bypass options, as described in [Deploy media bypass in Skype for Business Server](deploy-media-bypass.md) in the Deployment documentation.</span></span>
## <a name="see-also"></a><span data-ttu-id="238b2-231">另請參閱</span><span class="sxs-lookup"><span data-stu-id="238b2-231">See also</span></span>

[<span data-ttu-id="238b2-232">在商務用 Skype Server 中設定無媒體旁路的主幹</span><span class="sxs-lookup"><span data-stu-id="238b2-232">Configure a trunk without media bypass in Skype for Business Server</span></span>](configure-trunk-without-media-bypass.md)

[<span data-ttu-id="238b2-233">在商務用 Skype Server 中部署媒體旁路</span><span class="sxs-lookup"><span data-stu-id="238b2-233">Deploy media bypass in Skype for Business Server</span></span>](deploy-media-bypass.md)

[<span data-ttu-id="238b2-234">定義轉譯規則</span><span class="sxs-lookup"><span data-stu-id="238b2-234">Defining Translation Rules</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-defining-translation-rules)

[<span data-ttu-id="238b2-235">設定媒體旁路</span><span class="sxs-lookup"><span data-stu-id="238b2-235">Configure Media Bypass</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-configure-media-bypass)