---
title: 商務用 Skype Server 的拓撲基礎
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 113e8c3f-71de-435c-bc4a-918ac7b50008
description: 摘要：選擇商務用 Skype Server 的拓撲。 瞭解商務用 Skype Server 的伺服器 collocation。
ms.openlocfilehash: b3f45a37bde409dcda38f3047e60776ebc8560e6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41801693"
---
# <a name="topology-basics-for-skype-for-business-server"></a><span data-ttu-id="e8157-104">商務用 Skype Server 的拓撲基礎</span><span class="sxs-lookup"><span data-stu-id="e8157-104">Topology Basics for Skype for Business Server</span></span>

<span data-ttu-id="e8157-105">**摘要：** 選擇您的商務用 Skype Server 拓撲。</span><span class="sxs-lookup"><span data-stu-id="e8157-105">**Summary:** Choose your topology for Skype for Business Server.</span></span> <span data-ttu-id="e8157-106">瞭解商務用 Skype Server 的伺服器 collocation。</span><span class="sxs-lookup"><span data-stu-id="e8157-106">Learn about server collocation for Skype for Business Server.</span></span>

<span data-ttu-id="e8157-107">在準備任何其他專案之前，您可能會想知道您正在規劃適用于商務用 Skype Server 部署的正確拓撲。</span><span class="sxs-lookup"><span data-stu-id="e8157-107">Before preparing anything else, you'll want to know you're planning for the right topology for your deployment of Skype for Business Server.</span></span> <span data-ttu-id="e8157-108">您首先需要決定的做法是，如果您要使用內部部署的商務用 Skype Server，或是在混合式部署中將此專案與商務用 Skype Server Online 部署結合。</span><span class="sxs-lookup"><span data-stu-id="e8157-108">The first thing you need to decide is if you're going to have an on-premises deployment of Skype for Business Server, or if you're going to combine this with a Skype for Business Server Online deployment in a Hybrid deployment.</span></span> <span data-ttu-id="e8157-109">不論是哪一種方式，您都會想進一步瞭解，因為我們將在這裡詳細說明內部部署的拓撲，但是混合式詳細資料會記錄在各自的區段中。</span><span class="sxs-lookup"><span data-stu-id="e8157-109">Either way, you're going to want to read further, as we'll detail the on-premises topologies here, but the Hybrid details are documented in their own section.</span></span>

<span data-ttu-id="e8157-110">您也可以在[商務用 Skype Server 的參考拓朴](reference-topologies.md)中查看一些範例拓撲。</span><span class="sxs-lookup"><span data-stu-id="e8157-110">You can also see some example topologies in [Reference topologies for Skype for Business Server](reference-topologies.md).</span></span>

## <a name="sites"></a><span data-ttu-id="e8157-111">網站</span><span class="sxs-lookup"><span data-stu-id="e8157-111">Sites</span></span>

<span data-ttu-id="e8157-112">在商務用 Skype Server 中，您可以在網路上定義包含商務用 Skype 伺服器元件的網站。</span><span class="sxs-lookup"><span data-stu-id="e8157-112">In Skype for Business Server, you define sites on your network that contain Skype for Business Server components.</span></span> <span data-ttu-id="e8157-113">網站是一組由高速、低延遲網路連接的電腦，例如單一局域網（LAN），或由高速光纖光纖網路連接的兩個網路。</span><span class="sxs-lookup"><span data-stu-id="e8157-113">A site is a set of computers that is well-connected by a high-speed, low-latency network, such as a single local area network (LAN) or two networks connected by a high-speed fiber optic network.</span></span> <span data-ttu-id="e8157-114">請注意，商務用 Skype Server 網站是來自 Active Directory 網域服務網站和 Microsoft Exchange Server 網站的個別概念。</span><span class="sxs-lookup"><span data-stu-id="e8157-114">Note that Skype for Business Server sites are a separate concept from Active Directory Domain Services sites and Microsoft Exchange Server sites.</span></span> <span data-ttu-id="e8157-115">您的商務用 Skype Server 網站不需要對應至 Active Directory 網站。</span><span class="sxs-lookup"><span data-stu-id="e8157-115">Your Skype for Business Server sites do not need to correspond to your Active Directory sites.</span></span>

<span data-ttu-id="e8157-116">商務用 Skype 伺服器支援內部部署一或多個網站，可根據您的高可用性和位置需求來調整。</span><span class="sxs-lookup"><span data-stu-id="e8157-116">Skype for Business Server supports on-premises deployment of one or more sites that can be scaled according to your high availability and location requirements.</span></span>

<span data-ttu-id="e8157-117">您的部署將至少有一個中心網站（又稱為資料中心），而您部署中的每個中心網站都將有一個標準版伺服器，或至少有一個企業版頂層端池。</span><span class="sxs-lookup"><span data-stu-id="e8157-117">Your deployment will have at least one central site (also called a datacenter, this is a datacenter for all the servers located in it), and each central site in your deployment will have one Standard Edition server, or at least one Enterprise Edition Front End pool.</span></span> <span data-ttu-id="e8157-118">您可以在下列各項選項中查看差異：</span><span class="sxs-lookup"><span data-stu-id="e8157-118">You can see the differences in each option below:</span></span>

- <span data-ttu-id="e8157-119">標準版伺服器包括 collocated SQL Server Express 資料庫。</span><span class="sxs-lookup"><span data-stu-id="e8157-119">Standard Edition server includes a collocated SQL Server Express database.</span></span>

- <span data-ttu-id="e8157-120">企業版前端池包括：</span><span class="sxs-lookup"><span data-stu-id="e8157-120">Enterprise Edition Front End pool includes:</span></span>

  - <span data-ttu-id="e8157-121">一或多個前端伺服器（理想情況下至少為三個），最多可達12個。</span><span class="sxs-lookup"><span data-stu-id="e8157-121">One or more Front End Servers (Ideally at least three, for scalability), with a maximum of twelve.</span></span> <span data-ttu-id="e8157-122">需要對多個伺服器進行負載平衡。</span><span class="sxs-lookup"><span data-stu-id="e8157-122">Load-balancing would be required for more than one server.</span></span>

  - <span data-ttu-id="e8157-123">個別的後端伺服器。</span><span class="sxs-lookup"><span data-stu-id="e8157-123">A separate Back End Server.</span></span>

<span data-ttu-id="e8157-124">您可以在此區段中深入瞭解各種伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="e8157-124">You can learn more about the various server roles a little later in this section.</span></span>

<span data-ttu-id="e8157-125">除了您的中央網站之外，您也可能會有一個或多個與您的中央網站相關聯的分支網站。</span><span class="sxs-lookup"><span data-stu-id="e8157-125">In addition to your central sites, you may also end up having one or more branch sites associated with your central site.</span></span> <span data-ttu-id="e8157-126">它們依賴于中心網站，幾乎所有的功能，因此它們的用途是什麼？</span><span class="sxs-lookup"><span data-stu-id="e8157-126">They depend on the central site for almost all their functionality, so what are they made up of, exactly?</span></span>

- <span data-ttu-id="e8157-127">Survivable 分支裝置，它結合了公用的交換電話網絡（PSTN）閘道，以及部分商務用 Skype Server 功能。</span><span class="sxs-lookup"><span data-stu-id="e8157-127">Survivable Branch Appliance, which combines a public switched telephone network (PSTN) gateway, with some Skype for Business Server functionality.</span></span>

- <span data-ttu-id="e8157-128">Survivable [分支伺服器]，它是執行 Windows Server 且已安裝商務用 Skype Server 註冊機構和轉送伺服器軟體的伺服器。</span><span class="sxs-lookup"><span data-stu-id="e8157-128">Survivable Branch Server, it's a server running Windows Server that has Skype for Business Server Registrar and Mediation Server software installed.</span></span>

- <span data-ttu-id="e8157-129">獨立 PSTN 閘道（不是 Survivable 分支裝置的一部分）。</span><span class="sxs-lookup"><span data-stu-id="e8157-129">Stand-alone PSTN gateway (which isn't part of the Survivable Branch Appliance).</span></span>

- <span data-ttu-id="e8157-130">獨立的中繼伺服器或獨立的中繼伺服器池（如果您不想將此角色與 Survivable 分支裝置 collocate）。</span><span class="sxs-lookup"><span data-stu-id="e8157-130">Stand-alone Mediation Server or stand-alone Mediation Server pool (if you don't want to collocate this role with the Survivable Branch Appliance).</span></span>

## <a name="whats-in-a-skype-for-business-server-site"></a><span data-ttu-id="e8157-131">商務用 Skype Server 網站有什麼功能？</span><span class="sxs-lookup"><span data-stu-id="e8157-131">What's in a Skype for Business Server site?</span></span>

<span data-ttu-id="e8157-132">若要深入瞭解更多相關資訊，中央網站也可以有：</span><span class="sxs-lookup"><span data-stu-id="e8157-132">To get into more detail, a central site can also have:</span></span>

- <span data-ttu-id="e8157-133">在同一個網域或不同網域中有多個前端池，請記住，在規劃中的所有前端伺服器以及該池的後端伺服器，都必須在同一個網域中。</span><span class="sxs-lookup"><span data-stu-id="e8157-133">Multiple Front End pools, in the same domain or different domains (remember in planning that all the Front End Servers in a Front End pool, along with the Back End Servers for the pool, do have to be in the same domain).</span></span>

- <span data-ttu-id="e8157-134">多個標準版伺服器。</span><span class="sxs-lookup"><span data-stu-id="e8157-134">Multiple Standard Edition servers.</span></span>

- <span data-ttu-id="e8157-135">Office Web Apps Server，與商務用 Skype Server 中的 Office Web Apps 搭配使用，以共用和轉譯 PowerPoint 簡報。</span><span class="sxs-lookup"><span data-stu-id="e8157-135">Office Web Apps Server, which is used with Office Web Apps in Skype for Business Server for sharing and rendering of PowerPoint presentations.</span></span>

- <span data-ttu-id="e8157-136">Edge 伺服器或 Edge 池（在周邊網路中）。</span><span class="sxs-lookup"><span data-stu-id="e8157-136">Edge Server or Edge pool (in a perimeter network).</span></span> <span data-ttu-id="e8157-137">如果您想要讓您的部署支援同盟夥伴、公用 IM 連線、可擴展的訊息和目前狀態通訊協定（XMPP）閘道，以及遠端使用者存取權，您需要進行部署。</span><span class="sxs-lookup"><span data-stu-id="e8157-137">Needed if you want your deployment to support federated partners, public IM connectivity, extensible messaging and presence protocol (XMPP) gateway, and remote user access.</span></span> <span data-ttu-id="e8157-138">如需詳細資訊，請參閱 Edge 伺服器規劃檔。</span><span class="sxs-lookup"><span data-stu-id="e8157-138">More details can be found in the Edge Server Planning documentation.</span></span>

- <span data-ttu-id="e8157-139">持續聊天伺服器。</span><span class="sxs-lookup"><span data-stu-id="e8157-139">Persistent Chat Server.</span></span> <span data-ttu-id="e8157-140">如果您想要讓使用者能夠參與多個在一段時間內持續的主題式交談，這項功能很有用。</span><span class="sxs-lookup"><span data-stu-id="e8157-140">Useful if you want users to be able to take part in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="e8157-141">規劃持續聊天伺服器主題有更多的資訊。</span><span class="sxs-lookup"><span data-stu-id="e8157-141">There's more information at the Planning for Persistent Chat Server topic.</span></span>

- <span data-ttu-id="e8157-142">監控程式.</span><span class="sxs-lookup"><span data-stu-id="e8157-142">Monitoring.</span></span> <span data-ttu-id="e8157-143">用來支援音訊/視頻（A/V）體驗品質（QoE）的資料收集，以及在您的部署中呼叫企業語音和 A/V 會議的詳細資料錄製（CDR）。</span><span class="sxs-lookup"><span data-stu-id="e8157-143">Used to support data collection for audio/video (A/V) Quality of Experience (QoE) and call detail recording (CDR) for Enterprise Voice and A/V conferences in your deployment.</span></span> <span data-ttu-id="e8157-144">我們將在規劃監視主題中詳細討論。</span><span class="sxs-lookup"><span data-stu-id="e8157-144">We discuss it in detail at the Planning for Monitoring topic.</span></span>

- <span data-ttu-id="e8157-145">主管或主管池。</span><span class="sxs-lookup"><span data-stu-id="e8157-145">Director or Director pool.</span></span> <span data-ttu-id="e8157-146">不需要，但如果您想要改善復原能力，並讓商務用 Skype 使用者要求重新導向至使用者的主區，則此方法很有用。</span><span class="sxs-lookup"><span data-stu-id="e8157-146">Not required, but useful if you want to improve resiliency and enable redirection of Skype for Business user requests to the user's home pool.</span></span> <span data-ttu-id="e8157-147">如果您想要部署控制器，每個池最多可支援10個。</span><span class="sxs-lookup"><span data-stu-id="e8157-147">If you want to deploy Directors, a maximum of 10 per pool is supported.</span></span> <span data-ttu-id="e8157-148">如果這是您需要的專案，請務必繼續閱讀規劃主管主題。</span><span class="sxs-lookup"><span data-stu-id="e8157-148">If this is something you need, definitely continue reading at the Planning for Directors topic.</span></span>

- <span data-ttu-id="e8157-149">反向 proxy。</span><span class="sxs-lookup"><span data-stu-id="e8157-149">Reverse proxy.</span></span> <span data-ttu-id="e8157-150">這不是商務用 Skype Server 元件，但如果您想要支援同盟使用者的網頁內容共用，如果您想要支援行動流量，如果您的遠端使用者想要使用通訊錄、加入會議等，這就是您要的問題。想要在您的環境中使用。</span><span class="sxs-lookup"><span data-stu-id="e8157-150">This isn't a Skype for Business Server component, but if you want to support the sharing of web content for federated users, if you intend to support Mobility traffic, if your remote users want to use the address book, join meetings, and so on, this is something you'll want to have in your environment.</span></span> <span data-ttu-id="e8157-151">當您準備好時，請參閱設定反向 proxy 伺服器主題，以取得更多詳細資料。</span><span class="sxs-lookup"><span data-stu-id="e8157-151">There's a Setting up Reverse proxy server topic you can check out for more details, when you're ready.</span></span>

<span data-ttu-id="e8157-152">以下提供這些伺服器之 collocation 的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="e8157-152">Additional information on collocation for these servers can be found below.</span></span>

<span data-ttu-id="e8157-153">部署在您中央網站的所有前端池和標準版伺服器，假設您已部署下列各項：</span><span class="sxs-lookup"><span data-stu-id="e8157-153">All the Front End pools and Standard Edition servers deployed at your central site share the following, assuming you've deployed them:</span></span>

||||
|:-----|:-----|:-----|
|<span data-ttu-id="e8157-154">主管或主管池</span><span class="sxs-lookup"><span data-stu-id="e8157-154">Director or Director pool</span></span>  <br/> |<span data-ttu-id="e8157-155">獨立的中繼伺服器或轉送伺服器池</span><span class="sxs-lookup"><span data-stu-id="e8157-155">Stand-alone Mediation Server or Mediation Server pool</span></span>  <br/> |<span data-ttu-id="e8157-156">Office Web Apps 伺服器</span><span class="sxs-lookup"><span data-stu-id="e8157-156">Office Web Apps Server</span></span>  <br/> |
|<span data-ttu-id="e8157-157">Edge 伺服器或 Edge 池</span><span class="sxs-lookup"><span data-stu-id="e8157-157">Edge Server or Edge pool</span></span>  <br/> |<span data-ttu-id="e8157-158">持續聊天伺服器或持久聊天伺服器池</span><span class="sxs-lookup"><span data-stu-id="e8157-158">Persistent Chat Server or Persistent Chat Server pool</span></span>  <br/> |<span data-ttu-id="e8157-159">監視</span><span class="sxs-lookup"><span data-stu-id="e8157-159">Monitoring</span></span>  <br/> |

<span data-ttu-id="e8157-160">此清單中的 Exchange 整合訊息（UM）伺服器在哪裡？</span><span class="sxs-lookup"><span data-stu-id="e8157-160">Where is Exchange Unified Messaging (UM) Server in this list?</span></span> <span data-ttu-id="e8157-161">當然，如果您想要整合 Exchange UM，但它不是商務用 Skype Server 網站的元件，請務必將它與商務用 Skype Server 搭配使用，因此我們不會在此提及。</span><span class="sxs-lookup"><span data-stu-id="e8157-161">Well, you can certainly use it with Skype for Business Server if you want to integrate with Exchange UM, but it's not a component of the Skype for Business Server site, so we're not mentioning it here.</span></span>

<span data-ttu-id="e8157-162">您可能打算使用多個中央網站，如果是這樣，他們就可以共用下列伺服器和角色（如果它們已部署在您的中央網站上）：</span><span class="sxs-lookup"><span data-stu-id="e8157-162">You may be planning to have multiple central site, and if that's so, they can share the following servers and roles, if they're deployed on your central site:</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="e8157-163">獨立的中繼伺服器或轉送伺服器池</span><span class="sxs-lookup"><span data-stu-id="e8157-163">Stand-alone Mediation Server or Mediation Server pool</span></span>  <br/> |<span data-ttu-id="e8157-164">Edge 伺服器或 Edge 池</span><span class="sxs-lookup"><span data-stu-id="e8157-164">Edge Server or Edge pool</span></span>  <br/> |
|<span data-ttu-id="e8157-165">持續聊天伺服器或持久聊天伺服器池</span><span class="sxs-lookup"><span data-stu-id="e8157-165">Persistent Chat Server or Persistent Chat Server pool</span></span>  <br/> |<span data-ttu-id="e8157-166">監視</span><span class="sxs-lookup"><span data-stu-id="e8157-166">Monitoring</span></span>  <br/> |

<span data-ttu-id="e8157-167">就像最後一個清單一樣，我們不會在這裡包含 Exchange UM 伺服器，因為它不是商務用 Skype Server 部署的一部分，但在這裡也會位於同一個類別中。</span><span class="sxs-lookup"><span data-stu-id="e8157-167">Just like the last list, we aren't including the Exchange UM Server here because it's not part of the Skype for Business Server deployment, but it falls into the same category here, too.</span></span>

<span data-ttu-id="e8157-168">當然，還有一些其他元件和選項可進入部署。</span><span class="sxs-lookup"><span data-stu-id="e8157-168">There are some other components and options that go into deployments, of course.</span></span>

|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e8157-169">道</span><span class="sxs-lookup"><span data-stu-id="e8157-169">Firewalls</span></span>  <br/> |<span data-ttu-id="e8157-170">PSTN 閘道（如果您部署企業語音</span><span class="sxs-lookup"><span data-stu-id="e8157-170">PSTN gateways (if you deploy Enterprise Voice</span></span>  <br/> |<span data-ttu-id="e8157-171">Exchange UM 伺服器（如果您想要與 Exchange UM 整合）</span><span class="sxs-lookup"><span data-stu-id="e8157-171">Exchange UM Server (if you want to integrate with Exchange UM)</span></span>  <br/> |<span data-ttu-id="e8157-172">DNS 負載平衡</span><span class="sxs-lookup"><span data-stu-id="e8157-172">DNS load balancing</span></span>  <br/> |
|<span data-ttu-id="e8157-173">硬體負載平衡器</span><span class="sxs-lookup"><span data-stu-id="e8157-173">Hardware load balancers</span></span>  <br/> |<span data-ttu-id="e8157-174">SQL Server 資料庫</span><span class="sxs-lookup"><span data-stu-id="e8157-174">SQL Server databases</span></span>  <br/> |<span data-ttu-id="e8157-175">檔案共用</span><span class="sxs-lookup"><span data-stu-id="e8157-175">File shares</span></span>  <br/> ||

## <a name="server-roles"></a><span data-ttu-id="e8157-176">伺服器角色</span><span class="sxs-lookup"><span data-stu-id="e8157-176">Server roles</span></span>

<span data-ttu-id="e8157-177">每個執行商務用 Skype 伺服器的伺服器都會執行一或多個伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="e8157-177">Each server running Skype for Business Server runs one or more server roles.</span></span> <span data-ttu-id="e8157-178">伺服器角色是該伺服器所提供的一組商務用 Skype 伺服器功能。</span><span class="sxs-lookup"><span data-stu-id="e8157-178">A server role is a defined set of Skype for Business Server functionalities provided by that server.</span></span> <span data-ttu-id="e8157-179">您不需要在您的網路中部署所有可用的伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="e8157-179">You don't need to deploy all available server roles in your network.</span></span> <span data-ttu-id="e8157-180">只安裝包含所需功能的伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="e8157-180">Install only the server roles that contain the functionality that you want.</span></span>

<span data-ttu-id="e8157-181">針對大部分的伺服器角色，如需可伸縮性和高可用性，您可以將多個伺服器的 pool 部署在執行相同的伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="e8157-181">For most server roles, for scalability and high availability you can deploy pools of multiple servers all running the same server role.</span></span> <span data-ttu-id="e8157-182">池中的每個伺服器都必須執行相同的伺服器角色或角色。</span><span class="sxs-lookup"><span data-stu-id="e8157-182">Each server in a pool must run an identical server role or roles.</span></span> <span data-ttu-id="e8157-183">針對商務用 Skype Server 中的大部分類型的 pool，您必須部署負載平衡器，以便在池中的各個伺服器之間散佈流量。</span><span class="sxs-lookup"><span data-stu-id="e8157-183">For most types of pools in Skype for Business Server, you must deploy a load balancer to spread traffic between the various servers in the pool.</span></span> <span data-ttu-id="e8157-184">商務用 Skype 伺服器支援網域名稱系統（DNS）負載平衡與硬體負載平衡器。</span><span class="sxs-lookup"><span data-stu-id="e8157-184">Skype for Business Server supports both Domain Name System (DNS) load balancing and hardware load balancers.</span></span>

### <a name="front-end-server-and-back-end-server"></a><span data-ttu-id="e8157-185">前端伺服器和後端伺服器</span><span class="sxs-lookup"><span data-stu-id="e8157-185">Front End Server and Back End Server</span></span>

<span data-ttu-id="e8157-186">在商務用 Skype Server Enterprise Edition 中，前端伺服器是核心伺服器角色，並執行許多基本的商務用 Skype 伺服器功能。</span><span class="sxs-lookup"><span data-stu-id="e8157-186">In Skype for Business Server Enterprise Edition, the Front End Server is the core server role, and runs many basic Skype for Business Server functions.</span></span> <span data-ttu-id="e8157-187">前端伺服器（以及後端伺服器）是任何商務用 Skype Server Enterprise Edition 部署所需的伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="e8157-187">The Front End Server, along with the Back End Servers, are the only server roles required to be in any Skype for Business Server Enterprise Edition deployment.</span></span>

<span data-ttu-id="e8157-188">[前端] 池是一組前端伺服器（配置相同），共同作業為使用者群組提供服務。</span><span class="sxs-lookup"><span data-stu-id="e8157-188">A Front End pool is a set of Front End Servers, configured identically, that work together to provide services for a common group of users.</span></span> <span data-ttu-id="e8157-189">多台執行相同角色的伺服器池提供可伸縮性和容錯移轉功能。</span><span class="sxs-lookup"><span data-stu-id="e8157-189">A pool of multiple servers running the same role provides scalability and failover capability.</span></span>

<span data-ttu-id="e8157-190">前端伺服器包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="e8157-190">The Front End Server includes the following:</span></span>

- <span data-ttu-id="e8157-191">使用者驗證與註冊。</span><span class="sxs-lookup"><span data-stu-id="e8157-191">User authentication and registration.</span></span>

- <span data-ttu-id="e8157-192">目前狀態資訊與連絡人卡片 exchange。</span><span class="sxs-lookup"><span data-stu-id="e8157-192">Presence information and contact card exchange.</span></span>

- <span data-ttu-id="e8157-193">通訊錄服務與通訊群組清單展開。</span><span class="sxs-lookup"><span data-stu-id="e8157-193">Address book services and distribution list expansion.</span></span>

- <span data-ttu-id="e8157-194">IM 功能，包括多方 IM 會議。</span><span class="sxs-lookup"><span data-stu-id="e8157-194">IM functionality, including multiparty IM conferences.</span></span>

- <span data-ttu-id="e8157-195">網路會議、PSTN 電話撥入式會議及 A/V 會議（如果已部署）。</span><span class="sxs-lookup"><span data-stu-id="e8157-195">Web conferencing, PSTN Dial-in conferencing and A/V conferencing (if deployed).</span></span>

- <span data-ttu-id="e8157-196">針對商務用 Skype Server 隨附的兩個應用程式（例如，會議助理與回應群組應用程式）和協力廠商應用程式的應用程式託管。</span><span class="sxs-lookup"><span data-stu-id="e8157-196">Application hosting, for both applications included with Skype for Business Server (for example, Conferencing Attendant and Response Group application), and third-party applications.</span></span>

- <span data-ttu-id="e8157-197">您也可以選擇監視，以收集通話詳細資料記錄（CDRs）的使用方式資訊，並呼叫錯誤記錄（Cer）。</span><span class="sxs-lookup"><span data-stu-id="e8157-197">Optionally, Monitoring, to collect usage information in the form of call detail records (CDRs) and call error records (CERs).</span></span> <span data-ttu-id="e8157-198">此資訊提供有關透過企業語音通話和 A/V 會議來遍歷您網路之媒體質量（音訊與影片）的統計資料。</span><span class="sxs-lookup"><span data-stu-id="e8157-198">This information provides metrics about the quality of the media (audio and video) traversing your network for both Enterprise Voice calls and A/V conferences.</span></span>

- <span data-ttu-id="e8157-199">網頁元件（例如網頁排程程式及加入啟動器）支援的 web 工作。</span><span class="sxs-lookup"><span data-stu-id="e8157-199">Web components to supported web-based tasks such as web scheduler and join launcher.</span></span>

- <span data-ttu-id="e8157-200">您可以選擇性地封存 IM 通訊與會議內容，以符合合規性的原因。</span><span class="sxs-lookup"><span data-stu-id="e8157-200">Optionally, Archiving, to archive IM communications and meeting content for compliance reasons.</span></span> <span data-ttu-id="e8157-201">如需詳細資訊，請參閱規劃檔中的[存檔規劃](https://technet.microsoft.com/library/898b83c1-007b-43be-9484-08fe49c10951.aspx)。</span><span class="sxs-lookup"><span data-stu-id="e8157-201">For details, see [Planning for Archiving](https://technet.microsoft.com/library/898b83c1-007b-43be-9484-08fe49c10951.aspx) in the Planning documentation.</span></span>

    <span data-ttu-id="e8157-202">在 Lync Server 2010 和早期版本中，監視及封存是獨立的伺服器角色，而不是在前端伺服器上 collocated。</span><span class="sxs-lookup"><span data-stu-id="e8157-202">In Lync Server 2010 and prior versions, Monitoring and Archiving were separate server roles, not collocated on Front End Server.</span></span>

- <span data-ttu-id="e8157-203">您也可以選擇是否已啟用持續聊天、聊天室管理的持續聊天 Web 服務和檔案上傳/下載的持續聊天 Web 服務。</span><span class="sxs-lookup"><span data-stu-id="e8157-203">Optionally, if Persistent chat is enabled, Persistent Chat Web Services for Chat Room Management and Persistent Chat Web Services for File Upload/Download.</span></span>

<span data-ttu-id="e8157-204">前端池也是使用者和會議資料的主要存儲區。</span><span class="sxs-lookup"><span data-stu-id="e8157-204">Front End Pools are also the primary store for user and conference data.</span></span> <span data-ttu-id="e8157-205">每個使用者的相關資訊會在池中的三個前端伺服器之間複製，並在後端伺服器上備份。</span><span class="sxs-lookup"><span data-stu-id="e8157-205">Information about each user is replicated among three Front End Servers in the pool, and backed up on the Back End Servers.</span></span>

<span data-ttu-id="e8157-206">此外，部署中的一個前端伺服器也會執行中央管理伺服器，該伺服器會將基本配置資料管理並部署到執行商務用 Skype Server 的所有伺服器。</span><span class="sxs-lookup"><span data-stu-id="e8157-206">Additionally, one Front End Server in the deployment also runs the Central Management Server, which manages and deploys basic configuration data to all servers running Skype for Business Server.</span></span> <span data-ttu-id="e8157-207">中央管理伺服器也提供 Lync Server 管理命令介面和檔案傳輸功能。</span><span class="sxs-lookup"><span data-stu-id="e8157-207">The Central Management Server also provides Lync Server Management Shell and file transfer capabilities.</span></span>

<span data-ttu-id="e8157-208">後端伺服器是執行 Microsoft SQL Server 的資料庫伺服器，可為前端池提供資料庫服務。</span><span class="sxs-lookup"><span data-stu-id="e8157-208">The Back End Servers are database servers running Microsoft SQL Server that provide the database services for the Front End pool.</span></span> <span data-ttu-id="e8157-209">後端伺服器可做為池使用者與會議資料的備份儲存，而且是其他資料庫（例如回應群組資料庫）的主要存儲區。</span><span class="sxs-lookup"><span data-stu-id="e8157-209">The Back End Servers serve as backup stores for the pool's user and conference data, and are the primary stores for other databases such as the Response Group database.</span></span> <span data-ttu-id="e8157-210">您可以使用單一後端伺服器，但在進行容錯移轉時，建議[在商務用 Skype server 中使用後端伺服器高可用性](../high-availability-and-disaster-recovery/back-end-server.md)。</span><span class="sxs-lookup"><span data-stu-id="e8157-210">You can have a single Back End Server, but [Back End Server high availability in Skype for Business Server](../high-availability-and-disaster-recovery/back-end-server.md) is recommended for failover.</span></span> <span data-ttu-id="e8157-211">後端伺服器不會執行任何商務用 Skype Server 軟體。</span><span class="sxs-lookup"><span data-stu-id="e8157-211">Back End Servers do not run any Skype for Business Server software.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e8157-212">我們不建議將商務用 Skype Server 資料庫與其他資料庫 collocating。</span><span class="sxs-lookup"><span data-stu-id="e8157-212">We do not recommend collocating Skype for Business Server databases with other databases.</span></span> <span data-ttu-id="e8157-213">如果您這麼做，可用性和效能可能會受到影響。</span><span class="sxs-lookup"><span data-stu-id="e8157-213">If you do so, availability and performance may be affected.</span></span>

> [!NOTE]
> <span data-ttu-id="e8157-214">在商務用 Skype Server 2015 中提供 SQL 鏡像，但商務用 Skype Server 2019 已不再支援。</span><span class="sxs-lookup"><span data-stu-id="e8157-214">SQL Mirroring is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="e8157-215">使用商務用 Skype Server 2019 時，AlwaysOn 可用性群組、AlwaysOn 容錯移轉叢集實例（FCI）和 SQL 容錯移轉叢集方法都是可取的。</span><span class="sxs-lookup"><span data-stu-id="e8157-215">The  AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering methods are preferred with Skype for Business Server 2019.</span></span>

<span data-ttu-id="e8157-216">儲存在後端伺服器資料庫中的資訊包含目前狀態資訊、使用者的連絡人清單、會議資料，包括所有目前會議狀態的永久性資料，以及會議排程資料。</span><span class="sxs-lookup"><span data-stu-id="e8157-216">Information stored in the Back End Server databases includes presence information, users' Contacts lists, conferencing data, including persistent data about the state of all current conferences, and conference scheduling data.</span></span>

### <a name="edge-server"></a><span data-ttu-id="e8157-217">Edge 伺服器</span><span class="sxs-lookup"><span data-stu-id="e8157-217">Edge Server</span></span>

<span data-ttu-id="e8157-218">Edge 伺服器可讓您的使用者與組織防火牆以外的使用者進行通訊及共同作業。</span><span class="sxs-lookup"><span data-stu-id="e8157-218">Edge Server enables your users to communicate and collaborate with users outside the organization's firewalls.</span></span> <span data-ttu-id="e8157-219">這些外部使用者可以包含組織自己的使用者，這些使用者目前正在異地作業、同盟夥伴組織的使用者，以及受邀加入在您的商務用 Skype Server 部署中舉行會議的外部使用者。</span><span class="sxs-lookup"><span data-stu-id="e8157-219">These external users can include the organization's own users who are currently working offsite, users from federated partner organizations, and outside users who have been invited to join conferences hosted on your Skype for Business Server deployment.</span></span>

<span data-ttu-id="e8157-220">部署 Edge 伺服器也會啟用行動裝置服務，支援行動裝置上的 Lync 功能。</span><span class="sxs-lookup"><span data-stu-id="e8157-220">Deploying Edge Server also enables mobility services, which supports Lync functionality on mobile devices.</span></span> <span data-ttu-id="e8157-221">使用者可以使用支援的 Apple iOS、Android、Windows Phone 或 Nokia 行動裝置來執行諸如傳送和接收立即訊息、查看連絡人及查看目前狀態等活動。</span><span class="sxs-lookup"><span data-stu-id="e8157-221">Users can use supported Apple iOS, Android, Windows Phone, or Nokia mobile devices to perform activities such as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span> <span data-ttu-id="e8157-222">此外，行動裝置支援一些企業語音功能，例如按一下以加入會議、透過工作撥打電話、單一號碼達到、語音信箱及未接來電。</span><span class="sxs-lookup"><span data-stu-id="e8157-222">In addition, mobile devices support some Enterprise Voice features, such as click to join a conference, Call via Work, single number reach, voice mail, and missed calls.</span></span> <span data-ttu-id="e8157-223">行動裝置功能也支援不支援在背景中執行之應用程式之行動裝置的推播通知。</span><span class="sxs-lookup"><span data-stu-id="e8157-223">The mobility feature also supports push notifications for mobile devices that do not support applications running in the background.</span></span> <span data-ttu-id="e8157-224">推播通知是傳送給行動裝置的通知，在行動應用程式處於非使用中時，發生該事件。</span><span class="sxs-lookup"><span data-stu-id="e8157-224">A push notification is a notification that is sent to a mobile device about an event that occurs while a mobile application is inactive.</span></span>

<span data-ttu-id="e8157-225">Edge 伺服器也包含完全整合的可擴展訊息和目前狀態通訊協定（XMPP） proxy，並包含在前端伺服器上的 XMPP 閘道。</span><span class="sxs-lookup"><span data-stu-id="e8157-225">Edge Servers also include a fully-integrated Extensible Messaging and Presence Protocol (XMPP) proxy, with an XMPP gateway included on Front End Servers.</span></span> <span data-ttu-id="e8157-226">您可以設定這些 XMPP 元件，讓您的商務用 Skype 伺服器使用者可以新增來自以 XMPP 為基礎的合作夥伴的連絡人，以取得立即訊息和目前狀態。</span><span class="sxs-lookup"><span data-stu-id="e8157-226">You can configure these XMPP components to enable your Skype for Business Server users to add contacts from XMPP-based partners for instant messaging and presence.</span></span>

> [!NOTE]
> <span data-ttu-id="e8157-227">XMPP 閘道和 proxy 可在商務用 Skype Server 2015 中使用，但商務用 Skype Server 2019 已不再支援。</span><span class="sxs-lookup"><span data-stu-id="e8157-227">XMPP Gateways and proxies are available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="e8157-228">如需詳細資訊，請參閱[遷移 XMPP 同盟](../../../SfBServer2019/migration/migrating-xmpp-federation.md)。</span><span class="sxs-lookup"><span data-stu-id="e8157-228">See [Migrating XMPP federation](../../../SfBServer2019/migration/migrating-xmpp-federation.md) for more information.</span></span>

### <a name="mediation-server"></a><span data-ttu-id="e8157-229">中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="e8157-229">Mediation Server</span></span>

<span data-ttu-id="e8157-230">中繼伺服器是用於實現企業語音、通話和電話撥入式會議所需的元件。</span><span class="sxs-lookup"><span data-stu-id="e8157-230">Mediation Server is a necessary component for implementing Enterprise Voice, Call Via Work, and dial-in conferencing.</span></span> <span data-ttu-id="e8157-231">中繼伺服器會轉譯信號，在某些設定中，在內部商務用 Skype 伺服器基礎結構與公用交換式電話網絡（PSTN）閘道、IP PBX 或會話初始通訊協定（SIP）幹線之間的媒體。</span><span class="sxs-lookup"><span data-stu-id="e8157-231">Mediation Server translates signaling, and, in some configurations, media between your internal Skype for Business Server infrastructure and a public switched telephone network (PSTN) gateway, IP-PBX, or a Session Initiation Protocol (SIP) trunk.</span></span> <span data-ttu-id="e8157-232">您可以在與前臺伺服器相同的伺服器上執行轉送服務伺服器 collocated，或將它分割成獨立的中繼伺服器池。</span><span class="sxs-lookup"><span data-stu-id="e8157-232">You can run Mediation Server collocated on the same server as Front End Server, or separated into a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="e8157-233">如需詳細資訊，請參閱[商務用 Skype server 中的中繼伺服器元件](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md)。</span><span class="sxs-lookup"><span data-stu-id="e8157-233">For details, see [Mediation Server component in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md).</span></span>

### <a name="video-interop-server"></a><span data-ttu-id="e8157-234">視訊互通性伺服器</span><span class="sxs-lookup"><span data-stu-id="e8157-234">Video Interop Server</span></span>

<span data-ttu-id="e8157-235">影片交互操作伺服器是商務用 Skype Server 2015 的新角色。</span><span class="sxs-lookup"><span data-stu-id="e8157-235">Video Interop Server is a new role as of Skype for Business Server 2015.</span></span> <span data-ttu-id="e8157-236">它可讓您將商務用 Skype Server 部署與特定的協力廠商 VTC （Video Teleconferencing 系統）解決方案整合。</span><span class="sxs-lookup"><span data-stu-id="e8157-236">It enables you to integrate your Skype for Business Server deployment with certain third-party VTC (Video Teleconferencing System) solutions.</span></span> <span data-ttu-id="e8157-237">VIS 充當協力廠商電話會議系統與商務用 Skype Server 部署之間的媒介。</span><span class="sxs-lookup"><span data-stu-id="e8157-237">A VIS acts as an intermediary between a 3rd party teleconference system and a Skype for Business Server deployment.</span></span> <span data-ttu-id="e8157-238">在這個版本中，VIS 的重點是使用 Cisco/Tandberg 視頻系統進行互通性。</span><span class="sxs-lookup"><span data-stu-id="e8157-238">For this release, VIS is focused on interoperability with Cisco/Tandberg video systems.</span></span>

<span data-ttu-id="e8157-239">如需詳細資訊，請參閱[在商務用 Skype server 中規劃影片互通性伺服器](../../plan-your-deployment/video-interop-server.md)。</span><span class="sxs-lookup"><span data-stu-id="e8157-239">For details, see [Plan for Video Interop Server in Skype for Business Server](../../plan-your-deployment/video-interop-server.md).</span></span>

### <a name="director"></a><span data-ttu-id="e8157-240">Director</span><span class="sxs-lookup"><span data-stu-id="e8157-240">Director</span></span>

<span data-ttu-id="e8157-241">控制器可以驗證商務用 Skype Server 使用者要求，但不會提供使用者帳戶或提供目前狀態或會議服務。</span><span class="sxs-lookup"><span data-stu-id="e8157-241">Directors can authenticate Skype for Business Server user requests, but they do not home user accounts or provide presence or conferencing services.</span></span> <span data-ttu-id="e8157-242">在能讓外部使用者存取的部署中加強安全性時，控制器是最實用的。</span><span class="sxs-lookup"><span data-stu-id="e8157-242">Directors are most useful to enhance security in deployments that enable external user access.</span></span> <span data-ttu-id="e8157-243">Director 可以在將要求傳送到內部伺服器前進行驗證。</span><span class="sxs-lookup"><span data-stu-id="e8157-243">The Director can authenticate requests before sending them on to internal servers.</span></span> <span data-ttu-id="e8157-244">在拒絕服務攻擊的情況下，攻擊會以控制器為結束，而且不會到達前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="e8157-244">In the case of a denial-of-service attack, the attack ends with the Director and does not reach the Front End servers.</span></span>

### <a name="persistent-chat-server-roles"></a><span data-ttu-id="e8157-245">持續聊天伺服器角色</span><span class="sxs-lookup"><span data-stu-id="e8157-245">Persistent Chat Server Roles</span></span>

> [!NOTE]
> <span data-ttu-id="e8157-246">商務用 Skype Server 2015 提供持續聊天，但商務用 Skype Server 2019 已不再支援。</span><span class="sxs-lookup"><span data-stu-id="e8157-246">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="e8157-247">團隊中提供了相同的功能。</span><span class="sxs-lookup"><span data-stu-id="e8157-247">The same functionality is available in Teams.</span></span> <span data-ttu-id="e8157-248">如需詳細資訊，請參閱[Microsoft 團隊升級快速](/microsoftteams/upgrade-start-here)入門。</span><span class="sxs-lookup"><span data-stu-id="e8157-248">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="e8157-249">如果您需要使用持續聊天，您可以選擇將需要此功能的使用者遷移至小組，或繼續使用商務用 Skype Server 2015。</span><span class="sxs-lookup"><span data-stu-id="e8157-249">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span>

<span data-ttu-id="e8157-250">持續聊天可讓使用者參與多方、在一段時間內保持的、以主題為基礎的交談。</span><span class="sxs-lookup"><span data-stu-id="e8157-250">Persistent chat enables users to participate in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="e8157-251">持續聊天前端伺服器會執行持續聊天服務。</span><span class="sxs-lookup"><span data-stu-id="e8157-251">The Persistent Chat Front End Server runs the persistent chat service.</span></span> <span data-ttu-id="e8157-252">持續式聊天后端伺服器會儲存聊天記錄資料，以及類別和聊天室的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="e8157-252">The Persistent Chat Back End Server stores the chat history data, and information about categories and chat rooms.</span></span> <span data-ttu-id="e8157-253">選用的持續性聊天規範後端伺服器可以儲存聊天內容和相容性事件，以符合合規性的目的。</span><span class="sxs-lookup"><span data-stu-id="e8157-253">The optional Persistent Chat Compliance Back End Server can store the chat content and compliance events for the purpose of compliance.</span></span>

<span data-ttu-id="e8157-254">執行商務用 Skype Server 標準版的伺服器也可以在同一個伺服器上執行持續聊天 collocated。</span><span class="sxs-lookup"><span data-stu-id="e8157-254">Servers running Skype for Business Server Standard Edition can also run Persistent chat collocated on the same server.</span></span> <span data-ttu-id="e8157-255">您無法 collocate 與企業版前端伺服器的永久聊天前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="e8157-255">You cannot collocate the Persistent Chat Front End Server with Enterprise Edition Front End Server.</span></span>

<span data-ttu-id="e8157-256">如需詳細資訊，請參閱[在商務用 Skype server 2015 中規劃持久聊天伺服器](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)。</span><span class="sxs-lookup"><span data-stu-id="e8157-256">For details, see [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).</span></span>

## <a name="high-availability-and-disaster-recovery-support"></a><span data-ttu-id="e8157-257">高可用性和災害復原支援</span><span class="sxs-lookup"><span data-stu-id="e8157-257">High availability and disaster recovery support</span></span>

<span data-ttu-id="e8157-258">商務用 Skype 伺服器透過 [彙集]，透過伺服器冗余提供高可用性。</span><span class="sxs-lookup"><span data-stu-id="e8157-258">Skype for Business Server provides high availability by server redundancy via pooling.</span></span> <span data-ttu-id="e8157-259">如果執行特定伺服器角色的伺服器失敗，則池中執行相同角色的其他伺服器會載入該伺服器。</span><span class="sxs-lookup"><span data-stu-id="e8157-259">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="e8157-260">這適用于前端伺服器、邊緣伺服器、轉送伺服器和控制器。</span><span class="sxs-lookup"><span data-stu-id="e8157-260">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span>

<span data-ttu-id="e8157-261">商務用 Skype 伺服器也會透過啟用池配對來提供災害復原措施。</span><span class="sxs-lookup"><span data-stu-id="e8157-261">Skype for Business Server also provides disaster recovery measures by enabling pool pairing.</span></span> <span data-ttu-id="e8157-262">如果您部署這個拓朴，您將會指定一組前端池，其中每個池都位於另一個資料中心，且位於不同的地理區域中。</span><span class="sxs-lookup"><span data-stu-id="e8157-262">If you deploy this topology, you will designate pairs of Front End pools, with each pool in a pair located in a separate data center, and in a separate geographical area.</span></span> <span data-ttu-id="e8157-263">如果有一個池或網站停機，您可以重新導向該池的使用者，以使用該集中的其他池，並最少中斷服務。</span><span class="sxs-lookup"><span data-stu-id="e8157-263">If one pool or site goes down, you can redirect the users of that pool to use the other pool in the pair, with minimal interruption of service.</span></span>

<span data-ttu-id="e8157-264">商務用 Skype 伺服器也支援後端伺服器高可用性的數個選項。</span><span class="sxs-lookup"><span data-stu-id="e8157-264">Skype for Business Server also supports several options for Back End Server high availability.</span></span> <span data-ttu-id="e8157-265">其中包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="e8157-265">These include the following:</span></span>

- <span data-ttu-id="e8157-266">資料庫鏡像</span><span class="sxs-lookup"><span data-stu-id="e8157-266">Database mirroring</span></span>

- <span data-ttu-id="e8157-267">AlwaysOn 可用性群組</span><span class="sxs-lookup"><span data-stu-id="e8157-267">AlwaysOn Availability Groups</span></span>

- <span data-ttu-id="e8157-268">AlwaysOn 容錯移轉叢集實例（FCI）</span><span class="sxs-lookup"><span data-stu-id="e8157-268">AlwaysOn Failover Cluster Instances (FCI)</span></span>

- <span data-ttu-id="e8157-269">SQL 容錯移轉叢集</span><span class="sxs-lookup"><span data-stu-id="e8157-269">SQL failover clustering</span></span>

<span data-ttu-id="e8157-270">如需有關池配對及後端伺服器高可用性的詳細資料，請參閱[在商務用 Skype Server 中規劃高可用性和災難](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)復原。</span><span class="sxs-lookup"><span data-stu-id="e8157-270">For details about pool pairing and Back End Server high availability, see [Plan for high availability and disaster recovery in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>

## <a name="server-collocation-in-skype-for-business-server"></a><span data-ttu-id="e8157-271">商務用 Skype Server 中的 [伺服器 collocation]</span><span class="sxs-lookup"><span data-stu-id="e8157-271">Server collocation in Skype for Business Server</span></span>

<span data-ttu-id="e8157-272">我們已使用過字詞 collocate，但這代表什麼意思？</span><span class="sxs-lookup"><span data-stu-id="e8157-272">We've used the term collocate already, but what does this mean?</span></span> <span data-ttu-id="e8157-273">商務用 Skype Server 可讓您找出在同一台伺服器（也就是 collocation 或不同的伺服器）上的部分伺服器角色和功能，但在您開始時可能會造成混淆，以及您是執行標準版還是企業版伺服器部署（它們各自都有自己的規則）。</span><span class="sxs-lookup"><span data-stu-id="e8157-273">Skype for Business Server allows you to locate some server roles and features on the same server, which is collocation, or on different servers, but it can be confusing when you're starting out, and whether you're doing a Standard Edition or Enterprise Edition server deployment (they each come with their own rules).</span></span> <span data-ttu-id="e8157-274">為了協助您的規劃，我們在標準版伺服器部署和企業版的前端池部署中包含伺服器 collocation （在大多數情況下，這項資訊是完全相同的，而且在哪裡有所不同，就是特別指出的）。</span><span class="sxs-lookup"><span data-stu-id="e8157-274">To help with your planning, we're including server collocation in Standard Edition server deployments and Enterprise Edition Front End pool deployments (in most cases this information is identical, and where it's different, it's called out specifically).</span></span>

### <a name="collocation-of-server-roles"></a><span data-ttu-id="e8157-275">伺服器角色的 Collocation</span><span class="sxs-lookup"><span data-stu-id="e8157-275">Collocation of server roles</span></span>

<span data-ttu-id="e8157-276">標準版伺服器具有下列角色 collocated （不過還需要進行其他設定），而在企業版前端池中，此角色可以是 collocated，或部署到個別的伺服器：</span><span class="sxs-lookup"><span data-stu-id="e8157-276">The Standard Edition server has the following role collocated (additional configuration is required though), while in the Enterprise Edition Front End pool, this role can be collocated, or deployed to a separate server:</span></span>

- <span data-ttu-id="e8157-277">仲介</span><span class="sxs-lookup"><span data-stu-id="e8157-277">Mediation</span></span>

<span data-ttu-id="e8157-278">每個伺服器角色都必須部署在個別的伺服器上：</span><span class="sxs-lookup"><span data-stu-id="e8157-278">These server roles must each be deployed on a separate server:</span></span>

- <span data-ttu-id="e8157-279">Director</span><span class="sxs-lookup"><span data-stu-id="e8157-279">Director</span></span>

- <span data-ttu-id="e8157-280">左邊</span><span class="sxs-lookup"><span data-stu-id="e8157-280">Edge</span></span>

- <span data-ttu-id="e8157-281">視訊互通性伺服器</span><span class="sxs-lookup"><span data-stu-id="e8157-281">Video Interop Server</span></span>

- <span data-ttu-id="e8157-282">Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="e8157-282">Office Web Apps</span></span>

### <a name="databases"></a><span data-ttu-id="e8157-283">資料庫</span><span class="sxs-lookup"><span data-stu-id="e8157-283">Databases</span></span>

<span data-ttu-id="e8157-284">這是標準版伺服器部署與企業版伺服器池部署之間實際差異的區域，因此我們將提供兩個區段，後面再加上一些其他規則。</span><span class="sxs-lookup"><span data-stu-id="e8157-284">This is the area with real differences between Standard Edition server deployments and Enterprise Edition server pool deployments, so we'll have two sections below, followed by some additional rules for both.</span></span>

#### <a name="standard"></a><span data-ttu-id="e8157-285">標準</span><span class="sxs-lookup"><span data-stu-id="e8157-285">Standard</span></span>

<span data-ttu-id="e8157-286">因為 SQL Server Express 是在標準版伺服器上 collocated，而且無法移動，所以這相當簡單。</span><span class="sxs-lookup"><span data-stu-id="e8157-286">Since SQL Server Express is collocated on the Standard Edition server, and can't be moved, this is pretty straightforward.</span></span> <span data-ttu-id="e8157-287">此外，如果您在標準版伺服器上部署持久聊天伺服器，您也可以在標準版伺服器上 collocate 持續聊天和持續聊天合規性資料庫，但您不需要。</span><span class="sxs-lookup"><span data-stu-id="e8157-287">Furthermore, if you deploy Persistent Chat Server on a Standard Edition server, you're also able to collocate the Persistent Chat and the Persistent Chat compliance database on the Standard Edition server too, but you don't have to.</span></span>

> [!NOTE]
> <span data-ttu-id="e8157-288">商務用 Skype Server 2015 提供持續聊天，但商務用 Skype Server 2019 已不再支援。</span><span class="sxs-lookup"><span data-stu-id="e8157-288">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="e8157-289">團隊中提供了相同的功能。</span><span class="sxs-lookup"><span data-stu-id="e8157-289">The same functionality is available in Teams.</span></span> <span data-ttu-id="e8157-290">如需詳細資訊，請參閱[Microsoft 團隊升級快速](/microsoftteams/upgrade-start-here)入門。</span><span class="sxs-lookup"><span data-stu-id="e8157-290">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="e8157-291">如果您需要使用持續聊天，您可以選擇將需要此功能的使用者遷移至小組，或繼續使用商務用 Skype Server 2015。</span><span class="sxs-lookup"><span data-stu-id="e8157-291">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span>

<span data-ttu-id="e8157-292">這些不能在標準版 server 上 collocated，但可以在單一資料庫伺服器上繼續使用：</span><span class="sxs-lookup"><span data-stu-id="e8157-292">These can't be collocated on the Standard Edition server, but can go on a single database server of their own:</span></span>

- <span data-ttu-id="e8157-293">監控資料庫</span><span class="sxs-lookup"><span data-stu-id="e8157-293">Monitoring database</span></span>

- <span data-ttu-id="e8157-294">封存資料庫</span><span class="sxs-lookup"><span data-stu-id="e8157-294">Archiving database</span></span>

- <span data-ttu-id="e8157-295">企業版前端池的任何後端資料庫</span><span class="sxs-lookup"><span data-stu-id="e8157-295">Any back-end database for an Enterprise Edition Front End pool</span></span>

#### <a name="enterprise"></a><span data-ttu-id="e8157-296">級</span><span class="sxs-lookup"><span data-stu-id="e8157-296">Enterprise</span></span>

<span data-ttu-id="e8157-297">下列資料庫可以在同一個後端 SQL Server 上 collocated：</span><span class="sxs-lookup"><span data-stu-id="e8157-297">The following databases can be collocated on the same back end SQL Server:</span></span>

- <span data-ttu-id="e8157-298">後端資料庫</span><span class="sxs-lookup"><span data-stu-id="e8157-298">Back End database</span></span>

- <span data-ttu-id="e8157-299">監控資料庫</span><span class="sxs-lookup"><span data-stu-id="e8157-299">Monitoring database</span></span>

- <span data-ttu-id="e8157-300">封存資料庫</span><span class="sxs-lookup"><span data-stu-id="e8157-300">Archiving database</span></span>

- <span data-ttu-id="e8157-301">持續聊天資料庫</span><span class="sxs-lookup"><span data-stu-id="e8157-301">Persistent Chat database</span></span>

- <span data-ttu-id="e8157-302">持續聊天合規性資料庫</span><span class="sxs-lookup"><span data-stu-id="e8157-302">Persistent Chat compliance database</span></span>

#### <a name="both"></a><span data-ttu-id="e8157-303">同時</span><span class="sxs-lookup"><span data-stu-id="e8157-303">Both</span></span>

<span data-ttu-id="e8157-304">現在，當您 collocating 單一 SQL 實例中的商務用 Skype Server 資料庫，或同一 SQL Server 資料庫中的多個 SQL 實例時，還有一些其他規則：</span><span class="sxs-lookup"><span data-stu-id="e8157-304">Now, there are some additional rules to follow when collocating Skype for Business Server databases in a single SQL instance, or in multiple SQL instances in the same SQL Server database:</span></span>

- <span data-ttu-id="e8157-305">每個 SQL 實例只能包含企業版前端池的單一後端資料庫、單一監視資料庫、單一封存資料庫、單一持續式聊天資料庫，以及單一持續聊天合規性資料庫。</span><span class="sxs-lookup"><span data-stu-id="e8157-305">Each SQL instance can only contain a single back end database for an Enterprise Edition Front End pool, a single Monitoring database, a single Archiving database, a single Persistent Chat database, and a single Persistent Chat compliance database.</span></span>

- <span data-ttu-id="e8157-306">資料庫伺服器不支援一個以上的企業版前端池、一個伺服器執行封存、一個伺服器執行監視、單一持久性聊天資料庫，以及單一持續聊天合規性資料庫，但它可以支援其中一個專案，不論資料庫是使用相同的 SQL Server 實例，還是要使用不同的 SQL Server 實例。</span><span class="sxs-lookup"><span data-stu-id="e8157-306">The database server can't support more than one Enterprise Edition Front End pool, one server running Archiving, one server running Monitoring, a single Persistent Chat database, and a single Persistent Chat compliance database, but it can support one of each, regardless of whether the databases use the same instance of SQL Server or separate instances of SQL Server.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e8157-307">商務用 Skype Server 2015 提供持續聊天，但商務用 Skype Server 2019 已不再支援。</span><span class="sxs-lookup"><span data-stu-id="e8157-307">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="e8157-308">團隊中提供了相同的功能。</span><span class="sxs-lookup"><span data-stu-id="e8157-308">The same functionality is available in Teams.</span></span> <span data-ttu-id="e8157-309">如需詳細資訊，請參閱[Microsoft 團隊升級快速](/microsoftteams/upgrade-start-here)入門。</span><span class="sxs-lookup"><span data-stu-id="e8157-309">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="e8157-310">如果您需要使用持續聊天，您可以選擇將需要此功能的使用者遷移至小組，或繼續使用商務用 Skype Server 2015。</span><span class="sxs-lookup"><span data-stu-id="e8157-310">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span>

### <a name="file-shares"></a><span data-ttu-id="e8157-311">檔案共用</span><span class="sxs-lookup"><span data-stu-id="e8157-311">File shares</span></span>

<span data-ttu-id="e8157-312">檔案共用可以在不同的伺服器上，也可以在同一個伺服器上 collocate，就像下列任一或所有專案：</span><span class="sxs-lookup"><span data-stu-id="e8157-312">The file share can be on a separate server, or you can collocate it on the same server as any or all of the following:</span></span>

- <span data-ttu-id="e8157-313">資料庫伺服器，包括企業版頂層端池的後端伺服器</span><span class="sxs-lookup"><span data-stu-id="e8157-313">Database server, including the Back End Server of an Enterprise Edition Front End pool</span></span>

- <span data-ttu-id="e8157-314">監控資料庫</span><span class="sxs-lookup"><span data-stu-id="e8157-314">Monitoring database</span></span>

- <span data-ttu-id="e8157-315">封存資料庫</span><span class="sxs-lookup"><span data-stu-id="e8157-315">Archiving database</span></span>

- <span data-ttu-id="e8157-316">持續聊天資料庫</span><span class="sxs-lookup"><span data-stu-id="e8157-316">Persistent Chat database</span></span>

- <span data-ttu-id="e8157-317">持續聊天合規性資料庫</span><span class="sxs-lookup"><span data-stu-id="e8157-317">Persistent Chat compliance database</span></span>

> [!CAUTION]
> <span data-ttu-id="e8157-318">請注意，雖然您可以在這些伺服器上 collocate 檔案共用，但請務必注意，我們不建議您這麼做。</span><span class="sxs-lookup"><span data-stu-id="e8157-318">Note that while you can collocate the file share on these servers, it's vital to note that we don't recommend it.</span></span> <span data-ttu-id="e8157-319">如果您要與任何其他伺服器角色 collocating 檔案共用，請務必定期監視磁碟空間與效能問題。</span><span class="sxs-lookup"><span data-stu-id="e8157-319">If you're collocating the file share with any other server role, please make sure you're monitoring for disk space and performance issues on a regular basis.</span></span>

### <a name="keep-in-mind"></a><span data-ttu-id="e8157-320">切記</span><span class="sxs-lookup"><span data-stu-id="e8157-320">Keep in mind</span></span>

- <span data-ttu-id="e8157-321">您無法 collocate 反向 proxy 伺服器（不是商務用 Skype Server 元件），甚至可能不會在您的拓撲中。</span><span class="sxs-lookup"><span data-stu-id="e8157-321">You can't collocate a reverse proxy server, which isn't a Skype for Business Server component, and may not even be in your topology.</span></span> <span data-ttu-id="e8157-322">如果您想要支援共同處理共同使用者的網頁內容，您需要使用反向 proxy。</span><span class="sxs-lookup"><span data-stu-id="e8157-322">You'll need a reverse proxy if you want to support sharing of web content for federated users, among many other things.</span></span> <span data-ttu-id="e8157-323">如果您需要，請先設定貴組織中已供其他應用程式使用的現有反向 proxy 伺服器，以取得商務用 Skype 伺服器的反向 proxy 支援。</span><span class="sxs-lookup"><span data-stu-id="e8157-323">If you need to, go ahead and implement reverse proxy support for Skype for Business Server by configuring an existing reverse proxy server that's already in your organization that's being used by other applications.</span></span>

- <span data-ttu-id="e8157-324">您無法 collocate 任何 Exchange UM 元件或 SharePoint Server 元件（含任何商務用 Skype Server 角色）。</span><span class="sxs-lookup"><span data-stu-id="e8157-324">You can't collocate any Exchange UM component or SharePoint Server component with any Skype for Business Server role.</span></span>

## <a name="see-also"></a><span data-ttu-id="e8157-325">另請參閱</span><span class="sxs-lookup"><span data-stu-id="e8157-325">See also</span></span>

[<span data-ttu-id="e8157-326">商務用 Skype Server 的參考拓撲</span><span class="sxs-lookup"><span data-stu-id="e8157-326">Reference topologies for Skype for Business Server</span></span>](reference-topologies.md)
