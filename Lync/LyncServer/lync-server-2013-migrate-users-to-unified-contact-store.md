---
title: Lync Server 2013： 將使用者移轉至整合連絡人存放區
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migrate users to unified contact store
ms:assetid: 215a8ec1-d63e-4fdf-b73d-75aeb9dddb43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204737(v=OCS.15)
ms:contentKeyID: 48183600
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1a4bd640d4f2e13ff6ecec129bd86602a197a451
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42217499"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-users-to-unified-contact-store-in-lync-server-2013"></a><span data-ttu-id="1890f-102">將使用者移轉至 Lync Server 2013 中整合連絡人存放區</span><span class="sxs-lookup"><span data-stu-id="1890f-102">Migrate users to unified contact store in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1890f-103">_**主題上次修改日期：** 2012 年 10 月 15_</span><span class="sxs-lookup"><span data-stu-id="1890f-103">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="1890f-104">使用者的連絡人就會自動移轉至 Exchange 2013 伺服器時使用者：</span><span class="sxs-lookup"><span data-stu-id="1890f-104">A user's contacts are automatically migrated to the Exchange 2013 server when the user:</span></span>

  - <span data-ttu-id="1890f-105">已指派了 UcsAllowed 設為 True 的使用者服務原則。</span><span class="sxs-lookup"><span data-stu-id="1890f-105">Has been assigned a user services policy that has UcsAllowed set to True.</span></span>

  - <span data-ttu-id="1890f-106">已佈建與 Exchange 2013 信箱，並已至少一次登入信箱。</span><span class="sxs-lookup"><span data-stu-id="1890f-106">Has been provisioned with an Exchange 2013 mailbox and has signed into the mailbox at least once.</span></span>

  - <span data-ttu-id="1890f-107">使用 Lync 2013 豐富型用戶端中記錄。</span><span class="sxs-lookup"><span data-stu-id="1890f-107">Logs in by using a Lync 2013 rich client.</span></span>

<span data-ttu-id="1890f-108">如果使用者登入 Lync 2010 或更早的用戶端，或者如果使用者未連線至 Exchange 2013 伺服器，則會忽略使用者服務原則及使用者的連絡人會保留在 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="1890f-108">If the user logs in with a Lync 2010 or earlier client, or if the user is not connected to an Exchange 2013 server, the user services policy is ignored and the user's contacts remain in Lync Server.</span></span>

<span data-ttu-id="1890f-109">您可使用下列方法之一，來判斷使用者的連絡人是否已移轉：</span><span class="sxs-lookup"><span data-stu-id="1890f-109">You can determine whether a user's contacts have been migrated by using either of the following methods:</span></span>

  - <span data-ttu-id="1890f-110">檢查用戶端電腦上的下列登錄機碼：</span><span class="sxs-lookup"><span data-stu-id="1890f-110">Check the following registry key on the client computer:</span></span>
    
    <span data-ttu-id="1890f-111">HKEY\_目前\_使用者\\軟體\\Microsoft\\Office\\15.0\\Lync\\\<SIP URL\>\\UCS</span><span class="sxs-lookup"><span data-stu-id="1890f-111">HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync\\\<SIP URL\>\\UCS</span></span>
    
    <span data-ttu-id="1890f-112">如果使用者的連絡人會儲存在 Exchange 2013 中，此機碼會包含 InUCSMode 值為 2165年的值。</span><span class="sxs-lookup"><span data-stu-id="1890f-112">If the user's contacts are stored in Exchange 2013, this key contains a value of InUCSMode with a value of 2165.</span></span>

  - <span data-ttu-id="1890f-113">執行 **Test-CsUnifiedContactStore** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1890f-113">Run the **Test-CsUnifiedContactStore** cmdlet.</span></span> <span data-ttu-id="1890f-114">在 Lync Server 管理命令介面命令列中，輸入：</span><span class="sxs-lookup"><span data-stu-id="1890f-114">At the Lync Server Management Shell command line, type:</span></span>
    
        Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
    
    <span data-ttu-id="1890f-115">若 **Test-CsUnifiedContactStore** 成功，使用者的連絡人就已移轉至整合連絡人存放區。</span><span class="sxs-lookup"><span data-stu-id="1890f-115">If **Test-CsUnifiedContactStore** succeeds, the user's contacts were migrated to unified contact store.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

