---
title: 商務用 Skype Server 的拓撲基礎
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 摘要：選擇您的商務用 Skype 伺服器拓撲。 瞭解適用于商務用 Skype Server 的伺服器組合。
ms.openlocfilehash: 39a75de6162f51d5d838ace557a546db3500ac01
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103989"
---
# <a name="topology-basics-for-skype-for-business-server"></a><span data-ttu-id="38553-104">商務用 Skype Server 的拓撲基礎</span><span class="sxs-lookup"><span data-stu-id="38553-104">Topology Basics for Skype for Business Server</span></span>

<span data-ttu-id="38553-105">**摘要：** 選擇您的商務用 Skype 伺服器拓撲。</span><span class="sxs-lookup"><span data-stu-id="38553-105">**Summary:** Choose your topology for Skype for Business Server.</span></span> <span data-ttu-id="38553-106">瞭解適用于商務用 Skype Server 的伺服器組合。</span><span class="sxs-lookup"><span data-stu-id="38553-106">Learn about server collocation for Skype for Business Server.</span></span>

<span data-ttu-id="38553-107">準備其他任何專案之前，您會想要知道您在規劃商務用 Skype Server 的部署的正確拓撲。</span><span class="sxs-lookup"><span data-stu-id="38553-107">Before preparing anything else, you'll want to know you're planning for the right topology for your deployment of Skype for Business Server.</span></span> <span data-ttu-id="38553-108">您必須決定的第一件事是，如果您要部署商務用 Skype Server 的內部部署，或是您想要將此功能與混合式部署中的商務用 Skype Server Online 部署結合使用。</span><span class="sxs-lookup"><span data-stu-id="38553-108">The first thing you need to decide is if you're going to have an on-premises deployment of Skype for Business Server, or if you're going to combine this with a Skype for Business Server Online deployment in a Hybrid deployment.</span></span> <span data-ttu-id="38553-109">無論是哪一種方式，您都會想進一步閱讀，因為我們會在這裡詳述內部部署拓撲，但混合式詳細資料會記錄在其專屬的區段中。</span><span class="sxs-lookup"><span data-stu-id="38553-109">Either way, you're going to want to read further, as we'll detail the on-premises topologies here, but the Hybrid details are documented in their own section.</span></span>

<span data-ttu-id="38553-110">您也可以在 [商務用 Skype Server 的參考拓撲](reference-topologies.md)中查看一些範例拓撲。</span><span class="sxs-lookup"><span data-stu-id="38553-110">You can also see some example topologies in [Reference topologies for Skype for Business Server](reference-topologies.md).</span></span>

## <a name="sites"></a><span data-ttu-id="38553-111">網站</span><span class="sxs-lookup"><span data-stu-id="38553-111">Sites</span></span>

<span data-ttu-id="38553-112">在商務用 Skype Server 中，您可以在網路上定義包含商務用 Skype 伺服器元件的網站。</span><span class="sxs-lookup"><span data-stu-id="38553-112">In Skype for Business Server, you define sites on your network that contain Skype for Business Server components.</span></span> <span data-ttu-id="38553-113">網站是以高速、低延遲網路來妥善連線的一組電腦，例如單一區域網路 (LAN) 或以高速光纖網路連接的兩個網路。</span><span class="sxs-lookup"><span data-stu-id="38553-113">A site is a set of computers that is well-connected by a high-speed, low-latency network, such as a single local area network (LAN) or two networks connected by a high-speed fiber optic network.</span></span> <span data-ttu-id="38553-114">請注意，商務用 Skype 伺服器網站是來自 Active Directory 網域服務網站和 Microsoft Exchange Server 網站的不同概念。</span><span class="sxs-lookup"><span data-stu-id="38553-114">Note that Skype for Business Server sites are a separate concept from Active Directory Domain Services sites and Microsoft Exchange Server sites.</span></span> <span data-ttu-id="38553-115">您的商務用 Skype 伺服器網站不需要對應至您的 Active Directory 網站。</span><span class="sxs-lookup"><span data-stu-id="38553-115">Your Skype for Business Server sites do not need to correspond to your Active Directory sites.</span></span>

<span data-ttu-id="38553-116">商務用 Skype 伺服器支援內部部署一或多個網站，可根據您的高可用性和位置需求進行調整。</span><span class="sxs-lookup"><span data-stu-id="38553-116">Skype for Business Server supports on-premises deployment of one or more sites that can be scaled according to your high availability and location requirements.</span></span>

<span data-ttu-id="38553-117">您的部署至少有一個中央網站 (也稱為資料中心，這是) 中所有伺服器的資料中心，而部署中的每個中央網站都有一個 Standard Edition server，或至少一個 Enterprise Edition 前端集區。</span><span class="sxs-lookup"><span data-stu-id="38553-117">Your deployment will have at least one central site (also called a datacenter, this is a datacenter for all the servers located in it), and each central site in your deployment will have one Standard Edition server, or at least one Enterprise Edition Front End pool.</span></span> <span data-ttu-id="38553-118">您可以在下列每個選項中看到差異：</span><span class="sxs-lookup"><span data-stu-id="38553-118">You can see the differences in each option below:</span></span>

- <span data-ttu-id="38553-119">Standard Edition server 包含組合 SQL Server Express 資料庫。</span><span class="sxs-lookup"><span data-stu-id="38553-119">Standard Edition server includes a collocated SQL Server Express database.</span></span>

- <span data-ttu-id="38553-120">Enterprise Edition 前端集區包括：</span><span class="sxs-lookup"><span data-stu-id="38553-120">Enterprise Edition Front End pool includes:</span></span>

  - <span data-ttu-id="38553-121">一或多部前端伺服器 (理想情況下至少三個，可伸縮性) ，最多為12個。</span><span class="sxs-lookup"><span data-stu-id="38553-121">One or more Front End Servers (Ideally at least three, for scalability), with a maximum of twelve.</span></span> <span data-ttu-id="38553-122">有一部以上的伺服器需要進行負載平衡。</span><span class="sxs-lookup"><span data-stu-id="38553-122">Load-balancing would be required for more than one server.</span></span>

  - <span data-ttu-id="38553-123">個別的後端伺服器。</span><span class="sxs-lookup"><span data-stu-id="38553-123">A separate Back End Server.</span></span>

<span data-ttu-id="38553-124">您可以在本節稍後深入瞭解各種伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="38553-124">You can learn more about the various server roles a little later in this section.</span></span>

<span data-ttu-id="38553-125">除了您的中央網站之外，您還可以建立一個或多個與中央網站相關聯的分支網站。</span><span class="sxs-lookup"><span data-stu-id="38553-125">In addition to your central sites, you may also end up having one or more branch sites associated with your central site.</span></span> <span data-ttu-id="38553-126">它們主要取決於中央網站，以取得幾乎所有的功能，因此它們是由哪些專案所組成？</span><span class="sxs-lookup"><span data-stu-id="38553-126">They depend on the central site for almost all their functionality, so what are they made up of, exactly?</span></span>

- <span data-ttu-id="38553-127">Survivable 分支裝置，將公用交換電話網路 (PSTN) 閘道與某些商務用 Skype Server 功能結合在一起。</span><span class="sxs-lookup"><span data-stu-id="38553-127">Survivable Branch Appliance, which combines a public switched telephone network (PSTN) gateway, with some Skype for Business Server functionality.</span></span>

- <span data-ttu-id="38553-128">Survivable 分支伺服器是執行 Windows Server 的伺服器，該伺服器已安裝商務用 Skype Server 註冊機構和轉送伺服器軟體。</span><span class="sxs-lookup"><span data-stu-id="38553-128">Survivable Branch Server, it's a server running Windows Server that has Skype for Business Server Registrar and Mediation Server software installed.</span></span>

- <span data-ttu-id="38553-129">獨立的 PSTN 閘道 (，不屬於 Survivable 分支裝置) 。</span><span class="sxs-lookup"><span data-stu-id="38553-129">Stand-alone PSTN gateway (which isn't part of the Survivable Branch Appliance).</span></span>

- <span data-ttu-id="38553-130">如果您不想要使用 Survivable Branch) 裝置組合此角色，請使用獨立轉送伺服器或獨立轉送伺服器集區 (。</span><span class="sxs-lookup"><span data-stu-id="38553-130">Stand-alone Mediation Server or stand-alone Mediation Server pool (if you don't want to collocate this role with the Survivable Branch Appliance).</span></span>

## <a name="whats-in-a-skype-for-business-server-site"></a><span data-ttu-id="38553-131">商務用 Skype Server 網站有哪些功能？</span><span class="sxs-lookup"><span data-stu-id="38553-131">What's in a Skype for Business Server site?</span></span>

<span data-ttu-id="38553-132">若要深入瞭解詳細資訊，中央網站也可以使用：</span><span class="sxs-lookup"><span data-stu-id="38553-132">To get into more detail, a central site can also have:</span></span>

- <span data-ttu-id="38553-133">在相同網域或不同網域中的多個前端集區 (請記住，在規劃前端集區中的所有前端伺服器，以及集區的後端伺服器，都必須位於相同的網域中) 。</span><span class="sxs-lookup"><span data-stu-id="38553-133">Multiple Front End pools, in the same domain or different domains (remember in planning that all the Front End Servers in a Front End pool, along with the Back End Servers for the pool, do have to be in the same domain).</span></span>

- <span data-ttu-id="38553-134">多部 Standard Edition Server。</span><span class="sxs-lookup"><span data-stu-id="38553-134">Multiple Standard Edition servers.</span></span>

- <span data-ttu-id="38553-135">Office Web Apps Server，可用於商務用 Skype Server 中的 Office Web Apps，以用於共用及呈現 PowerPoint 簡報。</span><span class="sxs-lookup"><span data-stu-id="38553-135">Office Web Apps Server, which is used with Office Web Apps in Skype for Business Server for sharing and rendering of PowerPoint presentations.</span></span>

- <span data-ttu-id="38553-136">周邊網路) 中的 edge Server 或 Edge 集區 (。</span><span class="sxs-lookup"><span data-stu-id="38553-136">Edge Server or Edge pool (in a perimeter network).</span></span> <span data-ttu-id="38553-137">如果您想要部署支援同盟協力廠商、公用 IM 連線、可延伸的訊息和顯示狀態通訊協定 (XMPP) 閘道和遠端使用者存取，則需要。</span><span class="sxs-lookup"><span data-stu-id="38553-137">Needed if you want your deployment to support federated partners, public IM connectivity, extensible messaging and presence protocol (XMPP) gateway, and remote user access.</span></span> <span data-ttu-id="38553-138">您可以在 Edge Server 規劃檔中找到詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="38553-138">More details can be found in the Edge Server Planning documentation.</span></span>

- <span data-ttu-id="38553-139">Persistent Chat Server。</span><span class="sxs-lookup"><span data-stu-id="38553-139">Persistent Chat Server.</span></span> <span data-ttu-id="38553-140">如果您想要讓使用者能夠加入一段時間內，以主題為基礎的會話，則會很有用。</span><span class="sxs-lookup"><span data-stu-id="38553-140">Useful if you want users to be able to take part in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="38553-141">在「Persistent Chat Server」主題中有其他資訊。</span><span class="sxs-lookup"><span data-stu-id="38553-141">There's more information at the Planning for Persistent Chat Server topic.</span></span>

- <span data-ttu-id="38553-142">監測。</span><span class="sxs-lookup"><span data-stu-id="38553-142">Monitoring.</span></span> <span data-ttu-id="38553-143">用來支援音訊/視頻的資料收集 (A/V) 的經驗品質 (QoE) 及通話詳細資料記錄 (CDR) 在您的部署中的企業語音和 A/V 會議。</span><span class="sxs-lookup"><span data-stu-id="38553-143">Used to support data collection for audio/video (A/V) Quality of Experience (QoE) and call detail recording (CDR) for Enterprise Voice and A/V conferences in your deployment.</span></span> <span data-ttu-id="38553-144">我們會在規劃監控主題時詳細討論它。</span><span class="sxs-lookup"><span data-stu-id="38553-144">We discuss it in detail at the Planning for Monitoring topic.</span></span>

- <span data-ttu-id="38553-145">Director 或 Director 集區。</span><span class="sxs-lookup"><span data-stu-id="38553-145">Director or Director pool.</span></span> <span data-ttu-id="38553-146">不需要，但是如果您想要提升復原能力並啟用商務用 Skype 使用者要求重新導向至使用者的主集區，則此方法很有用。</span><span class="sxs-lookup"><span data-stu-id="38553-146">Not required, but useful if you want to improve resiliency and enable redirection of Skype for Business user requests to the user's home pool.</span></span> <span data-ttu-id="38553-147">如果您想要部署 Director，則每個集區最多可支援10個。</span><span class="sxs-lookup"><span data-stu-id="38553-147">If you want to deploy Directors, a maximum of 10 per pool is supported.</span></span> <span data-ttu-id="38553-148">如果這是您需要的專案，請務必繼續閱讀「董事會規劃」主題。</span><span class="sxs-lookup"><span data-stu-id="38553-148">If this is something you need, definitely continue reading at the Planning for Directors topic.</span></span>

- <span data-ttu-id="38553-149">反向 proxy。</span><span class="sxs-lookup"><span data-stu-id="38553-149">Reverse proxy.</span></span> <span data-ttu-id="38553-150">這不是商務用 Skype Server 元件，但是如果您想要支援同盟使用者的 web 內容共用，您若想要支援行動性流量，如果您想要支援行動性流量，您可以在環境中執行這項操作。</span><span class="sxs-lookup"><span data-stu-id="38553-150">This isn't a Skype for Business Server component, but if you want to support the sharing of web content for federated users, if you intend to support Mobility traffic, if your remote users want to use the address book, join meetings, and so on, this is something you'll want to have in your environment.</span></span> <span data-ttu-id="38553-151">有一個設定反向 proxy 伺服器主題，當您準備好時，您可以查看更多詳細資料。</span><span class="sxs-lookup"><span data-stu-id="38553-151">There's a Setting up Reverse proxy server topic you can check out for more details, when you're ready.</span></span>

<span data-ttu-id="38553-152">您可以在下列伺服器上找到組合的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="38553-152">Additional information on collocation for these servers can be found below.</span></span>

<span data-ttu-id="38553-153">在您的中央網站上部署的所有前端集區和 Standard Edition 伺服器，假設您已部署下列各項：</span><span class="sxs-lookup"><span data-stu-id="38553-153">All the Front End pools and Standard Edition servers deployed at your central site share the following, assuming you've deployed them:</span></span>

||||
|:-----|:-----|:-----|
|<span data-ttu-id="38553-154">Director 或 Director 集區</span><span class="sxs-lookup"><span data-stu-id="38553-154">Director or Director pool</span></span>  <br/> |<span data-ttu-id="38553-155">獨立轉送伺服器或轉送伺服器集區</span><span class="sxs-lookup"><span data-stu-id="38553-155">Stand-alone Mediation Server or Mediation Server pool</span></span>  <br/> |<span data-ttu-id="38553-156">Office Web Apps Server</span><span class="sxs-lookup"><span data-stu-id="38553-156">Office Web Apps Server</span></span>  <br/> |
|<span data-ttu-id="38553-157">Edge Server 或 Edge 集區</span><span class="sxs-lookup"><span data-stu-id="38553-157">Edge Server or Edge pool</span></span>  <br/> |<span data-ttu-id="38553-158">Persistent Chat Server 或 Persistent Chat Server 集區</span><span class="sxs-lookup"><span data-stu-id="38553-158">Persistent Chat Server or Persistent Chat Server pool</span></span>  <br/> |<span data-ttu-id="38553-159">監視</span><span class="sxs-lookup"><span data-stu-id="38553-159">Monitoring</span></span>  <br/> |

<span data-ttu-id="38553-160">在此清單中，Exchange 整合通訊 (UM) 伺服器在哪裡？</span><span class="sxs-lookup"><span data-stu-id="38553-160">Where is Exchange Unified Messaging (UM) Server in this list?</span></span> <span data-ttu-id="38553-161">當然，如果您想要與 Exchange UM 整合，但它不是商務用 Skype Server 網站的元件，您當然也可以使用它，因此我們不會在這裡提及。</span><span class="sxs-lookup"><span data-stu-id="38553-161">Well, you can certainly use it with Skype for Business Server if you want to integrate with Exchange UM, but it's not a component of the Skype for Business Server site, so we're not mentioning it here.</span></span>

<span data-ttu-id="38553-162">您可能會規劃多個中央網站，如果是的話，他們可以在您的中央網站上共用下列伺服器和角色：</span><span class="sxs-lookup"><span data-stu-id="38553-162">You may be planning to have multiple central site, and if that's so, they can share the following servers and roles, if they're deployed on your central site:</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="38553-163">獨立轉送伺服器或轉送伺服器集區</span><span class="sxs-lookup"><span data-stu-id="38553-163">Stand-alone Mediation Server or Mediation Server pool</span></span>  <br/> |<span data-ttu-id="38553-164">Edge Server 或 Edge 集區</span><span class="sxs-lookup"><span data-stu-id="38553-164">Edge Server or Edge pool</span></span>  <br/> |
|<span data-ttu-id="38553-165">Persistent Chat Server 或 Persistent Chat Server 集區</span><span class="sxs-lookup"><span data-stu-id="38553-165">Persistent Chat Server or Persistent Chat Server pool</span></span>  <br/> |<span data-ttu-id="38553-166">監視</span><span class="sxs-lookup"><span data-stu-id="38553-166">Monitoring</span></span>  <br/> |

<span data-ttu-id="38553-167">就像最後一個清單一樣，我們不會在這裡包含 Exchange UM 伺服器，因為這不是商務用 Skype Server 部署的一部分，但也在這裡也屬於相同的類別。</span><span class="sxs-lookup"><span data-stu-id="38553-167">Just like the last list, we aren't including the Exchange UM Server here because it's not part of the Skype for Business Server deployment, but it falls into the same category here, too.</span></span>

<span data-ttu-id="38553-168">當然，還有其他一些元件和選項會進入部署。</span><span class="sxs-lookup"><span data-stu-id="38553-168">There are some other components and options that go into deployments, of course.</span></span>

|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="38553-169">防火牆</span><span class="sxs-lookup"><span data-stu-id="38553-169">Firewalls</span></span>  <br/> |<span data-ttu-id="38553-170">當您部署企業語音時， (PSTN 閘道</span><span class="sxs-lookup"><span data-stu-id="38553-170">PSTN gateways (if you deploy Enterprise Voice</span></span>  <br/> |<span data-ttu-id="38553-171">Exchange UM Server (如果您想要與 Exchange UM 整合) </span><span class="sxs-lookup"><span data-stu-id="38553-171">Exchange UM Server (if you want to integrate with Exchange UM)</span></span>  <br/> |<span data-ttu-id="38553-172">DNS 負載平衡</span><span class="sxs-lookup"><span data-stu-id="38553-172">DNS load balancing</span></span>  <br/> |
|<span data-ttu-id="38553-173">硬體負載平衡器</span><span class="sxs-lookup"><span data-stu-id="38553-173">Hardware load balancers</span></span>  <br/> |<span data-ttu-id="38553-174">SQL Server 資料庫</span><span class="sxs-lookup"><span data-stu-id="38553-174">SQL Server databases</span></span>  <br/> |<span data-ttu-id="38553-175">檔案共用</span><span class="sxs-lookup"><span data-stu-id="38553-175">File shares</span></span>  <br/> ||

## <a name="server-roles"></a><span data-ttu-id="38553-176">伺服器角色</span><span class="sxs-lookup"><span data-stu-id="38553-176">Server roles</span></span>

<span data-ttu-id="38553-177">每一部執行商務用 Skype 伺服器的伺服器都會執行一或多個伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="38553-177">Each server running Skype for Business Server runs one or more server roles.</span></span> <span data-ttu-id="38553-178">伺服器角色是該伺服器所提供之商務用 Skype Server 功能的定義集合。</span><span class="sxs-lookup"><span data-stu-id="38553-178">A server role is a defined set of Skype for Business Server functionalities provided by that server.</span></span> <span data-ttu-id="38553-179">您不需要在您的網路中部署所有可用的伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="38553-179">You don't need to deploy all available server roles in your network.</span></span> <span data-ttu-id="38553-180">只安裝包含您想要之功能的伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="38553-180">Install only the server roles that contain the functionality that you want.</span></span>

<span data-ttu-id="38553-181">針對大部分的伺服器角色，針對可擴充性和高可用性，您可以部署多部伺服器的集區，所有執行相同的伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="38553-181">For most server roles, for scalability and high availability you can deploy pools of multiple servers all running the same server role.</span></span> <span data-ttu-id="38553-182">集區中的每部伺服器都必須執行一或多個相同的伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="38553-182">Each server in a pool must run an identical server role or roles.</span></span> <span data-ttu-id="38553-183">對於商務用 Skype Server 中的大部分類型的集區，您必須部署負載平衡器，以散佈集區中各種伺服器間的流量。</span><span class="sxs-lookup"><span data-stu-id="38553-183">For most types of pools in Skype for Business Server, you must deploy a load balancer to spread traffic between the various servers in the pool.</span></span> <span data-ttu-id="38553-184">商務用 Skype 伺服器支援網域名稱系統 (DNS) 負載平衡與硬體負載平衡器。</span><span class="sxs-lookup"><span data-stu-id="38553-184">Skype for Business Server supports both Domain Name System (DNS) load balancing and hardware load balancers.</span></span>

### <a name="front-end-server-and-back-end-server"></a><span data-ttu-id="38553-185">前端伺服器及後端伺服器</span><span class="sxs-lookup"><span data-stu-id="38553-185">Front End Server and Back End Server</span></span>

<span data-ttu-id="38553-186">在商務用 Skype Server Enterprise Edition 中，前端伺服器是核心伺服器角色，而且會執行許多基本商務用 Skype Server 功能。</span><span class="sxs-lookup"><span data-stu-id="38553-186">In Skype for Business Server Enterprise Edition, the Front End Server is the core server role, and runs many basic Skype for Business Server functions.</span></span> <span data-ttu-id="38553-187">在任何商務用 Skype Server Enterprise Edition 部署中，前端伺服器及後端伺服器都是唯一需要的伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="38553-187">The Front End Server, along with the Back End Servers, are the only server roles required to be in any Skype for Business Server Enterprise Edition deployment.</span></span>

<span data-ttu-id="38553-188">前端集區是一組前端伺服器（已正確設定），可共同運作，以提供通用使用者群組的服務。</span><span class="sxs-lookup"><span data-stu-id="38553-188">A Front End pool is a set of Front End Servers, configured identically, that work together to provide services for a common group of users.</span></span> <span data-ttu-id="38553-189">執行相同角色的多部伺服器集區提供可擴充性和容錯移轉功能。</span><span class="sxs-lookup"><span data-stu-id="38553-189">A pool of multiple servers running the same role provides scalability and failover capability.</span></span>

<span data-ttu-id="38553-190">前端伺服器包含下列專案：</span><span class="sxs-lookup"><span data-stu-id="38553-190">The Front End Server includes the following:</span></span>

- <span data-ttu-id="38553-191">使用者驗證和註冊。</span><span class="sxs-lookup"><span data-stu-id="38553-191">User authentication and registration.</span></span>

- <span data-ttu-id="38553-192">目前狀態資訊和連絡人卡片交換。</span><span class="sxs-lookup"><span data-stu-id="38553-192">Presence information and contact card exchange.</span></span>

- <span data-ttu-id="38553-193">通訊錄服務和通訊群組清單擴充。</span><span class="sxs-lookup"><span data-stu-id="38553-193">Address book services and distribution list expansion.</span></span>

- <span data-ttu-id="38553-194">IM 功能（包括多方 IM 會議）。</span><span class="sxs-lookup"><span data-stu-id="38553-194">IM functionality, including multiparty IM conferences.</span></span>

- <span data-ttu-id="38553-195">Web 會議、PSTN 電話撥入式會議和 A/V 會議 (（若已部署) ）。</span><span class="sxs-lookup"><span data-stu-id="38553-195">Web conferencing, PSTN Dial-in conferencing and A/V conferencing (if deployed).</span></span>

- <span data-ttu-id="38553-196">應用程式裝載（適用于商務用 Skype (Server 所包含的兩個應用程式）例如會議助理和回應群組應用程式) ，以及協力廠商應用程式。</span><span class="sxs-lookup"><span data-stu-id="38553-196">Application hosting, for both applications included with Skype for Business Server (for example, Conferencing Attendant and Response Group application), and third-party applications.</span></span>

- <span data-ttu-id="38553-197">（選用）監控，以 [通話詳細資料記錄] 的形式收集使用資訊 (Cdr) 並呼叫錯誤記錄 (Cer) 。</span><span class="sxs-lookup"><span data-stu-id="38553-197">Optionally, Monitoring, to collect usage information in the form of call detail records (CDRs) and call error records (CERs).</span></span> <span data-ttu-id="38553-198">此資訊提供有關媒體質量 (音訊和影片) 針對企業語音通話和 A/V 會議進行網路的統計資料。</span><span class="sxs-lookup"><span data-stu-id="38553-198">This information provides metrics about the quality of the media (audio and video) traversing your network for both Enterprise Voice calls and A/V conferences.</span></span>

- <span data-ttu-id="38553-199">網頁元件至支援的 web 工作，例如 web 排程器及加入啟動器。</span><span class="sxs-lookup"><span data-stu-id="38553-199">Web components to supported web-based tasks such as web scheduler and join launcher.</span></span>

- <span data-ttu-id="38553-200">（選用）封存 IM 通訊和會議內容，以符合合規性的原因。</span><span class="sxs-lookup"><span data-stu-id="38553-200">Optionally, Archiving, to archive IM communications and meeting content for compliance reasons.</span></span> <span data-ttu-id="38553-201">如需詳細資訊，請參閱規劃檔中的 [規劃](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-archiving) 封存。</span><span class="sxs-lookup"><span data-stu-id="38553-201">For details, see [Planning for Archiving](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-archiving) in the Planning documentation.</span></span>

    <span data-ttu-id="38553-202">在 Lync Server 2010 和舊版中，監控和封存是不同的伺服器角色，不會組合在前端伺服器上。</span><span class="sxs-lookup"><span data-stu-id="38553-202">In Lync Server 2010 and prior versions, Monitoring and Archiving were separate server roles, not collocated on Front End Server.</span></span>

- <span data-ttu-id="38553-203">（選用）啟用持續性聊天時，會持續聊天網頁服務用於聊天室管理，並可進行檔案上傳/下載的持續性聊天 Web 服務。</span><span class="sxs-lookup"><span data-stu-id="38553-203">Optionally, if Persistent chat is enabled, Persistent Chat Web Services for Chat Room Management and Persistent Chat Web Services for File Upload/Download.</span></span>

<span data-ttu-id="38553-204">前端集區也是使用者和會議資料的主要儲存區。</span><span class="sxs-lookup"><span data-stu-id="38553-204">Front End Pools are also the primary store for user and conference data.</span></span> <span data-ttu-id="38553-205">每個使用者的資訊都會在集區中的三部前端伺服器之間進行複製，並在後端伺服器上備份。</span><span class="sxs-lookup"><span data-stu-id="38553-205">Information about each user is replicated among three Front End Servers in the pool, and backed up on the Back End Servers.</span></span>

<span data-ttu-id="38553-206">此外，部署中的一部前端伺服器也會執行中央管理伺服器，此伺服器會管理及部署所有執行商務用 Skype Server 之伺服器的基本設定資料。</span><span class="sxs-lookup"><span data-stu-id="38553-206">Additionally, one Front End Server in the deployment also runs the Central Management Server, which manages and deploys basic configuration data to all servers running Skype for Business Server.</span></span> <span data-ttu-id="38553-207">中央管理伺服器也提供 Lync Server 管理命令介面和檔案傳輸功能。</span><span class="sxs-lookup"><span data-stu-id="38553-207">The Central Management Server also provides Lync Server Management Shell and file transfer capabilities.</span></span>

<span data-ttu-id="38553-208">後端伺服器是執行 Microsoft SQL Server 的資料庫伺服器，提供前端集區的資料庫服務。</span><span class="sxs-lookup"><span data-stu-id="38553-208">The Back End Servers are database servers running Microsoft SQL Server that provide the database services for the Front End pool.</span></span> <span data-ttu-id="38553-209">後端伺服器充當集區使用者和會議資料的備份存放區，也是其他資料庫（如回應群組資料庫）的主要儲存區。</span><span class="sxs-lookup"><span data-stu-id="38553-209">The Back End Servers serve as backup stores for the pool's user and conference data, and are the primary stores for other databases such as the Response Group database.</span></span> <span data-ttu-id="38553-210">您可以擁有單一的後端伺服器，但在進行容錯移轉時，建議使用 [商務用 Skype server 的後端伺服器高可用性](../high-availability-and-disaster-recovery/back-end-server.md) 。</span><span class="sxs-lookup"><span data-stu-id="38553-210">You can have a single Back End Server, but [Back End Server high availability in Skype for Business Server](../high-availability-and-disaster-recovery/back-end-server.md) is recommended for failover.</span></span> <span data-ttu-id="38553-211">後端伺服器不會執行任何商務用 Skype Server 軟體。</span><span class="sxs-lookup"><span data-stu-id="38553-211">Back End Servers do not run any Skype for Business Server software.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="38553-212">我們不建議使用其他資料庫組合商務用 Skype Server 資料庫。</span><span class="sxs-lookup"><span data-stu-id="38553-212">We do not recommend collocating Skype for Business Server databases with other databases.</span></span> <span data-ttu-id="38553-213">如果您這麼做，可用性和效能可能會受到影響。</span><span class="sxs-lookup"><span data-stu-id="38553-213">If you do so, availability and performance may be affected.</span></span>

> [!NOTE]
> <span data-ttu-id="38553-214">在商務用 Skype 2015 Server 中可使用 SQL 鏡像，但商務用 Skype Server 2019 已不再支援。</span><span class="sxs-lookup"><span data-stu-id="38553-214">SQL Mirroring is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="38553-215">AlwaysOn 可用性群組、AlwaysOn 容錯移轉叢集實例 (FCI) ，以及使用商務用 Skype Server 2019 的首選 SQL 容錯移轉叢集方法。</span><span class="sxs-lookup"><span data-stu-id="38553-215">The  AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering methods are preferred with Skype for Business Server 2019.</span></span>

<span data-ttu-id="38553-216">儲存在後端伺服器資料庫中的資訊包括目前狀態資訊、使用者的連絡人清單、會議資料（包括所有目前會議狀態的持續性資料）和會議排程資料。</span><span class="sxs-lookup"><span data-stu-id="38553-216">Information stored in the Back End Server databases includes presence information, users' Contacts lists, conferencing data, including persistent data about the state of all current conferences, and conference scheduling data.</span></span>

### <a name="edge-server"></a><span data-ttu-id="38553-217">Edge Server</span><span class="sxs-lookup"><span data-stu-id="38553-217">Edge Server</span></span>

<span data-ttu-id="38553-218">Edge Server 可讓您的使用者與組織防火牆外的使用者進行通訊及共同作業。</span><span class="sxs-lookup"><span data-stu-id="38553-218">Edge Server enables your users to communicate and collaborate with users outside the organization's firewalls.</span></span> <span data-ttu-id="38553-219">這些外部使用者可以包含組織的使用者，這些使用者目前正在異地工作、同盟夥伴組織的使用者，以及已被邀請加入您的商務用 Skype Server 部署會議的外部使用者。</span><span class="sxs-lookup"><span data-stu-id="38553-219">These external users can include the organization's own users who are currently working offsite, users from federated partner organizations, and outside users who have been invited to join conferences hosted on your Skype for Business Server deployment.</span></span>

<span data-ttu-id="38553-220">部署 Edge Server 也會啟用行動裝置，其支援行動裝置上的 Lync 功能。</span><span class="sxs-lookup"><span data-stu-id="38553-220">Deploying Edge Server also enables mobility services, which supports Lync functionality on mobile devices.</span></span> <span data-ttu-id="38553-221">使用者可以使用支援的 Apple iOS、Android、Windows Phone 或 Nokia 行動裝置執行活動，例如傳送和接收立即訊息、查看連絡人及查看顯示狀態。</span><span class="sxs-lookup"><span data-stu-id="38553-221">Users can use supported Apple iOS, Android, Windows Phone, or Nokia mobile devices to perform activities such as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span> <span data-ttu-id="38553-222">此外，行動裝置還可支援某些 Enterprise Voice 功能，例如按一下加入會議、從公司撥號、單一號碼搜尋、語音信箱及未接來電。</span><span class="sxs-lookup"><span data-stu-id="38553-222">In addition, mobile devices support some Enterprise Voice features, such as click to join a conference, Call via Work, single number reach, voice mail, and missed calls.</span></span> <span data-ttu-id="38553-223">行動功能也可以為不支援在背景執行應用程式的行動裝置，支援「推播通知」。</span><span class="sxs-lookup"><span data-stu-id="38553-223">The mobility feature also supports push notifications for mobile devices that do not support applications running in the background.</span></span> <span data-ttu-id="38553-224">推播通知是針對在行動應用程式為非使用中狀態時所發生的事件，傳送給行動裝置的通知。</span><span class="sxs-lookup"><span data-stu-id="38553-224">A push notification is a notification that is sent to a mobile device about an event that occurs while a mobile application is inactive.</span></span>

<span data-ttu-id="38553-225">Edge Server 也包含完整整合的可延伸訊息和顯示狀態通訊協定 (XMPP) proxy，包含在前端伺服器上的 XMPP 閘道。</span><span class="sxs-lookup"><span data-stu-id="38553-225">Edge Servers also include a fully-integrated Extensible Messaging and Presence Protocol (XMPP) proxy, with an XMPP gateway included on Front End Servers.</span></span> <span data-ttu-id="38553-226">您可以設定這些 XMPP 元件，讓商務用 Skype 伺服器使用者新增來自以 XMPP 為基礎的合作夥伴的連絡人，以進行立即訊息及顯示狀態。</span><span class="sxs-lookup"><span data-stu-id="38553-226">You can configure these XMPP components to enable your Skype for Business Server users to add contacts from XMPP-based partners for instant messaging and presence.</span></span>

> [!NOTE]
> <span data-ttu-id="38553-227">XMPP 閘道和 proxy 可用於商務用 Skype Server 2015，但在商務用 Skype Server 2019 中已不再支援。</span><span class="sxs-lookup"><span data-stu-id="38553-227">XMPP Gateways and proxies are available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="38553-228">如需詳細資訊，請參閱 [遷移 XMPP 同盟](../../../SfBServer2019/migration/migrating-xmpp-federation.md) 。</span><span class="sxs-lookup"><span data-stu-id="38553-228">See [Migrating XMPP federation](../../../SfBServer2019/migration/migrating-xmpp-federation.md) for more information.</span></span>

### <a name="mediation-server"></a><span data-ttu-id="38553-229">中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="38553-229">Mediation Server</span></span>

<span data-ttu-id="38553-230">轉送伺服器是用來執行企業語音、呼叫公司電話和電話撥入式會議的必要元件。</span><span class="sxs-lookup"><span data-stu-id="38553-230">Mediation Server is a necessary component for implementing Enterprise Voice, Call Via Work, and dial-in conferencing.</span></span> <span data-ttu-id="38553-231">轉送伺服器轉譯信號，在某些設定中，在內部商務用 Skype 伺服器基礎結構和公用交換電話網路 (PSTN) 閘道、IP-PBX 或會話初始通訊協定 (SIP) 主幹之間的媒體。</span><span class="sxs-lookup"><span data-stu-id="38553-231">Mediation Server translates signaling, and, in some configurations, media between your internal Skype for Business Server infrastructure and a public switched telephone network (PSTN) gateway, IP-PBX, or a Session Initiation Protocol (SIP) trunk.</span></span> <span data-ttu-id="38553-232">您可以在前端伺服器所在的伺服器上執行轉送伺服器組合，或將其分割成獨立的轉送伺服器集區。</span><span class="sxs-lookup"><span data-stu-id="38553-232">You can run Mediation Server collocated on the same server as Front End Server, or separated into a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="38553-233">如需詳細資訊，請參閱 lync server [component In 商務用 Skype server](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md)。</span><span class="sxs-lookup"><span data-stu-id="38553-233">For details, see [Mediation Server component in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md).</span></span>

### <a name="video-interop-server"></a><span data-ttu-id="38553-234">視訊互通性伺服器</span><span class="sxs-lookup"><span data-stu-id="38553-234">Video Interop Server</span></span>

<span data-ttu-id="38553-235">影片 Interop 伺服器是商務用 Skype Server 2015 的新角色。</span><span class="sxs-lookup"><span data-stu-id="38553-235">Video Interop Server is a new role as of Skype for Business Server 2015.</span></span> <span data-ttu-id="38553-236">它可讓您將商務用 Skype 伺服器部署與特定協力廠商 VTC (Video 電話會議 System) 解決方案進行整合。</span><span class="sxs-lookup"><span data-stu-id="38553-236">It enables you to integrate your Skype for Business Server deployment with certain third-party VTC (Video Teleconferencing System) solutions.</span></span> <span data-ttu-id="38553-237">VIS 充當協力廠商電話會議系統和商務用 Skype Server 部署之間的媒介。</span><span class="sxs-lookup"><span data-stu-id="38553-237">A VIS acts as an intermediary between a 3rd party teleconference system and a Skype for Business Server deployment.</span></span> <span data-ttu-id="38553-238">在此版本中，VIS 著重于與 Cisco/Tandberg 影片系統的互通性。</span><span class="sxs-lookup"><span data-stu-id="38553-238">For this release, VIS is focused on interoperability with Cisco/Tandberg video systems.</span></span>

<span data-ttu-id="38553-239">如需詳細資訊，請參閱 [在商務用 Skype server 中規劃影片 Interop 伺服器](../../plan-your-deployment/video-interop-server.md)。</span><span class="sxs-lookup"><span data-stu-id="38553-239">For details, see [Plan for Video Interop Server in Skype for Business Server](../../plan-your-deployment/video-interop-server.md).</span></span>

### <a name="director"></a><span data-ttu-id="38553-240">Director</span><span class="sxs-lookup"><span data-stu-id="38553-240">Director</span></span>

<span data-ttu-id="38553-241">Director 可驗證商務用 Skype Server 使用者要求，但不會家用使用者帳戶或提供目前狀態或會議服務。</span><span class="sxs-lookup"><span data-stu-id="38553-241">Directors can authenticate Skype for Business Server user requests, but they do not home user accounts or provide presence or conferencing services.</span></span> <span data-ttu-id="38553-242">Director 在啟用外部使用者存取的部署中增強安全性是非常有用的。</span><span class="sxs-lookup"><span data-stu-id="38553-242">Directors are most useful to enhance security in deployments that enable external user access.</span></span> <span data-ttu-id="38553-243">Director 可以在將要求傳送至內部伺服器之前先驗證要求。</span><span class="sxs-lookup"><span data-stu-id="38553-243">The Director can authenticate requests before sending them on to internal servers.</span></span> <span data-ttu-id="38553-244">在拒絕服務攻擊的情況下，攻擊會以 Director 結尾，而且不會到達前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="38553-244">In the case of a denial-of-service attack, the attack ends with the Director and does not reach the Front End servers.</span></span>

### <a name="persistent-chat-server-roles"></a><span data-ttu-id="38553-245">Persistent Chat Server Role</span><span class="sxs-lookup"><span data-stu-id="38553-245">Persistent Chat Server Roles</span></span>

> [!NOTE]
> <span data-ttu-id="38553-246">商務用 Skype Server 2015 仍提供持續聊天，但商務用 Skype Server 2019 已不再支援。</span><span class="sxs-lookup"><span data-stu-id="38553-246">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="38553-247">小組中提供相同的功能。</span><span class="sxs-lookup"><span data-stu-id="38553-247">The same functionality is available in Teams.</span></span> <span data-ttu-id="38553-248">如需詳細資訊，請參閱 [Microsoft 團隊升級快速](/microsoftteams/upgrade-start-here)入門。</span><span class="sxs-lookup"><span data-stu-id="38553-248">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="38553-249">如果您需要使用持續聊天，您可以選擇將需要這項功能的使用者遷移至小組，或是繼續使用商務用 Skype Server 2015。</span><span class="sxs-lookup"><span data-stu-id="38553-249">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span>

<span data-ttu-id="38553-250">Persistent chat 可讓使用者加入一段時間內的多方、主題型交談。</span><span class="sxs-lookup"><span data-stu-id="38553-250">Persistent chat enables users to participate in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="38553-251">Persistent Chat 前端伺服器會執行 persistent chat service。</span><span class="sxs-lookup"><span data-stu-id="38553-251">The Persistent Chat Front End Server runs the persistent chat service.</span></span> <span data-ttu-id="38553-252">Persistent Chat 後端伺服器會儲存聊天記錄資料，以及類別和聊天室的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="38553-252">The Persistent Chat Back End Server stores the chat history data, and information about categories and chat rooms.</span></span> <span data-ttu-id="38553-253">選用的持續性聊天規範後端伺服器可以儲存聊天內容和符合性事件，以符合規範的目的。</span><span class="sxs-lookup"><span data-stu-id="38553-253">The optional Persistent Chat Compliance Back End Server can store the chat content and compliance events for the purpose of compliance.</span></span>

<span data-ttu-id="38553-254">執行商務用 Skype Server Standard Edition 的伺服器也可以在同一部伺服器上執行 Persistent chat 組合。</span><span class="sxs-lookup"><span data-stu-id="38553-254">Servers running Skype for Business Server Standard Edition can also run Persistent chat collocated on the same server.</span></span> <span data-ttu-id="38553-255">您無法以 Enterprise Edition 前端伺服器組合持久聊天前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="38553-255">You cannot collocate the Persistent Chat Front End Server with Enterprise Edition Front End Server.</span></span>

<span data-ttu-id="38553-256">如需詳細資訊，請參閱 [Plan For Persistent Chat server In 商務用 Skype server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)。</span><span class="sxs-lookup"><span data-stu-id="38553-256">For details, see [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).</span></span>

## <a name="high-availability-and-disaster-recovery-support"></a><span data-ttu-id="38553-257">高可用性和嚴重損壞修復支援</span><span class="sxs-lookup"><span data-stu-id="38553-257">High availability and disaster recovery support</span></span>

<span data-ttu-id="38553-258">商務用 Skype 伺服器透過 pooling 透過伺服器的冗余度，提供高可用性。</span><span class="sxs-lookup"><span data-stu-id="38553-258">Skype for Business Server provides high availability by server redundancy via pooling.</span></span> <span data-ttu-id="38553-259">如果執行特定伺服器角色的伺服器失敗，集區中執行相同角色的其他伺服器就會接手該伺服器的負載。</span><span class="sxs-lookup"><span data-stu-id="38553-259">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="38553-260">這適用於前端伺服器、Edge Server、中繼伺服器和 Director。</span><span class="sxs-lookup"><span data-stu-id="38553-260">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span>

<span data-ttu-id="38553-261">商務用 Skype 伺服器也會啟用集區配對，以提供嚴重損壞修復措施。</span><span class="sxs-lookup"><span data-stu-id="38553-261">Skype for Business Server also provides disaster recovery measures by enabling pool pairing.</span></span> <span data-ttu-id="38553-262">如果您部署這個拓樸，將會指定前端集區配對，每一對中各個集區都位在不同的資料中心，並且在不同的地理區。</span><span class="sxs-lookup"><span data-stu-id="38553-262">If you deploy this topology, you will designate pairs of Front End pools, with each pool in a pair located in a separate data center, and in a separate geographical area.</span></span> <span data-ttu-id="38553-263">如果一個集區或網站故障，您可以重新導向該集區的使用者，以使用該配對中另一個集區，讓服務中斷時間降至最低。</span><span class="sxs-lookup"><span data-stu-id="38553-263">If one pool or site goes down, you can redirect the users of that pool to use the other pool in the pair, with minimal interruption of service.</span></span>

<span data-ttu-id="38553-264">商務用 Skype 伺服器也支援多種選項，以供後端伺服器高可用性之用。</span><span class="sxs-lookup"><span data-stu-id="38553-264">Skype for Business Server also supports several options for Back End Server high availability.</span></span> <span data-ttu-id="38553-265">包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="38553-265">These include the following:</span></span>

- <span data-ttu-id="38553-266">資料庫鏡像</span><span class="sxs-lookup"><span data-stu-id="38553-266">Database mirroring</span></span>

- <span data-ttu-id="38553-267">AlwaysOn 可用性群組</span><span class="sxs-lookup"><span data-stu-id="38553-267">AlwaysOn Availability Groups</span></span>

- <span data-ttu-id="38553-268">AlwaysOn (FCI 的容錯移轉叢集實例) </span><span class="sxs-lookup"><span data-stu-id="38553-268">AlwaysOn Failover Cluster Instances (FCI)</span></span>

- <span data-ttu-id="38553-269">SQL 容錯移轉叢集</span><span class="sxs-lookup"><span data-stu-id="38553-269">SQL failover clustering</span></span>

<span data-ttu-id="38553-270">如需有關集區配對及後端伺服器高可用性的詳細資訊，請參閱 [在商務用 Skype Server 中規劃高可用性和嚴重損壞修復](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。</span><span class="sxs-lookup"><span data-stu-id="38553-270">For details about pool pairing and Back End Server high availability, see [Plan for high availability and disaster recovery in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>

## <a name="server-collocation-in-skype-for-business-server"></a><span data-ttu-id="38553-271">商務用 Skype Server 中的伺服器組合</span><span class="sxs-lookup"><span data-stu-id="38553-271">Server collocation in Skype for Business Server</span></span>

<span data-ttu-id="38553-272">我們已使用字片語合，但這是什麼意思？</span><span class="sxs-lookup"><span data-stu-id="38553-272">We've used the term collocate already, but what does this mean?</span></span> <span data-ttu-id="38553-273">商務用 Skype Server 可讓您在同一部伺服器上尋找一些伺服器角色和功能，也就是在不同的伺服器上組合，但在您開始時，可能會造成混淆，以及您要執行的是 Standard Edition 還是 Enterprise Edition Server 部署 (各自都附帶各自的規則) 。</span><span class="sxs-lookup"><span data-stu-id="38553-273">Skype for Business Server allows you to locate some server roles and features on the same server, which is collocation, or on different servers, but it can be confusing when you're starting out, and whether you're doing a Standard Edition or Enterprise Edition server deployment (they each come with their own rules).</span></span> <span data-ttu-id="38553-274">為了協助您進行規劃，我們包括 Standard Edition server 部署和 Enterprise Edition 前端集區 (部署中的伺服器組合。在大多數情況下，這項資訊是相同的，而且在不同的地方，稱為特別) 。</span><span class="sxs-lookup"><span data-stu-id="38553-274">To help with your planning, we're including server collocation in Standard Edition server deployments and Enterprise Edition Front End pool deployments (in most cases this information is identical, and where it's different, it's called out specifically).</span></span>

### <a name="collocation-of-server-roles"></a><span data-ttu-id="38553-275">伺服器角色的組合</span><span class="sxs-lookup"><span data-stu-id="38553-275">Collocation of server roles</span></span>

<span data-ttu-id="38553-276">Standard Edition server 具有下列角色組合 (其他設定也是) ，但在 Enterprise Edition 前端集區中，此角色可以組合，或部署至不同的伺服器：</span><span class="sxs-lookup"><span data-stu-id="38553-276">The Standard Edition server has the following role collocated (additional configuration is required though), while in the Enterprise Edition Front End pool, this role can be collocated, or deployed to a separate server:</span></span>

- <span data-ttu-id="38553-277">調解</span><span class="sxs-lookup"><span data-stu-id="38553-277">Mediation</span></span>

<span data-ttu-id="38553-278">這些伺服器角色必須分別部署在不同的伺服器上：</span><span class="sxs-lookup"><span data-stu-id="38553-278">These server roles must each be deployed on a separate server:</span></span>

- <span data-ttu-id="38553-279">Director</span><span class="sxs-lookup"><span data-stu-id="38553-279">Director</span></span>

- <span data-ttu-id="38553-280">銳利</span><span class="sxs-lookup"><span data-stu-id="38553-280">Edge</span></span>

- <span data-ttu-id="38553-281">視訊互通性伺服器</span><span class="sxs-lookup"><span data-stu-id="38553-281">Video Interop Server</span></span>

- <span data-ttu-id="38553-282">Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="38553-282">Office Web Apps</span></span>

### <a name="databases"></a><span data-ttu-id="38553-283">資料庫</span><span class="sxs-lookup"><span data-stu-id="38553-283">Databases</span></span>

<span data-ttu-id="38553-284">這是 Standard Edition server 部署和 Enterprise Edition server 集區部署之間的實際差異區域，因此我們將會有兩個區段，後面接著提供一些額外的規則。</span><span class="sxs-lookup"><span data-stu-id="38553-284">This is the area with real differences between Standard Edition server deployments and Enterprise Edition server pool deployments, so we'll have two sections below, followed by some additional rules for both.</span></span>

#### <a name="standard"></a><span data-ttu-id="38553-285">標準版</span><span class="sxs-lookup"><span data-stu-id="38553-285">Standard</span></span>

<span data-ttu-id="38553-286">因為 SQL Server Express 是在 Standard Edition Server 上組合，而且無法移動，所以這相當簡單。</span><span class="sxs-lookup"><span data-stu-id="38553-286">Since SQL Server Express is collocated on the Standard Edition server, and can't be moved, this is pretty straightforward.</span></span> <span data-ttu-id="38553-287">此外，如果您在 Standard Edition server 上部署 Persistent Chat Server，您也可以組合 Standard Edition server 上的持續聊天和持續性聊天規範資料庫，但您不需要這樣做。</span><span class="sxs-lookup"><span data-stu-id="38553-287">Furthermore, if you deploy Persistent Chat Server on a Standard Edition server, you're also able to collocate the Persistent Chat and the Persistent Chat compliance database on the Standard Edition server too, but you don't have to.</span></span>

> [!NOTE]
> <span data-ttu-id="38553-288">商務用 Skype Server 2015 仍提供持續聊天，但商務用 Skype Server 2019 已不再支援。</span><span class="sxs-lookup"><span data-stu-id="38553-288">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="38553-289">小組中提供相同的功能。</span><span class="sxs-lookup"><span data-stu-id="38553-289">The same functionality is available in Teams.</span></span> <span data-ttu-id="38553-290">如需詳細資訊，請參閱 [Microsoft 團隊升級快速](/microsoftteams/upgrade-start-here)入門。</span><span class="sxs-lookup"><span data-stu-id="38553-290">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="38553-291">如果您需要使用持續聊天，您可以選擇將需要這項功能的使用者遷移至小組，或是繼續使用商務用 Skype Server 2015。</span><span class="sxs-lookup"><span data-stu-id="38553-291">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span>

<span data-ttu-id="38553-292">這些無法在 Standard Edition server 上組合，但可以繼續使用自己的單一資料庫伺服器：</span><span class="sxs-lookup"><span data-stu-id="38553-292">These can't be collocated on the Standard Edition server, but can go on a single database server of their own:</span></span>

- <span data-ttu-id="38553-293">監控資料庫</span><span class="sxs-lookup"><span data-stu-id="38553-293">Monitoring database</span></span>

- <span data-ttu-id="38553-294">封存資料庫</span><span class="sxs-lookup"><span data-stu-id="38553-294">Archiving database</span></span>

- <span data-ttu-id="38553-295">Enterprise Edition 前端集區的任何後端資料庫</span><span class="sxs-lookup"><span data-stu-id="38553-295">Any back-end database for an Enterprise Edition Front End pool</span></span>

#### <a name="enterprise"></a><span data-ttu-id="38553-296">企業</span><span class="sxs-lookup"><span data-stu-id="38553-296">Enterprise</span></span>

<span data-ttu-id="38553-297">下列資料庫可以在同一部後端 SQL Server 上組合：</span><span class="sxs-lookup"><span data-stu-id="38553-297">The following databases can be collocated on the same back end SQL Server:</span></span>

- <span data-ttu-id="38553-298">後端資料庫</span><span class="sxs-lookup"><span data-stu-id="38553-298">Back End database</span></span>

- <span data-ttu-id="38553-299">監控資料庫</span><span class="sxs-lookup"><span data-stu-id="38553-299">Monitoring database</span></span>

- <span data-ttu-id="38553-300">封存資料庫</span><span class="sxs-lookup"><span data-stu-id="38553-300">Archiving database</span></span>

- <span data-ttu-id="38553-301">Persistent Chat 資料庫</span><span class="sxs-lookup"><span data-stu-id="38553-301">Persistent Chat database</span></span>

- <span data-ttu-id="38553-302">Persistent Chat 規範資料庫</span><span class="sxs-lookup"><span data-stu-id="38553-302">Persistent Chat compliance database</span></span>

#### <a name="both"></a><span data-ttu-id="38553-303">兩者都要</span><span class="sxs-lookup"><span data-stu-id="38553-303">Both</span></span>

<span data-ttu-id="38553-304">現在，當您在單一 SQL 實例中組合商務用 Skype Server 資料庫，或在相同 SQL Server 資料庫的多個 SQL 實例中，請遵循下列其他規則：</span><span class="sxs-lookup"><span data-stu-id="38553-304">Now, there are some additional rules to follow when collocating Skype for Business Server databases in a single SQL instance, or in multiple SQL instances in the same SQL Server database:</span></span>

- <span data-ttu-id="38553-305">每個 SQL 實例僅可包含 Enterprise Edition 前端集區的單一後端資料庫、單一監控資料庫、單一封存資料庫、單一持久聊天資料庫及單一持久聊天規範資料庫。</span><span class="sxs-lookup"><span data-stu-id="38553-305">Each SQL instance can only contain a single back end database for an Enterprise Edition Front End pool, a single Monitoring database, a single Archiving database, a single Persistent Chat database, and a single Persistent Chat compliance database.</span></span>

- <span data-ttu-id="38553-306">資料庫伺服器不支援一個以上的 Enterprise Edition 前端集區、一部執行封存的伺服器、單一持久聊天資料庫，以及單一 Persistent Chat 規範資料庫，但不論資料庫使用相同的 SQL Server 實例，還是使用不同的 SQL Server 實例，都可以支援其中一個。</span><span class="sxs-lookup"><span data-stu-id="38553-306">The database server can't support more than one Enterprise Edition Front End pool, one server running Archiving, one server running Monitoring, a single Persistent Chat database, and a single Persistent Chat compliance database, but it can support one of each, regardless of whether the databases use the same instance of SQL Server or separate instances of SQL Server.</span></span>

    > [!NOTE]
    > <span data-ttu-id="38553-307">商務用 Skype Server 2015 仍提供持續聊天，但商務用 Skype Server 2019 已不再支援。</span><span class="sxs-lookup"><span data-stu-id="38553-307">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="38553-308">小組中提供相同的功能。</span><span class="sxs-lookup"><span data-stu-id="38553-308">The same functionality is available in Teams.</span></span> <span data-ttu-id="38553-309">如需詳細資訊，請參閱 [Microsoft 團隊升級快速](/microsoftteams/upgrade-start-here)入門。</span><span class="sxs-lookup"><span data-stu-id="38553-309">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="38553-310">如果您需要使用持續聊天，您可以選擇將需要這項功能的使用者遷移至小組，或是繼續使用商務用 Skype Server 2015。</span><span class="sxs-lookup"><span data-stu-id="38553-310">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span>

### <a name="file-shares"></a><span data-ttu-id="38553-311">檔案共用</span><span class="sxs-lookup"><span data-stu-id="38553-311">File shares</span></span>

<span data-ttu-id="38553-312">檔案共用可以位於不同的伺服器上，也可以在與下列任何或所有專案相同的伺服器上組合：</span><span class="sxs-lookup"><span data-stu-id="38553-312">The file share can be on a separate server, or you can collocate it on the same server as any or all of the following:</span></span>

- <span data-ttu-id="38553-313">資料庫伺服器，包括 Enterprise Edition 前端集區的後端伺服器</span><span class="sxs-lookup"><span data-stu-id="38553-313">Database server, including the Back End Server of an Enterprise Edition Front End pool</span></span>

- <span data-ttu-id="38553-314">監控資料庫</span><span class="sxs-lookup"><span data-stu-id="38553-314">Monitoring database</span></span>

- <span data-ttu-id="38553-315">封存資料庫</span><span class="sxs-lookup"><span data-stu-id="38553-315">Archiving database</span></span>

- <span data-ttu-id="38553-316">Persistent Chat 資料庫</span><span class="sxs-lookup"><span data-stu-id="38553-316">Persistent Chat database</span></span>

- <span data-ttu-id="38553-317">Persistent Chat 規範資料庫</span><span class="sxs-lookup"><span data-stu-id="38553-317">Persistent Chat compliance database</span></span>

> [!CAUTION]
> <span data-ttu-id="38553-318">請注意，雖然您可以在這些伺服器上組合檔案共用，但是請務必注意，我們不建議您這樣做。</span><span class="sxs-lookup"><span data-stu-id="38553-318">Note that while you can collocate the file share on these servers, it's vital to note that we don't recommend it.</span></span> <span data-ttu-id="38553-319">如果您要組合任何其他伺服器角色的檔案共用，請務必定期監控磁碟空間和效能問題。</span><span class="sxs-lookup"><span data-stu-id="38553-319">If you're collocating the file share with any other server role, please make sure you're monitoring for disk space and performance issues on a regular basis.</span></span>

### <a name="keep-in-mind"></a><span data-ttu-id="38553-320">請記住</span><span class="sxs-lookup"><span data-stu-id="38553-320">Keep in mind</span></span>

- <span data-ttu-id="38553-321">您無法組合反向 proxy 伺服器，這不是商務用 Skype Server 元件，甚至可能不會在您的拓撲中。</span><span class="sxs-lookup"><span data-stu-id="38553-321">You can't collocate a reverse proxy server, which isn't a Skype for Business Server component, and may not even be in your topology.</span></span> <span data-ttu-id="38553-322">如果您想要支援同盟使用者的 web 內容共用，以及許多其他專案，則需要反向 proxy。</span><span class="sxs-lookup"><span data-stu-id="38553-322">You'll need a reverse proxy if you want to support sharing of web content for federated users, among many other things.</span></span> <span data-ttu-id="38553-323">如有需要，請在您的組織中，設定其他應用程式所使用的現有反向 proxy 伺服器，繼續並為商務用 Skype 伺服器實施反向 proxy 支援。</span><span class="sxs-lookup"><span data-stu-id="38553-323">If you need to, go ahead and implement reverse proxy support for Skype for Business Server by configuring an existing reverse proxy server that's already in your organization that's being used by other applications.</span></span>

- <span data-ttu-id="38553-324">您無法組合任何 Exchange UM 元件或使用任何商務用 Skype Server 角色的 SharePoint 伺服器元件。</span><span class="sxs-lookup"><span data-stu-id="38553-324">You can't collocate any Exchange UM component or SharePoint Server component with any Skype for Business Server role.</span></span>

## <a name="see-also"></a><span data-ttu-id="38553-325">另請參閱</span><span class="sxs-lookup"><span data-stu-id="38553-325">See also</span></span>

[<span data-ttu-id="38553-326">商務用 Skype Server 的參考拓撲</span><span class="sxs-lookup"><span data-stu-id="38553-326">Reference topologies for Skype for Business Server</span></span>](reference-topologies.md)