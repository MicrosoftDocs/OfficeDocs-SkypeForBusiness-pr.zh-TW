---
title: 在商務用 Skype 中規劃 Exchange 整合通訊整合
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 摘要：在規劃整合商務用 Skype Server 與 Exchange 2013 或2016時，請參閱本主題。
ms.openlocfilehash: 95df4d0fa9d2a57385c5dd61c95bc07c07a8fa7c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096659"
---
# <a name="plan-for-exchange-unified-messaging-integration-in-skype-for-business"></a><span data-ttu-id="885d1-103">在商務用 Skype 中規劃 Exchange 整合通訊整合</span><span class="sxs-lookup"><span data-stu-id="885d1-103">Plan for Exchange Unified Messaging integration in Skype for Business</span></span>

<span data-ttu-id="885d1-104">**摘要：** 在規劃整合商務用 Skype Server 與 Exchange 2013 或2016時，請參閱本主題。</span><span class="sxs-lookup"><span data-stu-id="885d1-104">**Summary:** Review this topic while planning to integrate Skype for Business Server with Exchange 2013 or 2016.</span></span>

<span data-ttu-id="885d1-105">商務用 Skype 伺服器支援與 Exchange 整合通訊 (UM) 整合，以結合語音訊息與電子郵件至單一郵件基礎結構。</span><span class="sxs-lookup"><span data-stu-id="885d1-105">Skype for Business Server supports integration with Exchange Unified Messaging (UM) for combining voice messaging and email messaging into a single messaging infrastructure.</span></span> <span data-ttu-id="885d1-106">在 Exchange 中，Exchange 整合通訊 (UM) 是您可以安裝及設定數個 Exchange server role 中的其中一個。</span><span class="sxs-lookup"><span data-stu-id="885d1-106">In Exchange, Exchange Unified Messaging (UM) is one of several Exchange server roles that you can install and configure.</span></span>

<span data-ttu-id="885d1-107">在 Microsoft Exchange Server 2013 和2016中，Exchange UM 在 Exchange 信箱伺服器上以服務的身分執行。</span><span class="sxs-lookup"><span data-stu-id="885d1-107">In Microsoft Exchange Server 2013 and 2016, Exchange UM runs as a service on an Exchange Mailbox server.</span></span> <span data-ttu-id="885d1-108">針對商務用 Skype Server Enterprise Voice 部署，整合通訊會將語音訊息與電子郵件合併到單一存放區，使用者可以從電話存取 (Outlook 語音存取) 或電腦。</span><span class="sxs-lookup"><span data-stu-id="885d1-108">For Skype for Business Server Enterprise Voice deployments, Unified Messaging combines voice messaging and email messaging into a single store that users can access from a telephone (Outlook Voice Access) or a computer.</span></span> <span data-ttu-id="885d1-109">整合通訊和商務用 Skype 伺服器共同運作，為企業語音的使用者提供呼叫回應、Outlook Voice Access 和自動語音應答服務。</span><span class="sxs-lookup"><span data-stu-id="885d1-109">Unified Messaging and Skype for Business Server work together to provide call answering, Outlook Voice Access, and auto-attendant services to users of Enterprise Voice.</span></span>

> [!NOTE]
> <span data-ttu-id="885d1-110">當您整合商務用 Skype 2019 與 Exchange 2013 或 Exchange 2016 時，Exchange UM 仍可用於商務用 Skype Server 2019。</span><span class="sxs-lookup"><span data-stu-id="885d1-110">Exchange UM remains available in Skype for Business Server 2019 when you integrate Skype for Business 2019 with Exchange 2013 or Exchange 2016.</span></span> <span data-ttu-id="885d1-111">由於 Exchange 2019 中的支援變更，因此會取消考慮 Exchange UM 整合，以取代雲端語音信箱和雲端自動語音應答功能。</span><span class="sxs-lookup"><span data-stu-id="885d1-111">Due to changes in support in Exchange 2019, Exchange UM integration is being de-emphasized in favor of Cloud Voicemail and Cloud Auto Attendant features.</span></span>  <span data-ttu-id="885d1-112">如需詳細資訊，請參閱 [Plan Cloud 語音信箱服務](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) 並 [規劃商務用 Skype Server 和 Exchange Server 遷移](../../../sfbhybrid/hybrid/plan-um-migration.md) 。</span><span class="sxs-lookup"><span data-stu-id="885d1-112">See [Plan Cloud Voicemail service](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) and [Plan for Skype for Business Server and Exchange Server migration](../../../sfbhybrid/hybrid/plan-um-migration.md) for more information.</span></span>


<span data-ttu-id="885d1-113">若要在內部部署 Exchange UM 部署中支援這些功能，您必須執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="885d1-113">For these features to be supported in an on-premises Exchange UM deployment, you must be running one of the following:</span></span>

- <span data-ttu-id="885d1-114">僅限 Microsoft Exchange Server 2010 或最新的 service pack (商務用 Skype Server 2015) </span><span class="sxs-lookup"><span data-stu-id="885d1-114">Microsoft Exchange Server 2010 or latest service pack (Skype for Business Server 2015 only)</span></span>
- <span data-ttu-id="885d1-115">Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="885d1-115">Microsoft Exchange Server 2013</span></span>
- <span data-ttu-id="885d1-116">Microsoft Exchange Server 2016</span><span class="sxs-lookup"><span data-stu-id="885d1-116">Microsoft Exchange Server 2016</span></span>

> [!NOTE]
> <span data-ttu-id="885d1-117">Exchange 整合通訊（如先前所知）已無法在商務用 Skype Server 2019 中使用，它會使用電話系統來錄製語音信箱訊息，然後在使用者的 Exchange 信箱中留下記錄。</span><span class="sxs-lookup"><span data-stu-id="885d1-117">Exchange Unified Messaging as previously known is no longer available in Skype for Business Server 2019, which uses Phone System to record voicemail messages and then leave the recording in a user's Exchange mailbox.</span></span> <span data-ttu-id="885d1-118">如需詳細資訊，請參閱 [Plan Cloud 語音信箱服務](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) 。</span><span class="sxs-lookup"><span data-stu-id="885d1-118">See [Plan Cloud Voicemail service](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) for more information.</span></span>

## <a name="features-of-integrated-unified-messaging-and-skype-for-business-server"></a><span data-ttu-id="885d1-119">整合整合通訊和商務用 Skype 伺服器的功能</span><span class="sxs-lookup"><span data-stu-id="885d1-119">Features of integrated Unified Messaging and Skype for Business Server</span></span>

<span data-ttu-id="885d1-120">商務用 Skype 伺服器、Enterprise Voice 使用 Exchange 整合通訊 (UM) 基礎結構，提供通話回應、來電通知、語音存取 (包括語音信箱) 和自動語音應答服務。</span><span class="sxs-lookup"><span data-stu-id="885d1-120">Skype for Business Server, Enterprise Voice uses the Exchange Unified Messaging (UM) infrastructure to provide call answering, call notification, voice access (including voice mail), and auto-attendant services.</span></span>

- <span data-ttu-id="885d1-121">**來電應答** 呼叫應答是代表使用者接收語音訊息，但來電並未接聽或占線。</span><span class="sxs-lookup"><span data-stu-id="885d1-121">**Call Answering** Call answering is the receiving of voice messages on behalf of users whose calls are not answered or are busy.</span></span> <span data-ttu-id="885d1-122">它包含播放個人問候語、錄製郵件，並將郵件送出佇列以傳送至使用者的信箱，該信箱儲存在 Exchange 信箱伺服器上。</span><span class="sxs-lookup"><span data-stu-id="885d1-122">It includes playing a personal greeting, recording a message, and submitting the message to be queued for delivery to the user's mailbox, which is stored on the Exchange mailbox server.</span></span>

    <span data-ttu-id="885d1-p106">如果來電者留下訊息，該訊息就會傳送到使用者的收件匣。如果來電者選擇不留下任何訊息，則會在使用者的信箱中儲存未接來電通知。然後使用者可以使用 Microsoft Outlook 訊息和共同作業用戶端、Outlook Web Access、Exchange ActiveSync 技術或 Outlook Voice Access 存取自己的收件匣。可以使用與電子郵件類似的方式來顯示來電的主旨和優先順序。</span><span class="sxs-lookup"><span data-stu-id="885d1-p106">If a caller leaves a message, the message is routed to the user's Inbox. If a caller chooses not to leave a message, a missed call notification is stored in the user's mailbox. Users can then access their Inbox by using the Microsoft Outlook messaging and collaboration client, Outlook Web Access, the Exchange ActiveSync technology, or Outlook Voice Access. The subject and priority of calls can be displayed in a way similar to that of email.</span></span>

- <span data-ttu-id="885d1-127">**Outlook 語音存取** Outlook Voice Access 可讓企業語音使用者存取不只是語音信箱，也可存取 Exchange 收件匣（包括電子郵件、行事曆和電話語音介面中的連絡人）。</span><span class="sxs-lookup"><span data-stu-id="885d1-127">**Outlook Voice Access** Outlook Voice Access enables an Enterprise Voice user to access not just voice mail, but also the Exchange inbox, including email, calendar, and contacts from a telephony interface.</span></span> <span data-ttu-id="885d1-128">「使用者存取號碼」是由 Exchange UM 管理員所指派。</span><span class="sxs-lookup"><span data-stu-id="885d1-128">The subscriber access number is assigned by an Exchange UM administrator.</span></span>

- <span data-ttu-id="885d1-129">**自動** 語音應答自動語音應答是一種 Exchange UM 功能，可用來設定使用者可以撥出的電話號碼，以到達公司代表。</span><span class="sxs-lookup"><span data-stu-id="885d1-129">**Auto attendant** Auto attendant is an Exchange UM feature that can be used to configure a phone number that outside users can dial to reach company representatives.</span></span> <span data-ttu-id="885d1-130">特別是，它提供了一系列的語音提示，可協助外部來電者瀏覽功能表系統。</span><span class="sxs-lookup"><span data-stu-id="885d1-130">In particular, it provides a series of voice prompts that assist an external caller in navigating a menu system.</span></span> <span data-ttu-id="885d1-131">[可用選項] 清單是由 Exchange um 管理員在 Exchange UM 伺服器上設定。</span><span class="sxs-lookup"><span data-stu-id="885d1-131">The list of available options is configured on the Exchange UM server by the Exchange UM administrator.</span></span>

- <span data-ttu-id="885d1-132">**傳真服務** Exchange UM 包含傳真功能，可讓使用者在其 Exchange 信箱中接收傳入的傳真。</span><span class="sxs-lookup"><span data-stu-id="885d1-132">**Fax Services** Exchange UM includes fax features, which enable users to receive incoming faxes in their Exchange mailboxes.</span></span> <span data-ttu-id="885d1-133">如需詳細資訊，請參閱 Microsoft Exchange Server 檔中的 [整合通訊](/previous-versions/office/exchange-server-2007/bb123911(v=exchg.80)) 。</span><span class="sxs-lookup"><span data-stu-id="885d1-133">For details, see [Unified Messaging](/previous-versions/office/exchange-server-2007/bb123911(v=exchg.80)) in the Microsoft Exchange Server documentation.</span></span>

    > [!NOTE]
    > <span data-ttu-id="885d1-134">Exchange UM 伺服器所提供的傳真服務無法在商務用 Skype Server 中使用，這些部署是與 Microsoft Exchange Server 2010、Exchange 2010 搭配最新 service pack、Exchange 2013 或 Exchange 2016 整合。</span><span class="sxs-lookup"><span data-stu-id="885d1-134">Fax services provided by the Exchange UM server are not available in Skype for Business Server deployments that are integrated with Microsoft Exchange Server 2010, Exchange 2010 with the latest service pack, Exchange 2013, or Exchange 2016.</span></span>

## <a name="components-and-topologies-for-on-premises-unified-messaging-in-skype-for-business-server"></a><span data-ttu-id="885d1-135">商務用 Skype Server 中內部部署整合通訊的元件和拓撲</span><span class="sxs-lookup"><span data-stu-id="885d1-135">Components and topologies for on-premises Unified Messaging in Skype for Business Server</span></span>

### <a name="exchange-server-components"></a><span data-ttu-id="885d1-136">Exchange Server 元件</span><span class="sxs-lookup"><span data-stu-id="885d1-136">Exchange Server Components</span></span>

<span data-ttu-id="885d1-137">若要提供 Exchange UM 功能和服務中所述的整合式整合 [通訊和商務用 Skype Server](#features-of-integrated-unified-messaging-and-skype-for-business-server) 至組織中的 Enterprise Voice 使用者，您必須部署 Microsoft Exchange 信箱伺服器和用戶端存取伺服器，該伺服器主控使用者信箱，並提供電子郵件及語音信箱的單一存放位置。</span><span class="sxs-lookup"><span data-stu-id="885d1-137">To provide the Exchange UM features and services described in [Features of integrated Unified Messaging and Skype for Business Server](#features-of-integrated-unified-messaging-and-skype-for-business-server) to Enterprise Voice users in your organization, you must deploy an Microsoft Exchange Mailbox server and Client Access server, which hosts user mailboxes and provides a single storage location for email and voice mail.</span></span> <span data-ttu-id="885d1-138">Exchange UM 在 Exchange 信箱和用戶端存取伺服器上以服務的身分執行。</span><span class="sxs-lookup"><span data-stu-id="885d1-138">Exchange UM runs as a service on Exchange Mailbox and Client Access servers.</span></span>

<span data-ttu-id="885d1-139">如需 Microsoft Exchange Server 2010 中 Exchange UM 元件的詳細資訊，請參閱 [部署 On-Premises EXCHANGE UM，以提供 Lync Server 2013 預覽語音信箱](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail) 。</span><span class="sxs-lookup"><span data-stu-id="885d1-139">For details about Exchange UM components in Microsoft Exchange Server 2010, see [Deploying On-Premises Exchange UM to Provide Lync Server 2013 Preview Voice Mail](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail) .</span></span>

### <a name="supported-topologies"></a><span data-ttu-id="885d1-140">支援的拓撲</span><span class="sxs-lookup"><span data-stu-id="885d1-140">Supported Topologies</span></span>

<span data-ttu-id="885d1-141">您可以在相同樹系或多個樹系中部署商務用 Skype Server 和 Exchange 整合通訊 (UM) 。</span><span class="sxs-lookup"><span data-stu-id="885d1-141">You can deploy Skype for Business Server and Exchange Unified Messaging (UM) in the same forest or multiple forests.</span></span> <span data-ttu-id="885d1-142">如果部署跨越多個樹系，您必須針對每個 Exchange UM 樹系執行 Exchange 整合步驟。</span><span class="sxs-lookup"><span data-stu-id="885d1-142">If the deployment spans multiple forests, you must perform the Exchange integration steps for each Exchange UM forest.</span></span> <span data-ttu-id="885d1-143">此外，您必須將每個 Microsoft Exchange 樹系設定為信任商務用 Skype 伺服器樹系和商務用 Skype 伺服器樹系，以信任每個 Exchange UM 樹系。</span><span class="sxs-lookup"><span data-stu-id="885d1-143">Furthermore, you must configure each Microsoft Exchange forest to trust the Skype for Business Server forest and the Skype for Business Server forest to trust each Exchange UM forest.</span></span> <span data-ttu-id="885d1-144">除了此樹系信任之外，您必須在商務用 Skype 伺服器樹系中的使用者物件上設定所有使用者的 Exchange UM 設定。</span><span class="sxs-lookup"><span data-stu-id="885d1-144">In addition to this forest trust, the Exchange UM settings for all users must be set on the user objects in the Skype for Business Server forest.</span></span>

<span data-ttu-id="885d1-145">商務用 Skype 伺服器支援下列 Exchange UM 整合拓撲：</span><span class="sxs-lookup"><span data-stu-id="885d1-145">Skype for Business Server supports the following topologies for Exchange UM integration:</span></span>

- <span data-ttu-id="885d1-146">單一樹系</span><span class="sxs-lookup"><span data-stu-id="885d1-146">Single forest</span></span>

- <span data-ttu-id="885d1-147">單一網域 (亦即單一樹系搭配單一網域)。</span><span class="sxs-lookup"><span data-stu-id="885d1-147">Single domain (that is, a single forest with a single domain).</span></span> <span data-ttu-id="885d1-148">商務用 Skype 伺服器、Microsoft Exchange 和使用者都位於相同的網域。</span><span class="sxs-lookup"><span data-stu-id="885d1-148">Skype for Business Server, Microsoft Exchange, and users all reside in the same domain.</span></span>

- <span data-ttu-id="885d1-149">多重網域 (亦即，一個根網域搭配一或多個子網域)。</span><span class="sxs-lookup"><span data-stu-id="885d1-149">Multiple domain (that is, a root domain with one or more child domains).</span></span> <span data-ttu-id="885d1-150">商務用 Skype 伺服器和 Microsoft Exchange 伺服器會從您建立使用者的網域部署在不同的網域中。</span><span class="sxs-lookup"><span data-stu-id="885d1-150">Skype for Business Server, and Microsoft Exchange servers are deployed in different domains from the domain where you create users.</span></span> <span data-ttu-id="885d1-151">Exchange UM 伺服器可以從其支援的商務用 Skype 伺服器集區部署在不同的網域中。</span><span class="sxs-lookup"><span data-stu-id="885d1-151">Exchange UM servers can be deployed in different domains from the Skype for Business Server pool they support.</span></span>

- <span data-ttu-id="885d1-152">多重樹系 (亦即資源樹系)。</span><span class="sxs-lookup"><span data-stu-id="885d1-152">Multiple forest (that is, resource forest).</span></span> <span data-ttu-id="885d1-153">商務用 Skype Server 會部署在單一樹系中，然後將使用者散佈于多個樹系。</span><span class="sxs-lookup"><span data-stu-id="885d1-153">Skype for Business Server is deployed in a single forest, and then users are distributed across multiple forests.</span></span> <span data-ttu-id="885d1-154">使用者的 Exchange UM 屬性必須複製到商務用 Skype 伺服器樹系。</span><span class="sxs-lookup"><span data-stu-id="885d1-154">The users' Exchange UM attributes must be replicated over to the Skype for Business Server forest.</span></span>

    > [!NOTE]
    > <span data-ttu-id="885d1-155">Exchange 可以部署在多個樹系中。</span><span class="sxs-lookup"><span data-stu-id="885d1-155">Exchange can be deployed in multiple forests.</span></span> <span data-ttu-id="885d1-156">每個 Exchange 組織都可以為其使用者提供 Exchange UM，也可以將 Exchange UM 部署在與商務用 Skype 伺服器相同的樹系中。</span><span class="sxs-lookup"><span data-stu-id="885d1-156">Each Exchange organization can provide Exchange UM to its users, or Exchange UM can be deployed in the same forest as Skype for Business Server.</span></span>

## <a name="guidelines-for-integrating-on-premises-unified-messaging-and-skype-for-business-server"></a><span data-ttu-id="885d1-157">整合內部部署整合通訊和商務用 Skype 伺服器的指導方針</span><span class="sxs-lookup"><span data-stu-id="885d1-157">Guidelines for integrating on-premises Unified Messaging and Skype for Business Server</span></span>

<span data-ttu-id="885d1-158">以下是部署企業語音時所需考慮的指導方針和最佳作法：</span><span class="sxs-lookup"><span data-stu-id="885d1-158">The following are guidelines and best practices to consider when you deploy Enterprise Voice:</span></span>

> [!IMPORTANT]
> <span data-ttu-id="885d1-159">只有在您同時使用 UCMA 4 時，Exchange 整合通訊 (UM) 才會支援 IPv6。</span><span class="sxs-lookup"><span data-stu-id="885d1-159">Exchange Unified Messaging (UM) supports IPv6 only if you are also using UCMA 4.</span></span>

- <span data-ttu-id="885d1-160">部署商務用 Skype Server Standard Edition server 或前端集區。</span><span class="sxs-lookup"><span data-stu-id="885d1-160">Deploy a Skype for Business Server Standard Edition server or a Front End pool.</span></span>

- <span data-ttu-id="885d1-161">與 Exchange 系統管理員合作，確認每一個人將要執行的工作，以確保能夠順暢、成功地整合。</span><span class="sxs-lookup"><span data-stu-id="885d1-161">Work with Exchange administrators to confirm which tasks each of you will perform to assure a smooth and successful integration.</span></span>

- <span data-ttu-id="885d1-162">在您要為 Exchange UM 啟用使用者的每個 Exchange 整合通訊 (UM) 樹系中，部署 Exchange 信箱伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="885d1-162">Deploy the Exchange Mailbox server roles in each Exchange Unified Messaging (UM) forest where you want to enable users for Exchange UM.</span></span> <span data-ttu-id="885d1-163">如需安裝 Exchange 伺服器角色的詳細資訊，請參閱 Microsoft Exchange Server 檔。</span><span class="sxs-lookup"><span data-stu-id="885d1-163">For details about installing Exchange server roles, see the Microsoft Exchange Server documentation.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="885d1-164">安裝 Exchange 整合通訊 (UM) 時，會將其設定為使用自我簽署憑證。</span><span class="sxs-lookup"><span data-stu-id="885d1-164">When Exchange Unified Messaging (UM) is installed, it is configured to use a self-signed certificate.</span></span> <span data-ttu-id="885d1-165">自我簽署憑證不會讓商務用 Skype 伺服器和 Exchange UM 彼此信任，這就是為何必須從兩部伺服器信任的憑證授權單位單位要求個別憑證。</span><span class="sxs-lookup"><span data-stu-id="885d1-165">The self-signed certificate does not enable Skype for Business Server and Exchange UM to trust each other, which is why it is necessary to request a separate certificate from a certification authority that both servers trust.</span></span>

- <span data-ttu-id="885d1-166">如果商務用 Skype Server 和 Exchange UM 安裝在不同的樹系中，請將每個 Exchange 樹系設定為信任商務用 Skype 伺服器樹系和商務用 Skype 伺服器樹系，以信任每個 Exchange 樹系。</span><span class="sxs-lookup"><span data-stu-id="885d1-166">If Skype for Business Server and Exchange UM are installed in different forests, configure each Exchange forest to trust the Skype for Business Server forest and the Skype for Business Server forest to trust each Exchange forest.</span></span> <span data-ttu-id="885d1-167">此外，在商務用 Skype 伺服器樹系的使用者物件上設定使用者的 Exchange UM 設定，通常是使用腳本或跨樹系工具，例如身分識別生命週期管理員 (ILM) 。</span><span class="sxs-lookup"><span data-stu-id="885d1-167">Also, set the users' Exchange UM settings on the user objects in the Skype for Business Server forest, typically by using a script or a cross-forest tool, such as Identity Lifecycle Manager (ILM).</span></span>

- <span data-ttu-id="885d1-168">必要時，安裝 Exchange 管理主控台以便管理 Unified Messaging 伺服器。</span><span class="sxs-lookup"><span data-stu-id="885d1-168">If necessary, install the Exchange Management Console to manage your Unified Messaging servers.</span></span>

- <span data-ttu-id="885d1-169">取得 Outlook Voice Access 和自動語音應答的有效電話號碼。</span><span class="sxs-lookup"><span data-stu-id="885d1-169">Obtain valid phone numbers for Outlook Voice Access and auto attendant.</span></span>

- <span data-ttu-id="885d1-170">如果您使用的 Exchange UM 版本低於 Microsoft Exchange Server 2010 Service Pack 1 (SP1) ，則為 Exchange UM SIP URI 撥號對應表和 Enterprise Voice 撥號對應表的座標名稱。</span><span class="sxs-lookup"><span data-stu-id="885d1-170">If you are using a version of Exchange UM earlier than Microsoft Exchange Server 2010 Service Pack 1 (SP1), coordinate names for Exchange UM SIP URI dial plans and Enterprise Voice dial plans.</span></span>

### <a name="deploying-redundant-exchange-um-servers"></a><span data-ttu-id="885d1-171">部署重複的 Exchange UM 伺服器</span><span class="sxs-lookup"><span data-stu-id="885d1-171">Deploying Redundant Exchange UM Servers</span></span>

> [!IMPORTANT]
> <span data-ttu-id="885d1-172">建議您為組織設定的每個 Exchange UM SIP URI 撥號對應表，至少部署兩部執行 Exchange UM 服務的伺服器。</span><span class="sxs-lookup"><span data-stu-id="885d1-172">We recommend that you deploy a minimum of two servers on which Exchange UM services is running for each Exchange UM SIP URI dial plan that you configure for your organization.</span></span> <span data-ttu-id="885d1-173">除了提供擴充的容量之外，部署冗余伺服器也可提供高可用性。</span><span class="sxs-lookup"><span data-stu-id="885d1-173">In addition to providing expanded capacity, deploying redundant servers provides high availability.</span></span> <span data-ttu-id="885d1-174">在伺服器失敗的情況下，商務用 Skype 伺服器可以設定為容錯移轉至另一部伺服器。</span><span class="sxs-lookup"><span data-stu-id="885d1-174">In the event of an server failure, Skype for Business Server can be configured to fail over to another server.</span></span>

<span data-ttu-id="885d1-175">以下範例設定可提供 Exchange UM 恢復能力。</span><span class="sxs-lookup"><span data-stu-id="885d1-175">The following example configurations provide Exchange UM resiliency.</span></span>

<span data-ttu-id="885d1-176">**範例 1：Exchange UM 恢復能力**</span><span class="sxs-lookup"><span data-stu-id="885d1-176">**Example 1: Exchange UM Resiliency**</span></span>

![Exchange UM 恢復圖表](../../media/d8381ecc-0e4e-47ea-9bf7-e54fec9414e7.png)

<span data-ttu-id="885d1-178">在範例 1 中，Tukwila 資料中心內的 Exchange UM 伺服器 1 和伺服器 2 均已啟用；Dublin 資料中心內的 Exchange UM 伺服器 3 和伺服器 4 均已啟用。</span><span class="sxs-lookup"><span data-stu-id="885d1-178">In Example 1, Exchange UM servers 1 and 2 are enabled in the Tukwila data center, and Exchange UM servers 3 and 4 are enabled in the Dublin data center.</span></span> <span data-ttu-id="885d1-179">在 Tukwila 中發生 Exchange UM 中斷的情況時，網域名稱系統 (DNS) 伺服器1和2的記錄應該設定為分別指向 servers 3 和4。</span><span class="sxs-lookup"><span data-stu-id="885d1-179">In the event of an Exchange UM outage in Tukwila, the Domain Name System (DNS) A records for servers 1 and 2 should be configured to point to servers 3 and 4, respectively.</span></span> <span data-ttu-id="885d1-180">在都柏林中發生 Exchange UM 中斷的情況時，伺服器3和4的 DNS A 記錄應該設定為分別指向 servers 1 和2。</span><span class="sxs-lookup"><span data-stu-id="885d1-180">In the event of an Exchange UM outage in Dublin, the DNS A records for servers 3 and 4 should be configured to point to servers 1 and 2, respectively.</span></span>

> [!NOTE]
> <span data-ttu-id="885d1-181">在範例1中，您也應該在每個 Exchange UM 伺服器上指派下列其中一個憑證：在主體替代名稱中使用具有萬用字元的憑證 (SAN) 或將完整功能變數名稱 (FQDN) 放入 SAN 中的兩個 Exchange UM 伺服器。</span><span class="sxs-lookup"><span data-stu-id="885d1-181">For Example 1, you should also assign one of following certificates on each Exchange UM server: either use a certificate with a wildcard in the Subject Alternative Name (SAN) or Put the fully qualified domain name (FQDN) of each of the four Exchange UM servers in the SAN.</span></span>

<span data-ttu-id="885d1-182">**範例 2：Exchange UM 恢復能力**</span><span class="sxs-lookup"><span data-stu-id="885d1-182">**Example 2: Exchange UM Resiliency**</span></span>

![Exchange UM 恢復圖表](../../media/4ad101c3-f318-4fc0-b4da-c05f2e92a943.png)

<span data-ttu-id="885d1-p121">在範例 2 中，於正常運作情況下，Tukwila 資料中心內的 Exchange UM 伺服器 1 和伺服器 2 均已啟用；Dublin 資料中心內的 Exchange UM 伺服器 3 和伺服器 4 均已啟用。這四部伺服器均包含在 Tukwila 使用者的 SIP URI 撥號對應表中，不過伺服器 3 和 4 均已停用。當 Tukwila 的 Exchange UM 伺服器發生如停止運作等的情況時，應停用 Exchange UM 伺服器 1 和 2 並啟用 Exchange UM 伺服器 3 和 4，以將 Tukwila Exchange UM 的流量路由傳送至 Dublin 的伺服器。</span><span class="sxs-lookup"><span data-stu-id="885d1-p121">In Example 2, under ordinary operating conditions Exchange UM servers 1 and 2 are enabled in the Tukwila data center, and Exchange UM servers 3 and 4 are enabled in the Dublin data center. All four servers are included in the Tukwila users' SIP URI dial plan; however, servers 3 and 4 are disabled. In the event of an Exchange UM outage in Tukwila, for example, Exchange UM servers 1 and 2 should be disabled and Exchange UM servers 3 and 4 should be enabled so the Tukwila Exchange UM traffic will be routed to the servers in Dublin.</span></span>

<span data-ttu-id="885d1-187">如需如何在 Exchange 2013 上啟用或停用整合通訊的詳細資訊，請參閱將  [exchange 2013 UM 與 Lync Server 整合](/exchange/checklist-integrate-exchange-2013-um-with-lync-server-exchange-2013-help)。</span><span class="sxs-lookup"><span data-stu-id="885d1-187">For details about how to enable or disable Unified Messaging on Exchange 2013, see  [Integrate Exchange 2013 UM with Lync Server](/exchange/checklist-integrate-exchange-2013-um-with-lync-server-exchange-2013-help).</span></span> <span data-ttu-id="885d1-188">提供的資訊同樣適用于商務用 Skype Server。</span><span class="sxs-lookup"><span data-stu-id="885d1-188">The information provided applies equally to Skype for Business Server.</span></span>

<span data-ttu-id="885d1-189">如需如何在 Microsoft Exchange Server 2010 上啟用或停用整合通訊的詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="885d1-189">For details about how to enable or disable Unified Messaging on Microsoft Exchange Server 2010, see:</span></span>

- <span data-ttu-id="885d1-190">[在 Exchange 2010 上啟用整合通訊](/previous-versions/office/exchange-server-2010/aa997908(v=exchg.141))</span><span class="sxs-lookup"><span data-stu-id="885d1-190">[Enable Unified Messaging on Exchange 2010](/previous-versions/office/exchange-server-2010/aa997908(v=exchg.141))</span></span>

- <span data-ttu-id="885d1-191">[停用 Exchange 2010 的整合通訊](/previous-versions/office/exchange-server-2010/bb123529(v=exchg.141))</span><span class="sxs-lookup"><span data-stu-id="885d1-191">[Disable Unified Messaging on Exchange 2010](/previous-versions/office/exchange-server-2010/bb123529(v=exchg.141))</span></span>

### <a name="exchange-server-2019"></a><span data-ttu-id="885d1-192">Exchange Server 2019</span><span class="sxs-lookup"><span data-stu-id="885d1-192">Exchange Server 2019</span></span>

<span data-ttu-id="885d1-193">Exchange 2019 中不再顯示 exchange 整合通訊，如果您有 Exchange 2019，而且想要使用相同的功能，您必須使用 [計畫雲端語音信箱服務](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md)中所述的雲端語音信箱服務。</span><span class="sxs-lookup"><span data-stu-id="885d1-193">Exchange Unified Messaging is no longer present in Exchange 2019, if you have Exchange 2019 and you want equivalent functionality you will need to use the Cloud Voicemail service described in [Plan Cloud Voicemail service](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="885d1-194">另請參閱</span><span class="sxs-lookup"><span data-stu-id="885d1-194">See also</span></span>

[<span data-ttu-id="885d1-195">整合內部部署整合通訊和商務用 Skype 的部署程式概述</span><span class="sxs-lookup"><span data-stu-id="885d1-195">Deployment process overview for integrating on-premises Unified Messaging and Skype for Business</span></span>](deployment-overview.md)