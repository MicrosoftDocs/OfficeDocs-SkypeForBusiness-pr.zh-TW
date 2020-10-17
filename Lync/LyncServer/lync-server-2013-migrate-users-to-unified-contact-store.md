---
title: Lync Server 2013：將使用者遷移至整合連絡人存放區
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
ms.openlocfilehash: 3ab00e89c41b075e47d7764ce1c9c4cd3c471b8c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513630"
---
# <a name="migrate-users-to-unified-contact-store-in-lync-server-2013"></a><span data-ttu-id="5ed63-102">在 Lync Server 2013 中將使用者遷移至整合連絡人存放區</span><span class="sxs-lookup"><span data-stu-id="5ed63-102">Migrate users to unified contact store in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5ed63-103">_**主題上次修改日期：** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="5ed63-103">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="5ed63-104">當使用者執行下列動作時，使用者的連絡人會自動遷移至 Exchange 2013 伺服器：</span><span class="sxs-lookup"><span data-stu-id="5ed63-104">A user's contacts are automatically migrated to the Exchange 2013 server when the user:</span></span>

  - <span data-ttu-id="5ed63-105">已指派了 UcsAllowed 設為 True 的使用者服務原則。</span><span class="sxs-lookup"><span data-stu-id="5ed63-105">Has been assigned a user services policy that has UcsAllowed set to True.</span></span>

  - <span data-ttu-id="5ed63-106">已布建與 Exchange 2013 信箱，且至少已登入至信箱一次。</span><span class="sxs-lookup"><span data-stu-id="5ed63-106">Has been provisioned with an Exchange 2013 mailbox and has signed into the mailbox at least once.</span></span>

  - <span data-ttu-id="5ed63-107">使用 Lync 2013 豐富型用戶端登入。</span><span class="sxs-lookup"><span data-stu-id="5ed63-107">Logs in by using a Lync 2013 rich client.</span></span>

<span data-ttu-id="5ed63-108">如果使用者登入 Lync 2010 或更早版本的用戶端，或使用者未連線到 Exchange 2013 伺服器，則會略過使用者服務原則，且使用者的連絡人仍保留在 Lync Server 中。</span><span class="sxs-lookup"><span data-stu-id="5ed63-108">If the user logs in with a Lync 2010 or earlier client, or if the user is not connected to an Exchange 2013 server, the user services policy is ignored and the user's contacts remain in Lync Server.</span></span>

<span data-ttu-id="5ed63-109">您可使用下列方法之一，來判斷使用者的連絡人是否已移轉：</span><span class="sxs-lookup"><span data-stu-id="5ed63-109">You can determine whether a user's contacts have been migrated by using either of the following methods:</span></span>

  - <span data-ttu-id="5ed63-110">檢查用戶端電腦上的下列登錄機碼：</span><span class="sxs-lookup"><span data-stu-id="5ed63-110">Check the following registry key on the client computer:</span></span>
    
    <span data-ttu-id="5ed63-111">HKEY \_ 目前的 \_ 使用者 \\ 軟體 \\ Microsoft \\ Office \\ 15.0 \\ Lync \\ \<SIP URL\> \\ UCS</span><span class="sxs-lookup"><span data-stu-id="5ed63-111">HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync\\\<SIP URL\>\\UCS</span></span>
    
    <span data-ttu-id="5ed63-112">如果使用者的連絡人儲存在 Exchange 2013 中，則此機碼會包含值為2165的 InUCSMode。</span><span class="sxs-lookup"><span data-stu-id="5ed63-112">If the user's contacts are stored in Exchange 2013, this key contains a value of InUCSMode with a value of 2165.</span></span>

  - <span data-ttu-id="5ed63-113">執行 **Test-CsUnifiedContactStore** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="5ed63-113">Run the **Test-CsUnifiedContactStore** cmdlet.</span></span> <span data-ttu-id="5ed63-114">在 [Lync Server 管理命令介面] 命令列上輸入：</span><span class="sxs-lookup"><span data-stu-id="5ed63-114">At the Lync Server Management Shell command line, type:</span></span>
    
        Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
    
    <span data-ttu-id="5ed63-115">若 **Test-CsUnifiedContactStore** 成功，使用者的連絡人就已移轉至整合連絡人存放區。</span><span class="sxs-lookup"><span data-stu-id="5ed63-115">If **Test-CsUnifiedContactStore** succeeds, the user's contacts were migrated to unified contact store.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

