---
title: 對 Persistent Chat Server 執行回溯相容性
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Run backward compatibility for Persistent Chat Server
ms:assetid: 53f1a706-3104-4a94-8b4e-8badd9a066d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204901(v=OCS.15)
ms:contentKeyID: 48184175
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5308d39e4edcfeddf494aa364f6b7ed43b9822dc
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755767"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="run-backward-compatibility-for-persistent-chat-server"></a><span data-ttu-id="21f4d-102">對 Persistent Chat Server 執行回溯相容性</span><span class="sxs-lookup"><span data-stu-id="21f4d-102">Run backward compatibility for Persistent Chat Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="21f4d-103">_**主題上次修改日期：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="21f4d-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="21f4d-104">Lync Server 2013，Persistent Chat Server 端點提供一種方式，來建立指向 Persistent Chat Server 集區的簡單 URL。</span><span class="sxs-lookup"><span data-stu-id="21f4d-104">The Lync Server 2013, Persistent Chat Server endpoint provides a way to create a simple URL that points to a Persistent Chat Server pool.</span></span> <span data-ttu-id="21f4d-105">這對舊版用戶端（Microsoft Office 通訊伺服器 2007 R2 Group Chat Server 或 Lync Server 2010，群組聊天）很有用，因為使用者可以在手動設定中輸入簡單 URL，嘗試將舊版用戶端指向執行 Lync 2013 的電腦（持續聊天）。</span><span class="sxs-lookup"><span data-stu-id="21f4d-105">This is useful for legacy clients (Microsoft Office Communications Server 2007 R2 Group Chat Server or Lync Server 2010, Group Chat) because users can enter a simple URL in the manual configuration when trying to point the legacy client to a computer running Lync 2013, Persistent Chat.</span></span> <span data-ttu-id="21f4d-106">持續性聊天不會使用此端點，只對舊版用戶端是必要的。</span><span class="sxs-lookup"><span data-stu-id="21f4d-106">This endpoint isn’t used by Persistent Chat, and is required for legacy clients only.</span></span> <span data-ttu-id="21f4d-107">這對可以遷移會議室的過渡期很有用，但是尚未在整個組織中部署 Lync 2013 用戶端。</span><span class="sxs-lookup"><span data-stu-id="21f4d-107">This is useful for the interim period where rooms may be migrated, but the Lync 2013 clients have not been deployed throughout the organization.</span></span> <span data-ttu-id="21f4d-108">執行 Lync 2010 群組聊天（用戶端）的使用者仍可連線到 Persistent Chat Server 後端伺服器。</span><span class="sxs-lookup"><span data-stu-id="21f4d-108">Users running Lync 2010 Group Chat (client) can then still connect to the Persistent Chat Server Back End Server.</span></span>

<span data-ttu-id="21f4d-109">您不需要建立多個 Persistent 聊天伺服器端點;您只需要每個 Persistent Chat Server 集區的一個。</span><span class="sxs-lookup"><span data-stu-id="21f4d-109">You don’t need to create multiple Persistent Chat Server endpoints; you just need one for each Persistent Chat Server pool.</span></span> <span data-ttu-id="21f4d-110">系統管理員可以建立多個端點 (每個集區一個)，但可將舊版用戶端設定為一次只能連線至一個集區。</span><span class="sxs-lookup"><span data-stu-id="21f4d-110">Administrators can create multiple endpoints (one per pool), but legacy clients can be configured to connect to only one pool at a time.</span></span> <span data-ttu-id="21f4d-111">在一般或主流案例中，舊版部署只是一個集區。</span><span class="sxs-lookup"><span data-stu-id="21f4d-111">In the usual or mainstream scenario, the legacy deployment is one pool only.</span></span> <span data-ttu-id="21f4d-112">新的部署通常會將該集區遷移至新的 Lync Server 2013，而且可能會新增額外的其他 Persistent Chat Server 集區。</span><span class="sxs-lookup"><span data-stu-id="21f4d-112">A new deployment generally migrates that pool to a new Lync Server 2013 and might add some new additional Persistent Chat Server pools.</span></span>

<span data-ttu-id="21f4d-113">此主流案例通常會遵循下列模式：</span><span class="sxs-lookup"><span data-stu-id="21f4d-113">This mainstream scenario generally follows this pattern:</span></span>

  - <span data-ttu-id="21f4d-114">您可以管理具有一個 Lync Server 2010、群組聊天集區的使用者，以及 Lync 2010 群組聊天用戶端使用一些著名的使用者（預設 sip： ocschat@ \<domainName\> .com 或類似的使用者）連線至該集區。</span><span class="sxs-lookup"><span data-stu-id="21f4d-114">You administer users with one Lync Server 2010, Group Chat pool, and your Lync 2010 Group Chat clients connect to that pool by using some well-known user (either default sip:ocschat@\<domainName\>.com, or a similar one).</span></span> <span data-ttu-id="21f4d-115">使用者 SIP-enabled Active Directory 網域服務，且查閱服務會向其註冊以接收傳入的要求。</span><span class="sxs-lookup"><span data-stu-id="21f4d-115">The users are SIP-enabled Active Directory Domain Services, and the Lookup service registers with them to receive incoming requests.</span></span>

  - <span data-ttu-id="21f4d-116">接著，您會安裝 Lync Server 2013 Persistent Chat Server 和 Persistent Chat Server 集區。</span><span class="sxs-lookup"><span data-stu-id="21f4d-116">Subsequently, you install a Lync Server 2013 Persistent Chat Server and Persistent Chat Server pool.</span></span>

  - <span data-ttu-id="21f4d-117">在使用者通常是離線狀態的期間 (例如週末)：</span><span class="sxs-lookup"><span data-stu-id="21f4d-117">During a time when users are generally offline (for example, a weekend):</span></span>
    
      - <span data-ttu-id="21f4d-118">關閉 Lync Server 2010，群組聊天。</span><span class="sxs-lookup"><span data-stu-id="21f4d-118">Turn off Lync Server 2010, Group Chat.</span></span>
    
      - <span data-ttu-id="21f4d-119">將資料從 Lync Server 2010，Group Chat 集區遷移至 Lync Server 2013 Persistent Chat Server 集區。</span><span class="sxs-lookup"><span data-stu-id="21f4d-119">Migrate data from the Lync Server 2010, Group Chat pool to the Lync Server 2013 Persistent Chat Server pool.</span></span>
    
      - <span data-ttu-id="21f4d-120">從 Active Directory 網域服務中刪除眾所周知的使用者。</span><span class="sxs-lookup"><span data-stu-id="21f4d-120">Delete the well-known user from the Active Directory Domain Services.</span></span>
    
      - <span data-ttu-id="21f4d-121">利用與先前刪除之已知使用者相同的 SIP URI 來建立新的「舊版端點」\*\*。</span><span class="sxs-lookup"><span data-stu-id="21f4d-121">Create a new *legacy endpoint* with the same SIP URI as the previously deleted well-known user.</span></span>
    
      - <span data-ttu-id="21f4d-122">啟動 Lync Server 2013，Persistent Chat server。</span><span class="sxs-lookup"><span data-stu-id="21f4d-122">Start the Lync Server 2013, Persistent Chat Servers.</span></span>

  - <span data-ttu-id="21f4d-123">使用者可以使用其 Lync 2010 群組聊天（用戶端）重新登入，並連接至其資料，而不需要變更任何設定。</span><span class="sxs-lookup"><span data-stu-id="21f4d-123">Users log back on by using their Lync 2010 Group Chat (client) and connect to their data without needing to change any configuration.</span></span>

  - <span data-ttu-id="21f4d-124">您可以在稍後解除委任 Lync Server 2010，群組聊天。</span><span class="sxs-lookup"><span data-stu-id="21f4d-124">At a later time, you can decommission the Lync Server 2010, Group Chat.</span></span> <span data-ttu-id="21f4d-125">接著，您可以部署 Lync Server 2013、Persistent Chat Server，並安裝新的 Lync Server 2013 Persistent Chat Server 集區。</span><span class="sxs-lookup"><span data-stu-id="21f4d-125">Subsequently, you can deploy Lync Server 2013, Persistent Chat Server, and install new Lync Server 2013 Persistent Chat Server pools.</span></span>

<span data-ttu-id="21f4d-126">如需從 Lync Server 2010 （Group Chat to Lync Server 2013，Persistent Chat Server）進行遷移的詳細資訊，請參閱[從 Lync server 2010 遷移，Group chat 或 Office 通訊伺服器 2007 R2 Group chat To Lync server 2013，Persistent Chat server](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)。</span><span class="sxs-lookup"><span data-stu-id="21f4d-126">For details about migrating from Lync Server 2010, Group Chat to Lync Server 2013, Persistent Chat Server, see [Migration from Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md).</span></span>

<span data-ttu-id="21f4d-127">若要執行回溯相容性（若要建立會指向 Persistent Chat Server 集區的持久聊天伺服器端點，可供舊版群組聊天集區用戶端使用）：</span><span class="sxs-lookup"><span data-stu-id="21f4d-127">To run backward compatibility (to create a Persistent Chat Server endpoint that points to a Persistent Chat Server pool, which can be used by legacy Group Chat pool clients):</span></span>

    New-CsPersistentChatEndpoint -SipAddress <CO name, ex. persistentchat@contoso.com> -PersistentChatPoolFqdn <pool FQDN, like pcpool.contoso.com>

<span data-ttu-id="21f4d-128">接下來，設定 Persistent Chat 用戶端使用該 SIP 位址作為其連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="21f4d-128">Next, configure Persistent Chat clients to use that SIP address as their contact object.</span></span> <span data-ttu-id="21f4d-129">使用特定 Persistent Chat Server 集區的**New-CsPersistentChatEndpoint** Cmdlet 來建立 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="21f4d-129">The SIP address is created with the **New-CsPersistentChatEndpoint** cmdlet for a specific Persistent Chat Server pool.</span></span>

<span data-ttu-id="21f4d-130">若要使用 Windows PowerShell 命令列介面新增 Persistent Chat Server 端點，請考慮下列範例。</span><span class="sxs-lookup"><span data-stu-id="21f4d-130">To add the Persistent Chat Server endpoint by using Windows PowerShell command-line interface, consider the following example.</span></span> <span data-ttu-id="21f4d-131">在此案例中，您是在 "contoso.com"  拓撲上設定連絡人物件，並將它命名為 "persistentchat"，其中集區的完整網域名稱 (FQDN) 為 "pcpool.contoso.com"：</span><span class="sxs-lookup"><span data-stu-id="21f4d-131">In this case, you are configuring the contact object to be named "persistentchat" on the "contoso.com" topology, where the pool fully qualified domain name (FQDN) is "pcpool.contoso.com":</span></span>

    New-CsPersistentChatEndpoint -SipAddress sip:persistentchat@contoso.com -PersistentChatPoolFqdn pcpool.contoso.com

<div>

## <a name="see-also"></a><span data-ttu-id="21f4d-132">另請參閱</span><span class="sxs-lookup"><span data-stu-id="21f4d-132">See Also</span></span>


[<span data-ttu-id="21f4d-133">從 Lync Server 2010 群組聊天或 Office Communications Server 2007 R2 群組聊天移轉至 Lync Server 2013 常設聊天室伺服器</span><span class="sxs-lookup"><span data-stu-id="21f4d-133">Migration from Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server</span></span>](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

