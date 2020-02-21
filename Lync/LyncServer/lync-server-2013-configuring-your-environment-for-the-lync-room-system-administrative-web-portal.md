---
title: Lync Server 2013： 設定您環境的 Lync 會議室系統管理入口網站
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
ms.openlocfilehash: 5198416e3c06dfd83cf7d1cf5bf3c6002ebe72ca
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195476"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-your-lync-server-2013-environment-for-the-lync-room-system-administrative-web-portal"></a><span data-ttu-id="2418f-102">設定 Lync Server 2013 環境的 Lync 會議室系統管理入口網站</span><span class="sxs-lookup"><span data-stu-id="2418f-102">Configuring your Lync Server 2013 environment for the Lync Room System Administrative Web Portal</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2418f-103">_**上次修改主題：** 2014年-05-22_</span><span class="sxs-lookup"><span data-stu-id="2418f-103">_**Topic Last Modified:** 2014-05-22_</span></span>

<span data-ttu-id="2418f-104">若要使用 Lync 會議室系統 (LRS) 系統管理員入口網站，您將需要安裝或設定下列必要條件。</span><span class="sxs-lookup"><span data-stu-id="2418f-104">To use the Lync Room System (LRS) Administrative Web Portal, you will need to install or configure the following prerequisites.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2418f-105">如果將伺服器設定 Kerberos 及 NTLM 驗證，而且 LRS 執行不會加入網域的電腦上，Kerberos 驗證會失敗，但使用者看不到 LRS 管理入口網站中的狀態。</span><span class="sxs-lookup"><span data-stu-id="2418f-105">If the server is configured with both Kerberos and NTLM authentication, and LRS is running on a computer that is not joined to the domain, Kerberos authentication will fail and the user will not see the status of LRS in the administrative portal.</span></span> <span data-ttu-id="2418f-106">若要解決此問題，請使用 NTLM 驗證] 或 [NTLM 和 TLS DSK 驗證 （不含 Kerberos)]，設定伺服器或 LRS 電腦加入網域。</span><span class="sxs-lookup"><span data-stu-id="2418f-106">To resolve this issue, configure the server with NTLM authentication or both NTLM and TLS-DSK authentication (without Kerberos), or join the LRS computer to the domain.</span></span>



</div>

1.  <span data-ttu-id="2418f-107">安裝 Lync Server 2013 累計更新： 7 月 2013 中的 Lync Server 拓撲。</span><span class="sxs-lookup"><span data-stu-id="2418f-107">Install Lync Server 2013 Cumulative Updates: July 2013 in the Lync Server topology.</span></span>
    
    <span data-ttu-id="2418f-108">若要取得更新，或請參閱與其其中包含哪些功能，請參閱[Lync Server 2013 的更新](https://go.microsoft.com/fwlink/p/?linkid=323959)。</span><span class="sxs-lookup"><span data-stu-id="2418f-108">To get the update or see what’s included with it, see [Updates for Lync Server 2013](https://go.microsoft.com/fwlink/p/?linkid=323959).</span></span>

2.  <span data-ttu-id="2418f-109">建立已啟用 SIP 的 Active Directory 的使用者。</span><span class="sxs-lookup"><span data-stu-id="2418f-109">Create a SIP-enabled Active Directory user.</span></span>
    
    <span data-ttu-id="2418f-110">LRS 管理入口網站會使用這些認證查詢資訊從 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="2418f-110">The LRS Administrative Web Portal uses these credentials to query information from Lync Server.</span></span> <span data-ttu-id="2418f-111">建議的 username 是 LRSApp。</span><span class="sxs-lookup"><span data-stu-id="2418f-111">The recommended username is LRSApp.</span></span>

3.  <span data-ttu-id="2418f-112">建立 Active Directory 安全性群組名稱 LRSSupportAdminGroup。</span><span class="sxs-lookup"><span data-stu-id="2418f-112">Create an Active Directory security group with name LRSSupportAdminGroup.</span></span>
    
    <span data-ttu-id="2418f-113">建立群組，其為全域群組領域] 和 [作為安全性的群組類型。</span><span class="sxs-lookup"><span data-stu-id="2418f-113">Create the group with Group Scope as Global and Group Type as Security.</span></span> <span data-ttu-id="2418f-114">授權新增至這個群組的 SIP 啟用使用者看到的會議室清單和執行某些命令，如 [收集記錄檔。</span><span class="sxs-lookup"><span data-stu-id="2418f-114">SIP enabled users who are added to this group will be authorized to see the list of rooms and execute certain commands, such as collecting logs.</span></span>

4.  <span data-ttu-id="2418f-115">建立 Active Directory 安全性群組名稱 LRSFullAccessAdminGroup。</span><span class="sxs-lookup"><span data-stu-id="2418f-115">Create an Active Directory security group with name LRSFullAccessAdminGroup.</span></span>
    
    <span data-ttu-id="2418f-116">建立做為全域系統管理員和群組類型的群組範圍群組為 Security.SIP 啟用的使用者新增至這個群組會獲授權使用所有的系統管理員入口網站的功能。</span><span class="sxs-lookup"><span data-stu-id="2418f-116">Create the group with Group Scope as Global and Group Type as Security.SIP enabled users who are added to this group are authorized to use all admin portal functionality.</span></span>
    
     
    
    <span data-ttu-id="2418f-117">![系統管理員群組的清單與安全性群組角色](images/Dn436325.5d432819-a2e2-452c-bc2a-5d4ee79d8c33(OCS.15).png "系統管理員群組的清單與安全性群組角色")</span><span class="sxs-lookup"><span data-stu-id="2418f-117">![List of Admin Groups with security group role](images/Dn436325.5d432819-a2e2-452c-bc2a-5d4ee79d8c33(OCS.15).png "List of Admin Groups with security group role")</span></span>  
    
     

5.  <span data-ttu-id="2418f-118">新增 LRSFullAccessAdminGroup 作為 LRSSupportAdminGroup 的成員。</span><span class="sxs-lookup"><span data-stu-id="2418f-118">Add LRSFullAccessAdminGroup as a member of LRSSupportAdminGroup.</span></span>
    
    <span data-ttu-id="2418f-119">![LRSSupportAdminGroup Properties 成員] 頁面](images/Dn436325.91a4a28a-cacf-4ef6-aac1-915ec41c9648(OCS.15).png "LRSSupportAdminGroup Properties 成員] 頁面")</span><span class="sxs-lookup"><span data-stu-id="2418f-119">![LRSSupportAdminGroup Properties Members page](images/Dn436325.91a4a28a-cacf-4ef6-aac1-915ec41c9648(OCS.15).png "LRSSupportAdminGroup Properties Members page")</span></span>  
    
     

6.  <span data-ttu-id="2418f-120">以名稱 LRSSupport 建立 SIP 啟用 Active Directory 使用者。</span><span class="sxs-lookup"><span data-stu-id="2418f-120">Create a SIP enabled Active Directory user with name LRSSupport.</span></span> <span data-ttu-id="2418f-121">此使用者新增至 LRSSupportAdminGroup。</span><span class="sxs-lookup"><span data-stu-id="2418f-121">Add this user to LRSSupportAdminGroup.</span></span>
    
    <span data-ttu-id="2418f-122">![LRSSupportAdminGroup Properties 成員] 頁面](images/Dn436325.7638055d-22ac-4909-914d-1966f5623909(OCS.15).png "LRSSupportAdminGroup Properties 成員] 頁面")</span><span class="sxs-lookup"><span data-stu-id="2418f-122">![LRSSupportAdminGroup Properties Members page](images/Dn436325.7638055d-22ac-4909-914d-1966f5623909(OCS.15).png "LRSSupportAdminGroup Properties Members page")</span></span>  
    
     

7.  <span data-ttu-id="2418f-123">Visual Studio 2010 SP1 和 Visual Web Developer 2010 SP1，用於在 Microsoft 下載中心取得安裝 ASP.NET MVC 4 [https://go.microsoft.com/fwlink/p/?LinkId=323967](https://go.microsoft.com/fwlink/p/?linkid=323967)。</span><span class="sxs-lookup"><span data-stu-id="2418f-123">Install ASP.NET MVC 4 for Visual Studio 2010 SP1 and Visual Web Developer 2010 SP1, available in the Microsoft Download Center at [https://go.microsoft.com/fwlink/p/?LinkId=323967](https://go.microsoft.com/fwlink/p/?linkid=323967).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

