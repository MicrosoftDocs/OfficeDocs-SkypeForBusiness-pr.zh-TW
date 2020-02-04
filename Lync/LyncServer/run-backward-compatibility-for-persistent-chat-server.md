---
title: 針對常設聊天室伺服器執行回溯相容性
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Run backward compatibility for Persistent Chat Server
ms:assetid: 53f1a706-3104-4a94-8b4e-8badd9a066d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204901(v=OCS.15)
ms:contentKeyID: 48184175
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 22d7054e9dfb3eba8e6365710accfd3a9693bc39
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726963"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="run-backward-compatibility-for-persistent-chat-server"></a><span data-ttu-id="08136-102">針對常設聊天室伺服器執行回溯相容性</span><span class="sxs-lookup"><span data-stu-id="08136-102">Run backward compatibility for Persistent Chat Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="08136-103">_**主題上次修改日期：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="08136-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="08136-104">Lync Server 2013，持續聊天伺服器端點提供一種方式來建立指向持續聊天伺服器池的簡單 URL。</span><span class="sxs-lookup"><span data-stu-id="08136-104">The Lync Server 2013, Persistent Chat Server endpoint provides a way to create a simple URL that points to a Persistent Chat Server pool.</span></span> <span data-ttu-id="08136-105">這適用于舊版用戶端（Microsoft Office 通訊伺服器 2007 R2 群組聊天伺服器或 Lync Server 2010、群組聊天），因為當您嘗試將舊版用戶端指向執行 Lync 2013 的電腦時，使用者可以在手動設定中輸入簡單的 URL。持續聊天。</span><span class="sxs-lookup"><span data-stu-id="08136-105">This is useful for legacy clients (Microsoft Office Communications Server 2007 R2 Group Chat Server or Lync Server 2010, Group Chat) because users can enter a simple URL in the manual configuration when trying to point the legacy client to a computer running Lync 2013, Persistent Chat.</span></span> <span data-ttu-id="08136-106">此端點不會用於持續聊天，且僅適用于舊版用戶端。</span><span class="sxs-lookup"><span data-stu-id="08136-106">This endpoint isn’t used by Persistent Chat, and is required for legacy clients only.</span></span> <span data-ttu-id="08136-107">這適用于可遷移會議室的間歇期間，但尚未在整個組織中部署 Lync 2013 用戶端。</span><span class="sxs-lookup"><span data-stu-id="08136-107">This is useful for the interim period where rooms may be migrated, but the Lync 2013 clients have not been deployed throughout the organization.</span></span> <span data-ttu-id="08136-108">執行 Lync 2010 群組聊天（用戶端）的使用者仍然可以連線到持續聊天伺服器後端伺服器。</span><span class="sxs-lookup"><span data-stu-id="08136-108">Users running Lync 2010 Group Chat (client) can then still connect to the Persistent Chat Server Back End Server.</span></span>

<span data-ttu-id="08136-109">您不需要建立多個持續聊天伺服器端點;您只需要每個持續聊天伺服器池的一個。</span><span class="sxs-lookup"><span data-stu-id="08136-109">You don’t need to create multiple Persistent Chat Server endpoints; you just need one for each Persistent Chat Server pool.</span></span> <span data-ttu-id="08136-110">系統管理員可以建立多個端點（每個池一個），但舊用戶端可以設定為一次只連線到一個池。</span><span class="sxs-lookup"><span data-stu-id="08136-110">Administrators can create multiple endpoints (one per pool), but legacy clients can be configured to connect to only one pool at a time.</span></span> <span data-ttu-id="08136-111">在一般或主流案例中，舊版部署只是一個池。</span><span class="sxs-lookup"><span data-stu-id="08136-111">In the usual or mainstream scenario, the legacy deployment is one pool only.</span></span> <span data-ttu-id="08136-112">新的部署通常會將該池遷移至新的 Lync Server 2013，並且可能會新增其他額外的持久聊天伺服器池。</span><span class="sxs-lookup"><span data-stu-id="08136-112">A new deployment generally migrates that pool to a new Lync Server 2013 and might add some new additional Persistent Chat Server pools.</span></span>

<span data-ttu-id="08136-113">這個主要案例通常遵循下列模式：</span><span class="sxs-lookup"><span data-stu-id="08136-113">This mainstream scenario generally follows this pattern:</span></span>

  - <span data-ttu-id="08136-114">您可以使用一個 Lync Server 2010、群組聊天池及您的 Lync 2010 群組聊天用戶端連線至該池子，方法是使用一些知名使用者（預設 sip： ocschat@\<domainName\>或類似的使用者）連線到該池。</span><span class="sxs-lookup"><span data-stu-id="08136-114">You administer users with one Lync Server 2010, Group Chat pool, and your Lync 2010 Group Chat clients connect to that pool by using some well-known user (either default sip:ocschat@\<domainName\>.com, or a similar one).</span></span> <span data-ttu-id="08136-115">使用者是啟用 SIP 的 Active Directory 網域服務，且查閱服務會使用它們登錄來接收傳入的要求。</span><span class="sxs-lookup"><span data-stu-id="08136-115">The users are SIP-enabled Active Directory Domain Services, and the Lookup service registers with them to receive incoming requests.</span></span>

  - <span data-ttu-id="08136-116">接著，您會安裝 Lync Server 2013 永久聊天伺服器與持續聊天伺服器池。</span><span class="sxs-lookup"><span data-stu-id="08136-116">Subsequently, you install a Lync Server 2013 Persistent Chat Server and Persistent Chat Server pool.</span></span>

  - <span data-ttu-id="08136-117">在使用者一般離線時（例如，週末）：</span><span class="sxs-lookup"><span data-stu-id="08136-117">During a time when users are generally offline (for example, a weekend):</span></span>
    
      - <span data-ttu-id="08136-118">關閉 Lync Server 2010、群組聊天。</span><span class="sxs-lookup"><span data-stu-id="08136-118">Turn off Lync Server 2010, Group Chat.</span></span>
    
      - <span data-ttu-id="08136-119">將資料從 Lync Server 2010、群組聊天池遷移至 Lync Server 2013 持續聊天伺服器池。</span><span class="sxs-lookup"><span data-stu-id="08136-119">Migrate data from the Lync Server 2010, Group Chat pool to the Lync Server 2013 Persistent Chat Server pool.</span></span>
    
      - <span data-ttu-id="08136-120">從 Active Directory 網域服務刪除已知的使用者。</span><span class="sxs-lookup"><span data-stu-id="08136-120">Delete the well-known user from the Active Directory Domain Services.</span></span>
    
      - <span data-ttu-id="08136-121">建立新的*舊版端點*，其 SIP URI 與先前刪除的知名使用者相同。</span><span class="sxs-lookup"><span data-stu-id="08136-121">Create a new *legacy endpoint* with the same SIP URI as the previously deleted well-known user.</span></span>
    
      - <span data-ttu-id="08136-122">啟動 Lync Server 2013、持久聊天伺服器。</span><span class="sxs-lookup"><span data-stu-id="08136-122">Start the Lync Server 2013, Persistent Chat Servers.</span></span>

  - <span data-ttu-id="08136-123">使用者使用其 Lync 2010 群組聊天（用戶端）重新登入，並聯機至其資料，而不需要變更任何設定。</span><span class="sxs-lookup"><span data-stu-id="08136-123">Users log back on by using their Lync 2010 Group Chat (client) and connect to their data without needing to change any configuration.</span></span>

  - <span data-ttu-id="08136-124">您可以在日後解除 Lync Server 2010、群組聊天。</span><span class="sxs-lookup"><span data-stu-id="08136-124">At a later time, you can decommission the Lync Server 2010, Group Chat.</span></span> <span data-ttu-id="08136-125">接著，您可以部署 Lync Server 2013、持續聊天伺服器，以及安裝新的 Lync Server 2013 永久聊天伺服器池。</span><span class="sxs-lookup"><span data-stu-id="08136-125">Subsequently, you can deploy Lync Server 2013, Persistent Chat Server, and install new Lync Server 2013 Persistent Chat Server pools.</span></span>

<span data-ttu-id="08136-126">如需從 Lync Server 2010 遷移的詳細資料，群組聊天至 Lync Server 2013，持續聊天伺服器，請參閱[從 Lync server 2010 遷移、群組聊天或 Office 通訊伺服器 2007 R2 群組聊天至 Lync server 2013，持續聊天伺服器](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)。</span><span class="sxs-lookup"><span data-stu-id="08136-126">For details about migrating from Lync Server 2010, Group Chat to Lync Server 2013, Persistent Chat Server, see [Migration from Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md).</span></span>

<span data-ttu-id="08136-127">若要執行向後相容性（以建立指向持久聊天伺服器池的永久性聊天伺服器端點，可供舊版群組聊天池用戶端使用）：</span><span class="sxs-lookup"><span data-stu-id="08136-127">To run backward compatibility (to create a Persistent Chat Server endpoint that points to a Persistent Chat Server pool, which can be used by legacy Group Chat pool clients):</span></span>

    New-CsPersistentChatEndpoint -SipAddress <CO name, ex. persistentchat@contoso.com> -PersistentChatPoolFqdn <pool FQDN, like pcpool.contoso.com>

<span data-ttu-id="08136-128">接著，設定持久聊天用戶端，將該 SIP 位址當作其連絡人物件使用。</span><span class="sxs-lookup"><span data-stu-id="08136-128">Next, configure Persistent Chat clients to use that SIP address as their contact object.</span></span> <span data-ttu-id="08136-129">SIP 位址是針對特定持久性聊天伺服器池中的**新-CsPersistentChatEndpoint** Cmdlet 建立的。</span><span class="sxs-lookup"><span data-stu-id="08136-129">The SIP address is created with the **New-CsPersistentChatEndpoint** cmdlet for a specific Persistent Chat Server pool.</span></span>

<span data-ttu-id="08136-130">若要使用 Windows PowerShell 命令列介面新增持續聊天伺服器端點，請考慮下列範例。</span><span class="sxs-lookup"><span data-stu-id="08136-130">To add the Persistent Chat Server endpoint by using Windows PowerShell command-line interface, consider the following example.</span></span> <span data-ttu-id="08136-131">在這種情況下，您是將連絡人物件設定為「contoso.com」拓撲中的「persistentchat」，其中池的完整功能變數名稱（FQDN）是「pcpool.contoso.com」：</span><span class="sxs-lookup"><span data-stu-id="08136-131">In this case, you are configuring the contact object to be named "persistentchat" on the "contoso.com" topology, where the pool fully qualified domain name (FQDN) is "pcpool.contoso.com":</span></span>

    New-CsPersistentChatEndpoint -SipAddress sip:persistentchat@contoso.com -PersistentChatPoolFqdn pcpool.contoso.com

<div>

## <a name="see-also"></a><span data-ttu-id="08136-132">請參閱</span><span class="sxs-lookup"><span data-stu-id="08136-132">See Also</span></span>


[<span data-ttu-id="08136-133">從 Lync Server 2010 群組聊天或 Office Communications Server 2007 R2 群組聊天移轉至 Lync Server 2013 常設聊天室伺服器</span><span class="sxs-lookup"><span data-stu-id="08136-133">Migration from Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server</span></span>](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

