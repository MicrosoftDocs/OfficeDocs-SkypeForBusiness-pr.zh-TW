---
title: 對 Persistent Chat Server 執行回溯相容性
description: 對 Persistent Chat Server 執行回溯相容性。
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
ms.openlocfilehash: b0486992d44e6385559d3e9df9f9ffc2125120da
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570149"
---
# <a name="run-backward-compatibility-for-persistent-chat-server"></a><span data-ttu-id="7d565-103">對 Persistent Chat Server 執行回溯相容性</span><span class="sxs-lookup"><span data-stu-id="7d565-103">Run backward compatibility for Persistent Chat Server</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7d565-104">_**主題上次修改日期：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="7d565-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="7d565-105">Lync Server 2013，Persistent Chat Server 端點提供一種方式，來建立指向 Persistent Chat Server 集區的簡單 URL。</span><span class="sxs-lookup"><span data-stu-id="7d565-105">The Lync Server 2013, Persistent Chat Server endpoint provides a way to create a simple URL that points to a Persistent Chat Server pool.</span></span> <span data-ttu-id="7d565-106">這適用于舊版用戶端 (Microsoft Office 通訊伺服器 2007 R2 Group Chat Server 或 Lync Server 2010，群組聊天) 因為使用者可以在手動設定中輸入簡易 URL，以嘗試將舊版用戶端指向執行 Lync 2013 的電腦（持續聊天）。</span><span class="sxs-lookup"><span data-stu-id="7d565-106">This is useful for legacy clients (Microsoft Office Communications Server 2007 R2 Group Chat Server or Lync Server 2010, Group Chat) because users can enter a simple URL in the manual configuration when trying to point the legacy client to a computer running Lync 2013, Persistent Chat.</span></span> <span data-ttu-id="7d565-107">持續性聊天不會使用此端點，只對舊版用戶端是必要的。</span><span class="sxs-lookup"><span data-stu-id="7d565-107">This endpoint isn’t used by Persistent Chat, and is required for legacy clients only.</span></span> <span data-ttu-id="7d565-108">這對可以遷移會議室的過渡期很有用，但是尚未在整個組織中部署 Lync 2013 用戶端。</span><span class="sxs-lookup"><span data-stu-id="7d565-108">This is useful for the interim period where rooms may be migrated, but the Lync 2013 clients have not been deployed throughout the organization.</span></span> <span data-ttu-id="7d565-109">執行 Lync 2010 Group Chat (用戶端) 的使用者，仍然可以連線到 Persistent Chat Server 後端伺服器。</span><span class="sxs-lookup"><span data-stu-id="7d565-109">Users running Lync 2010 Group Chat (client) can then still connect to the Persistent Chat Server Back End Server.</span></span>

<span data-ttu-id="7d565-110">您不需要建立多個 Persistent 聊天伺服器端點;您只需要每個 Persistent Chat Server 集區的一個。</span><span class="sxs-lookup"><span data-stu-id="7d565-110">You don’t need to create multiple Persistent Chat Server endpoints; you just need one for each Persistent Chat Server pool.</span></span> <span data-ttu-id="7d565-111">系統管理員可以建立多個端點 (每個集區一個)，但可將舊版用戶端設定為一次只能連線至一個集區。</span><span class="sxs-lookup"><span data-stu-id="7d565-111">Administrators can create multiple endpoints (one per pool), but legacy clients can be configured to connect to only one pool at a time.</span></span> <span data-ttu-id="7d565-112">在一般或主流案例中，舊版部署只是一個集區。</span><span class="sxs-lookup"><span data-stu-id="7d565-112">In the usual or mainstream scenario, the legacy deployment is one pool only.</span></span> <span data-ttu-id="7d565-113">新的部署通常會將該集區遷移至新的 Lync Server 2013，而且可能會新增額外的其他 Persistent Chat Server 集區。</span><span class="sxs-lookup"><span data-stu-id="7d565-113">A new deployment generally migrates that pool to a new Lync Server 2013 and might add some new additional Persistent Chat Server pools.</span></span>

<span data-ttu-id="7d565-114">此主流案例通常會遵循下列模式：</span><span class="sxs-lookup"><span data-stu-id="7d565-114">This mainstream scenario generally follows this pattern:</span></span>

  - <span data-ttu-id="7d565-115">您可以管理具有一個 Lync Server 2010、群組聊天集區和 Lync 2010 群組聊天用戶端的使用者，方法是使用 (預設 sip： ocschat@ \<domainName\> .com 或類似一個) 的一些已知使用者連線到該集區。</span><span class="sxs-lookup"><span data-stu-id="7d565-115">You administer users with one Lync Server 2010, Group Chat pool, and your Lync 2010 Group Chat clients connect to that pool by using some well-known user (either default sip:ocschat@\<domainName\>.com, or a similar one).</span></span> <span data-ttu-id="7d565-116">使用者 SIP-enabled Active Directory 網域服務，且查閱服務會向其註冊以接收傳入的要求。</span><span class="sxs-lookup"><span data-stu-id="7d565-116">The users are SIP-enabled Active Directory Domain Services, and the Lookup service registers with them to receive incoming requests.</span></span>

  - <span data-ttu-id="7d565-117">接著，您會安裝 Lync Server 2013 Persistent Chat Server 和 Persistent Chat Server 集區。</span><span class="sxs-lookup"><span data-stu-id="7d565-117">Subsequently, you install a Lync Server 2013 Persistent Chat Server and Persistent Chat Server pool.</span></span>

  - <span data-ttu-id="7d565-118">在使用者通常是離線狀態的期間 (例如週末)：</span><span class="sxs-lookup"><span data-stu-id="7d565-118">During a time when users are generally offline (for example, a weekend):</span></span>
    
      - <span data-ttu-id="7d565-119">關閉 Lync Server 2010，群組聊天。</span><span class="sxs-lookup"><span data-stu-id="7d565-119">Turn off Lync Server 2010, Group Chat.</span></span>
    
      - <span data-ttu-id="7d565-120">將資料從 Lync Server 2010，Group Chat 集區遷移至 Lync Server 2013 Persistent Chat Server 集區。</span><span class="sxs-lookup"><span data-stu-id="7d565-120">Migrate data from the Lync Server 2010, Group Chat pool to the Lync Server 2013 Persistent Chat Server pool.</span></span>
    
      - <span data-ttu-id="7d565-121">從 Active Directory 網域服務中刪除眾所周知的使用者。</span><span class="sxs-lookup"><span data-stu-id="7d565-121">Delete the well-known user from the Active Directory Domain Services.</span></span>
    
      - <span data-ttu-id="7d565-122">利用與先前刪除之已知使用者相同的 SIP URI 來建立新的「舊版端點」\*\*。</span><span class="sxs-lookup"><span data-stu-id="7d565-122">Create a new *legacy endpoint* with the same SIP URI as the previously deleted well-known user.</span></span>
    
      - <span data-ttu-id="7d565-123">啟動 Lync Server 2013，Persistent Chat server。</span><span class="sxs-lookup"><span data-stu-id="7d565-123">Start the Lync Server 2013, Persistent Chat Servers.</span></span>

  - <span data-ttu-id="7d565-124">使用者可以使用其 Lync 2010 群組聊天 (用戶端) 重新登入，並連接至其資料，而不需要變更任何設定。</span><span class="sxs-lookup"><span data-stu-id="7d565-124">Users log back on by using their Lync 2010 Group Chat (client) and connect to their data without needing to change any configuration.</span></span>

  - <span data-ttu-id="7d565-125">您可以在稍後解除委任 Lync Server 2010，群組聊天。</span><span class="sxs-lookup"><span data-stu-id="7d565-125">At a later time, you can decommission the Lync Server 2010, Group Chat.</span></span> <span data-ttu-id="7d565-126">接著，您可以部署 Lync Server 2013、Persistent Chat Server，並安裝新的 Lync Server 2013 Persistent Chat Server 集區。</span><span class="sxs-lookup"><span data-stu-id="7d565-126">Subsequently, you can deploy Lync Server 2013, Persistent Chat Server, and install new Lync Server 2013 Persistent Chat Server pools.</span></span>

<span data-ttu-id="7d565-127">如需從 Lync Server 2010 （Group Chat to Lync Server 2013，Persistent Chat Server）進行遷移的詳細資訊，請參閱 [從 Lync server 2010 遷移，Group chat 或 Office 通訊伺服器 2007 R2 Group chat To Lync server 2013，Persistent Chat server](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)。</span><span class="sxs-lookup"><span data-stu-id="7d565-127">For details about migrating from Lync Server 2010, Group Chat to Lync Server 2013, Persistent Chat Server, see [Migration from Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md).</span></span>

<span data-ttu-id="7d565-128">若要執行回溯相容性 (以建立一個指向 Persistent Chat Server 集區的持久聊天伺服器端點，可供舊版群組聊天集區用戶端使用) ：</span><span class="sxs-lookup"><span data-stu-id="7d565-128">To run backward compatibility (to create a Persistent Chat Server endpoint that points to a Persistent Chat Server pool, which can be used by legacy Group Chat pool clients):</span></span>

    New-CsPersistentChatEndpoint -SipAddress <CO name, ex. persistentchat@contoso.com> -PersistentChatPoolFqdn <pool FQDN, like pcpool.contoso.com>

<span data-ttu-id="7d565-129">接下來，設定 Persistent Chat 用戶端使用該 SIP 位址作為其連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="7d565-129">Next, configure Persistent Chat clients to use that SIP address as their contact object.</span></span> <span data-ttu-id="7d565-130">使用特定 Persistent Chat Server 集區的 **New-CsPersistentChatEndpoint** Cmdlet 來建立 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="7d565-130">The SIP address is created with the **New-CsPersistentChatEndpoint** cmdlet for a specific Persistent Chat Server pool.</span></span>

<span data-ttu-id="7d565-131">若要使用 Windows PowerShell 命令列介面新增 Persistent Chat Server 端點，請考慮下列範例。</span><span class="sxs-lookup"><span data-stu-id="7d565-131">To add the Persistent Chat Server endpoint by using Windows PowerShell command-line interface, consider the following example.</span></span> <span data-ttu-id="7d565-132">在此案例中，您是在 "contoso.com"  拓撲上設定連絡人物件，並將它命名為 "persistentchat"，其中集區的完整網域名稱 (FQDN) 為 "pcpool.contoso.com"：</span><span class="sxs-lookup"><span data-stu-id="7d565-132">In this case, you are configuring the contact object to be named "persistentchat" on the "contoso.com" topology, where the pool fully qualified domain name (FQDN) is "pcpool.contoso.com":</span></span>

    New-CsPersistentChatEndpoint -SipAddress sip:persistentchat@contoso.com -PersistentChatPoolFqdn pcpool.contoso.com

<div>

## <a name="see-also"></a><span data-ttu-id="7d565-133">另請參閱</span><span class="sxs-lookup"><span data-stu-id="7d565-133">See Also</span></span>


[<span data-ttu-id="7d565-134">從 Lync Server 2010 群組聊天或 Office Communications Server 2007 R2 群組聊天移轉至 Lync Server 2013 常設聊天室伺服器</span><span class="sxs-lookup"><span data-stu-id="7d565-134">Migration from Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server</span></span>](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

