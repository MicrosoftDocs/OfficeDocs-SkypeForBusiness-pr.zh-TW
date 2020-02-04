---
title: Lync Server 2013：為 Lync Room System Administrative Web Portal 設定您的環境
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
ms.openlocfilehash: 4f0f415cfeca5b798a1e29ac6ebe09105fbf08b4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740583"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-your-lync-server-2013-environment-for-the-lync-room-system-administrative-web-portal"></a><span data-ttu-id="207d3-102">為 Lync Room System Administrative Web Portal 設定您的 Lync Server 2013 環境</span><span class="sxs-lookup"><span data-stu-id="207d3-102">Configuring your Lync Server 2013 environment for the Lync Room System Administrative Web Portal</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="207d3-103">_**主題上次修改日期：** 2014-05-22_</span><span class="sxs-lookup"><span data-stu-id="207d3-103">_**Topic Last Modified:** 2014-05-22_</span></span>

<span data-ttu-id="207d3-104">若要使用 Lync 會議室系統（LRS）的系統管理網頁入口網站，您必須安裝或設定下列先決條件。</span><span class="sxs-lookup"><span data-stu-id="207d3-104">To use the Lync Room System (LRS) Administrative Web Portal, you will need to install or configure the following prerequisites.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="207d3-105">如果伺服器已設定 Kerberos 和 NTLM 驗證，且 LRS 是在未加入網域的電腦上執行，Kerberos 驗證將會失敗，而且使用者將無法在系統管理入口網站中看到 LRS 的狀態。</span><span class="sxs-lookup"><span data-stu-id="207d3-105">If the server is configured with both Kerberos and NTLM authentication, and LRS is running on a computer that is not joined to the domain, Kerberos authentication will fail and the user will not see the status of LRS in the administrative portal.</span></span> <span data-ttu-id="207d3-106">若要解決此問題，請使用 NTLM 驗證或 NTLM 與 TLS DSK 驗證（沒有 Kerberos）來設定伺服器，或將 LRS 電腦加入網域。</span><span class="sxs-lookup"><span data-stu-id="207d3-106">To resolve this issue, configure the server with NTLM authentication or both NTLM and TLS-DSK authentication (without Kerberos), or join the LRS computer to the domain.</span></span>



</div>

1.  <span data-ttu-id="207d3-107">安裝 Lync Server 2013 累計更新： Lync Server 拓撲中的2013年7月。</span><span class="sxs-lookup"><span data-stu-id="207d3-107">Install Lync Server 2013 Cumulative Updates: July 2013 in the Lync Server topology.</span></span>
    
    <span data-ttu-id="207d3-108">若要取得更新或查看其隨附的內容，請參閱[Lync Server 2013 的更新](http://go.microsoft.com/fwlink/p/?linkid=323959)。</span><span class="sxs-lookup"><span data-stu-id="207d3-108">To get the update or see what’s included with it, see [Updates for Lync Server 2013](http://go.microsoft.com/fwlink/p/?linkid=323959).</span></span>

2.  <span data-ttu-id="207d3-109">建立啟用 SIP 的 Active Directory 使用者。</span><span class="sxs-lookup"><span data-stu-id="207d3-109">Create a SIP-enabled Active Directory user.</span></span>
    
    <span data-ttu-id="207d3-110">LRS 系統管理網頁入口網站使用這些認證來查詢 Lync Server 的資訊。</span><span class="sxs-lookup"><span data-stu-id="207d3-110">The LRS Administrative Web Portal uses these credentials to query information from Lync Server.</span></span> <span data-ttu-id="207d3-111">建議的使用者名稱為 LRSApp。</span><span class="sxs-lookup"><span data-stu-id="207d3-111">The recommended username is LRSApp.</span></span>

3.  <span data-ttu-id="207d3-112">使用 [名稱 LRSSupportAdminGroup] 建立 Active Directory 安全性群組。</span><span class="sxs-lookup"><span data-stu-id="207d3-112">Create an Active Directory security group with name LRSSupportAdminGroup.</span></span>
    
    <span data-ttu-id="207d3-113">建立群組範圍為全域且群組類型為安全性的群組。</span><span class="sxs-lookup"><span data-stu-id="207d3-113">Create the group with Group Scope as Global and Group Type as Security.</span></span> <span data-ttu-id="207d3-114">加入到這個群組的 SIP 啟用的使用者，都會獲授權查看聊天室清單並執行某些命令，例如收集記錄。</span><span class="sxs-lookup"><span data-stu-id="207d3-114">SIP enabled users who are added to this group will be authorized to see the list of rooms and execute certain commands, such as collecting logs.</span></span>

4.  <span data-ttu-id="207d3-115">使用 [名稱 LRSFullAccessAdminGroup] 建立 Active Directory 安全性群組。</span><span class="sxs-lookup"><span data-stu-id="207d3-115">Create an Active Directory security group with name LRSFullAccessAdminGroup.</span></span>
    
    <span data-ttu-id="207d3-116">建立將群組範圍作為全域和群組類型做為安全性的群組。加入此群組的 SIP 啟用使用者已獲授權使用所有系統管理入口網站功能。</span><span class="sxs-lookup"><span data-stu-id="207d3-116">Create the group with Group Scope as Global and Group Type as Security.SIP enabled users who are added to this group are authorized to use all admin portal functionality.</span></span>
    
     
    
    <span data-ttu-id="207d3-117">![具有安全性群組角色之管理員群組的清單](images/Dn436325.5d432819-a2e2-452c-bc2a-5d4ee79d8c33(OCS.15).png "具有安全性群組角色之管理員群組的清單")</span><span class="sxs-lookup"><span data-stu-id="207d3-117">![List of Admin Groups with security group role](images/Dn436325.5d432819-a2e2-452c-bc2a-5d4ee79d8c33(OCS.15).png "List of Admin Groups with security group role")</span></span>  
    
     

5.  <span data-ttu-id="207d3-118">將 LRSFullAccessAdminGroup 新增為 LRSSupportAdminGroup 的成員。</span><span class="sxs-lookup"><span data-stu-id="207d3-118">Add LRSFullAccessAdminGroup as a member of LRSSupportAdminGroup.</span></span>
    
    <span data-ttu-id="207d3-119">![[LRSSupportAdminGroup 內容成員] 頁面](images/Dn436325.91a4a28a-cacf-4ef6-aac1-915ec41c9648(OCS.15).png "[LRSSupportAdminGroup 內容成員] 頁面")</span><span class="sxs-lookup"><span data-stu-id="207d3-119">![LRSSupportAdminGroup Properties Members page](images/Dn436325.91a4a28a-cacf-4ef6-aac1-915ec41c9648(OCS.15).png "LRSSupportAdminGroup Properties Members page")</span></span>  
    
     

6.  <span data-ttu-id="207d3-120">使用 [名稱 LRSSupport] 建立啟用 SIP 的 Active Directory 使用者。</span><span class="sxs-lookup"><span data-stu-id="207d3-120">Create a SIP enabled Active Directory user with name LRSSupport.</span></span> <span data-ttu-id="207d3-121">將此使用者新增至 LRSSupportAdminGroup。</span><span class="sxs-lookup"><span data-stu-id="207d3-121">Add this user to LRSSupportAdminGroup.</span></span>
    
    <span data-ttu-id="207d3-122">![[LRSSupportAdminGroup 內容成員] 頁面](images/Dn436325.7638055d-22ac-4909-914d-1966f5623909(OCS.15).png "[LRSSupportAdminGroup 內容成員] 頁面")</span><span class="sxs-lookup"><span data-stu-id="207d3-122">![LRSSupportAdminGroup Properties Members page](images/Dn436325.7638055d-22ac-4909-914d-1966f5623909(OCS.15).png "LRSSupportAdminGroup Properties Members page")</span></span>  
    
     

7.  <span data-ttu-id="207d3-123">安裝適用于 Visual Studio 2010 SP1 及 Visual Web Developer 2010 SP1 的 ASP.NET MVC 4，請參閱 Microsoft 下載中心中[http://go.microsoft.com/fwlink/p/?LinkId=323967](http://go.microsoft.com/fwlink/p/?linkid=323967)的。</span><span class="sxs-lookup"><span data-stu-id="207d3-123">Install ASP.NET MVC 4 for Visual Studio 2010 SP1 and Visual Web Developer 2010 SP1, available in the Microsoft Download Center at [http://go.microsoft.com/fwlink/p/?LinkId=323967](http://go.microsoft.com/fwlink/p/?linkid=323967).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

