---
title: 在商務用 Skype Server 中規劃立即訊息和目前狀態
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
ms.assetid: 70d2151e-9382-485d-ab14-758597571a74
description: 摘要：瞭解如何在商務用 Skype Server 中規劃立即訊息和目前狀態。
ms.openlocfilehash: a29d68cc66e0ac4a70fc759283646fc3ce49cdf5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816273"
---
# <a name="plan-for-instant-messaging-and-presence-in-skype-for-business-server"></a><span data-ttu-id="bb56f-103">在商務用 Skype Server 中規劃立即訊息和目前狀態</span><span class="sxs-lookup"><span data-stu-id="bb56f-103">Plan for instant messaging and presence in Skype for Business Server</span></span>
 
<span data-ttu-id="bb56f-104">**摘要：** 瞭解如何在商務用 Skype Server 中規劃立即訊息和目前狀態。</span><span class="sxs-lookup"><span data-stu-id="bb56f-104">**Summary:** Learn how to plan for instant messaging and presence in Skype for Business Server.</span></span>
  
<span data-ttu-id="bb56f-105">在商務用 Skype Server 中規劃立即訊息和目前狀態。</span><span class="sxs-lookup"><span data-stu-id="bb56f-105">Plan for instant messaging and presence in Skype for Business Server.</span></span> <span data-ttu-id="bb56f-106">若要瞭解特定的部署選項，例如啟用或停用離線立即訊息 (IM) ，請參閱 [在商務用 Skype Server 中部署立即訊息與顯示狀態](../deploy/im-and-presence/im-and-presence.md)。</span><span class="sxs-lookup"><span data-stu-id="bb56f-106">To learn about specific deployment options, such as enabling or disabling Offline Instant Messaging (IM), see [Deploy instant messaging and presence in Skype for Business Server](../deploy/im-and-presence/im-and-presence.md).</span></span>
  
## <a name="plan-for-instant-messaging-and-presence-in-skype-for-business-server"></a><span data-ttu-id="bb56f-107">在商務用 Skype Server 中規劃立即訊息和目前狀態</span><span class="sxs-lookup"><span data-stu-id="bb56f-107">Plan for instant messaging and presence in Skype for Business Server</span></span>

<span data-ttu-id="bb56f-108">前端伺服器提供核心商務用 Skype Server 功能（如立即訊息 (IM) 和顯示狀態），並包含在每個商務用 Skype Server 部署中。</span><span class="sxs-lookup"><span data-stu-id="bb56f-108">Front End Servers provide core Skype for Business Server functionality such as instant messaging (IM) and presence and are included in every Skype for Business Server deployment.</span></span> <span data-ttu-id="bb56f-109">有兩種可供使用的版本：商務用 Skype Server Enterprise Edition 主要專為較大的組織和商務用 Skype Server Standard Edition 設計，其主要是針對需要較小硬體投資且不需要完整高可用性選項的小型組織所設計。</span><span class="sxs-lookup"><span data-stu-id="bb56f-109">There are two editions available: Skype for Business Server Enterprise Edition, which is designed primarily for larger organizations, and Skype for Business Server Standard Edition, which is designed primarily for smaller organizations which want a smaller hardware investment and do not require full high availability options.</span></span> <span data-ttu-id="bb56f-110">這兩種版本都支援所有商務用 Skype Server 工作負載，包括 IM、顯示狀態、會議及 Enterprise Voice。</span><span class="sxs-lookup"><span data-stu-id="bb56f-110">Both editions support all Skype for Business Server workloads including IM, presence, conferencing, and Enterprise Voice.</span></span>
  
<span data-ttu-id="bb56f-p103">立即訊息 (IM) 可讓使用者在電腦上使用文字訊息，與其他使用者進行即時溝通。同時支援雙方或多方 IM 工作階段。雙方 IM 交談中的參與者可以隨時將第三個參與者加入交談中。若發生這種情況，[交談] 視窗會變更成可支援會議功能。</span><span class="sxs-lookup"><span data-stu-id="bb56f-p103">Instant messaging (IM) enables your users to communicate with each other in real time on their computers using text-based messages. Both two-party and multiparty IM sessions are supported. A participant in a two-party IM conversation can add a third participant to the conversation at any time. When this happens, the Conversation window changes to support conferencing features.</span></span>
  
<span data-ttu-id="bb56f-115">目前狀態為使用者提供有關網路上其他人狀態的資訊。</span><span class="sxs-lookup"><span data-stu-id="bb56f-115">Presence provides information to users about the status of others on the network.</span></span> <span data-ttu-id="bb56f-116">使用者的目前狀態提供的資訊可協助其他人決定是否應該嘗試聯繫使用者，以及是否使用立即訊息、電話或電子郵件。</span><span class="sxs-lookup"><span data-stu-id="bb56f-116">A user's presence status provides information to help others decide whether they should try to contact the user and whether to use instant messaging, phone, or email.</span></span> <span data-ttu-id="bb56f-117">目前狀態會促進立即通訊，但也會提供使用者正在開會中或不在辦公室的資訊，指出無法進行立即通訊。</span><span class="sxs-lookup"><span data-stu-id="bb56f-117">Presence encourages instant communication when possible, but it also provides information about whether a user is in a meeting or out of the office, indicating that instant communication is not possible.</span></span> <span data-ttu-id="bb56f-118">這種目前狀態會顯示為商務用 Skype 中的目前狀態圖示及其他狀態識別應用程式，包括 Microsoft Outlook 訊息和共同作業用戶端、Microsoft SharePoint 技術和 Microsoft Office。</span><span class="sxs-lookup"><span data-stu-id="bb56f-118">This presence status is displayed as a presence icon in Skype for Business and other presence-aware applications, including the Microsoft Outlook messaging and collaboration client, Microsoft SharePoint technologies, and Microsoft Office.</span></span> <span data-ttu-id="bb56f-119">目前狀態圖示代表使用者的目前可用性和溝通意願。</span><span class="sxs-lookup"><span data-stu-id="bb56f-119">The presence icon represents the user's current availability and willingness to communicate.</span></span> 
  
### <a name="technical-requirements"></a><span data-ttu-id="bb56f-120">技術需求</span><span class="sxs-lookup"><span data-stu-id="bb56f-120">Technical requirements</span></span>

<span data-ttu-id="bb56f-121">立即訊息 (IM) 和目前狀態，永遠都是在 Enterprise Edition 前端集區和 Standard Edition server 上執行。</span><span class="sxs-lookup"><span data-stu-id="bb56f-121">Instant messaging (IM) and presence always run on Enterprise Edition Front End pools and Standard Edition servers.</span></span> <span data-ttu-id="bb56f-122">如需支援的硬體、作業系統及資料庫軟體的資訊，請參閱已  [驗證的閘道](../../SfbPartnerCertification/certification/infra-gateways.md)、  [商務用 skype 2015 環境的需求](requirements-for-your-environment/requirements-for-your-environment.md)，以及商務用 [Skype Server 2019 的基礎結構需求](../../SfBServer2019/plan/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="bb56f-122">For information on supported hardware, operating systems, and database software, see  [Certified Gateways](../../SfbPartnerCertification/certification/infra-gateways.md),  [Requirements for your Skype for Business 2015 environment](requirements-for-your-environment/requirements-for-your-environment.md), and [Infrastructure requirements for Skype for Business Server 2019](../../SfBServer2019/plan/system-requirements.md).</span></span>
  
### <a name="enabling-communication-with-external-users"></a><span data-ttu-id="bb56f-123">啟用與外部使用者的通訊</span><span class="sxs-lookup"><span data-stu-id="bb56f-123">Enabling communication with external users</span></span>

<span data-ttu-id="bb56f-124">您可以讓您的使用者與外部使用者通訊，以大幅提高商務用 Skype Server 中的投資效益。</span><span class="sxs-lookup"><span data-stu-id="bb56f-124">You can greatly increase the benefits of your investment in Skype for Business Server by enabling your users to communicate with external users.</span></span> <span data-ttu-id="bb56f-125">外部使用者包括：</span><span class="sxs-lookup"><span data-stu-id="bb56f-125">External users can include:</span></span>
  
- <span data-ttu-id="bb56f-126">遠端使用者：貴組織自身的使用者、在防火牆外工作時使用其膝上型電腦或其他商務用 Skype Server 裝置的使用者。</span><span class="sxs-lookup"><span data-stu-id="bb56f-126">Remote users: Your organization's own users, when they are working outside your firewalls and are using their laptops or other Skype for Business Server devices.</span></span>
    
- <span data-ttu-id="bb56f-127">同盟使用者：來自公司的使用者，您可以使用同時執行商務用 Skype 伺服器的使用者。</span><span class="sxs-lookup"><span data-stu-id="bb56f-127">Federated users: Users from companies you work with who also run Skype for Business Server.</span></span> <span data-ttu-id="bb56f-128">為了方便您的使用者輕鬆連絡這些使用者，您可以和這些公司建立同盟關係。</span><span class="sxs-lookup"><span data-stu-id="bb56f-128">To enable your users to easily contact these users, you create federated relationships with these companies.</span></span> 
    
- <span data-ttu-id="bb56f-129">Skype 使用者：商務用 Skype 使用者可以使用 IM、語音和影片，抵達數百億位使用者的 Skype。</span><span class="sxs-lookup"><span data-stu-id="bb56f-129">Skype users: Skype for Business users can reach the hundreds of millions of users on Skype with IM, voice and video.</span></span>
    
> [!NOTE]
> <span data-ttu-id="bb56f-130">已不再支援 AOL、Yahoo 和 Google 交談。</span><span class="sxs-lookup"><span data-stu-id="bb56f-130">AOL, Yahoo, and Google Talk are no longer supported.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="bb56f-131">若要啟用任何或所有上述案例，您必須部署 Edge Server，以協助啟用商務用 Skype 伺服器部署與外部使用者之間的安全通訊。</span><span class="sxs-lookup"><span data-stu-id="bb56f-131">To enable any or all of these scenarios, you need to deploy an Edge Server to help enable secure communications between your Skype for Business Server deployment and external users.</span></span> <span data-ttu-id="bb56f-132">貴組織的遠端使用者和同盟組織的使用者，將能夠看到彼此的目前狀態，並使用 IM 進行通訊。</span><span class="sxs-lookup"><span data-stu-id="bb56f-132">Your organization's remote users and users at federated organizations will be able to see each other's presence and communicate using IM.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="bb56f-133">只有整合功能共同作業平臺 (UCCP (XMPP) 支援 [可延伸的訊息和顯示狀態通訊協定]，) 協同互通性測試命令 (JITC) 認證案例。</span><span class="sxs-lookup"><span data-stu-id="bb56f-133">Extensible Messaging and Presence Protocol (XMPP) is only supported for Unified Capabilities Collaboration Platform (UCCP) Joint Interoperability Test Command (JITC) certification scenarios.</span></span> 
  
### <a name="archiving-im-content"></a><span data-ttu-id="bb56f-134">封存 IM 內容</span><span class="sxs-lookup"><span data-stu-id="bb56f-134">Archiving IM content</span></span>

<span data-ttu-id="bb56f-135">如果您的組織必須遵循合規性規定，商務用 Skype 伺服器提供您可以使用的功能。</span><span class="sxs-lookup"><span data-stu-id="bb56f-135">Skype for Business Server provides features you can use if your organization must follow compliance regulations.</span></span> <span data-ttu-id="bb56f-136">您可以使用封存為組織中的所有使用者或您指定的特定使用者封存 IM 訊息的內容。</span><span class="sxs-lookup"><span data-stu-id="bb56f-136">You can use Archiving to archive the content of IM messages for all users in your organization or for only certain users that you specify.</span></span> <span data-ttu-id="bb56f-137">如需詳細資訊，請參閱 Plan for 封存 [In 商務用 Skype Server](archiving/archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="bb56f-137">For details, see [Plan for archiving in Skype for Business Server](archiving/archiving.md).</span></span> 
  
<span data-ttu-id="bb56f-138">如果您也部署 Microsoft Exchange Server 2013，您可以整合 Exchange 資料與商務用 Skype Server 資料的封存，並使用單一工具來搜尋這兩種類型的封存資料。</span><span class="sxs-lookup"><span data-stu-id="bb56f-138">If you also have Microsoft Exchange Server 2013 deployed, you can integrate the archiving of Exchange data with the archiving of Skype for Business Server data, and use a single tool to search both types of archived data.</span></span> <span data-ttu-id="bb56f-139">如需詳細資訊，請參閱 [Configure 商務用 Skype Server to Use Exchange Server](../deploy/integrate-with-exchange-server/use-exchange-archiving.md)封存。</span><span class="sxs-lookup"><span data-stu-id="bb56f-139">For more information, see [Configure Skype for Business Server to use Exchange Server archiving](../deploy/integrate-with-exchange-server/use-exchange-archiving.md).</span></span>
  
### <a name="topologies-and-components"></a><span data-ttu-id="bb56f-140">拓撲和元件</span><span class="sxs-lookup"><span data-stu-id="bb56f-140">Topologies and components</span></span>

<span data-ttu-id="bb56f-141">立即訊息 (IM) 和目前狀態所需的元件包括：</span><span class="sxs-lookup"><span data-stu-id="bb56f-141">The only components required for instant messaging (IM) and presence are:</span></span>
  
- <span data-ttu-id="bb56f-142">組織的前端伺服器 (稱為集區) 或 Standard Edition server。</span><span class="sxs-lookup"><span data-stu-id="bb56f-142">Your organization's Front End servers (known as a pool) or a Standard Edition server.</span></span> <span data-ttu-id="bb56f-143">IM 和目前狀態功能在這些伺服器上一定會啟用。</span><span class="sxs-lookup"><span data-stu-id="bb56f-143">IM and presence capabilities are always enabled on these servers.</span></span> <span data-ttu-id="bb56f-144">如需前端集區拓撲和管理的詳細資訊，請參閱 [前端集區高可用性和管理](high-availability-and-disaster-recovery/high-availability.md)。</span><span class="sxs-lookup"><span data-stu-id="bb56f-144">For more information on Front End pool topologies and management, see [Front End Pool high availability and management](high-availability-and-disaster-recovery/high-availability.md).</span></span>
    
- <span data-ttu-id="bb56f-145">負載平衡器（如果您有 Enterprise Edition 前端集區）。</span><span class="sxs-lookup"><span data-stu-id="bb56f-145">A load balancer, if you have an Enterprise Edition Front End pool.</span></span>
    
### <a name="supported-collocation"></a><span data-ttu-id="bb56f-146">支援的組合</span><span class="sxs-lookup"><span data-stu-id="bb56f-146">Supported collocation</span></span>

<span data-ttu-id="bb56f-147">組合定義為具有已安裝多個角色的單一伺服器或伺服器群組。</span><span class="sxs-lookup"><span data-stu-id="bb56f-147">Collocation is defined as having a single server, or group of servers, with multiple roles installed.</span></span> <span data-ttu-id="bb56f-148">如需組合的詳細資訊，請參閱 [適用于商務用 Skype Server 的拓撲基礎](topology-basics/topology-basics.md)。</span><span class="sxs-lookup"><span data-stu-id="bb56f-148">For details on collocation, see [Topology Basics for Skype for Business Server](topology-basics/topology-basics.md).</span></span> 
  

