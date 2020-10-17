---
title: Lync Server 2013：設定 Lync 會議室系統管理 Web 入口網站的環境
description: Lync Server 2013：設定 Lync 會議室系統管理 Web 入口網站的環境。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring your environment for the Lync Room System Administrative Web Portal
ms:assetid: 1bf3cc55-cfa8-46ee-a8bc-6dab3bff76b2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn436325(v=OCS.15)
ms:contentKeyID: 56737623
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c942e1db799a7336a3eafb5571e82584694ddbf3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542199"
---
# <a name="configuring-your-lync-server-2013-environment-for-the-lync-room-system-administrative-web-portal"></a><span data-ttu-id="111b3-103">設定 lync 會議室系統管理 Web 入口網站的 Lync Server 2013 環境</span><span class="sxs-lookup"><span data-stu-id="111b3-103">Configuring your Lync Server 2013 environment for the Lync Room System Administrative Web Portal</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="111b3-104">_**主題上次修改日期：** 2014-05-22_</span><span class="sxs-lookup"><span data-stu-id="111b3-104">_**Topic Last Modified:** 2014-05-22_</span></span>

<span data-ttu-id="111b3-105">若要使用 Lync 會議室系統 (LRS) 管理網頁入口網站，您必須安裝或設定下列必要條件。</span><span class="sxs-lookup"><span data-stu-id="111b3-105">To use the Lync Room System (LRS) Administrative Web Portal, you will need to install or configure the following prerequisites.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="111b3-106">如果伺服器設定了 Kerberos 和 NTLM 驗證，且 LRS 是在未加入網域的電腦上執行，則 Kerberos 驗證會失敗，且使用者將不會在系統管理入口網站看到 LRS 的狀態。</span><span class="sxs-lookup"><span data-stu-id="111b3-106">If the server is configured with both Kerberos and NTLM authentication, and LRS is running on a computer that is not joined to the domain, Kerberos authentication will fail and the user will not see the status of LRS in the administrative portal.</span></span> <span data-ttu-id="111b3-107">若要解決此問題，請使用沒有 Kerberos) 的 ntlm 和 TLS DSK 驗證 (來設定伺服器，或將 LRS 電腦加入網域。</span><span class="sxs-lookup"><span data-stu-id="111b3-107">To resolve this issue, configure the server with NTLM authentication or both NTLM and TLS-DSK authentication (without Kerberos), or join the LRS computer to the domain.</span></span>



</div>

1.  <span data-ttu-id="111b3-108">安裝 Lync Server 2013 累計更新： Lync Server 拓撲中的7月2013。</span><span class="sxs-lookup"><span data-stu-id="111b3-108">Install Lync Server 2013 Cumulative Updates: July 2013 in the Lync Server topology.</span></span>
    
    <span data-ttu-id="111b3-109">若要取得更新或查看其隨附的內容，請參閱 [Lync Server 2013 的更新](https://go.microsoft.com/fwlink/p/?linkid=323959)。</span><span class="sxs-lookup"><span data-stu-id="111b3-109">To get the update or see what’s included with it, see [Updates for Lync Server 2013](https://go.microsoft.com/fwlink/p/?linkid=323959).</span></span>

2.  <span data-ttu-id="111b3-110">建立 SIP-enabled Active Directory 使用者。</span><span class="sxs-lookup"><span data-stu-id="111b3-110">Create a SIP-enabled Active Directory user.</span></span>
    
    <span data-ttu-id="111b3-111">LRS 系統管理 Web 入口網站會使用這些認證來查詢 Lync Server 的資訊。</span><span class="sxs-lookup"><span data-stu-id="111b3-111">The LRS Administrative Web Portal uses these credentials to query information from Lync Server.</span></span> <span data-ttu-id="111b3-112">建議的使用者名稱是 LRSApp。</span><span class="sxs-lookup"><span data-stu-id="111b3-112">The recommended username is LRSApp.</span></span>

3.  <span data-ttu-id="111b3-113">使用 name LRSSupportAdminGroup 建立 Active Directory 安全性群組。</span><span class="sxs-lookup"><span data-stu-id="111b3-113">Create an Active Directory security group with name LRSSupportAdminGroup.</span></span>
    
    <span data-ttu-id="111b3-114">以「全域」和「群組」類型為安全性的群組範圍建立群組。</span><span class="sxs-lookup"><span data-stu-id="111b3-114">Create the group with Group Scope as Global and Group Type as Security.</span></span> <span data-ttu-id="111b3-115">新增至此群組的 SIP 啟用使用者可查看聊天室清單，並執行某些命令，例如收集記錄檔。</span><span class="sxs-lookup"><span data-stu-id="111b3-115">SIP enabled users who are added to this group will be authorized to see the list of rooms and execute certain commands, such as collecting logs.</span></span>

4.  <span data-ttu-id="111b3-116">使用名稱 LRSFullAccessAdminGroup 建立 Active Directory 安全性群組。</span><span class="sxs-lookup"><span data-stu-id="111b3-116">Create an Active Directory security group with name LRSFullAccessAdminGroup.</span></span>
    
    <span data-ttu-id="111b3-117">以「全域」和「群組」類型為安全性的群組範圍建立群組。加入此群組的 SIP 啟用使用者已獲得授權，可使用所有系統管理員入口網站功能。</span><span class="sxs-lookup"><span data-stu-id="111b3-117">Create the group with Group Scope as Global and Group Type as Security.SIP enabled users who are added to this group are authorized to use all admin portal functionality.</span></span>
    
     
    
    <span data-ttu-id="111b3-118">![具有安全性群組角色的系統管理員群組清單](images/Dn436325.5d432819-a2e2-452c-bc2a-5d4ee79d8c33(OCS.15).png "具有安全性群組角色的系統管理員群組清單")</span><span class="sxs-lookup"><span data-stu-id="111b3-118">![List of Admin Groups with security group role](images/Dn436325.5d432819-a2e2-452c-bc2a-5d4ee79d8c33(OCS.15).png "List of Admin Groups with security group role")</span></span>  
    
     

5.  <span data-ttu-id="111b3-119">將 LRSFullAccessAdminGroup 新增為 LRSSupportAdminGroup 的成員。</span><span class="sxs-lookup"><span data-stu-id="111b3-119">Add LRSFullAccessAdminGroup as a member of LRSSupportAdminGroup.</span></span>
    
    <span data-ttu-id="111b3-120">![LRSSupportAdminGroup 屬性成員] 頁面](images/Dn436325.91a4a28a-cacf-4ef6-aac1-915ec41c9648(OCS.15).png "LRSSupportAdminGroup 屬性成員] 頁面")</span><span class="sxs-lookup"><span data-stu-id="111b3-120">![LRSSupportAdminGroup Properties Members page](images/Dn436325.91a4a28a-cacf-4ef6-aac1-915ec41c9648(OCS.15).png "LRSSupportAdminGroup Properties Members page")</span></span>  
    
     

6.  <span data-ttu-id="111b3-121">使用名稱 LRSSupport 建立啟用 SIP 的 Active Directory 使用者。</span><span class="sxs-lookup"><span data-stu-id="111b3-121">Create a SIP enabled Active Directory user with name LRSSupport.</span></span> <span data-ttu-id="111b3-122">將此使用者新增至 LRSSupportAdminGroup。</span><span class="sxs-lookup"><span data-stu-id="111b3-122">Add this user to LRSSupportAdminGroup.</span></span>
    
    <span data-ttu-id="111b3-123">![LRSSupportAdminGroup 屬性成員] 頁面](images/Dn436325.7638055d-22ac-4909-914d-1966f5623909(OCS.15).png "LRSSupportAdminGroup 屬性成員] 頁面")</span><span class="sxs-lookup"><span data-stu-id="111b3-123">![LRSSupportAdminGroup Properties Members page](images/Dn436325.7638055d-22ac-4909-914d-1966f5623909(OCS.15).png "LRSSupportAdminGroup Properties Members page")</span></span>  
    
     

7.  <span data-ttu-id="111b3-124">在的 Microsoft 下載中心中，安裝 ASP.NET 的 MVC 4，以供 Visual Studio 2010 SP1 和 Visual Web Developer 2010 SP1 使用 [https://go.microsoft.com/fwlink/p/?LinkId=323967](https://go.microsoft.com/fwlink/p/?linkid=323967) 。</span><span class="sxs-lookup"><span data-stu-id="111b3-124">Install ASP.NET MVC 4 for Visual Studio 2010 SP1 and Visual Web Developer 2010 SP1, available in the Microsoft Download Center at [https://go.microsoft.com/fwlink/p/?LinkId=323967](https://go.microsoft.com/fwlink/p/?linkid=323967).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

