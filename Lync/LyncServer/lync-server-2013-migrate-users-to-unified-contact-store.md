---
title: Lync Server 2013：將使用者移轉到整合的連絡人存放區
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Migrate users to unified contact store
ms:assetid: 215a8ec1-d63e-4fdf-b73d-75aeb9dddb43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204737(v=OCS.15)
ms:contentKeyID: 48183600
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fd0ec64192f1aa83eb9c076976c20a9e87ab9115
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982652"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-users-to-unified-contact-store-in-lync-server-2013"></a><span data-ttu-id="3f3a5-102">在 Lync Server 2013 中將使用者移轉到整合的連絡人存放區</span><span class="sxs-lookup"><span data-stu-id="3f3a5-102">Migrate users to unified contact store in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3f3a5-103">_**主題上次修改日期：** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="3f3a5-103">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="3f3a5-104">當使用者在下列情況下，使用者的連絡人會自動轉移至 Exchange 2013 伺服器：</span><span class="sxs-lookup"><span data-stu-id="3f3a5-104">A user's contacts are automatically migrated to the Exchange 2013 server when the user:</span></span>

  - <span data-ttu-id="3f3a5-105">已指派 UcsAllowed 設定為 True 的使用者服務原則。</span><span class="sxs-lookup"><span data-stu-id="3f3a5-105">Has been assigned a user services policy that has UcsAllowed set to True.</span></span>

  - <span data-ttu-id="3f3a5-106">已使用 Exchange 2013 信箱進行預配，且至少已在信箱中登入一次。</span><span class="sxs-lookup"><span data-stu-id="3f3a5-106">Has been provisioned with an Exchange 2013 mailbox and has signed into the mailbox at least once.</span></span>

  - <span data-ttu-id="3f3a5-107">使用 Lync 2013 胖用戶端登入。</span><span class="sxs-lookup"><span data-stu-id="3f3a5-107">Logs in by using a Lync 2013 rich client.</span></span>

<span data-ttu-id="3f3a5-108">如果使用者使用 Lync 2010 或較舊版本的用戶端登入，或者如果使用者未連線到 Exchange 2013 伺服器，則系統會忽略使用者服務原則，且使用者的連絡人會保留在 Lync Server 中。</span><span class="sxs-lookup"><span data-stu-id="3f3a5-108">If the user logs in with a Lync 2010 or earlier client, or if the user is not connected to an Exchange 2013 server, the user services policy is ignored and the user's contacts remain in Lync Server.</span></span>

<span data-ttu-id="3f3a5-109">您可以使用下列其中一種方法來判斷使用者的連絡人是否已被遷移：</span><span class="sxs-lookup"><span data-stu-id="3f3a5-109">You can determine whether a user's contacts have been migrated by using either of the following methods:</span></span>

  - <span data-ttu-id="3f3a5-110">檢查用戶端電腦上的下列登錄機碼：</span><span class="sxs-lookup"><span data-stu-id="3f3a5-110">Check the following registry key on the client computer:</span></span>
    
    <span data-ttu-id="3f3a5-111">HKEY\_目前\_的\\使用者\\軟體\\Microsoft\\Office\\15.0\\\<Lync SIP\>\\URL UCS</span><span class="sxs-lookup"><span data-stu-id="3f3a5-111">HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync\\\<SIP URL\>\\UCS</span></span>
    
    <span data-ttu-id="3f3a5-112">如果使用者的連絡人儲存在 Exchange 2013 中，此索引鍵會包含值為2165的 InUCSMode 值。</span><span class="sxs-lookup"><span data-stu-id="3f3a5-112">If the user's contacts are stored in Exchange 2013, this key contains a value of InUCSMode with a value of 2165.</span></span>

  - <span data-ttu-id="3f3a5-113">執行**Test CsUnifiedContactStore** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="3f3a5-113">Run the **Test-CsUnifiedContactStore** cmdlet.</span></span> <span data-ttu-id="3f3a5-114">在 Lync Server Management Shell 命令列上，輸入：</span><span class="sxs-lookup"><span data-stu-id="3f3a5-114">At the Lync Server Management Shell command line, type:</span></span>
    
        Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
    
    <span data-ttu-id="3f3a5-115">如果**CsUnifiedContactStore**成功，則使用者的連絡人已遷移至整合連絡人存放區。</span><span class="sxs-lookup"><span data-stu-id="3f3a5-115">If **Test-CsUnifiedContactStore** succeeds, the user's contacts were migrated to unified contact store.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

