---
title: 在商務用 Skype Server 中設定不使用媒體的主幹
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3422e93e-7bd2-4470-968c-dc38345b18ca
description: '摘要: 針對商務用 Skype Server, 請針對沒有啟用媒體旁路的設定主幹。'
ms.openlocfilehash: c60217b6dc127616dfbaf9590c43adec25c20eff
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233878"
---
# <a name="configure-a-trunk-without-media-bypass-in-skype-for-business-server"></a><span data-ttu-id="81efd-103">在商務用 Skype Server 中設定不使用媒體的主幹</span><span class="sxs-lookup"><span data-stu-id="81efd-103">Configure a trunk without media bypass in Skype for Business Server</span></span>

<span data-ttu-id="81efd-104">**摘要:** 針對商務用 Skype Server 啟用不使用媒體旁路的主幹設定。</span><span class="sxs-lookup"><span data-stu-id="81efd-104">**Summary:** Configure a trunk without media bypass enabled for Skype for Business Server.</span></span>

<span data-ttu-id="81efd-105">如果您想要在停用媒體旁路的情況下設定幹線, 請遵循下列步驟。</span><span class="sxs-lookup"><span data-stu-id="81efd-105">If you want to configure a trunk with media bypass disabled, follow these steps.</span></span> <span data-ttu-id="81efd-106">如果您想要設定啟用媒體旁路的幹線, 請參閱[使用商務用 Skype Server 中的 [媒體旁路] 設定主幹](configure-trunk-with-media-bypass.md)。</span><span class="sxs-lookup"><span data-stu-id="81efd-106">If you want to configure a trunk with media bypass enabled, see [Configure a trunk with media bypass in Skype for Business Server](configure-trunk-with-media-bypass.md).</span></span>

<span data-ttu-id="81efd-107">主幹設定 (如下所述) 將套用至 trunks 的一組參數群組指派給此幹線設定。</span><span class="sxs-lookup"><span data-stu-id="81efd-107">A trunk configuration, as described below, groups a set of parameters that are applied to trunks assigned this trunk configuration.</span></span> <span data-ttu-id="81efd-108">您可以將特定的主幹設定設為全域 (所有 trunks, 而不會有更具體的網站或池配置), 或是到網站或池中。</span><span class="sxs-lookup"><span data-stu-id="81efd-108">A particular trunk configuration can be scoped globally (to all trunks that do not have more specific site or pool configuration), or to a site, or to a pool.</span></span> <span data-ttu-id="81efd-109">[池層級中繼] 設定是用來將特定主幹設定的範圍限定在單一干線中。</span><span class="sxs-lookup"><span data-stu-id="81efd-109">The pool-level trunk configuration is used to scope a specific trunk configuration to a single trunk.</span></span>

### <a name="to-configure-a-trunk-without-media-bypass"></a><span data-ttu-id="81efd-110">在沒有媒體旁路的情況下設定幹線</span><span class="sxs-lookup"><span data-stu-id="81efd-110">To configure a trunk without media bypass</span></span>

1. <span data-ttu-id="81efd-111">開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="81efd-111">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="81efd-112">在左側導覽列中, 按一下 [**語音路由**], 然後按一下 [**幹線**設定]。</span><span class="sxs-lookup"><span data-stu-id="81efd-112">In the left navigation bar, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

3. <span data-ttu-id="81efd-113">在 [**幹線**設定] 頁面上, 使用下列其中一種方法來設定幹線:</span><span class="sxs-lookup"><span data-stu-id="81efd-113">On the **Trunk Configuration** page, use one of the following methods to configure a trunk:</span></span>

   - <span data-ttu-id="81efd-114">按兩下現有的幹線 (例如,**全域**幹線), 以顯示 [**編輯主幹**設定] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="81efd-114">Double-click an existing trunk (for example, the **Global** trunk) to display the **Edit Trunk Configuration** dialog box.</span></span>

   - <span data-ttu-id="81efd-115">按一下 [**新增**], 然後選取新主幹設定的範圍:</span><span class="sxs-lookup"><span data-stu-id="81efd-115">Click **New**, and then select a scope for the new trunk configuration:</span></span>

   - <span data-ttu-id="81efd-116">**網站主幹**: 在 [**選取網站**] 中選擇此主幹設定的網站, 然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="81efd-116">**Site trunk**: Choose the site for this trunk configuration in **Select a Site**, and then click **OK**.</span></span> <span data-ttu-id="81efd-117">請注意, 如果已為網站建立中繼設定, 網站就不會出現在 [**選取網站**] 中。</span><span class="sxs-lookup"><span data-stu-id="81efd-117">Note that if a trunk configuration has already been created for a site, the site does not appear in **Select a Site**.</span></span> <span data-ttu-id="81efd-118">此主幹設定將會套用至網站中的所有 trunks。</span><span class="sxs-lookup"><span data-stu-id="81efd-118">This trunk configuration will be applied to all trunks in the site.</span></span>

   - <span data-ttu-id="81efd-119">[**泳池主幹**]: 選擇此幹線設定適用的主幹名稱,**請選取服務**, 然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="81efd-119">**Pool trunk**: Choose the name of the trunk that this trunk configuration applies to in **Select a Service** and click **OK**.</span></span> <span data-ttu-id="81efd-120">這個幹線可以是根主幹, 或拓撲建立器中定義的任何其他 trunks。</span><span class="sxs-lookup"><span data-stu-id="81efd-120">This trunk can be the root trunk, or any additional trunks defined in Topology Builder.</span></span> <span data-ttu-id="81efd-121">請注意, 如果已為特定主幹建立幹線設定, 主幹不會出現在 [**選取服務**] 中。</span><span class="sxs-lookup"><span data-stu-id="81efd-121">Note that if a trunk configuration has already been created for a specific trunk, the trunk does not appear in **Select a Service**.</span></span>

     > [!NOTE]
     > <span data-ttu-id="81efd-122">在您選取主幹設定的範圍之後, 就無法變更它。</span><span class="sxs-lookup"><span data-stu-id="81efd-122">After you select the scope of the trunk configuration, it cannot be changed.</span></span> <span data-ttu-id="81efd-123">> [ **Name** ] (名稱) 欄位會預先填入與幹線設定的關聯網站或服務名稱, 且無法變更。</span><span class="sxs-lookup"><span data-stu-id="81efd-123">> The **Name** field is pre-populated with the name of the trunk configuration's associated site or service and cannot be changed.</span></span>

4. <span data-ttu-id="81efd-124">選取下列其中一個**加密支援等級**選項:</span><span class="sxs-lookup"><span data-stu-id="81efd-124">Select one of the following **Encryption support level** options:</span></span>

   - <span data-ttu-id="81efd-125">**必要**: 安全即時傳輸通訊協定 (SRTP) 加密必須用來協助保護中繼伺服器與閘道或私人分支 EXCHANGE (PBX) 之間的流量。</span><span class="sxs-lookup"><span data-stu-id="81efd-125">**Required**: Secure Realtime Transport Protocol (SRTP) encryption must be used to help protect traffic between the Mediation Server and the gateway or Private Branch eXchange (PBX).</span></span>

   - <span data-ttu-id="81efd-126">**選用**: 如果服務提供者或設備製造商支援, 則會使用 SRTP 加密。</span><span class="sxs-lookup"><span data-stu-id="81efd-126">**Optional**: SRTP encryption will be used if the service provider or equipment manufacturer supports it.</span></span>

   - <span data-ttu-id="81efd-127">**不支援**: 服務提供者或設備製造商不支援 SRTP 加密, 因此將無法使用。</span><span class="sxs-lookup"><span data-stu-id="81efd-127">**Not Supported**: SRTP encryption is not supported by the service provider or equipment manufacturer and therefore will not be used.</span></span>

5. <span data-ttu-id="81efd-128">請確定已清除 [**啟用媒體旁路**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="81efd-128">Be sure that the **Enable media bypass** check box is cleared.</span></span>

6. <span data-ttu-id="81efd-129">如果有已知的媒體端接點, 請選取 [**集中式媒體處理**] 核取方塊 (例如, 在媒體端接的公用交換電話網絡 (PSTN) 閘道與 [信號終止] 相同)。</span><span class="sxs-lookup"><span data-stu-id="81efd-129">Select the **Centralized media processing** check box if there is a well-known media termination point (for example, a Public Switched Telephone Network (PSTN) gateway where the media termination has the same IP as the signaling termination).</span></span> <span data-ttu-id="81efd-130">如果主幹沒有已知的媒體端接點, 請清除此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="81efd-130">Clear this check box if the trunk does not have a well-known media termination point.</span></span>

7. <span data-ttu-id="81efd-131">如果乾線對等支援接收來自中繼伺服器的 SIP, 請選取 [**啟用傳送參照至閘道**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="81efd-131">If the trunk peer supports receiving SIP REFER requests from the Mediation Server, select the **Enable sending refer to the gateway** check box.</span></span>

8. <span data-ttu-id="81efd-132">可選若要啟用站間路由, 請將 PSTN 使用記錄關聯並設定為此主幹設定。</span><span class="sxs-lookup"><span data-stu-id="81efd-132">(Optional) To enable inter-trunk routing, associate and configure PSTN usage records to this trunk configuration.</span></span> <span data-ttu-id="81efd-133">與此幹線設定關聯的 PSTN 用法, 將會針對並非源自商務用 Skype 伺服器端點的主幹進行所有來電。</span><span class="sxs-lookup"><span data-stu-id="81efd-133">The PSTN usages associated to this trunk configuration will be applied for all incoming calls through the trunk that is not originating from a Skype for Business Server endpoint.</span></span> <span data-ttu-id="81efd-134">若要管理與幹線設定相關聯的 PSTN 使用記錄, 請使用下列其中一種方法:</span><span class="sxs-lookup"><span data-stu-id="81efd-134">To manage PSTN usage records associated to a trunk configuration, use one of the following methods:</span></span>

   - <span data-ttu-id="81efd-135">若要從企業語音部署中所有可用的 PSTN 使用記錄清單中選取一或多筆記錄, 請按一下 [**選取**]。</span><span class="sxs-lookup"><span data-stu-id="81efd-135">To select one or more records from a list of all PSTN usage records available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="81efd-136">醒目提示您要與此主幹設定關聯的記錄, 然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="81efd-136">Highlight the records you want to associate with this trunk configuration and then click **OK**.</span></span>

   - <span data-ttu-id="81efd-137">若要從此幹線設定中移除 PSTN 使用記錄, 請選取該記錄, 然後按一下 [**移除**]。</span><span class="sxs-lookup"><span data-stu-id="81efd-137">To remove a PSTN usage record from this trunk configuration, select the record and click **Remove**.</span></span>

   - <span data-ttu-id="81efd-138">若要定義新的 PSTN 使用記錄, 並將它與此幹線設定關聯, 請執行下列動作:</span><span class="sxs-lookup"><span data-stu-id="81efd-138">To define a new PSTN usage record and associate it with this trunk configuration, do the following:</span></span>

     <span data-ttu-id="81efd-139">是.</span><span class="sxs-lookup"><span data-stu-id="81efd-139">a.</span></span> <span data-ttu-id="81efd-140">按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="81efd-140">Click **New**.</span></span>

     <span data-ttu-id="81efd-141">乙.</span><span class="sxs-lookup"><span data-stu-id="81efd-141">b.</span></span> <span data-ttu-id="81efd-142">在 [**名稱**] 欄位中, 為記錄指定唯一的描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="81efd-142">In the **Name** field, specify a descriptive name for the record that is unique.</span></span>

     > [!NOTE]
     > <span data-ttu-id="81efd-143">PSTN 使用記錄名稱在企業語音部署中必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="81efd-143">The PSTN usage record name must be unique within the Enterprise Voice deployment.</span></span> <span data-ttu-id="81efd-144">在儲存記錄之後, [**名稱**] 欄位就無法進行編輯。</span><span class="sxs-lookup"><span data-stu-id="81efd-144">After the record is saved, the **Name** field cannot be edited.</span></span>

     <span data-ttu-id="81efd-145">c-clip.</span><span class="sxs-lookup"><span data-stu-id="81efd-145">c.</span></span> <span data-ttu-id="81efd-146">使用下列其中一種方法來關聯及設定此 PSTN 使用記錄的路線:</span><span class="sxs-lookup"><span data-stu-id="81efd-146">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>

     - <span data-ttu-id="81efd-147">若要從企業語音部署中所有可用路由的清單中選取一或多個路由, 請按一下 [**選取**]。</span><span class="sxs-lookup"><span data-stu-id="81efd-147">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="81efd-148">醒目提示您想要與此 PSTN 使用記錄產生關聯的路線, 然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="81efd-148">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span>

     - <span data-ttu-id="81efd-149">若要從 PSTN 使用量記錄移除路由, 請選取路由, 然後按一下 [**移除**]。</span><span class="sxs-lookup"><span data-stu-id="81efd-149">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>

     - <span data-ttu-id="81efd-150">若要定義新的路由, 並將它與此 PSTN 使用記錄建立關聯, 請按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="81efd-150">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="81efd-151">如需詳細資訊, 請參閱[在商務用 Skype 中建立或修改語音路線](create-or-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="81efd-151">For details, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span>

     - <span data-ttu-id="81efd-152">若要編輯與此 PSTN 使用記錄相關聯的路線, 請選取該路線, 然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="81efd-152">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span>

     <span data-ttu-id="81efd-153">希望.</span><span class="sxs-lookup"><span data-stu-id="81efd-153">d.</span></span> <span data-ttu-id="81efd-154">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="81efd-154">Click **OK**.</span></span>

   - <span data-ttu-id="81efd-155">若要編輯已與此幹線設定關聯的 PSTN 使用記錄, 請執行下列動作:</span><span class="sxs-lookup"><span data-stu-id="81efd-155">To edit a PSTN usage record that is already associated with this trunk configuration, do the following:</span></span>

     <span data-ttu-id="81efd-156">是.</span><span class="sxs-lookup"><span data-stu-id="81efd-156">a.</span></span> <span data-ttu-id="81efd-157">選取您要編輯的 PSTN 使用量記錄, 然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="81efd-157">Select the PSTN usage record you want to edit, and click **Show details**.</span></span>

     <span data-ttu-id="81efd-158">乙.</span><span class="sxs-lookup"><span data-stu-id="81efd-158">b.</span></span> <span data-ttu-id="81efd-159">使用下列其中一種方法來關聯及設定此 PSTN 使用記錄的路線:</span><span class="sxs-lookup"><span data-stu-id="81efd-159">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>

     - <span data-ttu-id="81efd-160">若要從企業語音部署中所有可用路由的清單中選取一或多個路由, 請按一下 [**選取**]。</span><span class="sxs-lookup"><span data-stu-id="81efd-160">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="81efd-161">醒目提示您想要與此 PSTN 使用記錄產生關聯的路線, 然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="81efd-161">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span>

     - <span data-ttu-id="81efd-162">若要從 PSTN 使用量記錄移除路由, 請選取路由, 然後按一下 [**移除**]。</span><span class="sxs-lookup"><span data-stu-id="81efd-162">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>

     - <span data-ttu-id="81efd-163">若要定義新的路由, 並將它與此 PSTN 使用記錄建立關聯, 請按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="81efd-163">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="81efd-164">如需詳細資訊, 請參閱[在商務用 Skype 中建立或修改語音路線](create-or-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="81efd-164">For details, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span>

     - <span data-ttu-id="81efd-165">若要編輯與此 PSTN 使用記錄相關聯的路線, 請選取該路線, 然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="81efd-165">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span>

     <span data-ttu-id="81efd-166">c-clip.</span><span class="sxs-lookup"><span data-stu-id="81efd-166">c.</span></span> <span data-ttu-id="81efd-167">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="81efd-167">Click **OK**.</span></span>

     > [!IMPORTANT]
     > <span data-ttu-id="81efd-168">請務必將 PSTN 使用記錄與所設定的幹線相關聯的中繼伺服器對進行關聯。</span><span class="sxs-lookup"><span data-stu-id="81efd-168">It is important to associate PSTN usage records according to the Mediation Server peer that is associated to the trunk being configured.</span></span> <span data-ttu-id="81efd-169">如果中繼伺服器對等是 PSTN 閘道或會話邊界控制器 (SBC), 強烈建議您不要將幹線設定與路由至 PSTN 目的地或透過 Skype 連接的任何其他下游系統的 PSTN 使用記錄相關聯商務用伺服器。</span><span class="sxs-lookup"><span data-stu-id="81efd-169">If the Mediation Server peer is a PSTN gateway or a Session Border Controller (SBC), it is strongly recommended that the trunk configuration is not associated to a PSTN usage record that routes to a PSTN destination or any other downstream systems connected via Skype for Business Server.</span></span>

9. <span data-ttu-id="81efd-170">排列 PSTN 使用狀況記錄, 以獲得最佳效能。</span><span class="sxs-lookup"><span data-stu-id="81efd-170">Arrange the PSTN usage records for optimum performance.</span></span> <span data-ttu-id="81efd-171">若要變更記錄在清單中的位置, 請選取 PSTN 使用記錄, 然後按一下向上或向下箭號。</span><span class="sxs-lookup"><span data-stu-id="81efd-171">To change a record's position in the list, select the PSTN usage record, and click the up or down arrows.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="81efd-172">PSTN 使用記錄在幹線設定中的顯示順序非常重要。</span><span class="sxs-lookup"><span data-stu-id="81efd-172">The order in which PSTN usage records are listed in the trunk configuration is significant.</span></span> <span data-ttu-id="81efd-173">商務用 Skype 伺服器會從上到下遍歷清單。</span><span class="sxs-lookup"><span data-stu-id="81efd-173">Skype for Business Server traverses the list from top to down.</span></span>

10. <span data-ttu-id="81efd-174">應選取 [**啟用 RTP 閉鎖**], 以便為 NAT 或防火牆後的用戶端使用旁路媒體, 以及支援閉鎖的 SBC。</span><span class="sxs-lookup"><span data-stu-id="81efd-174">**Enable RTP Latching** should be selected to enable bypass media for clients behind a NAT or firewall and an SBC that supports latching.</span></span>

11. <span data-ttu-id="81efd-175">應選取 [**啟用轉寄通話記錄**], 以允許將通話記錄資訊傳送到中繼伺服器的閘道對等。</span><span class="sxs-lookup"><span data-stu-id="81efd-175">**Enable forward call history** should be selected to enable sending of call history information to the gateway peer of the Mediation Server.</span></span>

12. <span data-ttu-id="81efd-176">[**啟用前 P-已斷言身分識別的資料**] 必須選取, 才能讓 PAI 通話發信方資訊在中繼伺服器端和閘道端之間 (反之亦然), 在目前狀態中轉寄。</span><span class="sxs-lookup"><span data-stu-id="81efd-176">**Enable forward P-Asserted-Identity data** should be selected to enable PAI call originator information to be forwarded between the Mediation Server side and gateway side (and vice versa), when present.</span></span>

13. <span data-ttu-id="81efd-177">若要啟用快速容錯移轉, 請選取 [**啟用輸出路由容錯移轉計時器**]。</span><span class="sxs-lookup"><span data-stu-id="81efd-177">**Enable outbound routing failover timer** should be selected to enable fast failover.</span></span> <span data-ttu-id="81efd-178">與此幹線關聯的閘道可以在處理撥出通話的10秒內發出通知。</span><span class="sxs-lookup"><span data-stu-id="81efd-178">The gateway associated with this trunk can give notification within 10 seconds that it is processing an outbound call.</span></span> <span data-ttu-id="81efd-179">如果中繼伺服器未收到此通知, 就會將重新路由至另一個主幹。</span><span class="sxs-lookup"><span data-stu-id="81efd-179">Rerouting to another trunk will occur if this notification is not received by the Mediation Server.</span></span> <span data-ttu-id="81efd-180">在延遲可能會延遲回應時間的網路上, 或閘道需要10秒以上的時間才能回應, 就應該停用 [快速容錯移轉]。</span><span class="sxs-lookup"><span data-stu-id="81efd-180">On networks where latency may delay the response time or the gateway takes longer than 10 seconds to respond, the fast failover should be disabled.</span></span>

14. <span data-ttu-id="81efd-181">可選關聯並設定主幹的**通話數轉譯規則**。</span><span class="sxs-lookup"><span data-stu-id="81efd-181">(Optional) Associate and configure **calling number translation rules** for the trunk.</span></span> <span data-ttu-id="81efd-182">這些翻譯規則會套用至撥出通話的電話號碼</span><span class="sxs-lookup"><span data-stu-id="81efd-182">These translation rules apply to the calling number for outbound calls</span></span>

    - <span data-ttu-id="81efd-183">若要從企業語音部署中提供的所有翻譯規則清單中選擇一或多個規則, 請按一下 [**選取**]。</span><span class="sxs-lookup"><span data-stu-id="81efd-183">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="81efd-184">在 [**選取翻譯規則**] 中, 按一下您要與主幹建立關聯的規則, 然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="81efd-184">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>

    - <span data-ttu-id="81efd-185">若要定義新的翻譯規則, 並將其與骨幹建立關聯, 請按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="81efd-185">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="81efd-186">如需翻譯規則的詳細資訊, 請參閱[商務用 Skype Server 中的翻譯規則](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="81efd-186">For details about translation rules, see [Translation rules in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md).</span></span>

    - <span data-ttu-id="81efd-187">若要編輯已經與主幹建立關聯的翻譯規則, 請按一下規則名稱, 然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="81efd-187">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span>

    - <span data-ttu-id="81efd-188">若要複製現有的翻譯規則, 以做為定義新規則的起點, 請按一下規則名稱, 然後按一下 [**複製**], 然後按一下 [**貼**上]。</span><span class="sxs-lookup"><span data-stu-id="81efd-188">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span>

    - <span data-ttu-id="81efd-189">若要從主幹中移除翻譯規則, 請將規則名稱醒目提示, 然後按一下 [**移除**]。</span><span class="sxs-lookup"><span data-stu-id="81efd-189">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>

      > [!CAUTION]
      > <span data-ttu-id="81efd-190">如果您已在關聯的中繼對等上設定翻譯規則, 請不要將翻譯規則與幹線建立關聯, 因為這兩個規則可能會衝突。</span><span class="sxs-lookup"><span data-stu-id="81efd-190">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>

15. <span data-ttu-id="81efd-191">可選關聯並設定主幹的已**呼叫數位轉譯規則**。</span><span class="sxs-lookup"><span data-stu-id="81efd-191">(Optional) Associate and configure **called number translation rules** for the trunk.</span></span> <span data-ttu-id="81efd-192">翻譯規則會套用至撥出通話中呼叫的號碼。</span><span class="sxs-lookup"><span data-stu-id="81efd-192">The translation rules apply to the called number in an outbound call.</span></span>

    - <span data-ttu-id="81efd-193">若要從企業語音部署中提供的所有翻譯規則清單中選擇一或多個規則, 請按一下 [**選取**]。</span><span class="sxs-lookup"><span data-stu-id="81efd-193">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="81efd-194">在 [**選取翻譯規則**] 中, 按一下您要與主幹建立關聯的規則, 然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="81efd-194">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>

    - <span data-ttu-id="81efd-195">若要定義新的翻譯規則, 並將其與骨幹建立關聯, 請按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="81efd-195">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="81efd-196">如需翻譯規則的詳細資訊, 請參閱[商務用 Skype Server 中的翻譯規則](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="81efd-196">For details about translation rules, see [Translation rules in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md).</span></span>

    - <span data-ttu-id="81efd-197">若要編輯已經與主幹建立關聯的翻譯規則, 請按一下規則名稱, 然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="81efd-197">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span>

    - <span data-ttu-id="81efd-198">若要複製現有的翻譯規則, 以做為定義新規則的起點, 請按一下規則名稱, 然後按一下 [**複製**], 然後按一下 [**貼**上]。</span><span class="sxs-lookup"><span data-stu-id="81efd-198">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span>

    - <span data-ttu-id="81efd-199">若要從主幹中移除翻譯規則, 請將規則名稱醒目提示, 然後按一下 [**移除**]。</span><span class="sxs-lookup"><span data-stu-id="81efd-199">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>

      > [!CAUTION]
      > <span data-ttu-id="81efd-200">如果您已在關聯的中繼對等上設定翻譯規則, 請不要將翻譯規則與幹線建立關聯, 因為這兩個規則可能會衝突。</span><span class="sxs-lookup"><span data-stu-id="81efd-200">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>

16. <span data-ttu-id="81efd-201">確定主幹的轉譯規則依正確順序排列。</span><span class="sxs-lookup"><span data-stu-id="81efd-201">Make sure that the trunk's translation rules are arranged in the correct order.</span></span> <span data-ttu-id="81efd-202">若要變更規則在清單中的位置, 請醒目提示 [規則名稱], 然後按一下向上或向下箭號。</span><span class="sxs-lookup"><span data-stu-id="81efd-202">To change a rule's position in the list, highlight the rule name, and then click the up or down arrow.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="81efd-203">商務用 Skype 伺服器會從上到下遍歷翻譯規則清單, 並使用與撥打的號碼相符的第一個規則。</span><span class="sxs-lookup"><span data-stu-id="81efd-203">Skype for Business Server traverses the translation rule list from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="81efd-204">如果您設定幹線, 讓撥入的號碼可以符合多個翻譯規則, 請確定更嚴格的規則, 在限制性較低的規則之上排序。</span><span class="sxs-lookup"><span data-stu-id="81efd-204">If you configure a trunk so that a dialed number can match more than one translation rule, be sure that the more restrictive rules are sorted above the less restrictive rules.</span></span> <span data-ttu-id="81efd-205">例如, 如果您已包含符合任何11位數的翻譯規則, 以及只符合以 + 1425 開頭的11位數的翻譯規則, 請確定符合任何11位數數位的規則, 將其排序為*低於*較嚴格的限制基準.</span><span class="sxs-lookup"><span data-stu-id="81efd-205">For example, if you have included a translation rule that matches any 11-digit number and a translation rule that matches only 11-digit numbers that start with +1425, be sure that the rule that matches any 11-digit number is sorted  *below*  the more restrictive rule.</span></span>

17. <span data-ttu-id="81efd-206">當您完成設定主幹時, 請按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="81efd-206">When you are finished configuring the trunk, click **OK**.</span></span>

18. <span data-ttu-id="81efd-207">在 [**幹線**設定] 頁面上, 按一下 [**認可**], 然後按一下 [**全部確認**]。</span><span class="sxs-lookup"><span data-stu-id="81efd-207">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="81efd-208">每當您建立或修改幹線設定時, 您都必須執行 [**全部提交**] 命令才能發佈設定變更。</span><span class="sxs-lookup"><span data-stu-id="81efd-208">Whenever you create or modify a trunk configuration, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="81efd-209">如需詳細資訊, 請參閱在作業檔中[發佈商務用 Skype 中的語音路由設定的待處理變更](voice-route-config-changes.md)。</span><span class="sxs-lookup"><span data-stu-id="81efd-209">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="81efd-210">另請參閱</span><span class="sxs-lookup"><span data-stu-id="81efd-210">See also</span></span>

<span data-ttu-id="81efd-211">[在商務用 Skype Server 中使用 [旁路媒體] 設定主幹](configure-trunk-with-media-bypass.md)</span><span class="sxs-lookup"><span data-stu-id="81efd-211">[Configure a trunk with media bypass in Skype for Business Server](configure-trunk-with-media-bypass.md)</span></span>

[<span data-ttu-id="81efd-212">定義翻譯規則</span><span class="sxs-lookup"><span data-stu-id="81efd-212">Defining Translation Rules</span></span>](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx)

