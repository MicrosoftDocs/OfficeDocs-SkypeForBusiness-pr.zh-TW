---
title: Lync Server 2013：新增及啟用 Lync Server 的使用者帳戶
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Add and enable user account for Lync Server
ms:assetid: 1edd1c1c-307d-450b-abea-33aaf56bdf13
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520961(v=OCS.15)
ms:contentKeyID: 48183578
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0fc52e76d480e323669b88c1ee461eeccf9aef38
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977113"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-and-enable-user-account-for-lync-server-2013"></a><span data-ttu-id="300a9-102">新增及啟用 Lync Server 2013 的使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="300a9-102">Add and enable user account for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="300a9-103">_**主題上次修改日期：** 2012-11-02_</span><span class="sxs-lookup"><span data-stu-id="300a9-103">_**Topic Last Modified:** 2012-11-02_</span></span>

<span data-ttu-id="300a9-104">在 Active Directory 使用者和電腦中啟用使用者帳戶之後，您就可以使用 Lync Server [控制台]，透過將 Active Directory 使用者新增到 Lync Server 來建立並啟用新的 Lync Server 2013 使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="300a9-104">After enabling a user account in Active Directory Users and Computers, you can use Lync Server Control Panel to create and enable new Lync Server 2013 user accounts by adding an Active Directory user to Lync Server.</span></span>

<div>

## <a name="to-add-and-enable-a-new-lync-server-user"></a><span data-ttu-id="300a9-105">新增並啟用新的 Lync Server 使用者</span><span class="sxs-lookup"><span data-stu-id="300a9-105">To add and enable a new Lync Server user</span></span>

1.  <span data-ttu-id="300a9-106">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="300a9-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="300a9-107">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="300a9-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="300a9-108">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="300a9-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="300a9-109">在左側導覽列中，按一下 [**使用者**]。</span><span class="sxs-lookup"><span data-stu-id="300a9-109">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="300a9-110">按一下 [**啟用使用者**]。</span><span class="sxs-lookup"><span data-stu-id="300a9-110">Click **Enable users**.</span></span>

5.  <span data-ttu-id="300a9-111">在 [**新的 Lync Server 使用者**] 對話方塊中 **，按一下 [新增]**。</span><span class="sxs-lookup"><span data-stu-id="300a9-111">On the **New Lync Server User** dialog, click **Add**.</span></span>

6.  <span data-ttu-id="300a9-112">在 [**搜尋使用者**] 方塊中，輸入所有或第一個部分的名稱、顯示名稱、名字、姓氏、安全帳戶管理員（SAM）帳戶名稱、電子郵件地址、使用者主體名稱（UPN），或您想要的 Active Directory 使用者帳戶的電話號碼，然後按一下 [**尋找**]。</span><span class="sxs-lookup"><span data-stu-id="300a9-112">In the **Search users** box, type all or the first portion of the name, display name, first name, last name, Security Accounts Manager (SAM) account name, email address, User Principal Name (UPN), or phone number of the Active Directory user account that you want, and then click **Find**.</span></span>

7.  <span data-ttu-id="300a9-113">在表格中，選取您要新增至 Lync Server 的帳戶，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="300a9-113">In the table, select the account you want to add to Lync Server, and then click **OK**.</span></span>

8.  <span data-ttu-id="300a9-114">將使用者指派至 [泳池]，指定任何其他詳細資料，然後將原則指派給您想要的使用者，然後按一下 [**啟用**]。</span><span class="sxs-lookup"><span data-stu-id="300a9-114">Assign the user to a pool, specify any additional details, and assign the policies to the user you want, and then click **Enable**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="300a9-115">請參閱</span><span class="sxs-lookup"><span data-stu-id="300a9-115">See Also</span></span>


[<span data-ttu-id="300a9-116">停用或重新啟用 Lync Server 2013 的使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="300a9-116">Disable or re-enable user account for Lync Server 2013</span></span>](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  
[<span data-ttu-id="300a9-117">從 Lync Server 2013 移除使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="300a9-117">Remove a user account from Lync Server 2013</span></span>](lync-server-2013-remove-a-user-account-from-lync-server.md)  


[<span data-ttu-id="300a9-118">啟用和停用 Lync Server 2013 的使用者</span><span class="sxs-lookup"><span data-stu-id="300a9-118">Enabling and disabling users for Lync Server 2013</span></span>](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

