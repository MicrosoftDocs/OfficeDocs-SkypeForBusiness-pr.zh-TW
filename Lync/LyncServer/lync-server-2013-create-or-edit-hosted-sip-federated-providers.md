---
title: Lync Server 2013：建立或編輯主控的 SIP 同盟提供者
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or edit hosted SIP federated providers
ms:assetid: 0dd6dcb6-a88d-46b8-9c96-b35967309bcd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552445(v=OCS.15)
ms:contentKeyID: 48679556
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3bbdc22f2e877d7dafc8f52506d77312730ab428
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981840"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-edit-hosted-sip-federated-providers-lync-server-2013"></a><span data-ttu-id="4f5a6-102">建立或編輯主控的 SIP 同盟提供者 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4f5a6-102">Create or edit hosted SIP federated providers Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4f5a6-103">_**主題上次修改日期：** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="4f5a6-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="4f5a6-104">宿主提供者立即訊息（IM）連線功能可讓貴組織中的使用者使用 IM 與託管提供者所提供的 IM 服務使用者通訊，包括 Microsoft Office 365 和 Lync Online。</span><span class="sxs-lookup"><span data-stu-id="4f5a6-104">Hosted provider instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by hosted providers, including the Microsoft Office 365 and Lync Online.</span></span>

<span data-ttu-id="4f5a6-105">每個託管提供者都是以提供者的 Edge 伺服器的完整功能變數名稱進行設定，而且預設驗證層級**可讓使用者只與他們的連絡人清單中使用這個提供者的人通訊**。</span><span class="sxs-lookup"><span data-stu-id="4f5a6-105">Each hosted provider is configured with the provider’s Edge server fully qualified domain name, and the default verification level **Allow users to communicate only with people on their Contacts list who use this provider**.</span></span>

<span data-ttu-id="4f5a6-106">使用下列程式來建立或編輯託管提供者：</span><span class="sxs-lookup"><span data-stu-id="4f5a6-106">Use the following procedure to create or edit Hosted providers:</span></span>

<div>

## <a name="to-create-or-edit-hosted-providers"></a><span data-ttu-id="4f5a6-107">建立或編輯託管提供者</span><span class="sxs-lookup"><span data-stu-id="4f5a6-107">To create or edit hosted providers</span></span>

1.  <span data-ttu-id="4f5a6-108">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="4f5a6-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4f5a6-109">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="4f5a6-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="4f5a6-110">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="4f5a6-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="4f5a6-111">在左側導覽列中，按一下 [**同盟與外部存取**]，然後按一下 [ **SIP 同盟提供者**]。</span><span class="sxs-lookup"><span data-stu-id="4f5a6-111">In the left navigation bar, click **Federation and External Access**, and then click **SIP Federated Providers**.</span></span>

4.  <span data-ttu-id="4f5a6-112">如果您需要建立新的託管提供者，請按一下 [**新增**]，然後按一下 [**託管提供者**]。</span><span class="sxs-lookup"><span data-stu-id="4f5a6-112">If you need to create a new Hosted provider, click **New** and then click **Hosted provider**.</span></span>

5.  <span data-ttu-id="4f5a6-113">如果您需要編輯託管提供者清單中的專案，請選取託管提供者，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="4f5a6-113">If you need to edit an entry from the list of Hosted providers, select a hosted provider, click **Edit**, then click **Show details**.</span></span>

6.  <span data-ttu-id="4f5a6-114">在 [**編輯 SIP 聯盟提供者**] 頁面上，您可以輸入或編輯下列設定：</span><span class="sxs-lookup"><span data-stu-id="4f5a6-114">On the **Edit SIP Federated Provider** page, you can type or edit the following settings:</span></span>
    
      - <span data-ttu-id="4f5a6-115">**啟用與此提供者**   的通訊選取此設定，即可與此提供者的使用者進行通訊。</span><span class="sxs-lookup"><span data-stu-id="4f5a6-115">**Enable communications with this provider**   Selecting this setting enables communications with this provider’s users.</span></span>
    
      - <span data-ttu-id="4f5a6-116">**提供者名稱：**   required 屬性，請輸入提供者的名稱，因為它會反映在 SIP 同盟提供者清單中。</span><span class="sxs-lookup"><span data-stu-id="4f5a6-116">**Provider name:**   A required property, type the name of the provider as it will be reflected in the listing of SIP Federated Providers.</span></span>
    
      - <span data-ttu-id="4f5a6-117">**[存取邊緣服務（FQDN）]：**   [必要] 屬性，請輸入您要設定之託管提供者的存取邊緣服務的完整功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="4f5a6-117">**Access Edge service (FQDN):**   A required property, type the fully qualified domain name of the Access Edge service of the hosted provider that you are configuring.</span></span> <span data-ttu-id="4f5a6-118">此資訊應該由託管提供者提供，而且只有在託管提供者對託管提供者的存取邊緣服務的 FQDN 進行變更時，才應進行變更。</span><span class="sxs-lookup"><span data-stu-id="4f5a6-118">This information should be provided by the hosted provider, and should only be changed if the hosted provider makes a change to the FQDN of the Access Edge service at the hosted provider.</span></span>
    
      - <span data-ttu-id="4f5a6-119">**預設驗證階層：**   預設設定是 [**允許使用者與連絡人清單中的人員通訊]，使用這個提供者**時，會將通訊限制在您已接受的連絡人，並在您的連絡人清單中。</span><span class="sxs-lookup"><span data-stu-id="4f5a6-119">**Default verification level:**   The default setting, **Allow users to communicate with people on their Contacts list who use this provider** will limit communication to contacts that you have accepted and are in your contact list.</span></span>
        
        <span data-ttu-id="4f5a6-120">選取 [**允許使用者與使用這個提供者的所有人通訊**]，就會移除您必須收到並接受連絡人邀請的限制。</span><span class="sxs-lookup"><span data-stu-id="4f5a6-120">Selecting **Allow users to communicate with everyone using this provider** removes the restriction that you must have received and accepted a contact invite.</span></span> <span data-ttu-id="4f5a6-121">此設定不會限制誰能從主機託管提供者的網路與您聯繫。</span><span class="sxs-lookup"><span data-stu-id="4f5a6-121">This setting does not limit who can contact you from the hosted provider’s network.</span></span>

7.  <span data-ttu-id="4f5a6-122">設定完畢後，請按一下 [**認可**] 來儲存，或按一下 [**取消**] 放棄您的變更。</span><span class="sxs-lookup"><span data-stu-id="4f5a6-122">When you are done configuring the settings, click **Commit** to save, or click **Cancel** to discard your changes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4f5a6-123">請參閱</span><span class="sxs-lookup"><span data-stu-id="4f5a6-123">See Also</span></span>


[<span data-ttu-id="4f5a6-124">在 Lync Server 2013 中設定原則以控制公用使用者存取</span><span class="sxs-lookup"><span data-stu-id="4f5a6-124">Configure policies to control public user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-public-user-access.md)  
[<span data-ttu-id="4f5a6-125">在 Lync Server 2013 中啟用或停用同盟與公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="4f5a6-125">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

