---
title: Lync Server 2013： 設定外部使用者存取的支援
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring support for external user access
ms:assetid: f8424f8c-f965-4414-8485-30f07e10214a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413051(v=OCS.15)
ms:contentKeyID: 48185874
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 94250ec0fbae3a7077e545eebdc848db3c370d19
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190896"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-support-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="75d46-102">在 Lync Server 2013 中設定外部使用者存取的支援</span><span class="sxs-lookup"><span data-stu-id="75d46-102">Configuring support for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="75d46-103">_**上次修改主題：** 2013年-02-21_</span><span class="sxs-lookup"><span data-stu-id="75d46-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="75d46-104">支援外部使用者的首要步驟，是部署 Edge Server 或 Edge 集區。</span><span class="sxs-lookup"><span data-stu-id="75d46-104">Deploying an Edge Server or Edge pool is the first step to supporting external users.</span></span> <span data-ttu-id="75d46-105">如需部署 Edge Server 的詳細資訊，請參閱部署文件中的[Deploying Lync Server 2013 中的外部使用者存取](lync-server-2013-deploying-external-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="75d46-105">For details about deploying Edge Servers, see [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation.</span></span> <span data-ttu-id="75d46-106">設定原則的考量重點在於了解原則和如何套用原則的優先順序。</span><span class="sxs-lookup"><span data-stu-id="75d46-106">An important consideration for the configuration of policies is to understand the precedence of policies and how the policies are applied.</span></span> <span data-ttu-id="75d46-107">Lync Server 在一個原則層級套用的原則設定可以覆寫其他原則層級套用的設定。</span><span class="sxs-lookup"><span data-stu-id="75d46-107">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="75d46-108">Lync Server 原則的優先順序為: （影響最大） 的使用者原則會覆寫網站原則，並再網站原則會覆寫全域原則 （最低影響）。</span><span class="sxs-lookup"><span data-stu-id="75d46-108">Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="75d46-109">這表示接近的原則設定為，這個物件會影響到該原則，它具有物件的多個影響。</span><span class="sxs-lookup"><span data-stu-id="75d46-109">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>

<span data-ttu-id="75d46-110">完成 Edge Server 或 Edge 集區的安裝後，您必須啟用的一種外部使用者存取您要提供，並設定外部存取的設定。</span><span class="sxs-lookup"><span data-stu-id="75d46-110">After completing the setup of an Edge Server or Edge pool, you must enable the types of external user access that you want to provide, and configure the settings for the external access.</span></span> <span data-ttu-id="75d46-111">在 Lync Server 2013 中，啟用及設定外部使用者存取和使用 Lync Server Control Panel、 Lync Server 管理命令介面或兩者的原則工作需求為基礎。</span><span class="sxs-lookup"><span data-stu-id="75d46-111">In Lync Server 2013, you enable and configure external user access and policies using the Lync Server Control Panel, the Lync Server Management Shell or both, based on the task requirements.</span></span>

<span data-ttu-id="75d46-112">若要支援外部使用者存取，您必須執行下列兩項動作：</span><span class="sxs-lookup"><span data-stu-id="75d46-112">To support external user access, you must do both of the following:</span></span>

  - <span data-ttu-id="75d46-113">**啟用支援的組織**   若要啟用支援的部署中的外部使用者存取，您可以啟用每一種要支援的外部存取。</span><span class="sxs-lookup"><span data-stu-id="75d46-113">**Enable support for your organization**   To enable support for external user access in your deployment, you enable each type of external access that you want to support.</span></span> <span data-ttu-id="75d46-114">您啟用及停用的編輯全域設定或建立和設定網站或使用者原則上或 Lync Server 控制台的 [**同盟和外部存取**] 群組中的 [**外部存取原則**] 頁面上使用 Lync Server 管理命令介面和相關聯的指令程式支援外部使用者存取。</span><span class="sxs-lookup"><span data-stu-id="75d46-114">You enable and disable support for external user access by editing the global settings or creating and configuring a site or user policy on the **External Access Policy** page in the **Federation and External Access** group of the Lync Server Control Panel or by using the Lync Server Management Shell and associated cmdlets.</span></span> <span data-ttu-id="75d46-115">[同盟和外部存取 cmdlet，在 Lync Server 2013 中](https://docs.microsoft.com/powershell/module/skype/)的主題中找到 Cmdlet 來管理**外部存取原則**。</span><span class="sxs-lookup"><span data-stu-id="75d46-115">Cmdlets for managing the **External Access Policy** are found in the topic [Federation and external access cmdlets in Lync Server 2013](https://docs.microsoft.com/powershell/module/skype/).</span></span> <span data-ttu-id="75d46-116">啟用外部存取的支援，會指定您執行 Lync Server Access Edge service 的伺服器支援與外部使用者與伺服器通訊。</span><span class="sxs-lookup"><span data-stu-id="75d46-116">Enabling support for external access specifies that your servers running the Lync Server Access Edge service support communications with external users and servers.</span></span> <span data-ttu-id="75d46-117">內部與外部使用者無法進行通訊時停用外部使用者存取，或原則有尚未設定為支援它。</span><span class="sxs-lookup"><span data-stu-id="75d46-117">Internal and external users cannot communicate while external user access is disabled or if policies have not yet been configured to support it.</span></span>

  - <span data-ttu-id="75d46-118">**設定並指派一或多個原則**   若要支援外部使用者存取，您可以設定原則以滿足需求，包括：</span><span class="sxs-lookup"><span data-stu-id="75d46-118">**Configure and assign one or more policies**   To support external user access, you configure policies to address requirements that include:</span></span>
    
      - <span data-ttu-id="75d46-119">**外部存取原則**   建立網站或使用者範圍 （全域原則預設會存在，且沒有啟用的設定）。</span><span class="sxs-lookup"><span data-stu-id="75d46-119">**External access policies**   Created with either a site or user scope (a global policy exists by default and has no enabled settings).</span></span> <span data-ttu-id="75d46-120">建立並設定原則以控制的一或多個類型的外部使用者存取，包括，同盟的使用者存取 （包括，如果選取，同盟的 XMPP 網域） 使用遠端使用者的使用者存取權和支援的公用 IM 服務提供者。</span><span class="sxs-lookup"><span data-stu-id="75d46-120">You create and configure policies to control the use of one or more types of external user access, including, federated user access (including, if selected, federated XMPP domains)remote users user access, and supported public IM service providers.</span></span> <span data-ttu-id="75d46-121">您使用的全域原則或一或多個行政規定必須建立的網站與使用者原則，在 [**同盟和外部存取**] 群組中的**外部存取原則**] 頁面上的 Lync Server Control Panel 中設定外部的原則。</span><span class="sxs-lookup"><span data-stu-id="75d46-121">You configure external policies in Lync Server Control Panel using the global policy or one or more administratively created site and user policies, on the **External Access Policy** page in the **Federation and External Access** group.</span></span> <span data-ttu-id="75d46-122">全域原則無法刪除。</span><span class="sxs-lookup"><span data-stu-id="75d46-122">The global policy cannot be deleted.</span></span> <span data-ttu-id="75d46-123">您建立及設定您想要用來限制對特定網站或使用者的外部使用者存取任何網站與使用者原則。</span><span class="sxs-lookup"><span data-stu-id="75d46-123">You create and configure any site and user policies that you want to use to limit external user access for specific sites or users.</span></span> <span data-ttu-id="75d46-124">自動指派全域與網站原則。</span><span class="sxs-lookup"><span data-stu-id="75d46-124">Global and site policies are automatically assigned.</span></span> <span data-ttu-id="75d46-125">如果您建立及設定使用者原則，您必須再將其指派給特定使用者使用 Lync Server 控制台，在 [**使用者**] 頁面上的 [使用者設定] 頁面。</span><span class="sxs-lookup"><span data-stu-id="75d46-125">If you create and configure a user policy, you must then assign it to the specific users by using the user configuration page in the Lync Server Control Panel on the **Users** page.</span></span> <span data-ttu-id="75d46-126">尋找您想要套用至將原則指派此原則的使用者。</span><span class="sxs-lookup"><span data-stu-id="75d46-126">Find the user or users that you want this policy to apply to and assign the policy.</span></span> <span data-ttu-id="75d46-127">您想要套用。</span><span class="sxs-lookup"><span data-stu-id="75d46-127">to whom you want it to apply.</span></span> <span data-ttu-id="75d46-128">若要設定的使用者原則指派給使用者，請參閱[指派給 Lync Server 2013 中啟用 Lync 功能之使用者的外部使用者存取原則](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)。</span><span class="sxs-lookup"><span data-stu-id="75d46-128">To assign a configured user policy to a user, see [Assign an external user access policy to a Lync enabled user in Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md).</span></span> <span data-ttu-id="75d46-129">每個外部使用者存取原則可支援一或多個項目： 遠端使用者存取，SIP 同盟使用者存取、 XMPP 同盟使用者存取和公用 IM 連線。</span><span class="sxs-lookup"><span data-stu-id="75d46-129">Each external user access policy can support one or more of the following: remote user access, SIP federated user access, XMPP federated user access and public IM connectivity.</span></span>
    
      - <span data-ttu-id="75d46-130">**會議原則**   建立並設定原則以控制您的組織，包括您組織中的哪些使用者可以邀請匿名使用者加入他們所主控的會議中的會議。</span><span class="sxs-lookup"><span data-stu-id="75d46-130">**Conferencing policies**   You create and configure policies to control conferencing in your organization, including which users in your organization can invite anonymous users to conferences that they host.</span></span> <span data-ttu-id="75d46-131">在 [Lync Server Control Panel **會議**] 頁面會在全域、 網站與使用者範圍的原則設定可控制的實際的會議設定。</span><span class="sxs-lookup"><span data-stu-id="75d46-131">On the Lync Server Control Panel **Conferencing** page are policy settings at the global, site and user scope that control settings for the actual conferences.</span></span> <span data-ttu-id="75d46-132">如需詳細資訊，請參閱[Managing 會議和 Lync Server 2013 中的會議](lync-server-2013-managing-meetings-and-conferences.md)。</span><span class="sxs-lookup"><span data-stu-id="75d46-132">For details, see [Managing meetings and conferences in Lync Server 2013](lync-server-2013-managing-meetings-and-conferences.md).</span></span> <span data-ttu-id="75d46-133">讓匿名使用者在會議、 遠端使用者和在 [ **Access Edge 設定**] 頁面上的同盟的使用者。</span><span class="sxs-lookup"><span data-stu-id="75d46-133">You enable anonymous users for conferencing, remote users and federated users on the **Access Edge Configuration** page.</span></span> <span data-ttu-id="75d46-134">**Access Edge 設定**原則是全域範圍中。</span><span class="sxs-lookup"><span data-stu-id="75d46-134">The policy on the **Access Edge Configuration** is global in scope.</span></span> <span data-ttu-id="75d46-135">沒有定義網站或使用者原則的選項。</span><span class="sxs-lookup"><span data-stu-id="75d46-135">There are no options to define a site or user policy.</span></span> <span data-ttu-id="75d46-136">範圍被控制的**外部存取原則**] 頁面上，透過全域、 網站或使用者原則設定。</span><span class="sxs-lookup"><span data-stu-id="75d46-136">The scope is controlled on the **External Access Policy** page through the use of global, site, or user policy settings.</span></span>
        
        <span data-ttu-id="75d46-137">例如，如果您想要允許使用者建立、 邀請和管理會議與遠端使用者，您必須**啟用與遠端使用者的通訊**上設定**外部存取原則**全域、 網站或使用者原則，並**啟用與遠端使用者的通訊** **Access Edge 設定**] 頁面上。</span><span class="sxs-lookup"><span data-stu-id="75d46-137">For example, if you want to allow users to create, invite and manage conferencing with remote users, you must set **Enable communications with remote users** on the **External Access Policy** global, site or user policy, and **Enable Communications with remote users** on the **Access Edge Configuration** page.</span></span> <span data-ttu-id="75d46-138">同樣地，若要允許會議與匿名使用者或同盟協力廠商，您必須具有的定義關聯性 （例如設定同盟的 SIP 網域和提供者 – XMPP 同盟不支援會議），在**外部存取原則**全域、 網站或使用者原則設定**啟用與公用使用者的通訊**，並**啟用與同盟使用者的通訊**。</span><span class="sxs-lookup"><span data-stu-id="75d46-138">Similarly, to allow conferencing with anonymous users or federated partners that you have a defined relationship with (such as configured federated SIP domains and providers – XMPP federation does not support conferencing), you set **Enable communications with public users** and **Enable communications with federated users** in the **External Access Policy** global, site or user policy.</span></span> <span data-ttu-id="75d46-139">然後選取 [ **Access Edge 設定**」 頁面上**啟用會議的匿名使用者存取**，並**啟用同盟和公用 IM 連線**的附贈全域原則設定。</span><span class="sxs-lookup"><span data-stu-id="75d46-139">You then select complimentary global policy settings **Enable anonymous user access to conferences** and **Enable federated and public IM connectivity** on the **Access Edge Configuration** page.</span></span>

<span data-ttu-id="75d46-p107">您可以設定外部使用者存取設定，包括任何您要用以控制外部使用者存取的原則，即使您並未啟用組織的外部使用者存取亦然。但只有在您啟用組織的外部使用者存取後，您所設定的原則與其他設定才會生效。當外部使用者存取停用，或未設定外部使用者存取原則加以支援時，外部使用者將無法與您組織的使用者通訊。</span><span class="sxs-lookup"><span data-stu-id="75d46-p107">You can configure external user access settings, including any policies that you want to use to control external user access, even if you have not enabled external user access for your organization. However, the policies and other settings that you configure are in effect only when you have external user access enabled for your organization. External users cannot communicate with users of your organization when external user access is disabled or if no external user access policies are configured to support it.</span></span>

<span data-ttu-id="75d46-p108">您的 Edge 部署會根據您設定 Edge 支援的方式，來驗證外部使用者 (但匿名使用者除外，匿名使用者是由當您建立會議並邀請參與者時，所傳送給匿名參與者的會議 ID 及密碼金鑰加以驗證) 的類型及控制存取。若要控制通訊，您可以設定一或多項原則並設定其他設定，以定義您部署內外之使用者彼此通訊的方式。這些原則及設定包括外部使用者存取的預設全域原則，以及您可以建立並設定以針對特定網站或使用者啟用一或多種外部使用者存取類型的網站與使用者原則。</span><span class="sxs-lookup"><span data-stu-id="75d46-p108">Your edge deployment authenticates the types of external users (except for anonymous users, who are authenticated by the conference ID and a passkey that is sent to the anonymous participant when you create the conference and invite participants) and controls access based on how you configure your edge support. In order to control communications, you can configure one or more policies and configure settings that define how users inside and outside your deployment communicate with each other. The policies and settings include the default global policy for external user access, in addition to site and user policies that you can create and configure to enable one or more types of external user access for specific sites or users.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="75d46-146">本章節內容</span><span class="sxs-lookup"><span data-stu-id="75d46-146">In This Section</span></span>

  - [<span data-ttu-id="75d46-147">設定原則以控制在 Lync Server 2013 中的遠端使用者存取</span><span class="sxs-lookup"><span data-stu-id="75d46-147">Configure policies to control remote user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-remote-user-access.md)

  - [<span data-ttu-id="75d46-148">啟用或停用 Lync Server 2013 中的遠端使用者存取</span><span class="sxs-lookup"><span data-stu-id="75d46-148">Enable or disable remote user access in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-remote-user-access.md)

  - [<span data-ttu-id="75d46-149">啟用或停用 Lync Server 2013 中的匿名使用者存取</span><span class="sxs-lookup"><span data-stu-id="75d46-149">Enable or disable anonymous user access in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-anonymous-user-access.md)

  - [<span data-ttu-id="75d46-150">指派會議原則以支援匿名使用者在 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75d46-150">Assign conferencing policies to support anonymous users in Lync Server 2013</span></span>](lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

