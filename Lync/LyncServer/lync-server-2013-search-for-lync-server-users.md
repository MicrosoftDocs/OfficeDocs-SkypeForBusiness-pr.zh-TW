---
title: Lync Server 2013：搜尋 Lync Server 使用者
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
ms.openlocfilehash: 7134afbc86134471e8d536b36fc8e28142a64db2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764921"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="search-for-lync-server-users-in-lync-server-2013"></a><span data-ttu-id="a416c-102">在 Lync Server 2013 中搜尋 Lync Server 使用者</span><span class="sxs-lookup"><span data-stu-id="a416c-102">Search for Lync Server users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a416c-103">_**主題上次修改日期：** 2014-05-14_</span><span class="sxs-lookup"><span data-stu-id="a416c-103">_**Topic Last Modified:** 2014-05-14_</span></span>

<span data-ttu-id="a416c-104">您可以使用搜尋查詢的結果來設定 Lync Server 2013 的使用者。</span><span class="sxs-lookup"><span data-stu-id="a416c-104">You can use the results of a search query to configure users for Lync Server 2013.</span></span> <span data-ttu-id="a416c-105">您可以依顯示名稱、名字、姓氏、安全帳戶管理員（SAM）帳戶名稱、SIP 位址或行統一資源識別項（URI）來搜尋使用者。</span><span class="sxs-lookup"><span data-stu-id="a416c-105">You can search for users by display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI).</span></span>

<span data-ttu-id="a416c-106">您可以使用 Lync Server [控制台] 或 [Active Directory 使用者和電腦] 管理單元來搜尋使用者。</span><span class="sxs-lookup"><span data-stu-id="a416c-106">You can search for users by using the Lync Server Control Panel or the Active Directory Users and Computers snap-in.</span></span> <span data-ttu-id="a416c-107">下列程式說明如何使用 Lync Server 的 [控制台] 搜尋使用者。</span><span class="sxs-lookup"><span data-stu-id="a416c-107">The following procedure describes how to use Lync Server Control Panel to search for users.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a416c-108">在具有中央林拓撲的環境中，當您使用使用者的電子郵件地址搜尋使用者時，搜尋結果可能不正確。</span><span class="sxs-lookup"><span data-stu-id="a416c-108">In an environment with a central forest topology, search results might not be accurate when you search for a user by the user’s email address.</span></span> <span data-ttu-id="a416c-109">相反地，您可以透過指定 SIP 位址首碼（例如 sip： name、新增搜尋篩選器，然後選取包含部分電子郵件地址的 SIP 位址）來搜尋使用者，或使用<STRONG>move-csuser</STRONG> Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a416c-109">Instead, you can search for users by specifying a SIP address prefix, for example, sip:name, add a search filter and select a SIP address that contains a partial email address, or use the <STRONG>Get-CSUser</STRONG> cmdlet.</span></span>



</div>

<div>

## <a name="to-search-for-one-or-more-users"></a><span data-ttu-id="a416c-110">搜尋一或多位使用者</span><span class="sxs-lookup"><span data-stu-id="a416c-110">To search for one or more users</span></span>

1.  <span data-ttu-id="a416c-111">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="a416c-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a416c-112">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="a416c-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a416c-113">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="a416c-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="a416c-114">在左側導覽列中，按一下 [**使用者**]。</span><span class="sxs-lookup"><span data-stu-id="a416c-114">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="a416c-115">在 [**搜尋使用者**] 方塊中，輸入您要搜尋之使用者帳戶的全部或第一部分的顯示名稱、名字、姓氏、SAM 帳戶名稱、SIP 位址或行 URI，然後按一下 [**尋找**]。</span><span class="sxs-lookup"><span data-stu-id="a416c-115">In the **Search users** box, type all or the first portion of the display name, first name, last name, SAM account name, SIP address, or line URI of the user account that you want to search for, and then click **Find**.</span></span>

5.  <span data-ttu-id="a416c-116">可選指定額外的搜尋準則以縮小結果範圍：</span><span class="sxs-lookup"><span data-stu-id="a416c-116">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="a416c-117">按一下 [**搜尋結果**] 上方畫面右上角的展開箭號按鈕，然後按一下 [**新增篩選**]。</span><span class="sxs-lookup"><span data-stu-id="a416c-117">Click the expand arrow button in the upper-right corner of the screen above **Search results**, and then click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="a416c-118">輸入使用者屬性或按一下下拉式清單中的箭號，以選取使用者屬性。</span><span class="sxs-lookup"><span data-stu-id="a416c-118">Enter the user property by typing it or clicking the arrow in the drop-down list to select a user property.</span></span>
    
    3.  <span data-ttu-id="a416c-119">在 [**等於**] 清單中，按一下 [**等於**或**不等於**]。</span><span class="sxs-lookup"><span data-stu-id="a416c-119">In the **Equal to** list, click **Equal to** or **Not equal to**.</span></span>
    
    4.  <span data-ttu-id="a416c-120">在文字方塊中，輸入您要用來篩選搜尋結果的搜尋準則，然後按一下 [**尋找**]。</span><span class="sxs-lookup"><span data-stu-id="a416c-120">In the text box, type the search criteria you want to use to filter search results, and then click **Find**.</span></span>

6.  <span data-ttu-id="a416c-121">搜尋結果會顯示在 [**搜尋結果**] 下。</span><span class="sxs-lookup"><span data-stu-id="a416c-121">The search results appear under **Search Results**.</span></span> <span data-ttu-id="a416c-122">您可以選取清單中的任何或所有使用者，並在您選取的使用者上執行設定工作。</span><span class="sxs-lookup"><span data-stu-id="a416c-122">You can select any or all of the users in the list and perform configuration tasks on the users you select.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a416c-123">請參閱</span><span class="sxs-lookup"><span data-stu-id="a416c-123">See Also</span></span>


[<span data-ttu-id="a416c-124">查看已針對 Lync Server 2013 啟用的使用者帳戶資訊</span><span class="sxs-lookup"><span data-stu-id="a416c-124">Viewing information about user accounts enabled for Lync Server 2013</span></span>](lync-server-2013-viewing-information-about-user-accounts-enabled-for-lync-server.md)  
[<span data-ttu-id="a416c-125">啟用和停用 Lync Server 2013 的使用者</span><span class="sxs-lookup"><span data-stu-id="a416c-125">Enabling and disabling users for Lync Server 2013</span></span>](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

