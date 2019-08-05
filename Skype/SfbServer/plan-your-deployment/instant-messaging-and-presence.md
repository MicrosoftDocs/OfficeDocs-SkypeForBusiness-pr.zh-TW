---
title: 在商務用 Skype Server 中規劃立即訊息和目前狀態
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 70d2151e-9382-485d-ab14-758597571a74
description: '摘要: 瞭解如何在商務用 Skype Server 中規劃立即訊息和目前狀態。'
ms.openlocfilehash: 29026a0b4ef7cce55f155f024efc9ccc84457906
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192990"
---
# <a name="plan-for-instant-messaging-and-presence-in-skype-for-business-server"></a><span data-ttu-id="14907-103">在商務用 Skype Server 中規劃立即訊息和目前狀態</span><span class="sxs-lookup"><span data-stu-id="14907-103">Plan for instant messaging and presence in Skype for Business Server</span></span>
 
<span data-ttu-id="14907-104">**摘要:** 瞭解如何在商務用 Skype Server 中規劃立即訊息和目前狀態。</span><span class="sxs-lookup"><span data-stu-id="14907-104">**Summary:** Learn how to plan for instant messaging and presence in Skype for Business Server.</span></span>
  
<span data-ttu-id="14907-105">規劃商務用 Skype Server 中的立即訊息和目前狀態。</span><span class="sxs-lookup"><span data-stu-id="14907-105">Plan for instant messaging and presence in Skype for Business Server.</span></span> <span data-ttu-id="14907-106">若要瞭解特定的部署選項 (例如啟用或停用離線立即訊息 (IM)), 請參閱[在商務用 Skype Server 中部署立即訊息和目前狀態](../deploy/im-and-presence/im-and-presence.md)。</span><span class="sxs-lookup"><span data-stu-id="14907-106">To learn about specific deployment options, such as enabling or disabling Offline Instant Messaging (IM), see [Deploy instant messaging and presence in Skype for Business Server](../deploy/im-and-presence/im-and-presence.md).</span></span>
  
## <a name="plan-for-instant-messaging-and-presence-in-skype-for-business-server"></a><span data-ttu-id="14907-107">在商務用 Skype Server 中規劃立即訊息和目前狀態</span><span class="sxs-lookup"><span data-stu-id="14907-107">Plan for instant messaging and presence in Skype for Business Server</span></span>

<span data-ttu-id="14907-108">前端伺服器提供核心的商務用 Skype 伺服器功能, 例如立即訊息 (IM) 和目前狀態, 且包含在每個商務用 Skype Server 部署中。</span><span class="sxs-lookup"><span data-stu-id="14907-108">Front End Servers provide core Skype for Business Server functionality such as instant messaging (IM) and presence and are included in every Skype for Business Server deployment.</span></span> <span data-ttu-id="14907-109">有兩種版本可供使用: 商務用 Skype Server Enterprise Edition, 主要針對較大型的組織和商務用 Skype Server Standard Edition 設計, 主要針對需要較小單位的較小組織。硬體投資且不需要完整的高可用性選項。</span><span class="sxs-lookup"><span data-stu-id="14907-109">There are two editions available: Skype for Business Server Enterprise Edition, which is designed primarily for larger organizations, and Skype for Business Server Standard Edition, which is designed primarily for smaller organizations which want a smaller hardware investment and do not require full high availability options.</span></span> <span data-ttu-id="14907-110">這兩種版本都支援所有商務用 Skype 伺服器工作負載, 包括 IM、目前狀態、會議和企業語音。</span><span class="sxs-lookup"><span data-stu-id="14907-110">Both editions support all Skype for Business Server workloads including IM, presence, conferencing, and Enterprise Voice.</span></span>
  
<span data-ttu-id="14907-111">[立即訊息 (IM)] 可讓您的使用者在電腦上使用文字型郵件即時相互通訊。</span><span class="sxs-lookup"><span data-stu-id="14907-111">Instant messaging (IM) enables your users to communicate with each other in real time on their computers using text-based messages.</span></span> <span data-ttu-id="14907-112">支援兩方和多方 IM 會話。</span><span class="sxs-lookup"><span data-stu-id="14907-112">Both two-party and multiparty IM sessions are supported.</span></span> <span data-ttu-id="14907-113">在雙方的 IM 交談中, 參與者可以隨時新增協力廠商參與者加入交談。</span><span class="sxs-lookup"><span data-stu-id="14907-113">A participant in a two-party IM conversation can add a third participant to the conversation at any time.</span></span> <span data-ttu-id="14907-114">發生這種情況時, 交談視窗會變更以支援會議功能。</span><span class="sxs-lookup"><span data-stu-id="14907-114">When this happens, the Conversation window changes to support conferencing features.</span></span>
  
<span data-ttu-id="14907-115">[目前狀態] 會提供資訊給使用者, 瞭解網路上其他人的狀態。</span><span class="sxs-lookup"><span data-stu-id="14907-115">Presence provides information to users about the status of others on the network.</span></span> <span data-ttu-id="14907-116">使用者的目前狀態會提供資訊, 協助其他人決定是否應該嘗試與使用者聯繫, 以及是否要使用立即訊息、電話或電子郵件。</span><span class="sxs-lookup"><span data-stu-id="14907-116">A user's presence status provides information to help others decide whether they should try to contact the user and whether to use instant messaging, phone, or email.</span></span> <span data-ttu-id="14907-117">如果可能的話, 目前狀態會鼓勵立即通訊, 但它也會提供使用者是否在會議中或不在辦公室的相關資訊, 指出無法進行立即通訊。</span><span class="sxs-lookup"><span data-stu-id="14907-117">Presence encourages instant communication when possible, but it also provides information about whether a user is in a meeting or out of the office, indicating that instant communication is not possible.</span></span> <span data-ttu-id="14907-118">在商務用 Skype 和其他存在感知的應用程式 (包括 Microsoft Outlook 訊息與共同作業用戶端、Microsoft SharePoint 技術及 Microsoft Office) 中, 此目前狀態會顯示為「目前狀態」圖示。</span><span class="sxs-lookup"><span data-stu-id="14907-118">This presence status is displayed as a presence icon in Skype for Business and other presence-aware applications, including the Microsoft Outlook messaging and collaboration client, Microsoft SharePoint technologies, and Microsoft Office.</span></span> <span data-ttu-id="14907-119">[目前狀態] 圖示代表使用者目前的可用性和溝通意願。</span><span class="sxs-lookup"><span data-stu-id="14907-119">The presence icon represents the user's current availability and willingness to communicate.</span></span> 
  
### <a name="technical-requirements"></a><span data-ttu-id="14907-120">技術需求</span><span class="sxs-lookup"><span data-stu-id="14907-120">Technical requirements</span></span>

<span data-ttu-id="14907-121">[立即訊息 (IM)] 和 [目前狀態] 都是在企業版前端池和標準版伺服器上執行。</span><span class="sxs-lookup"><span data-stu-id="14907-121">Instant messaging (IM) and presence always run on Enterprise Edition Front End pools and Standard Edition servers.</span></span> <span data-ttu-id="14907-122">如需支援的硬體、作業系統及資料庫軟體的相關資訊, 請參閱[認證閘道](../../SfbPartnerCertification/certification/infra-gateways.md)、[商務用 skype 2015 環境的需求](requirements-for-your-environment/requirements-for-your-environment.md), 以及[商務用 Skype Server 2019 的基礎結構需求](../../SfBServer2019/plan/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="14907-122">For information on supported hardware, operating systems, and database software, see  [Certified Gateways](../../SfbPartnerCertification/certification/infra-gateways.md),  [Requirements for your Skype for Business 2015 environment](requirements-for-your-environment/requirements-for-your-environment.md), and [Infrastructure requirements for Skype for Business Server 2019](../../SfBServer2019/plan/system-requirements.md).</span></span>
  
### <a name="enabling-communication-with-external-users"></a><span data-ttu-id="14907-123">啟用與外部使用者的通訊</span><span class="sxs-lookup"><span data-stu-id="14907-123">Enabling communication with external users</span></span>

<span data-ttu-id="14907-124">您可以讓您的使用者與外部使用者通訊, 大幅提高您在商務用 Skype Server 中投資的益處。</span><span class="sxs-lookup"><span data-stu-id="14907-124">You can greatly increase the benefits of your investment in Skype for Business Server by enabling your users to communicate with external users.</span></span> <span data-ttu-id="14907-125">外部使用者可以包括:</span><span class="sxs-lookup"><span data-stu-id="14907-125">External users can include:</span></span>
  
- <span data-ttu-id="14907-126">遠端使用者: 貴組織自己的使用者、在防火牆外工作, 且正在使用其膝上型電腦或其他商務用 Skype 伺服器裝置。</span><span class="sxs-lookup"><span data-stu-id="14907-126">Remote users: Your organization's own users, when they are working outside your firewalls and are using their laptops or other Skype for Business Server devices.</span></span>
    
- <span data-ttu-id="14907-127">同盟使用者: 您與其他人同時執行商務用 Skype Server 的公司使用者。</span><span class="sxs-lookup"><span data-stu-id="14907-127">Federated users: Users from companies you work with who also run Skype for Business Server.</span></span> <span data-ttu-id="14907-128">若要讓您的使用者能夠輕鬆地與這些使用者聯繫, 您可以建立與這些公司的聯盟關聯。</span><span class="sxs-lookup"><span data-stu-id="14907-128">To enable your users to easily contact these users, you create federated relationships with these companies.</span></span> 
    
- <span data-ttu-id="14907-129">Skype 使用者: 商務用 Skype 使用者可以使用 IM、語音和影片, 在 Skype 中與成百上千的使用者取得聯繫。</span><span class="sxs-lookup"><span data-stu-id="14907-129">Skype users: Skype for Business users can reach the hundreds of millions of users on Skype with IM, voice and video.</span></span>
    
> [!NOTE]
> <span data-ttu-id="14907-130">已不再支援 AOL、Yahoo 和 Google 交談。</span><span class="sxs-lookup"><span data-stu-id="14907-130">AOL, Yahoo, and Google Talk are no longer supported.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="14907-131">若要啟用任何一種或所有案例, 您必須部署邊緣伺服器, 以協助您在商務用 Skype Server 部署與外部使用者之間進行安全通訊。</span><span class="sxs-lookup"><span data-stu-id="14907-131">To enable any or all of these scenarios, you need to deploy an Edge Server to help enable secure communications between your Skype for Business Server deployment and external users.</span></span> <span data-ttu-id="14907-132">貴組織的遠端使用者和聯盟組織中的使用者將能夠彼此查看其目前狀態並使用 IM 進行通訊。</span><span class="sxs-lookup"><span data-stu-id="14907-132">Your organization's remote users and users at federated organizations will be able to see each other's presence and communicate using IM.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="14907-133">只有整合功能共同作業平臺 (UCCP) 聯合互通性測試命令 (JITC) 認證案例, 才能支援可擴展訊息與目前狀態通訊協定 (XMPP)。</span><span class="sxs-lookup"><span data-stu-id="14907-133">Extensible Messaging and Presence Protocol (XMPP) is only supported for Unified Capabilities Collaboration Platform (UCCP) Joint Interoperability Test Command (JITC) certification scenarios.</span></span> 
  
### <a name="archiving-im-content"></a><span data-ttu-id="14907-134">封存 IM 內容</span><span class="sxs-lookup"><span data-stu-id="14907-134">Archiving IM content</span></span>

<span data-ttu-id="14907-135">如果您的組織必須遵循合規性規範, 商務用 Skype Server 提供您可以使用的功能。</span><span class="sxs-lookup"><span data-stu-id="14907-135">Skype for Business Server provides features you can use if your organization must follow compliance regulations.</span></span> <span data-ttu-id="14907-136">您可以使用 [封存] 來封存貴組織中所有使用者的 IM 訊息內容, 或只針對您指定的特定使用者封存 IM 訊息的內容。</span><span class="sxs-lookup"><span data-stu-id="14907-136">You can use Archiving to archive the content of IM messages for all users in your organization or for only certain users that you specify.</span></span> <span data-ttu-id="14907-137">如需詳細資訊, 請參閱[在商務用 Skype 伺服器中規劃](archiving/archiving.md)封存。</span><span class="sxs-lookup"><span data-stu-id="14907-137">For details, see [Plan for archiving in Skype for Business Server](archiving/archiving.md).</span></span> 
  
<span data-ttu-id="14907-138">如果您也已部署 Microsoft Exchange Server 2013, 您可以將 Exchange 資料的存檔與商務用 Skype 伺服器資料進行整合, 然後使用單一工具來搜尋這兩種類型的已歸檔資料。</span><span class="sxs-lookup"><span data-stu-id="14907-138">If you also have Microsoft Exchange Server 2013 deployed, you can integrate the archiving of Exchange data with the archiving of Skype for Business Server data, and use a single tool to search both types of archived data.</span></span> <span data-ttu-id="14907-139">如需詳細資訊, 請參閱[設定商務用 Skype 伺服器以使用 Exchange 伺服器](../deploy/integrate-with-exchange-server/use-exchange-archiving.md)封存。</span><span class="sxs-lookup"><span data-stu-id="14907-139">For more information, see [Configure Skype for Business Server to use Exchange Server archiving](../deploy/integrate-with-exchange-server/use-exchange-archiving.md).</span></span>
  
### <a name="topologies-and-components"></a><span data-ttu-id="14907-140">拓撲與元件</span><span class="sxs-lookup"><span data-stu-id="14907-140">Topologies and components</span></span>

<span data-ttu-id="14907-141">立即訊息 (IM) 與目前狀態所需的元件如下:</span><span class="sxs-lookup"><span data-stu-id="14907-141">The only components required for instant messaging (IM) and presence are:</span></span>
  
- <span data-ttu-id="14907-142">貴組織的前端伺服器 (稱為「池」) 或標準版伺服器。</span><span class="sxs-lookup"><span data-stu-id="14907-142">Your organization's Front End servers (known as a pool) or a Standard Edition server.</span></span> <span data-ttu-id="14907-143">在這些伺服器上, 系統永遠都能啟用 IM 和目前狀態功能。</span><span class="sxs-lookup"><span data-stu-id="14907-143">IM and presence capabilities are always enabled on these servers.</span></span> <span data-ttu-id="14907-144">如需前端池拓撲與管理的詳細資訊, 請參閱[前端池高可用性和管理](high-availability-and-disaster-recovery/high-availability.md)。</span><span class="sxs-lookup"><span data-stu-id="14907-144">For more information on Front End pool topologies and management, see [Front End Pool high availability and management](high-availability-and-disaster-recovery/high-availability.md).</span></span>
    
- <span data-ttu-id="14907-145">[負載平衡器] (如果您有企業版的 [前端] 池)。</span><span class="sxs-lookup"><span data-stu-id="14907-145">A load balancer, if you have an Enterprise Edition Front End pool.</span></span>
    
### <a name="supported-collocation"></a><span data-ttu-id="14907-146">支援的 collocation</span><span class="sxs-lookup"><span data-stu-id="14907-146">Supported collocation</span></span>

<span data-ttu-id="14907-147">Collocation 定義為安裝了多個角色的單一伺服器或一組伺服器。</span><span class="sxs-lookup"><span data-stu-id="14907-147">Collocation is defined as having a single server, or group of servers, with multiple roles installed.</span></span> <span data-ttu-id="14907-148">如需 collocation 的詳細資訊, 請參閱[商務用 Skype Server 的拓撲基礎](topology-basics/topology-basics.md)。</span><span class="sxs-lookup"><span data-stu-id="14907-148">For details on collocation, see [Topology Basics for Skype for Business Server](topology-basics/topology-basics.md).</span></span> 
  

