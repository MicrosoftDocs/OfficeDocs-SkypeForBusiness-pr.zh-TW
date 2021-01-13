---
title: 管理貴組織的 SIP 同盟提供者
ms.reviewer: ''
ms:assetid: c78d7e9b-c496-40c6-9249-06ced9cb87f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552455(v=OCS.15)
ms:contentKeyID: 48679566
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 瞭解如何為 SIP 同盟提供者的使用者設定支援。
ms.openlocfilehash: 8d4c6224a66454f8fb28bb4f991faf6ad672f596
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823563"
---
# <a name="manage-sip-federated-providers-for-your-organization-in-skype-for-business-server"></a><span data-ttu-id="f398f-103">在商務用 Skype Server 中管理組織的 SIP 同盟提供者</span><span class="sxs-lookup"><span data-stu-id="f398f-103">Manage SIP federated providers for your organization in Skype for Business Server</span></span>

<span data-ttu-id="f398f-104">若要為 SIP 同盟提供者的使用者設定支援，您需要執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="f398f-104">To configure support for users of SIP federated providers, you need to do the following:</span></span>

  - <span data-ttu-id="f398f-105">設定一或多個外部使用者存取原則，以支援與 SIP 同盟提供者連絡人的通訊</span><span class="sxs-lookup"><span data-stu-id="f398f-105">Configure one or more external user access policies to support communicating with SIP federated provider contacts</span></span>

  - <span data-ttu-id="f398f-106">指定您要支援的主控提供者</span><span class="sxs-lookup"><span data-stu-id="f398f-106">Specify which hosted providers you want to support</span></span>

  - <span data-ttu-id="f398f-107">指定您要支援的公用 IM 提供者</span><span class="sxs-lookup"><span data-stu-id="f398f-107">Specify which public IM providers you want to support</span></span>

## <a name="create-or-edit-public-sip-federated-providers-in-skype-for-business-server"></a><span data-ttu-id="f398f-108">在商務用 Skype Server 中建立或編輯公用 SIP 同盟提供者</span><span class="sxs-lookup"><span data-stu-id="f398f-108">Create or edit public SIP federated providers in Skype for Business Server</span></span>

<span data-ttu-id="f398f-109">公用立即訊息 (IM) 連線能力，讓組織中的使用者能夠使用 IM 與公用提供者所提供的 IM 服務使用者通訊。</span><span class="sxs-lookup"><span data-stu-id="f398f-109">Public instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by public providers.</span></span>

<span data-ttu-id="f398f-110">商務用 Skype 伺服器具有立即訊息的公用提供者設定。</span><span class="sxs-lookup"><span data-stu-id="f398f-110">Skype for Business Server has public provider configurations for instant messaging.</span></span> <span data-ttu-id="f398f-111">每個公用提供者都會使用提供者的 Edge Server 完整網域名稱，以及預設驗證層級 **[僅允許使用者與其連絡人清單上使用此提供者的人通訊]** 來設定。</span><span class="sxs-lookup"><span data-stu-id="f398f-111">Each public provider is configured with the provider’s Edge server fully qualified domain name, and the default verification level **Allow users to communicate only with people on their Contacts list who use this provider**.</span></span>

<span data-ttu-id="f398f-112">預設設定為不啟用任何公用提供者。</span><span class="sxs-lookup"><span data-stu-id="f398f-112">As a default setting, none of the public providers are enabled.</span></span> <span data-ttu-id="f398f-113">在啟用公用提供者之前，您應該先完成授權合約及佈建工作。</span><span class="sxs-lookup"><span data-stu-id="f398f-113">You should complete license agreement and provisioning work before enabling the public providers.</span></span> <span data-ttu-id="f398f-114">您可以在完成授權和佈建工作之前啟用提供者。</span><span class="sxs-lookup"><span data-stu-id="f398f-114">You can enable the provider before completing the licensing and provisioning work.</span></span> <span data-ttu-id="f398f-115">在必要工作完成之前，使用者將無法與這些提供者的連絡人通訊。</span><span class="sxs-lookup"><span data-stu-id="f398f-115">Users will not be able to communicate with contacts on those providers until the pre-requisite work is completed.</span></span> <span data-ttu-id="f398f-116">如需授權及布建公用提供者的詳細資訊，請參閱 [設定原則以控制公用使用者](../external-access-policies/configure-policies-to-control-public-user-access.md)訪問。</span><span class="sxs-lookup"><span data-stu-id="f398f-116">For details on licensing and provisioning of public providers, see [Configure policies to control public user acces](../external-access-policies/configure-policies-to-control-public-user-access.md).</span></span>

<span data-ttu-id="f398f-117">請使用下列程式來建立或編輯公用提供者。</span><span class="sxs-lookup"><span data-stu-id="f398f-117">Use the following procedure to create or edit Public providers.</span></span>


### <a name="to-create-or-edit-public-providers"></a><span data-ttu-id="f398f-118">建立或編輯公用提供者</span><span class="sxs-lookup"><span data-stu-id="f398f-118">To create or edit public providers</span></span>

1.  <span data-ttu-id="f398f-119">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="f398f-119">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f398f-120">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="f398f-120">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="f398f-121">在左導覽列中，依序按一下 **[同盟和外部存取]** 和 **[SIP 同盟提供者]**。</span><span class="sxs-lookup"><span data-stu-id="f398f-121">In the left navigation bar, click **Federation and External Access**, and then click **SIP Federated Providers**.</span></span>

4.  <span data-ttu-id="f398f-122">如果您需要建立新的公用提供者，請依序按一下 **[新增]** 和 **[公用提供者]**。</span><span class="sxs-lookup"><span data-stu-id="f398f-122">If you need to create a new Public provider, click **New** and then click **Public provider**.</span></span>

5.  <span data-ttu-id="f398f-123">如果您需要編輯公用提供者清單中的項目，選取公用提供者，然後依序按一下 **[編輯]** 和 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="f398f-123">If you need to edit an entry from the list of Public providers, select a public provider, click **Edit**, then click **Show details**.</span></span>

6.  <span data-ttu-id="f398f-124">在 **[編輯 SIP 同盟提供者]** 頁面上，您可以鍵入或編輯下列設定：</span><span class="sxs-lookup"><span data-stu-id="f398f-124">On the **Edit SIP Federated Provider** page, you can type or edit the following settings:</span></span>
    
      - <span data-ttu-id="f398f-125">**[允許與這個提供者的通訊]**    選取此設定可讓 IM 與此提供者的使用者通訊。</span><span class="sxs-lookup"><span data-stu-id="f398f-125">**Enable communications with this provider**   Selecting this setting enables IM with this provider’s users.</span></span>
    
      - <span data-ttu-id="f398f-126">**提供者名稱：**    必要內容，請輸入提供者的名稱，其將反映在 SIP 同盟提供者清單中。</span><span class="sxs-lookup"><span data-stu-id="f398f-126">**Provider name:**   A required property, type the name of the provider as it will be reflected in the listing of SIP Federated Providers.</span></span>
    
      - <span data-ttu-id="f398f-127">**Access Edge service (FQDN) ：**   必要的屬性，請輸入您要設定之提供者的 Access Edge service 的完整功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="f398f-127">**Access Edge service (FQDN):**   A required property, type the fully qualified domain name of the Access Edge service of the provider that you are configuring.</span></span> <span data-ttu-id="f398f-128">此資訊是以預設專案提供，只在公用提供者對公用提供者的 Access Edge service 的 FQDN 進行變更時，才應變更。</span><span class="sxs-lookup"><span data-stu-id="f398f-128">This information is provided as a default item, and should only be changed if the public provider makes a change to the FQDN of the Access Edge service at the public provider.</span></span>
    
      - <span data-ttu-id="f398f-129">**[預設驗證層級：]**    預設設定，**[僅允許使用者與其連絡人清單上使用此提供者的人通訊]** 會限制與您已接受並且在您的連絡人清單中的連絡人通訊。</span><span class="sxs-lookup"><span data-stu-id="f398f-129">**Default verification level:**   The default setting, **Allow users to communicate with people on their Contacts list who use this provider** will limit communication to contacts that you have accepted and are in your contact list.</span></span>
        
        <span data-ttu-id="f398f-p104">選取 **[允許使用者與使用此提供者的所有人通訊]** 會移除您必須已收到並接受連絡人邀請的限制。此設定不會限制誰可以從公用提供者網路與您連絡。</span><span class="sxs-lookup"><span data-stu-id="f398f-p104">Selecting **Allow users to communicate with everyone using this provider** removes the restriction that you must have received and accepted a contact invite. This setting does not limit who can contact you from the public provider’s network.</span></span>

7.  <span data-ttu-id="f398f-132">完成設定之後，請按一下 **[認可]** 儲存，或按一下 **[取消]** 捨棄您的變更。</span><span class="sxs-lookup"><span data-stu-id="f398f-132">When you are done configuring the settings, click **Commit** to save, or click **Cancel** to discard your changes.</span></span>

## <a name="create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server"></a><span data-ttu-id="f398f-133">在商務用 Skype Server 中建立或編輯主控的 SIP 同盟提供者</span><span class="sxs-lookup"><span data-stu-id="f398f-133">Create or edit hosted SIP federated providers in Skype for Business Server</span></span>

<span data-ttu-id="f398f-134">主控提供者立即訊息 (IM) 連線能力，讓組織中的使用者能夠使用 IM，與託管提供者所提供之 IM 服務的使用者進行通訊。</span><span class="sxs-lookup"><span data-stu-id="f398f-134">Hosted provider instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by hosted providers.</span></span>

<span data-ttu-id="f398f-135">每個裝載提供者都設有提供者的 Edge Server 完整網域名稱，以及預設驗證層級 [允許使用者僅與其連絡人清單中使用此提供者的人通訊]。</span><span class="sxs-lookup"><span data-stu-id="f398f-135">Each hosted provider is configured with the provider’s Edge server fully qualified domain name, and the default verification level **Allow users to communicate only with people on their Contacts list who use this provider**.</span></span>

<span data-ttu-id="f398f-136">請使用下列程式來建立或編輯主控的提供者。</span><span class="sxs-lookup"><span data-stu-id="f398f-136">Use the following procedure to create or edit hosted providers.</span></span>

### <a name="to-create-or-edit-hosted-providers"></a><span data-ttu-id="f398f-137">建立或編輯裝載提供者</span><span class="sxs-lookup"><span data-stu-id="f398f-137">To create or edit hosted providers</span></span>

1.  <span data-ttu-id="f398f-138">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="f398f-138">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f398f-139">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="f398f-139">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="f398f-140">在左導覽列中，按一下 [同盟及外部存取]，然後按一下 [SIP 同盟提供者]。</span><span class="sxs-lookup"><span data-stu-id="f398f-140">In the left navigation bar, click **Federation and External Access**, and then click **SIP Federated Providers**.</span></span>

4.  <span data-ttu-id="f398f-141">如果您需要建立新的裝載提供者，請按一下 [新增]，然後按一下 [裝載提供者]。</span><span class="sxs-lookup"><span data-stu-id="f398f-141">If you need to create a new Hosted provider, click **New** and then click **Hosted provider**.</span></span>

5.  <span data-ttu-id="f398f-142">如果您需要編輯裝載提供者清單中的項目，請選取裝載提供者，按一下 [編輯]，然後按一下 [顯示詳細資料]。</span><span class="sxs-lookup"><span data-stu-id="f398f-142">If you need to edit an entry from the list of Hosted providers, select a hosted provider, click **Edit**, then click **Show details**.</span></span>

6.  <span data-ttu-id="f398f-143">在「編輯 SIP 同盟提供者」頁面上，您可以輸入或編輯下列設定：</span><span class="sxs-lookup"><span data-stu-id="f398f-143">On the **Edit SIP Federated Provider** page, you can type or edit the following settings:</span></span>
    
      - <span data-ttu-id="f398f-144">**允許與這個提供者的通訊**   選取此設定可與這個提供者的使用者進行通訊。</span><span class="sxs-lookup"><span data-stu-id="f398f-144">**Enable communications with this provider**   Selecting this setting enables communications with this provider’s users.</span></span>
    
      - <span data-ttu-id="f398f-145">**提供者名稱：**    必要內容，請輸入提供者的名稱，其將反映在 SIP 同盟提供者清單中。</span><span class="sxs-lookup"><span data-stu-id="f398f-145">**Provider name:**   A required property, type the name of the provider as it will be reflected in the listing of SIP Federated Providers.</span></span>
    
      - <span data-ttu-id="f398f-146">**Access Edge service (FQDN) ：**   必要的屬性，請輸入您要設定之主控提供者的 Access Edge service 的完整功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="f398f-146">**Access Edge service (FQDN):**   A required property, type the fully qualified domain name of the Access Edge service of the hosted provider that you are configuring.</span></span> <span data-ttu-id="f398f-147">此資訊應由主控的提供者提供，而且只有在主控提供者對主控提供者的 Access Edge service 的 FQDN 進行變更時，才應變更此資訊。</span><span class="sxs-lookup"><span data-stu-id="f398f-147">This information should be provided by the hosted provider, and should only be changed if the hosted provider makes a change to the FQDN of the Access Edge service at the hosted provider.</span></span>
    
      - <span data-ttu-id="f398f-148">**預設驗證層級：**    預設設定，[允許使用者僅與其連絡人清單中使用此提供者的人通訊] 會將通訊範圍限制為您已接受並且在連絡人清單中的連絡人。</span><span class="sxs-lookup"><span data-stu-id="f398f-148">**Default verification level:**   The default setting, **Allow users to communicate with people on their Contacts list who use this provider** will limit communication to contacts that you have accepted and are in your contact list.</span></span>
        
        <span data-ttu-id="f398f-p106">選取 [允許使用者與使用此提供者的所有人通訊] 會移除您必須收到並接受連絡人邀請的限制。此設定不限制哪些人可以從裝載提供者的網路連絡您。</span><span class="sxs-lookup"><span data-stu-id="f398f-p106">Selecting **Allow users to communicate with everyone using this provider** removes the restriction that you must have received and accepted a contact invite. This setting does not limit who can contact you from the hosted provider’s network.</span></span>

7.  <span data-ttu-id="f398f-151">完成設定時，按一下 [認可] 以儲存，或按一下 [取消] 以捨棄變更。</span><span class="sxs-lookup"><span data-stu-id="f398f-151">When you are done configuring the settings, click **Commit** to save, or click **Cancel** to discard your changes.</span></span>


## <a name="see-also"></a><span data-ttu-id="f398f-152">另請參閱</span><span class="sxs-lookup"><span data-stu-id="f398f-152">See Also</span></span>


[<span data-ttu-id="f398f-153">設定原則以控制公用使用者的加入</span><span class="sxs-lookup"><span data-stu-id="f398f-153">Configure policies to control public user acces</span></span>](../external-access-policies/configure-policies-to-control-public-user-access.md)

[<span data-ttu-id="f398f-154">啟用或停用同盟和公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="f398f-154">Enable or disable federation and public IM connectivity</span></span>](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)

