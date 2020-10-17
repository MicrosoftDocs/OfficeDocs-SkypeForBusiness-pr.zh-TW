---
title: Lync Server 2013：已啟用 Lync Server 的使用者帳戶
description: Lync Server 2013：已啟用 Lync Server 的使用者帳戶。
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
ms.openlocfilehash: bf87177c378ffe61715d5332d2fd23b1d8e6fce6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569869"
---
# <a name="user-accounts-enabled-for-lync-server-2013"></a><span data-ttu-id="e1126-103">啟用 Lync Server 2013 的使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="e1126-103">User accounts enabled for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e1126-104">_**主題上次修改日期：** 2014-04-18_</span><span class="sxs-lookup"><span data-stu-id="e1126-104">_**Topic Last Modified:** 2014-04-18_</span></span>

<span data-ttu-id="e1126-105">本節中的主題提供逐步程式，以設定您可以使用 Lync Server 2013 控制台執行的使用者設定。</span><span class="sxs-lookup"><span data-stu-id="e1126-105">Topics in this section provide step-by-step procedures for configuring user settings that you can perform using the Lync Server 2013 Control Panel.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e1126-106">您無法使用 Lync Server 控制台來管理屬於 Active Directory Domain Admins 群組成員的使用者。</span><span class="sxs-lookup"><span data-stu-id="e1126-106">You cannot use Lync Server Control Panel to manage users who are members of the Active Directory Domain Admins group.</span></span> <span data-ttu-id="e1126-107">針對 Domain Admins 使用者，您可以使用 Lync Server 控制台只執行唯讀的搜尋作業。</span><span class="sxs-lookup"><span data-stu-id="e1126-107">For Domain Admins users, you can use Lync Server Control Panel only to perform read-only search operations.</span></span> <span data-ttu-id="e1126-108">若要在 Domain Admins 使用者上執行寫入作業 (例如，啟用或停用 Lync Server 控制台、變更集區或原則指派、電話語音設定、SIP 位址) ，您必須在以 Domain Admins 使用者的身分登入時使用 Windows PowerShell Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e1126-108">To perform write operations on Domain Admins users (for example, enable or disable for Lync Server Control Panel, change pool or policy assignments, telephony settings, SIP address), you must use Windows PowerShell cmdlets while logged on as a Domain Admins user.</span></span> <span data-ttu-id="e1126-109">如需使用 Windows PowerShell Cmdlet 來管理使用者的詳細資訊，請參閱 <A href="lync-server-2013-lync-server-management-shell.md">Lync Server 2013 管理命令</A>介面。</span><span class="sxs-lookup"><span data-stu-id="e1126-109">For details about using Windows PowerShell cmdlets to manage users, see <A href="lync-server-2013-lync-server-management-shell.md">Lync Server 2013 Management Shell</A>.</span></span>



</div>

<span data-ttu-id="e1126-110">當您執行任何需要搜尋使用者或篩選使用者搜尋結果的 Lync Server 2013 系統管理工作時，會有一些使用者屬性存在於 Active Directory 網域服務中，但在部署 Microsoft Exchange Server 之前，不會複製到通用類別目錄。</span><span class="sxs-lookup"><span data-stu-id="e1126-110">When you perform any Lync Server 2013 administrative task that involves searching for a user or filtering user search results, there are some user properties that exist as attributes in Active Directory Domain Services but are not replicated to the global catalog until Microsoft Exchange Server is deployed.</span></span> <span data-ttu-id="e1126-111">Microsoft Exchange 不是 Lync Server，當安裝時，會將下列屬性標示為已安裝的通用類別目錄：</span><span class="sxs-lookup"><span data-stu-id="e1126-111">Microsoft Exchange, not Lync Server, marks the following attributes for replication to the global catalog when it is installed:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e1126-112">使用者資訊</span><span class="sxs-lookup"><span data-stu-id="e1126-112">User Information</span></span></th>
<th><span data-ttu-id="e1126-113">地址和電話</span><span class="sxs-lookup"><span data-stu-id="e1126-113">Address and Phone</span></span></th>
<th><span data-ttu-id="e1126-114">組織</span><span class="sxs-lookup"><span data-stu-id="e1126-114">Organization</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e1126-115">縮寫</span><span class="sxs-lookup"><span data-stu-id="e1126-115">Initials</span></span></p></td>
<td><p><span data-ttu-id="e1126-116">街道地址</span><span class="sxs-lookup"><span data-stu-id="e1126-116">Street address</span></span></p>
<p><span data-ttu-id="e1126-117">國家/地區</span><span class="sxs-lookup"><span data-stu-id="e1126-117">Country/region</span></span></p>
<p><span data-ttu-id="e1126-118">呼叫器</span><span class="sxs-lookup"><span data-stu-id="e1126-118">Pager</span></span></p>
<p><span data-ttu-id="e1126-119">傳真</span><span class="sxs-lookup"><span data-stu-id="e1126-119">Fax</span></span></p>
<p><span data-ttu-id="e1126-120">Mobile</span><span class="sxs-lookup"><span data-stu-id="e1126-120">Mobile</span></span></p></td>
<td><p><span data-ttu-id="e1126-121">職稱</span><span class="sxs-lookup"><span data-stu-id="e1126-121">Title</span></span></p>
<p><span data-ttu-id="e1126-122">Company</span><span class="sxs-lookup"><span data-stu-id="e1126-122">Company</span></span></p>
<p><span data-ttu-id="e1126-123">部門</span><span class="sxs-lookup"><span data-stu-id="e1126-123">Department</span></span></p>
<p><span data-ttu-id="e1126-124">辦公室</span><span class="sxs-lookup"><span data-stu-id="e1126-124">Office</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a><span data-ttu-id="e1126-125">本章節內容</span><span class="sxs-lookup"><span data-stu-id="e1126-125">In This Section</span></span>

  - [<span data-ttu-id="e1126-126">查看啟用 Lync Server 2013 之使用者帳戶的相關資訊</span><span class="sxs-lookup"><span data-stu-id="e1126-126">Viewing information about user accounts enabled for Lync Server 2013</span></span>](lync-server-2013-viewing-information-about-user-accounts-enabled-for-lync-server.md)

  - [<span data-ttu-id="e1126-127">啟用和停用 Lync Server 2013 的使用者</span><span class="sxs-lookup"><span data-stu-id="e1126-127">Enabling and disabling users for Lync Server 2013</span></span>](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)

  - [<span data-ttu-id="e1126-128">在 Lync Server 2013 中管理使用者的企業語音</span><span class="sxs-lookup"><span data-stu-id="e1126-128">Managing Enterprise Voice for users in Lync Server 2013</span></span>](lync-server-2013-managing-enterprise-voice-for-users.md)

  - [<span data-ttu-id="e1126-129">在 Lync Server 2013 中修改使用者帳戶屬性</span><span class="sxs-lookup"><span data-stu-id="e1126-129">Modifying user account properties in Lync Server 2013</span></span>](lync-server-2013-modifying-user-account-properties.md)

  - [<span data-ttu-id="e1126-130">在 Lync Server 2013 中管理外部存取原則</span><span class="sxs-lookup"><span data-stu-id="e1126-130">Manage external access policy in Lync Server 2013</span></span>](lync-server-2013-manage-external-access-policy-for-your-organization.md)

  - [<span data-ttu-id="e1126-131">在 Lync Server 2013 中指派每一使用者原則</span><span class="sxs-lookup"><span data-stu-id="e1126-131">Assigning per-user policies in Lync Server 2013</span></span>](lync-server-2013-assigning-per-user-policies.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e1126-132">另請參閱</span><span class="sxs-lookup"><span data-stu-id="e1126-132">See Also</span></span>


[<span data-ttu-id="e1126-133">Lync Server 2013 中的使用者管理 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="e1126-133">User management cmdlets in Lync Server 2013</span></span>](lync-server-2013-user-management-cmdlets.md)  


[<span data-ttu-id="e1126-134">在 Lync Server 2013 中管理使用者</span><span class="sxs-lookup"><span data-stu-id="e1126-134">Managing users in Lync Server 2013</span></span>](lync-server-2013-managing-users-in-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

