---
title: Lync Server 2013：搜尋 Lync Server 使用者
description: Lync Server 2013：搜尋 Lync Server 使用者。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Search for Lync Server users
ms:assetid: 3b9f6f55-d7a9-46ae-8e10-f221ba0d3bb5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429701(v=OCS.15)
ms:contentKeyID: 48183871
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0c4860b7b89ad13b3a0003c5666a320172dad6d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557079"
---
# <a name="search-for-lync-server-users-in-lync-server-2013"></a><span data-ttu-id="ebba4-103">在 Lync Server 2013 中搜尋 Lync Server 使用者</span><span class="sxs-lookup"><span data-stu-id="ebba4-103">Search for Lync Server users in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ebba4-104">_**主題上次修改日期：** 2014-05-14_</span><span class="sxs-lookup"><span data-stu-id="ebba4-104">_**Topic Last Modified:** 2014-05-14_</span></span>

<span data-ttu-id="ebba4-105">您可以使用搜尋查詢的結果來設定 Lync Server 2013 的使用者。</span><span class="sxs-lookup"><span data-stu-id="ebba4-105">You can use the results of a search query to configure users for Lync Server 2013.</span></span> <span data-ttu-id="ebba4-106">您可以依顯示名稱、名字、姓氏、安全性帳戶管理員 (SAM) 帳戶名稱、SIP 位址或線路統一資源識別元 (URI) 來搜尋使用者。</span><span class="sxs-lookup"><span data-stu-id="ebba4-106">You can search for users by display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI).</span></span>

<span data-ttu-id="ebba4-107">您可以使用 Lync Server 控制台或 Active Directory 使用者和電腦嵌入式管理單元來搜尋使用者。</span><span class="sxs-lookup"><span data-stu-id="ebba4-107">You can search for users by using the Lync Server Control Panel or the Active Directory Users and Computers snap-in.</span></span> <span data-ttu-id="ebba4-108">下列程式說明如何使用 Lync Server 控制台來搜尋使用者。</span><span class="sxs-lookup"><span data-stu-id="ebba4-108">The following procedure describes how to use Lync Server Control Panel to search for users.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ebba4-109">在具有中央樹系拓撲的環境中，如果以使用者的電子郵件地址來搜尋使用者，搜尋結果可能會不正確。</span><span class="sxs-lookup"><span data-stu-id="ebba4-109">In an environment with a central forest topology, search results might not be accurate when you search for a user by the user’s email address.</span></span> <span data-ttu-id="ebba4-110">您可以改為指定 SIP 位址首碼 (例如 sip:name) 來進行搜尋、新增搜尋篩選並選取包含部分電子郵件位址的 SIP 位址，或使用 <STRONG>Get-CSUser</STRONG> Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ebba4-110">Instead, you can search for users by specifying a SIP address prefix, for example, sip:name, add a search filter and select a SIP address that contains a partial email address, or use the <STRONG>Get-CSUser</STRONG> cmdlet.</span></span>



</div>

<div>

## <a name="to-search-for-one-or-more-users"></a><span data-ttu-id="ebba4-111">若要搜尋一個或多個使用者</span><span class="sxs-lookup"><span data-stu-id="ebba4-111">To search for one or more users</span></span>

1.  <span data-ttu-id="ebba4-112">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="ebba4-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ebba4-113">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="ebba4-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="ebba4-114">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="ebba4-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="ebba4-115">在左導覽列中，按一下 **[使用者]**。</span><span class="sxs-lookup"><span data-stu-id="ebba4-115">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="ebba4-116">在 **[搜尋使用者]** 方塊中，輸入您要搜尋之使用者帳戶的顯示名稱、名字、姓氏、SAM 帳戶名稱、SIP 位址或線路 URI 的全部或頭幾個字，然後按一下 **[尋找]**。</span><span class="sxs-lookup"><span data-stu-id="ebba4-116">In the **Search users** box, type all or the first portion of the display name, first name, last name, SAM account name, SIP address, or line URI of the user account that you want to search for, and then click **Find**.</span></span>

5.  <span data-ttu-id="ebba4-117">(選用) 指定其他搜尋條件，縮減結果：</span><span class="sxs-lookup"><span data-stu-id="ebba4-117">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="ebba4-118">按一下畫面右上角就在 **[搜尋結果]** 上方的展開箭頭，然後按一下 **[新增篩選]**。</span><span class="sxs-lookup"><span data-stu-id="ebba4-118">Click the expand arrow button in the upper-right corner of the screen above **Search results**, and then click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="ebba4-119">輸入使用者內容，您可以直接輸入文字或是按一下下拉式清單的箭頭以選取使用者內容。</span><span class="sxs-lookup"><span data-stu-id="ebba4-119">Enter the user property by typing it or clicking the arrow in the drop-down list to select a user property.</span></span>
    
    3.  <span data-ttu-id="ebba4-120">在 **[等於]** 清單中，按一下 **[等於]** 或 **[不等於]**。</span><span class="sxs-lookup"><span data-stu-id="ebba4-120">In the **Equal to** list, click **Equal to** or **Not equal to**.</span></span>
    
    4.  <span data-ttu-id="ebba4-121">在文字方塊中，輸入您要用來篩選搜尋結果的搜尋條件，然後按一下 **[尋找]**。</span><span class="sxs-lookup"><span data-stu-id="ebba4-121">In the text box, type the search criteria you want to use to filter search results, and then click **Find**.</span></span>

6.  <span data-ttu-id="ebba4-p105">搜尋結果會出現在 **[搜尋結果]** 下方。您可以選取清單中任一或全部使用者，然後對所選使用者執行設定工作。</span><span class="sxs-lookup"><span data-stu-id="ebba4-p105">The search results appear under **Search Results**. You can select any or all of the users in the list and perform configuration tasks on the users you select.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ebba4-124">另請參閱</span><span class="sxs-lookup"><span data-stu-id="ebba4-124">See Also</span></span>


[<span data-ttu-id="ebba4-125">查看啟用 Lync Server 2013 之使用者帳戶的相關資訊</span><span class="sxs-lookup"><span data-stu-id="ebba4-125">Viewing information about user accounts enabled for Lync Server 2013</span></span>](lync-server-2013-viewing-information-about-user-accounts-enabled-for-lync-server.md)  
[<span data-ttu-id="ebba4-126">啟用和停用 Lync Server 2013 的使用者</span><span class="sxs-lookup"><span data-stu-id="ebba4-126">Enabling and disabling users for Lync Server 2013</span></span>](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

