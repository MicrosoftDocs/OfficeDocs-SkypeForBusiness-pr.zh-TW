---
title: 管理組織的 SIP 同盟提供者
ms.reviewer: ''
ms:assetid: c78d7e9b-c496-40c6-9249-06ced9cb87f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552455(v=OCS.15)
ms:contentKeyID: 48679566
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 瞭解如何設定 SIP 聯盟提供者的使用者支援。
ms.openlocfilehash: 42845bfd39c65e60765ee8d3fd2f1e3a58a08aae
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818364"
---
# <a name="manage-sip-federated-providers-for-your-organization-in-skype-for-business-server"></a><span data-ttu-id="64cf1-103">在商務用 Skype Server 中管理貴組織的 SIP 聯盟提供者</span><span class="sxs-lookup"><span data-stu-id="64cf1-103">Manage SIP federated providers for your organization in Skype for Business Server</span></span>

<span data-ttu-id="64cf1-104">若要針對 SIP 聯盟提供者的使用者設定支援，您必須執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="64cf1-104">To configure support for users of SIP federated providers, you need to do the following:</span></span>

  - <span data-ttu-id="64cf1-105">設定一或多個外部使用者存取原則，以支援與 SIP 聯盟提供者連絡人的通訊</span><span class="sxs-lookup"><span data-stu-id="64cf1-105">Configure one or more external user access policies to support communicating with SIP federated provider contacts</span></span>

  - <span data-ttu-id="64cf1-106">指定您要支援的託管提供者</span><span class="sxs-lookup"><span data-stu-id="64cf1-106">Specify which hosted providers you want to support</span></span>

  - <span data-ttu-id="64cf1-107">指定您想要支援的公用 IM 提供者</span><span class="sxs-lookup"><span data-stu-id="64cf1-107">Specify which public IM providers you want to support</span></span>

## <a name="create-or-edit-public-sip-federated-providers-in-skype-for-business-server"></a><span data-ttu-id="64cf1-108">在商務用 Skype Server 中建立或編輯公用 SIP 聯盟提供者</span><span class="sxs-lookup"><span data-stu-id="64cf1-108">Create or edit public SIP federated providers in Skype for Business Server</span></span>

<span data-ttu-id="64cf1-109">公用立即訊息（IM）連線功能可讓貴組織中的使用者使用 IM 與公用提供者所提供的 IM 服務使用者通訊。</span><span class="sxs-lookup"><span data-stu-id="64cf1-109">Public instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by public providers.</span></span>

<span data-ttu-id="64cf1-110">商務用 Skype 伺服器具有立即訊息的公用提供者配置。</span><span class="sxs-lookup"><span data-stu-id="64cf1-110">Skype for Business Server has public provider configurations for instant messaging.</span></span> <span data-ttu-id="64cf1-111">每個公開提供者都是使用提供者的邊緣伺服器完整功能變數名稱來設定，而且預設驗證層級**可讓使用者只與他們的連絡人清單中使用這個提供者的人通訊**。</span><span class="sxs-lookup"><span data-stu-id="64cf1-111">Each public provider is configured with the provider’s Edge server fully qualified domain name, and the default verification level **Allow users to communicate only with people on their Contacts list who use this provider**.</span></span>

<span data-ttu-id="64cf1-112">預設設定為 [未啟用任何公用提供者]。</span><span class="sxs-lookup"><span data-stu-id="64cf1-112">As a default setting, none of the public providers are enabled.</span></span> <span data-ttu-id="64cf1-113">在啟用公用提供者之前，您應該先完成授權協定和置備作業。</span><span class="sxs-lookup"><span data-stu-id="64cf1-113">You should complete license agreement and provisioning work before enabling the public providers.</span></span> <span data-ttu-id="64cf1-114">您可以先啟用提供者，然後才能完成授權及預配作業。</span><span class="sxs-lookup"><span data-stu-id="64cf1-114">You can enable the provider before completing the licensing and provisioning work.</span></span> <span data-ttu-id="64cf1-115">在完成先決條件工作完成之前，使用者將無法與這些提供者上的連絡人通訊。</span><span class="sxs-lookup"><span data-stu-id="64cf1-115">Users will not be able to communicate with contacts on those providers until the pre-requisite work is completed.</span></span> <span data-ttu-id="64cf1-116">如需授權與提供公用提供者的詳細資料，請參閱[設定控制公用使用者](../external-access-policies/configure-policies-to-control-public-user-access.md)訪問的原則。</span><span class="sxs-lookup"><span data-stu-id="64cf1-116">For details on licensing and provisioning of public providers, see [Configure policies to control public user acces](../external-access-policies/configure-policies-to-control-public-user-access.md).</span></span>

<span data-ttu-id="64cf1-117">使用下列程式來建立或編輯公用提供者。</span><span class="sxs-lookup"><span data-stu-id="64cf1-117">Use the following procedure to create or edit Public providers.</span></span>


### <a name="to-create-or-edit-public-providers"></a><span data-ttu-id="64cf1-118">建立或編輯公用提供者</span><span class="sxs-lookup"><span data-stu-id="64cf1-118">To create or edit public providers</span></span>

1.  <span data-ttu-id="64cf1-119">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="64cf1-119">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="64cf1-120">開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="64cf1-120">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="64cf1-121">在左側導覽列中，按一下 [**同盟與外部存取**]，然後按一下 [ **SIP 同盟提供者**]。</span><span class="sxs-lookup"><span data-stu-id="64cf1-121">In the left navigation bar, click **Federation and External Access**, and then click **SIP Federated Providers**.</span></span>

4.  <span data-ttu-id="64cf1-122">如果您需要建立新的公用提供者，請按一下 [**新增**]，然後按一下 [**公用提供者**]。</span><span class="sxs-lookup"><span data-stu-id="64cf1-122">If you need to create a new Public provider, click **New** and then click **Public provider**.</span></span>

5.  <span data-ttu-id="64cf1-123">如果您需要從公用提供者清單中編輯專案，請選取公用提供者，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="64cf1-123">If you need to edit an entry from the list of Public providers, select a public provider, click **Edit**, then click **Show details**.</span></span>

6.  <span data-ttu-id="64cf1-124">在 [**編輯 SIP 聯盟提供者**] 頁面上，您可以輸入或編輯下列設定：</span><span class="sxs-lookup"><span data-stu-id="64cf1-124">On the **Edit SIP Federated Provider** page, you can type or edit the following settings:</span></span>
    
      - <span data-ttu-id="64cf1-125">**啟用與此提供者**   的通訊選取此設定即可啟用與此提供者使用者的 IM。</span><span class="sxs-lookup"><span data-stu-id="64cf1-125">**Enable communications with this provider**   Selecting this setting enables IM with this provider’s users.</span></span>
    
      - <span data-ttu-id="64cf1-126">**提供者名稱：**   required 屬性，請輸入提供者的名稱，因為它會反映在 SIP 同盟提供者清單中。</span><span class="sxs-lookup"><span data-stu-id="64cf1-126">**Provider name:**   A required property, type the name of the provider as it will be reflected in the listing of SIP Federated Providers.</span></span>
    
      - <span data-ttu-id="64cf1-127">**[存取邊緣服務（FQDN）]：**   [必要] 屬性，請輸入您要設定之提供者的存取邊緣服務的完整功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="64cf1-127">**Access Edge service (FQDN):**   A required property, type the fully qualified domain name of the Access Edge service of the provider that you are configuring.</span></span> <span data-ttu-id="64cf1-128">此資訊是以預設專案提供的，只有在公用提供者變更公用提供者的存取邊緣服務的 FQDN 時，才能加以變更。</span><span class="sxs-lookup"><span data-stu-id="64cf1-128">This information is provided as a default item, and should only be changed if the public provider makes a change to the FQDN of the Access Edge service at the public provider.</span></span>
    
      - <span data-ttu-id="64cf1-129">**預設驗證階層：**   預設設定是 [**允許使用者與連絡人清單中的人員通訊]，使用這個提供者**時，會將通訊限制在您已接受的連絡人，並在您的連絡人清單中。</span><span class="sxs-lookup"><span data-stu-id="64cf1-129">**Default verification level:**   The default setting, **Allow users to communicate with people on their Contacts list who use this provider** will limit communication to contacts that you have accepted and are in your contact list.</span></span>
        
        <span data-ttu-id="64cf1-130">選取 [**允許使用者與使用這個提供者的所有人通訊**]，就會移除您必須收到並接受連絡人邀請的限制。</span><span class="sxs-lookup"><span data-stu-id="64cf1-130">Selecting **Allow users to communicate with everyone using this provider** removes the restriction that you must have received and accepted a contact invite.</span></span> <span data-ttu-id="64cf1-131">此設定不會限制誰能從公用提供者的網路與您聯繫。</span><span class="sxs-lookup"><span data-stu-id="64cf1-131">This setting does not limit who can contact you from the public provider’s network.</span></span>

7.  <span data-ttu-id="64cf1-132">設定完畢後，請按一下 [**認可**] 來儲存，或按一下 [**取消**] 放棄您的變更。</span><span class="sxs-lookup"><span data-stu-id="64cf1-132">When you are done configuring the settings, click **Commit** to save, or click **Cancel** to discard your changes.</span></span>

## <a name="create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server"></a><span data-ttu-id="64cf1-133">在商務用 Skype Server 中建立或編輯託管 SIP 聯盟提供者</span><span class="sxs-lookup"><span data-stu-id="64cf1-133">Create or edit hosted SIP federated providers in Skype for Business Server</span></span>

<span data-ttu-id="64cf1-134">宿主提供者立即訊息（IM）連線可讓貴組織中的使用者使用 IM 與託管提供者所提供之 IM 服務的使用者通訊。</span><span class="sxs-lookup"><span data-stu-id="64cf1-134">Hosted provider instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by hosted providers.</span></span>

<span data-ttu-id="64cf1-135">每個託管提供者都是以提供者的 Edge 伺服器的完整功能變數名稱進行設定，而且預設驗證層級**可讓使用者只與他們的連絡人清單中使用這個提供者的人通訊**。</span><span class="sxs-lookup"><span data-stu-id="64cf1-135">Each hosted provider is configured with the provider’s Edge server fully qualified domain name, and the default verification level **Allow users to communicate only with people on their Contacts list who use this provider**.</span></span>

<span data-ttu-id="64cf1-136">使用下列程式來建立或編輯託管提供者。</span><span class="sxs-lookup"><span data-stu-id="64cf1-136">Use the following procedure to create or edit hosted providers.</span></span>

### <a name="to-create-or-edit-hosted-providers"></a><span data-ttu-id="64cf1-137">建立或編輯託管提供者</span><span class="sxs-lookup"><span data-stu-id="64cf1-137">To create or edit hosted providers</span></span>

1.  <span data-ttu-id="64cf1-138">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="64cf1-138">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="64cf1-139">開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="64cf1-139">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="64cf1-140">在左側導覽列中，按一下 [**同盟與外部存取**]，然後按一下 [ **SIP 同盟提供者**]。</span><span class="sxs-lookup"><span data-stu-id="64cf1-140">In the left navigation bar, click **Federation and External Access**, and then click **SIP Federated Providers**.</span></span>

4.  <span data-ttu-id="64cf1-141">如果您需要建立新的託管提供者，請按一下 [**新增**]，然後按一下 [**託管提供者**]。</span><span class="sxs-lookup"><span data-stu-id="64cf1-141">If you need to create a new Hosted provider, click **New** and then click **Hosted provider**.</span></span>

5.  <span data-ttu-id="64cf1-142">如果您需要編輯託管提供者清單中的專案，請選取託管提供者，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="64cf1-142">If you need to edit an entry from the list of Hosted providers, select a hosted provider, click **Edit**, then click **Show details**.</span></span>

6.  <span data-ttu-id="64cf1-143">在 [**編輯 SIP 聯盟提供者**] 頁面上，您可以輸入或編輯下列設定：</span><span class="sxs-lookup"><span data-stu-id="64cf1-143">On the **Edit SIP Federated Provider** page, you can type or edit the following settings:</span></span>
    
      - <span data-ttu-id="64cf1-144">**啟用與此提供者**   的通訊選取此設定，即可與此提供者的使用者進行通訊。</span><span class="sxs-lookup"><span data-stu-id="64cf1-144">**Enable communications with this provider**   Selecting this setting enables communications with this provider’s users.</span></span>
    
      - <span data-ttu-id="64cf1-145">**提供者名稱：**   required 屬性，請輸入提供者的名稱，因為它會反映在 SIP 同盟提供者清單中。</span><span class="sxs-lookup"><span data-stu-id="64cf1-145">**Provider name:**   A required property, type the name of the provider as it will be reflected in the listing of SIP Federated Providers.</span></span>
    
      - <span data-ttu-id="64cf1-146">**[存取邊緣服務（FQDN）]：**   [必要] 屬性，請輸入您要設定之託管提供者的存取邊緣服務的完整功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="64cf1-146">**Access Edge service (FQDN):**   A required property, type the fully qualified domain name of the Access Edge service of the hosted provider that you are configuring.</span></span> <span data-ttu-id="64cf1-147">此資訊應該由託管提供者提供，而且只有在託管提供者對託管提供者的存取邊緣服務的 FQDN 進行變更時，才應進行變更。</span><span class="sxs-lookup"><span data-stu-id="64cf1-147">This information should be provided by the hosted provider, and should only be changed if the hosted provider makes a change to the FQDN of the Access Edge service at the hosted provider.</span></span>
    
      - <span data-ttu-id="64cf1-148">**預設驗證階層：**   預設設定是 [**允許使用者與連絡人清單中的人員通訊]，使用這個提供者**時，會將通訊限制在您已接受的連絡人，並在您的連絡人清單中。</span><span class="sxs-lookup"><span data-stu-id="64cf1-148">**Default verification level:**   The default setting, **Allow users to communicate with people on their Contacts list who use this provider** will limit communication to contacts that you have accepted and are in your contact list.</span></span>
        
        <span data-ttu-id="64cf1-149">選取 [**允許使用者與使用這個提供者的所有人通訊**]，就會移除您必須收到並接受連絡人邀請的限制。</span><span class="sxs-lookup"><span data-stu-id="64cf1-149">Selecting **Allow users to communicate with everyone using this provider** removes the restriction that you must have received and accepted a contact invite.</span></span> <span data-ttu-id="64cf1-150">此設定不會限制誰能從主機託管提供者的網路與您聯繫。</span><span class="sxs-lookup"><span data-stu-id="64cf1-150">This setting does not limit who can contact you from the hosted provider’s network.</span></span>

7.  <span data-ttu-id="64cf1-151">設定完畢後，請按一下 [**認可**] 來儲存，或按一下 [**取消**] 放棄您的變更。</span><span class="sxs-lookup"><span data-stu-id="64cf1-151">When you are done configuring the settings, click **Commit** to save, or click **Cancel** to discard your changes.</span></span>


## <a name="see-also"></a><span data-ttu-id="64cf1-152">請參閱</span><span class="sxs-lookup"><span data-stu-id="64cf1-152">See Also</span></span>


[<span data-ttu-id="64cf1-153">設定控制公用使用者進行控制的原則</span><span class="sxs-lookup"><span data-stu-id="64cf1-153">Configure policies to control public user acces</span></span>](../external-access-policies/configure-policies-to-control-public-user-access.md)

[<span data-ttu-id="64cf1-154">啟用或停用同盟和公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="64cf1-154">Enable or disable federation and public IM connectivity</span></span>](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)

