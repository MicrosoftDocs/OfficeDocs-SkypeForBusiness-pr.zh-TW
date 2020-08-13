---
title: Lync Server 2013：查看位置原則資訊
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing location policy information
ms:assetid: 14e41bcb-ea0a-49c2-99b3-1f61fc34416d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520954(v=OCS.15)
ms:contentKeyID: 48183489
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9ebd92944d02cf899ad6da60a586cd5ec24e9aa8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211219"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="viewing-location-policy-information-in-lync-server-2013"></a><span data-ttu-id="5cfe9-102">在 Lync Server 2013 中查看位置原則資訊</span><span class="sxs-lookup"><span data-stu-id="5cfe9-102">Viewing location policy information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5cfe9-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="5cfe9-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="5cfe9-104">在 Lync Server 2013 中，您可以使用位置原則，套用與增強型 9-1-1 (E9-1-1) 功能及使用者或連絡人的位置設定相關的設定。</span><span class="sxs-lookup"><span data-stu-id="5cfe9-104">In Lync Server 2013, you can use the location policy to apply settings that relate to Enhanced 9-1-1 (E9-1-1) functionality and to location settings for users or contacts.</span></span> <span data-ttu-id="5cfe9-105">位置原則會判斷使用者是否已啟用 E9-1-1，如果是，則會決定緊急電話的行為。</span><span class="sxs-lookup"><span data-stu-id="5cfe9-105">The location policy determines whether a user is enabled for E9-1-1, and if so what the behavior is of an emergency call.</span></span> <span data-ttu-id="5cfe9-106">例如，您可以使用位置原則來定義組成緊急電話的數字 (例如，在美國為 911)、是否應自動告知公司的安全部門，以及應如何路由傳送來電。</span><span class="sxs-lookup"><span data-stu-id="5cfe9-106">For example, you can use the location policy to define what number constitutes an emergency call (for example, 911 in the United States), whether corporate security should be automatically notified, and how the call should be routed.</span></span>

<span data-ttu-id="5cfe9-107">您可以在 Lync Server 2013 [控制台] 中的 [**網路**設定] 群組設定位置原則。</span><span class="sxs-lookup"><span data-stu-id="5cfe9-107">You can configure location policies from the **Network Configuration** group in Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="5cfe9-108">從 Lync Server 控制台，您可以查看、建立、修改或刪除位置原則。</span><span class="sxs-lookup"><span data-stu-id="5cfe9-108">From Lync Server Control Panel you can view, create, modify, or delete location policies.</span></span> <span data-ttu-id="5cfe9-109">請使用下列程序來檢視位置原則的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="5cfe9-109">Use the following procedure to view information about location policies.</span></span> <span data-ttu-id="5cfe9-110">如需建立或修改位置原則的詳細資訊，請參閱[在 Lync Server 2013 中建立或修改位置原則](lync-server-2013-creating-or-modifying-a-location-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="5cfe9-110">For details on creating or modifying location policies, see [Creating or modifying a location policy in Lync Server 2013](lync-server-2013-creating-or-modifying-a-location-policy.md).</span></span>

<div>

## <a name="to-view-information-about-a-location-policy"></a><span data-ttu-id="5cfe9-111">檢視位置原則的相關資訊</span><span class="sxs-lookup"><span data-stu-id="5cfe9-111">To view information about a location policy</span></span>

1.  <span data-ttu-id="5cfe9-112">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="5cfe9-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="5cfe9-113">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="5cfe9-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="5cfe9-114">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="5cfe9-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="5cfe9-115">在左導覽列中按一下 **[網路設定]**，然後按一下 **[位置原則]**。</span><span class="sxs-lookup"><span data-stu-id="5cfe9-115">In the left navigation bar, click **Network Configuration** and then click **Location Policy**.</span></span>

4.  <span data-ttu-id="5cfe9-116">在 **[位置原則]** 頁面上，選取您要修改的位置原則。</span><span class="sxs-lookup"><span data-stu-id="5cfe9-116">On the **Location Policy** page, select the location policy that you want to modify.</span></span>

5.  <span data-ttu-id="5cfe9-117">在 **[編輯]** 功能表上，按一下 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="5cfe9-117">On the **Edit** menu, click **Show details**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5cfe9-118">您一次只能檢視一個位置原則的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="5cfe9-118">You can only view information about one location policy at a time.</span></span>

    
    </div>

<span data-ttu-id="5cfe9-p104">依預設會有名為「通用」的單一原則存在，且無法刪除或重新命名。但您可以修改全域原則。若您未建立網站原則或個別使用者原則，則所有使用者與連絡人都會套用此原則。特定的使用者必須套用個別使用者原則。</span><span class="sxs-lookup"><span data-stu-id="5cfe9-p104">A single policy, called Global, exists by default and cannot be deleted or renamed. However, you can modify the Global policy. This policy will apply to all users and contacts, unless you create site policies or per-user policies. Per-user policies must be applied to specific users.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5cfe9-123">另請參閱</span><span class="sxs-lookup"><span data-stu-id="5cfe9-123">See Also</span></span>


[<span data-ttu-id="5cfe9-124">在 Lync Server 2013 中建立或修改位置原則</span><span class="sxs-lookup"><span data-stu-id="5cfe9-124">Creating or modifying a location policy in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-a-location-policy.md)  
[<span data-ttu-id="5cfe9-125">在 Lync Server 2013 中建立位置原則</span><span class="sxs-lookup"><span data-stu-id="5cfe9-125">Create location policies in Lync Server 2013</span></span>](lync-server-2013-create-location-policies.md)  
[<span data-ttu-id="5cfe9-126">在 Lync Server 2013 中建立或修改網路網站</span><span class="sxs-lookup"><span data-stu-id="5cfe9-126">Create or modify a network site in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-network-site.md)  


[<span data-ttu-id="5cfe9-127">New-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="5cfe9-127">New-CsLocationPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsLocationPolicy)  
[<span data-ttu-id="5cfe9-128">Set-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="5cfe9-128">Set-CsLocationPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsLocationPolicy)  
[<span data-ttu-id="5cfe9-129">Remove-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="5cfe9-129">Remove-CsLocationPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsLocationPolicy)  
[<span data-ttu-id="5cfe9-130">Get-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="5cfe9-130">Get-CsLocationPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsLocationPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

