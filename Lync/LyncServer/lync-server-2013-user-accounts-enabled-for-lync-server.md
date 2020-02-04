---
title: Lync Server 2013：已啟用 Lync Server 的使用者帳戶
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User accounts enabled for Lync Server 2013
ms:assetid: 8021087e-5084-4a39-9fef-ab9376c6d371
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182543(v=OCS.15)
ms:contentKeyID: 48184651
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 613d6350fcb405b1ae8beef78c3ee8c8a64a084c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744653"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-accounts-enabled-for-lync-server-2013"></a><span data-ttu-id="9cc97-102">已啟用 Lync Server 2013 的使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="9cc97-102">User accounts enabled for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9cc97-103">_**主題上次修改日期：** 2014-04-18_</span><span class="sxs-lookup"><span data-stu-id="9cc97-103">_**Topic Last Modified:** 2014-04-18_</span></span>

<span data-ttu-id="9cc97-104">本節中的主題提供設定使用者設定的逐步程式，您可以使用 Lync Server 2013 控制台進行設定。</span><span class="sxs-lookup"><span data-stu-id="9cc97-104">Topics in this section provide step-by-step procedures for configuring user settings that you can perform using the Lync Server 2013 Control Panel.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="9cc97-105">您無法使用 Lync Server [控制台] 來管理屬於 Active Directory 網域系統管理員群組成員的使用者。</span><span class="sxs-lookup"><span data-stu-id="9cc97-105">You cannot use Lync Server Control Panel to manage users who are members of the Active Directory Domain Admins group.</span></span> <span data-ttu-id="9cc97-106">對於網域管理員使用者，您只能使用 Lync Server [控制台] 執行唯讀搜尋作業。</span><span class="sxs-lookup"><span data-stu-id="9cc97-106">For Domain Admins users, you can use Lync Server Control Panel only to perform read-only search operations.</span></span> <span data-ttu-id="9cc97-107">若要在網域管理員使用者上執行寫入操作（例如，針對 Lync Server [控制台] 啟用或停用，請變更池或原則指派，電話設定，SIP 位址），您必須在以網域管理員使用者身分登入的情況下，才能使用 Windows PowerShell Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9cc97-107">To perform write operations on Domain Admins users (for example, enable or disable for Lync Server Control Panel, change pool or policy assignments, telephony settings, SIP address), you must use Windows PowerShell cmdlets while logged on as a Domain Admins user.</span></span> <span data-ttu-id="9cc97-108">如需使用 Windows PowerShell Cmdlet 來管理使用者的詳細資料，請參閱<A href="lync-server-2013-lync-server-management-shell.md">Lync Server 2013 管理命令</A>介面。</span><span class="sxs-lookup"><span data-stu-id="9cc97-108">For details about using Windows PowerShell cmdlets to manage users, see <A href="lync-server-2013-lync-server-management-shell.md">Lync Server 2013 Management Shell</A>.</span></span>



</div>

<span data-ttu-id="9cc97-109">當您執行任何涉及搜尋使用者或篩選使用者搜尋結果的 Lync Server 2013 系統管理工作時，會有一些使用者屬性作為屬性存在於 Active Directory 網域服務中，但不會複製到通用類別目錄在部署 Microsoft Exchange Server 之前。</span><span class="sxs-lookup"><span data-stu-id="9cc97-109">When you perform any Lync Server 2013 administrative task that involves searching for a user or filtering user search results, there are some user properties that exist as attributes in Active Directory Domain Services but are not replicated to the global catalog until Microsoft Exchange Server is deployed.</span></span> <span data-ttu-id="9cc97-110">Microsoft Exchange （而非 Lync Server）會將下列屬性標示為在安裝時，將其複製到全域編目：</span><span class="sxs-lookup"><span data-stu-id="9cc97-110">Microsoft Exchange, not Lync Server, marks the following attributes for replication to the global catalog when it is installed:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9cc97-111">使用者資訊</span><span class="sxs-lookup"><span data-stu-id="9cc97-111">User Information</span></span></th>
<th><span data-ttu-id="9cc97-112">位址和電話</span><span class="sxs-lookup"><span data-stu-id="9cc97-112">Address and Phone</span></span></th>
<th><span data-ttu-id="9cc97-113">組織</span><span class="sxs-lookup"><span data-stu-id="9cc97-113">Organization</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9cc97-114">中間</span><span class="sxs-lookup"><span data-stu-id="9cc97-114">Initials</span></span></p></td>
<td><p><span data-ttu-id="9cc97-115">街道位址</span><span class="sxs-lookup"><span data-stu-id="9cc97-115">Street address</span></span></p>
<p><span data-ttu-id="9cc97-116">國家/地區</span><span class="sxs-lookup"><span data-stu-id="9cc97-116">Country/region</span></span></p>
<p><span data-ttu-id="9cc97-117">值班</span><span class="sxs-lookup"><span data-stu-id="9cc97-117">Pager</span></span></p>
<p><span data-ttu-id="9cc97-118">傳入</span><span class="sxs-lookup"><span data-stu-id="9cc97-118">Fax</span></span></p>
<p><span data-ttu-id="9cc97-119">行動裝置</span><span class="sxs-lookup"><span data-stu-id="9cc97-119">Mobile</span></span></p></td>
<td><p><span data-ttu-id="9cc97-120">職稱</span><span class="sxs-lookup"><span data-stu-id="9cc97-120">Title</span></span></p>
<p><span data-ttu-id="9cc97-121">家</span><span class="sxs-lookup"><span data-stu-id="9cc97-121">Company</span></span></p>
<p><span data-ttu-id="9cc97-122">部門</span><span class="sxs-lookup"><span data-stu-id="9cc97-122">Department</span></span></p>
<p><span data-ttu-id="9cc97-123">Office</span><span class="sxs-lookup"><span data-stu-id="9cc97-123">Office</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a><span data-ttu-id="9cc97-124">本節內容</span><span class="sxs-lookup"><span data-stu-id="9cc97-124">In This Section</span></span>

  - [<span data-ttu-id="9cc97-125">查看已針對 Lync Server 2013 啟用的使用者帳戶資訊</span><span class="sxs-lookup"><span data-stu-id="9cc97-125">Viewing information about user accounts enabled for Lync Server 2013</span></span>](lync-server-2013-viewing-information-about-user-accounts-enabled-for-lync-server.md)

  - [<span data-ttu-id="9cc97-126">啟用和停用 Lync Server 2013 的使用者</span><span class="sxs-lookup"><span data-stu-id="9cc97-126">Enabling and disabling users for Lync Server 2013</span></span>](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)

  - [<span data-ttu-id="9cc97-127">在 Lync Server 2013 中管理企業版使用者語音</span><span class="sxs-lookup"><span data-stu-id="9cc97-127">Managing Enterprise Voice for users in Lync Server 2013</span></span>](lync-server-2013-managing-enterprise-voice-for-users.md)

  - [<span data-ttu-id="9cc97-128">在 Lync Server 2013 中修改使用者帳戶屬性</span><span class="sxs-lookup"><span data-stu-id="9cc97-128">Modifying user account properties in Lync Server 2013</span></span>](lync-server-2013-modifying-user-account-properties.md)

  - [<span data-ttu-id="9cc97-129">在 Lync Server 2013 中管理外部使用存取原則</span><span class="sxs-lookup"><span data-stu-id="9cc97-129">Manage external access policy in Lync Server 2013</span></span>](lync-server-2013-manage-external-access-policy-for-your-organization.md)

  - [<span data-ttu-id="9cc97-130">在 Lync Server 2013 中指派每個使用者的原則</span><span class="sxs-lookup"><span data-stu-id="9cc97-130">Assigning per-user policies in Lync Server 2013</span></span>](lync-server-2013-assigning-per-user-policies.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9cc97-131">請參閱</span><span class="sxs-lookup"><span data-stu-id="9cc97-131">See Also</span></span>


[<span data-ttu-id="9cc97-132">Lync Server 2013 中的使用者管理 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="9cc97-132">User management cmdlets in Lync Server 2013</span></span>](lync-server-2013-user-management-cmdlets.md)  


[<span data-ttu-id="9cc97-133">在 Lync Server 2013 中管理使用者</span><span class="sxs-lookup"><span data-stu-id="9cc97-133">Managing users in Lync Server 2013</span></span>](lync-server-2013-managing-users-in-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

