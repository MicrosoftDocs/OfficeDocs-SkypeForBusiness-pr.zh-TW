---
title: Lync Server 2013：建立或編輯公用 SIP 同盟提供者
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or edit public SIP federated providers
ms:assetid: 5321598c-1ab1-40e3-b739-4b2e6d0a3a3b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398349(v=OCS.15)
ms:contentKeyID: 48184167
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 58b0ffdc009d48ef82d1bdf3ba8662cd4072ea1c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514850"
---
# <a name="create-or-edit-public-sip-federated-providers-in-lync-server-2013"></a><span data-ttu-id="40b7b-102">在 Lync Server 2013 中建立或編輯公用 SIP 同盟提供者</span><span class="sxs-lookup"><span data-stu-id="40b7b-102">Create or edit public SIP federated providers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="40b7b-103">_**主題上次修改日期：** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="40b7b-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="40b7b-104">公用立即訊息 (IM) 連線能力，讓組織中的使用者能夠使用 IM，與公用 IM 服務提供者所提供的 IM 服務使用者通訊，包括 Windows Live Messenger、Yahoo \! 和 AOL。</span><span class="sxs-lookup"><span data-stu-id="40b7b-104">Public instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by public IM service providers, including the Windows Live Messenger, Yahoo\!, and AOL.</span></span>

<span data-ttu-id="40b7b-105">Lync Server 2013 具有適用于北美線上、Windows Live 和 Yahoo 的公用提供者設定\!</span><span class="sxs-lookup"><span data-stu-id="40b7b-105">Lync Server 2013 has public provider configurations for America Online, Windows Live and Yahoo\!</span></span> <span data-ttu-id="40b7b-106">立即訊息的公用提供者設定。</span><span class="sxs-lookup"><span data-stu-id="40b7b-106">instant messaging.</span></span> <span data-ttu-id="40b7b-107">每個公用提供者都會使用提供者的 Edge Server 完整網域名稱，以及預設驗證層級 **[僅允許使用者與其連絡人清單上使用此提供者的人通訊]** 來設定。</span><span class="sxs-lookup"><span data-stu-id="40b7b-107">Each public provider is configured with the provider’s Edge server fully qualified domain name, and the default verification level **Allow users to communicate only with people on their Contacts list who use this provider**.</span></span>

<span data-ttu-id="40b7b-108">預設設定為不啟用任何公用提供者。</span><span class="sxs-lookup"><span data-stu-id="40b7b-108">As a default setting, none of the public providers are enabled.</span></span> <span data-ttu-id="40b7b-109">在啟用公用提供者之前，您應該先完成授權合約及佈建工作。</span><span class="sxs-lookup"><span data-stu-id="40b7b-109">You should complete license agreement and provisioning work before enabling the public providers.</span></span> <span data-ttu-id="40b7b-110">您可以在完成授權和佈建工作之前啟用提供者。</span><span class="sxs-lookup"><span data-stu-id="40b7b-110">You can enable the provider before completing the licensing and provisioning work.</span></span> <span data-ttu-id="40b7b-111">在必要工作完成之前，使用者將無法與這些提供者的連絡人通訊。</span><span class="sxs-lookup"><span data-stu-id="40b7b-111">Users will not be able to communicate with contacts on those providers until the pre-requisite work is completed.</span></span> <span data-ttu-id="40b7b-112">如需授權及布建公用提供者的詳細資訊，請參閱 [Configure 原則 to control public user access In Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="40b7b-112">For details on licensing and provisioning of public providers, see [Configure policies to control public user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md).</span></span>

<span data-ttu-id="40b7b-113">請使用下列程序來建立或編輯公用提供者：</span><span class="sxs-lookup"><span data-stu-id="40b7b-113">Use the following procedure to create or edit Public providers:</span></span>

<div>

## <a name="to-create-or-edit-public-providers"></a><span data-ttu-id="40b7b-114">建立或編輯公用提供者</span><span class="sxs-lookup"><span data-stu-id="40b7b-114">To create or edit public providers</span></span>

1.  <span data-ttu-id="40b7b-115">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="40b7b-115">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="40b7b-116">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="40b7b-116">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="40b7b-117">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="40b7b-117">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="40b7b-118">在左導覽列中，依序按一下 **[同盟和外部存取]** 和 **[SIP 同盟提供者]**。</span><span class="sxs-lookup"><span data-stu-id="40b7b-118">In the left navigation bar, click **Federation and External Access**, and then click **SIP Federated Providers**.</span></span>

4.  <span data-ttu-id="40b7b-119">如果您需要建立新的公用提供者，請依序按一下 **[新增]** 和 **[公用提供者]**。</span><span class="sxs-lookup"><span data-stu-id="40b7b-119">If you need to create a new Public provider, click **New** and then click **Public provider**.</span></span>

5.  <span data-ttu-id="40b7b-120">如果您需要編輯公用提供者清單中的項目，選取公用提供者，然後依序按一下 **[編輯]** 和 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="40b7b-120">If you need to edit an entry from the list of Public providers, select a public provider, click **Edit**, then click **Show details**.</span></span>

6.  <span data-ttu-id="40b7b-121">在 **[編輯 SIP 同盟提供者]** 頁面上，您可以鍵入或編輯下列設定：</span><span class="sxs-lookup"><span data-stu-id="40b7b-121">On the **Edit SIP Federated Provider** page, you can type or edit the following settings:</span></span>
    
      - <span data-ttu-id="40b7b-122">**啟用與此提供者**     的通訊選取此設定可讓 IM 使用此提供者的使用者。</span><span class="sxs-lookup"><span data-stu-id="40b7b-122">**Enable communications with this provider**   Selecting this setting enables IM with this provider’s users.</span></span>
    
      - <span data-ttu-id="40b7b-123">**提供者名稱：**    必要的屬性，請輸入提供者的名稱，因為它會反映在 SIP 同盟提供者的清單中。</span><span class="sxs-lookup"><span data-stu-id="40b7b-123">**Provider name:**   A required property, type the name of the provider as it will be reflected in the listing of SIP Federated Providers.</span></span>
    
      - <span data-ttu-id="40b7b-124">**Access Edge service (FQDN) ：**    必要的屬性，請輸入您要設定之提供者的 Access Edge service 的完整功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="40b7b-124">**Access Edge service (FQDN):**   A required property, type the fully qualified domain name of the Access Edge service of the provider that you are configuring.</span></span> <span data-ttu-id="40b7b-125">此資訊是以預設專案提供，只在公用提供者對公用提供者的 Access Edge service 的 FQDN 進行變更時，才應變更。</span><span class="sxs-lookup"><span data-stu-id="40b7b-125">This information is provided as a default item, and should only be changed if the public provider makes a change to the FQDN of the Access Edge service at the public provider.</span></span>
    
      - <span data-ttu-id="40b7b-126">**預設驗證層級：**    預設設定為 [**允許使用者與使用此提供者的連絡人清單上的人員通訊**]，會限制對您已接受的連絡人和連絡人清單中的連絡人進行通訊。</span><span class="sxs-lookup"><span data-stu-id="40b7b-126">**Default verification level:**   The default setting, **Allow users to communicate with people on their Contacts list who use this provider** will limit communication to contacts that you have accepted and are in your contact list.</span></span>
        
        <span data-ttu-id="40b7b-p105">選取 **[允許使用者與使用此提供者的所有人通訊]** 會移除您必須已收到並接受連絡人邀請的限制。此設定不會限制誰可以從公用提供者網路與您連絡。</span><span class="sxs-lookup"><span data-stu-id="40b7b-p105">Selecting **Allow users to communicate with everyone using this provider** removes the restriction that you must have received and accepted a contact invite. This setting does not limit who can contact you from the public provider’s network.</span></span>

7.  <span data-ttu-id="40b7b-129">完成設定之後，請按一下 **[認可]** 儲存，或按一下 **[取消]** 捨棄您的變更。</span><span class="sxs-lookup"><span data-stu-id="40b7b-129">When you are done configuring the settings, click **Commit** to save, or click **Cancel** to discard your changes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="40b7b-130">另請參閱</span><span class="sxs-lookup"><span data-stu-id="40b7b-130">See Also</span></span>


[<span data-ttu-id="40b7b-131">在 Lync Server 2013 中設定原則以控制公用使用者存取</span><span class="sxs-lookup"><span data-stu-id="40b7b-131">Configure policies to control public user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-public-user-access.md)  
[<span data-ttu-id="40b7b-132">在 Lync Server 2013 中啟用或停用同盟與公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="40b7b-132">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

