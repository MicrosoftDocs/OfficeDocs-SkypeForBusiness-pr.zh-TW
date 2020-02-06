---
title: 在商務用 Skype 中規劃 Exchange 整合訊息整合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7b22002b-7e6a-4d3f-b600-a733a7e3778a
description: 摘要：在規劃將商務用 Skype 伺服器與 Exchange 2013 或2016整合時，請複習本主題。
ms.openlocfilehash: 1ae6ad10f1e817b9ace0240c79d09251a23dd61c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815861"
---
# <a name="plan-for-exchange-unified-messaging-integration-in-skype-for-business"></a><span data-ttu-id="adb31-103">在商務用 Skype 中規劃 Exchange 整合訊息整合</span><span class="sxs-lookup"><span data-stu-id="adb31-103">Plan for Exchange Unified Messaging integration in Skype for Business</span></span>

<span data-ttu-id="adb31-104">**摘要：** 在規劃將商務用 Skype Server 與 Exchange 2013 或2016整合時，請複習本主題。</span><span class="sxs-lookup"><span data-stu-id="adb31-104">**Summary:** Review this topic while planning to integrate Skype for Business Server with Exchange 2013 or 2016.</span></span>

<span data-ttu-id="adb31-105">商務用 Skype 伺服器支援與 Exchange 整合通訊（UM）整合，以將語音訊息和電子郵件訊息結合到單一訊息基礎結構。</span><span class="sxs-lookup"><span data-stu-id="adb31-105">Skype for Business Server supports integration with Exchange Unified Messaging (UM) for combining voice messaging and email messaging into a single messaging infrastructure.</span></span> <span data-ttu-id="adb31-106">在 Exchange 中，Exchange 整合通訊（UM）是您可以安裝及設定的數個 Exchange 伺服器角色之一。</span><span class="sxs-lookup"><span data-stu-id="adb31-106">In Exchange, Exchange Unified Messaging (UM) is one of several Exchange server roles that you can install and configure.</span></span>

<span data-ttu-id="adb31-107">在 Microsoft Exchange Server 2013 和2016中，Exchange UM 在 Exchange 信箱伺服器上以服務的方式執行。</span><span class="sxs-lookup"><span data-stu-id="adb31-107">In Microsoft Exchange Server 2013 and 2016, Exchange UM runs as a service on an Exchange Mailbox server.</span></span> <span data-ttu-id="adb31-108">針對商務用 Skype Server 企業版語音部署，整合的訊息結合了語音訊息和電子郵件訊息，以便讓使用者能夠從電話（Outlook 語音存取）或電腦存取單一商店。</span><span class="sxs-lookup"><span data-stu-id="adb31-108">For Skype for Business Server Enterprise Voice deployments, Unified Messaging combines voice messaging and email messaging into a single store that users can access from a telephone (Outlook Voice Access) or a computer.</span></span> <span data-ttu-id="adb31-109">整合通訊與商務用 Skype 伺服器共同作業，為企業語音的使用者提供呼叫應答、Outlook 語音存取及自動助理服務。</span><span class="sxs-lookup"><span data-stu-id="adb31-109">Unified Messaging and Skype for Business Server work together to provide call answering, Outlook Voice Access, and auto-attendant services to users of Enterprise Voice.</span></span>

> [!NOTE]
> <span data-ttu-id="adb31-110">當您將商務用 Skype 2019 與 Exchange 2013 或 Exchange 2016 整合時，Exchange UM 仍可在商務用 Skype Server 2019 中使用。</span><span class="sxs-lookup"><span data-stu-id="adb31-110">Exchange UM remains available in Skype for Business Server 2019 when you integrate Skype for Business 2019 with Exchange 2013 or Exchange 2016.</span></span> <span data-ttu-id="adb31-111">由於 Exchange 2019 中的支援變更，因此需要取消 Exchange UM 整合，以取代雲端語音信箱和雲端自動語音應答功能。</span><span class="sxs-lookup"><span data-stu-id="adb31-111">Due to changes in support in Exchange 2019, Exchange UM integration is being de-emphasized in favor of Cloud Voicemail and Cloud Auto Attendant features.</span></span>  <span data-ttu-id="adb31-112">如需詳細資訊，請參閱[規劃雲端語音信箱服務](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md)並[規劃商務用 Skype Server 和 Exchange server 遷移](../../../sfbhybrid/hybrid/plan-um-migration.md)。</span><span class="sxs-lookup"><span data-stu-id="adb31-112">See [Plan Cloud Voicemail service](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) and [Plan for Skype for Business Server and Exchange Server migration](../../../sfbhybrid/hybrid/plan-um-migration.md) for more information.</span></span>


<span data-ttu-id="adb31-113">若要在內部部署 Exchange UM 部署中支援這些功能，您必須執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="adb31-113">For these features to be supported in an on-premises Exchange UM deployment, you must be running one of the following:</span></span>

- <span data-ttu-id="adb31-114">Microsoft Exchange Server 2010 或最新 service pack （僅適用于商務用 Skype Server 2015）</span><span class="sxs-lookup"><span data-stu-id="adb31-114">Microsoft Exchange Server 2010 or latest service pack (Skype for Business Server 2015 only)</span></span>
- <span data-ttu-id="adb31-115">Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="adb31-115">Microsoft Exchange Server 2013</span></span>
- <span data-ttu-id="adb31-116">Microsoft Exchange Server 2016</span><span class="sxs-lookup"><span data-stu-id="adb31-116">Microsoft Exchange Server 2016</span></span>

> [!NOTE]
> <span data-ttu-id="adb31-117">在商務用 Skype Server 2019 中，Exchange 整合的郵件功能已不再提供，因為它會使用電話系統來錄製語音信箱訊息，然後將錄製保留在使用者的 Exchange 信箱中。</span><span class="sxs-lookup"><span data-stu-id="adb31-117">Exchange Unified Messaging as previously known is no longer available in Skype for Business Server 2019, which uses Phone System to record voicemail messages and then leave the recording in a user's Exchange mailbox.</span></span> <span data-ttu-id="adb31-118">如需詳細資訊，請參閱[規劃雲端語音信箱服務](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md)。</span><span class="sxs-lookup"><span data-stu-id="adb31-118">See [Plan Cloud Voicemail service](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) for more information.</span></span>

## <a name="features-of-integrated-unified-messaging-and-skype-for-business-server"></a><span data-ttu-id="adb31-119">整合式整合訊息及商務用 Skype 伺服器的功能</span><span class="sxs-lookup"><span data-stu-id="adb31-119">Features of integrated Unified Messaging and Skype for Business Server</span></span>

<span data-ttu-id="adb31-120">商務用 Skype Server、企業語音使用 Exchange 整合訊息（UM）基礎結構來提供通話應答、呼叫通知、語音存取（包括語音信箱）及自動助理服務。</span><span class="sxs-lookup"><span data-stu-id="adb31-120">Skype for Business Server, Enterprise Voice uses the Exchange Unified Messaging (UM) infrastructure to provide call answering, call notification, voice access (including voice mail), and auto-attendant services.</span></span>

- <span data-ttu-id="adb31-121">**呼叫應答**[通話接聽] 是代表不接聽或忙碌通話的使用者接收語音訊息。</span><span class="sxs-lookup"><span data-stu-id="adb31-121">**Call Answering** Call answering is the receiving of voice messages on behalf of users whose calls are not answered or are busy.</span></span> <span data-ttu-id="adb31-122">它包括播放個人問候語、記錄郵件，以及提交郵件以傳送到使用者的信箱，而該信箱會儲存在 Exchange 信箱伺服器上。</span><span class="sxs-lookup"><span data-stu-id="adb31-122">It includes playing a personal greeting, recording a message, and submitting the message to be queued for delivery to the user's mailbox, which is stored on the Exchange mailbox server.</span></span>

    <span data-ttu-id="adb31-123">如果來電者離開郵件，郵件會傳送到使用者的 [收件匣]。</span><span class="sxs-lookup"><span data-stu-id="adb31-123">If a caller leaves a message, the message is routed to the user's Inbox.</span></span> <span data-ttu-id="adb31-124">如果來電者選擇不留下訊息，就會將未接來電通知儲存在使用者的信箱中。</span><span class="sxs-lookup"><span data-stu-id="adb31-124">If a caller chooses not to leave a message, a missed call notification is stored in the user's mailbox.</span></span> <span data-ttu-id="adb31-125">然後，使用者就可以使用 Microsoft Outlook 的訊息與共同作業用戶端、Outlook Web Access、Exchange ActiveSync 技術或 Outlook 語音存取來存取收件匣。</span><span class="sxs-lookup"><span data-stu-id="adb31-125">Users can then access their Inbox by using the Microsoft Outlook messaging and collaboration client, Outlook Web Access, the Exchange ActiveSync technology, or Outlook Voice Access.</span></span> <span data-ttu-id="adb31-126">通話的主旨與優先順序可以以與電子郵件類似的方式顯示。</span><span class="sxs-lookup"><span data-stu-id="adb31-126">The subject and priority of calls can be displayed in a way similar to that of email.</span></span>

- <span data-ttu-id="adb31-127">**Outlook 語音存取**Outlook 語音存取可讓企業語音使用者存取除語音信箱以外的 [Exchange 收件匣]，包括來自電話介面的電子郵件、行事曆和連絡人。</span><span class="sxs-lookup"><span data-stu-id="adb31-127">**Outlook Voice Access** Outlook Voice Access enables an Enterprise Voice user to access not just voice mail, but also the Exchange inbox, including email, calendar, and contacts from a telephony interface.</span></span> <span data-ttu-id="adb31-128">訂閱者存取號碼是由 Exchange UM 管理員指派。</span><span class="sxs-lookup"><span data-stu-id="adb31-128">The subscriber access number is assigned by an Exchange UM administrator.</span></span>

- <span data-ttu-id="adb31-129">**自動**語音應答自動語音應答是一種 Exchange UM 功能，可讓您用來設定使用者可以撥打電話給公司代表的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="adb31-129">**Auto attendant** Auto attendant is an Exchange UM feature that can be used to configure a phone number that outside users can dial to reach company representatives.</span></span> <span data-ttu-id="adb31-130">特別是，它提供一系列的語音提示，協助外部呼叫者流覽功能表系統。</span><span class="sxs-lookup"><span data-stu-id="adb31-130">In particular, it provides a series of voice prompts that assist an external caller in navigating a menu system.</span></span> <span data-ttu-id="adb31-131">可用選項的清單是由 Exchange UM 管理員在 Exchange UM 伺服器上設定。</span><span class="sxs-lookup"><span data-stu-id="adb31-131">The list of available options is configured on the Exchange UM server by the Exchange UM administrator.</span></span>

- <span data-ttu-id="adb31-132">**傳真服務**Exchange UM 包括 [傳真] 功能，可讓使用者在其 Exchange 信箱中接收傳入的傳真。</span><span class="sxs-lookup"><span data-stu-id="adb31-132">**Fax Services** Exchange UM includes fax features, which enable users to receive incoming faxes in their Exchange mailboxes.</span></span> <span data-ttu-id="adb31-133">如需詳細資訊，請參閱 Microsoft Exchange Server 檔中的[統一訊息](https://go.microsoft.com/fwlink/p/?linkId=135652)。</span><span class="sxs-lookup"><span data-stu-id="adb31-133">For details, see [Unified Messaging](https://go.microsoft.com/fwlink/p/?linkId=135652) in the Microsoft Exchange Server documentation.</span></span>

    > [!NOTE]
    > <span data-ttu-id="adb31-134">Exchange UM 伺服器提供的傳真服務無法在與 Microsoft Exchange Server 2010 2010 （含最新 service pack、Exchange 2013 或 Exchange 2016）整合的商務用 Skype Server 部署中使用。</span><span class="sxs-lookup"><span data-stu-id="adb31-134">Fax services provided by the Exchange UM server are not available in Skype for Business Server deployments that are integrated with Microsoft Exchange Server 2010, Exchange 2010 with the latest service pack, Exchange 2013, or Exchange 2016.</span></span>

## <a name="components-and-topologies-for-on-premises-unified-messaging-in-skype-for-business-server"></a><span data-ttu-id="adb31-135">商務用 Skype Server 中內部部署整合訊息的元件與拓撲</span><span class="sxs-lookup"><span data-stu-id="adb31-135">Components and topologies for on-premises Unified Messaging in Skype for Business Server</span></span>

### <a name="exchange-server-components"></a><span data-ttu-id="adb31-136">Exchange Server 元件</span><span class="sxs-lookup"><span data-stu-id="adb31-136">Exchange Server Components</span></span>

<span data-ttu-id="adb31-137">若要提供在您組織中[的整合式整合訊息與商務用 Skype Server 的功能](#features-of-integrated-unified-messaging-and-skype-for-business-server)中所說明的 Exchange UM 功能及服務，您必須部署 Microsoft Exchange 信箱伺服器和用戶端存取伺服器，以存放使用者信箱，並提供電子郵件和語音信箱的單一儲存位置。</span><span class="sxs-lookup"><span data-stu-id="adb31-137">To provide the Exchange UM features and services described in [Features of integrated Unified Messaging and Skype for Business Server](#features-of-integrated-unified-messaging-and-skype-for-business-server) to Enterprise Voice users in your organization, you must deploy an Microsoft Exchange Mailbox server and Client Access server, which hosts user mailboxes and provides a single storage location for email and voice mail.</span></span> <span data-ttu-id="adb31-138">Exchange UM 在 Exchange 信箱和用戶端存取伺服器上以服務的方式執行。</span><span class="sxs-lookup"><span data-stu-id="adb31-138">Exchange UM runs as a service on Exchange Mailbox and Client Access servers.</span></span>

<span data-ttu-id="adb31-139">如需 Microsoft Exchange Server 2010 中 Exchange UM 元件的詳細資訊，請參閱[部署內部部署 EXCHANGE UM，以提供 Lync Server 2013 預覽語音信箱](https://technet.microsoft.com/library/9673bd73-a3a3-425d-870f-04d801c6d0d5.aspx)。</span><span class="sxs-lookup"><span data-stu-id="adb31-139">For details about Exchange UM components in Microsoft Exchange Server 2010, see [Deploying On-Premises Exchange UM to Provide Lync Server 2013 Preview Voice Mail](https://technet.microsoft.com/library/9673bd73-a3a3-425d-870f-04d801c6d0d5.aspx) .</span></span>

### <a name="supported-topologies"></a><span data-ttu-id="adb31-140">支援的拓撲</span><span class="sxs-lookup"><span data-stu-id="adb31-140">Supported Topologies</span></span>

<span data-ttu-id="adb31-141">您可以在同一個目錄林中或多個目錄林中部署商務用 Skype Server 和 Exchange 整合通訊（UM）。</span><span class="sxs-lookup"><span data-stu-id="adb31-141">You can deploy Skype for Business Server and Exchange Unified Messaging (UM) in the same forest or multiple forests.</span></span> <span data-ttu-id="adb31-142">如果部署跨越多個目錄林，您必須針對每個 Exchange UM 目錄林執行 Exchange 整合步驟。</span><span class="sxs-lookup"><span data-stu-id="adb31-142">If the deployment spans multiple forests, you must perform the Exchange integration steps for each Exchange UM forest.</span></span> <span data-ttu-id="adb31-143">此外，您必須將每個 Microsoft Exchange 林設定為信任商務用 Skype Server 林與商務用 Skype 伺服器林，以信任每個 Exchange UM 林。</span><span class="sxs-lookup"><span data-stu-id="adb31-143">Furthermore, you must configure each Microsoft Exchange forest to trust the Skype for Business Server forest and the Skype for Business Server forest to trust each Exchange UM forest.</span></span> <span data-ttu-id="adb31-144">除了此目錄林信任之外，所有使用者的 Exchange UM 設定都必須在商務用 Skype Server 林中的使用者物件上設定。</span><span class="sxs-lookup"><span data-stu-id="adb31-144">In addition to this forest trust, the Exchange UM settings for all users must be set on the user objects in the Skype for Business Server forest.</span></span>

<span data-ttu-id="adb31-145">商務用 Skype 伺服器支援適用于 Exchange UM 整合的下列拓朴：</span><span class="sxs-lookup"><span data-stu-id="adb31-145">Skype for Business Server supports the following topologies for Exchange UM integration:</span></span>

- <span data-ttu-id="adb31-146">單一目錄林</span><span class="sxs-lookup"><span data-stu-id="adb31-146">Single forest</span></span>

- <span data-ttu-id="adb31-147">單一網域（也就是單一網域的單一林）。</span><span class="sxs-lookup"><span data-stu-id="adb31-147">Single domain (that is, a single forest with a single domain).</span></span> <span data-ttu-id="adb31-148">商務用 Skype Server、Microsoft Exchange 和使用者都位於同一個網域中。</span><span class="sxs-lookup"><span data-stu-id="adb31-148">Skype for Business Server, Microsoft Exchange, and users all reside in the same domain.</span></span>

- <span data-ttu-id="adb31-149">多個網域（也就是包含一或多個子域的根網域）。</span><span class="sxs-lookup"><span data-stu-id="adb31-149">Multiple domain (that is, a root domain with one or more child domains).</span></span> <span data-ttu-id="adb31-150">商務用 Skype Server 及 Microsoft Exchange 伺服器會從您建立使用者的網域部署在不同的網域中。</span><span class="sxs-lookup"><span data-stu-id="adb31-150">Skype for Business Server, and Microsoft Exchange servers are deployed in different domains from the domain where you create users.</span></span> <span data-ttu-id="adb31-151">Exchange UM 伺服器可以在他們支援的商務用 Skype 伺服器池以外的不同網域中部署。</span><span class="sxs-lookup"><span data-stu-id="adb31-151">Exchange UM servers can be deployed in different domains from the Skype for Business Server pool they support.</span></span>

- <span data-ttu-id="adb31-152">多個目錄林（也就是資原始目錄林）。</span><span class="sxs-lookup"><span data-stu-id="adb31-152">Multiple forest (that is, resource forest).</span></span> <span data-ttu-id="adb31-153">商務用 Skype 伺服器會部署在單一目錄林中，然後使用者會分佈在多個目錄林。</span><span class="sxs-lookup"><span data-stu-id="adb31-153">Skype for Business Server is deployed in a single forest, and then users are distributed across multiple forests.</span></span> <span data-ttu-id="adb31-154">使用者的 Exchange UM 屬性必須複製到商務用 Skype Server 林。</span><span class="sxs-lookup"><span data-stu-id="adb31-154">The users' Exchange UM attributes must be replicated over to the Skype for Business Server forest.</span></span>

    > [!NOTE]
    > <span data-ttu-id="adb31-155">Exchange 可以在多個林中部署。</span><span class="sxs-lookup"><span data-stu-id="adb31-155">Exchange can be deployed in multiple forests.</span></span> <span data-ttu-id="adb31-156">每個 Exchange 組織都可以為其使用者提供 Exchange UM，或者 Exchange UM 可以部署在與商務用 Skype Server 相同的林中。</span><span class="sxs-lookup"><span data-stu-id="adb31-156">Each Exchange organization can provide Exchange UM to its users, or Exchange UM can be deployed in the same forest as Skype for Business Server.</span></span>

## <a name="guidelines-for-integrating-on-premises-unified-messaging-and-skype-for-business-server"></a><span data-ttu-id="adb31-157">整合內部部署整合通訊和商務用 Skype 伺服器的指導方針</span><span class="sxs-lookup"><span data-stu-id="adb31-157">Guidelines for integrating on-premises Unified Messaging and Skype for Business Server</span></span>

<span data-ttu-id="adb31-158">下列是在您部署企業語音時要考慮的指導方針和最佳做法：</span><span class="sxs-lookup"><span data-stu-id="adb31-158">The following are guidelines and best practices to consider when you deploy Enterprise Voice:</span></span>

> [!IMPORTANT]
> <span data-ttu-id="adb31-159">Exchange 整合通訊（UM）只有在您同時使用 UCMA 4 時才支援 IPv6。</span><span class="sxs-lookup"><span data-stu-id="adb31-159">Exchange Unified Messaging (UM) supports IPv6 only if you are also using UCMA 4.</span></span>

- <span data-ttu-id="adb31-160">部署商務用 Skype Server 標準版伺服器或前端池。</span><span class="sxs-lookup"><span data-stu-id="adb31-160">Deploy a Skype for Business Server Standard Edition server or a Front End pool.</span></span>

- <span data-ttu-id="adb31-161">與 Exchange 管理員共同確認您將執行的工作，以確保順利且順利地整合。</span><span class="sxs-lookup"><span data-stu-id="adb31-161">Work with Exchange administrators to confirm which tasks each of you will perform to assure a smooth and successful integration.</span></span>

- <span data-ttu-id="adb31-162">在您要啟用 Exchange UM 使用者的每個 Exchange 整合通訊（UM）目錄林中，部署 Exchange 信箱伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="adb31-162">Deploy the Exchange Mailbox server roles in each Exchange Unified Messaging (UM) forest where you want to enable users for Exchange UM.</span></span> <span data-ttu-id="adb31-163">如需安裝 Exchange server 角色的詳細資料，請參閱 Microsoft Exchange Server 檔。</span><span class="sxs-lookup"><span data-stu-id="adb31-163">For details about installing Exchange server roles, see the Microsoft Exchange Server documentation.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="adb31-164">安裝 Exchange 整合通訊（UM）後，系統會將它設定為使用自行簽署式認證。</span><span class="sxs-lookup"><span data-stu-id="adb31-164">When Exchange Unified Messaging (UM) is installed, it is configured to use a self-signed certificate.</span></span> <span data-ttu-id="adb31-165">自行簽署式認證不會啟用商務用 Skype Server 與 Exchange UM 互相信任，這就是為什麼必須從兩個伺服器信任的憑證授權單位要求個別憑證的原因。</span><span class="sxs-lookup"><span data-stu-id="adb31-165">The self-signed certificate does not enable Skype for Business Server and Exchange UM to trust each other, which is why it is necessary to request a separate certificate from a certification authority that both servers trust.</span></span>

- <span data-ttu-id="adb31-166">如果商務用 Skype Server 和 Exchange UM 已安裝在不同的林中，請將每個 Exchange 林設定為信任商務用 Skype Server 林與商務用 Skype 伺服器林，以信任每個 Exchange 目錄林。</span><span class="sxs-lookup"><span data-stu-id="adb31-166">If Skype for Business Server and Exchange UM are installed in different forests, configure each Exchange forest to trust the Skype for Business Server forest and the Skype for Business Server forest to trust each Exchange forest.</span></span> <span data-ttu-id="adb31-167">此外，您也可以在商務用 Skype Server 林中的使用者物件上設定使用者的 Exchange UM 設定，通常是使用腳本或跨林工具（例如 [身分識別週期管理員（ILM）]）。</span><span class="sxs-lookup"><span data-stu-id="adb31-167">Also, set the users' Exchange UM settings on the user objects in the Skype for Business Server forest, typically by using a script or a cross-forest tool, such as Identity Lifecycle Manager (ILM).</span></span>

- <span data-ttu-id="adb31-168">如有需要，請安裝 Exchange 管理主控台來管理您的整合郵件伺服器。</span><span class="sxs-lookup"><span data-stu-id="adb31-168">If necessary, install the Exchange Management Console to manage your Unified Messaging servers.</span></span>

- <span data-ttu-id="adb31-169">取得 Outlook 語音存取和自動語音應答的有效電話號碼。</span><span class="sxs-lookup"><span data-stu-id="adb31-169">Obtain valid phone numbers for Outlook Voice Access and auto attendant.</span></span>

- <span data-ttu-id="adb31-170">如果您使用的 Exchange UM 版本早于 Microsoft Exchange Server 2010 Service Pack 1 （SP1），請調整 Exchange UM SIP URI 撥號方案和企業語音撥號方案的名稱。</span><span class="sxs-lookup"><span data-stu-id="adb31-170">If you are using a version of Exchange UM earlier than Microsoft Exchange Server 2010 Service Pack 1 (SP1), coordinate names for Exchange UM SIP URI dial plans and Enterprise Voice dial plans.</span></span>

### <a name="deploying-redundant-exchange-um-servers"></a><span data-ttu-id="adb31-171">部署重複的 Exchange UM 伺服器</span><span class="sxs-lookup"><span data-stu-id="adb31-171">Deploying Redundant Exchange UM Servers</span></span>

> [!IMPORTANT]
> <span data-ttu-id="adb31-172">我們建議您在針對您的組織設定的每個 Exchange UM SIP URI 撥號方案中，部署至少有兩個 Exchange UM 服務正在執行的伺服器。</span><span class="sxs-lookup"><span data-stu-id="adb31-172">We recommend that you deploy a minimum of two servers on which Exchange UM services is running for each Exchange UM SIP URI dial plan that you configure for your organization.</span></span> <span data-ttu-id="adb31-173">除了提供擴充的容量之外，部署冗余伺服器也提供高可用性。</span><span class="sxs-lookup"><span data-stu-id="adb31-173">In addition to providing expanded capacity, deploying redundant servers provides high availability.</span></span> <span data-ttu-id="adb31-174">當伺服器發生故障時，可將商務用 Skype 伺服器設定為容錯移轉到另一個伺服器。</span><span class="sxs-lookup"><span data-stu-id="adb31-174">In the event of an server failure, Skype for Business Server can be configured to fail over to another server.</span></span>

<span data-ttu-id="adb31-175">下列範例配置提供 Exchange UM 復原。</span><span class="sxs-lookup"><span data-stu-id="adb31-175">The following example configurations provide Exchange UM resiliency.</span></span>

<span data-ttu-id="adb31-176">**範例1： Exchange UM 復原**</span><span class="sxs-lookup"><span data-stu-id="adb31-176">**Example 1: Exchange UM Resiliency**</span></span>

![Exchange UM 復原圖表](../../media/d8381ecc-0e4e-47ea-9bf7-e54fec9414e7.png)

<span data-ttu-id="adb31-178">在範例1中，Exchange UM 伺服器1和2在 Tukwila 資料中心中啟用，而在都柏林資料中心啟用 Exchange UM 伺服器3和4。</span><span class="sxs-lookup"><span data-stu-id="adb31-178">In Example 1, Exchange UM servers 1 and 2 are enabled in the Tukwila data center, and Exchange UM servers 3 and 4 are enabled in the Dublin data center.</span></span> <span data-ttu-id="adb31-179">在 Tukwila 中發生 Exchange UM 停用時，網域名稱系統（DNS）會將伺服器1和2的記錄分別設定為指向 [伺服器 3] 和 [4]。</span><span class="sxs-lookup"><span data-stu-id="adb31-179">In the event of an Exchange UM outage in Tukwila, the Domain Name System (DNS) A records for servers 1 and 2 should be configured to point to servers 3 and 4, respectively.</span></span> <span data-ttu-id="adb31-180">在都柏林中發生 Exchange UM 停用時，伺服器3和4的 DNS A 記錄應該設定為分別指向 [伺服器 1] 和 [2]。</span><span class="sxs-lookup"><span data-stu-id="adb31-180">In the event of an Exchange UM outage in Dublin, the DNS A records for servers 3 and 4 should be configured to point to servers 1 and 2, respectively.</span></span>

> [!NOTE]
> <span data-ttu-id="adb31-181">例如，您也應該在每個 Exchange UM 伺服器上指派下列其中一個憑證：在 [Subject 替換名稱（SAN）] 中使用萬用字元，或將四個 Exchange UM 伺服器的完整功能變數名稱（FQDN）放在 SAN 中。</span><span class="sxs-lookup"><span data-stu-id="adb31-181">For Example 1, you should also assign one of following certificates on each Exchange UM server: either use a certificate with a wildcard in the Subject Alternative Name (SAN) or Put the fully qualified domain name (FQDN) of each of the four Exchange UM servers in the SAN.</span></span>

<span data-ttu-id="adb31-182">**範例2： Exchange UM 復原**</span><span class="sxs-lookup"><span data-stu-id="adb31-182">**Example 2: Exchange UM Resiliency**</span></span>

![Exchange UM 復原圖表](../../media/4ad101c3-f318-4fc0-b4da-c05f2e92a943.png)

<span data-ttu-id="adb31-184">在範例2的 [一般操作條件] 下，Exchange UM 伺服器1和2在 Tukwila 資料中心中啟用，且在都柏林資料中心啟用 Exchange UM 伺服器3和4。</span><span class="sxs-lookup"><span data-stu-id="adb31-184">In Example 2, under ordinary operating conditions Exchange UM servers 1 and 2 are enabled in the Tukwila data center, and Exchange UM servers 3 and 4 are enabled in the Dublin data center.</span></span> <span data-ttu-id="adb31-185">所有四個伺服器都包含在 Tukwila 使用者的 SIP URI 撥號計畫中;不過，伺服器3和4會停用。</span><span class="sxs-lookup"><span data-stu-id="adb31-185">All four servers are included in the Tukwila users' SIP URI dial plan; however, servers 3 and 4 are disabled.</span></span> <span data-ttu-id="adb31-186">例如，在 Tukwila 中發生 Exchange um 停用時，應該停用 exchange UM 伺服器1和2，然後啟用 Exchange UM 伺服器3和4，以便將 Tukwila Exchange UM 流量路由到都柏林中的伺服器。</span><span class="sxs-lookup"><span data-stu-id="adb31-186">In the event of an Exchange UM outage in Tukwila, for example, Exchange UM servers 1 and 2 should be disabled and Exchange UM servers 3 and 4 should be enabled so the Tukwila Exchange UM traffic will be routed to the servers in Dublin.</span></span>

<span data-ttu-id="adb31-187">如需有關如何啟用或停用 Exchange 2013 整合訊息的詳細資訊，請參閱將[Exchange 2013 UM 與 Lync Server 整合](https://go.microsoft.com/fwlink/p/?LinkId=265372)。</span><span class="sxs-lookup"><span data-stu-id="adb31-187">For details about how to enable or disable Unified Messaging on Exchange 2013, see  [Integrate Exchange 2013 UM with Lync Server](https://go.microsoft.com/fwlink/p/?LinkId=265372).</span></span> <span data-ttu-id="adb31-188">所提供的資訊同樣適用于商務用 Skype 伺服器。</span><span class="sxs-lookup"><span data-stu-id="adb31-188">The information provided applies equally to Skype for Business Server.</span></span>

<span data-ttu-id="adb31-189">如需有關如何啟用或停用 Microsoft Exchange Server 2010 整合訊息的詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="adb31-189">For details about how to enable or disable Unified Messaging on Microsoft Exchange Server 2010, see:</span></span>

- [<span data-ttu-id="adb31-190">在 Exchange 2010 上啟用整合訊息</span><span class="sxs-lookup"><span data-stu-id="adb31-190">Enable Unified Messaging on Exchange 2010</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=204418)

- [<span data-ttu-id="adb31-191">停用 Exchange 2010 上的整合訊息</span><span class="sxs-lookup"><span data-stu-id="adb31-191">Disable Unified Messaging on Exchange 2010</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=204416)

### <a name="exchange-server-2019"></a><span data-ttu-id="adb31-192">Exchange Server 2019</span><span class="sxs-lookup"><span data-stu-id="adb31-192">Exchange Server 2019</span></span>

<span data-ttu-id="adb31-193">Exchange 整合訊息在 Exchange 2019 中已不存在，如果您有 Exchange 2019，而且您想要使用相同的功能，您需要使用雲端語音信箱服務（在[規劃雲端語音信箱服務](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md)中所述）。</span><span class="sxs-lookup"><span data-stu-id="adb31-193">Exchange Unified Messaging is no longer present in Exchange 2019, if you have Exchange 2019 and you want equivalent functionality you will need to use the Cloud Voicemail service described in [Plan Cloud Voicemail service](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="adb31-194">另請參閱</span><span class="sxs-lookup"><span data-stu-id="adb31-194">See also</span></span>

[<span data-ttu-id="adb31-195">整合內部部署整合訊息與商務用 Skype 的部署程式概述</span><span class="sxs-lookup"><span data-stu-id="adb31-195">Deployment process overview for integrating on-premises Unified Messaging and Skype for Business</span></span>](deployment-overview.md)
