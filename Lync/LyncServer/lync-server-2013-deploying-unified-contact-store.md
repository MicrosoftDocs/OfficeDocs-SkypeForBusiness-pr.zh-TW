---
title: Lync Server 2013：部署整合連絡人存放區
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying unified contact store
ms:assetid: 68959d58-ac8a-45de-afcd-b9de2c36799c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204963(v=OCS.15)
ms:contentKeyID: 48184373
ms.date: 06/06/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 94f4c52eb3adda31f32de410f139154788fa37e9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975993"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-unified-contact-store-in-lync-server-2013"></a><span data-ttu-id="dfbba-102">在 Lync Server 2013 中部署整合連絡人存放區</span><span class="sxs-lookup"><span data-stu-id="dfbba-102">Deploying unified contact store in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dfbba-103">_**主題上次修改日期：** 2016-06-06_</span><span class="sxs-lookup"><span data-stu-id="dfbba-103">_**Topic Last Modified:** 2016-06-06_</span></span>

<span data-ttu-id="dfbba-104">在 Lync Server 2013 中啟用整合連絡人存放區，不需要任何拓撲設定。</span><span class="sxs-lookup"><span data-stu-id="dfbba-104">Enabling unified contact store in Lync Server 2013 does not require any topology settings.</span></span> <span data-ttu-id="dfbba-105">為使用者啟用整合連絡人存放區需要下列專案：</span><span class="sxs-lookup"><span data-stu-id="dfbba-105">Enabling unified contact store for users requires the following:</span></span>

  - <span data-ttu-id="dfbba-106">已啟用整合連絡人存放區原則（預設為啟用）。</span><span class="sxs-lookup"><span data-stu-id="dfbba-106">Unified contact store policy is enabled (default is enabled).</span></span>

  - <span data-ttu-id="dfbba-107">使用者至少以 Lync 2013 登入一次。</span><span class="sxs-lookup"><span data-stu-id="dfbba-107">Users log in with Lync 2013 at least once.</span></span>

<span data-ttu-id="dfbba-108">在使用者的連絡人已完成遷移之後，當使用者以 Lync 2013 登入時，該使用者可以從 Lync 2013、Outlook 2013 或 Outlook Web Access 存取及管理其 Lync 連絡人。</span><span class="sxs-lookup"><span data-stu-id="dfbba-108">After a user’s contacts have been migrated, which happens automatically when a user logs in with Lync 2013, the user can access and manage their Lync contacts from Lync 2013, Outlook 2013, or Outlook Web Access.</span></span> <span data-ttu-id="dfbba-109">使用者不需要登入 Lync 就能從 Outlook 或 Outlook Web Access 管理他們的連絡人。</span><span class="sxs-lookup"><span data-stu-id="dfbba-109">The user does not have to be logged in to Lync to manage their contacts from Outlook or Outlook Web Access.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="dfbba-110">如果使用者在遷移之後從 Lync 2010 登入，就可以使用 [連絡人] 和 [群組]，但使用者無法管理（也就是新增、刪除、移動、標記、將或修改）這些連絡人。</span><span class="sxs-lookup"><span data-stu-id="dfbba-110">If a user logs in from Lync 2010 after migration, contacts and groups are available and up-to-date, but the user cannot manage (that is, add, delete, move, tag, untag, or modify) those contacts.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="dfbba-111">本節內容</span><span class="sxs-lookup"><span data-stu-id="dfbba-111">In This Section</span></span>

  - [<span data-ttu-id="dfbba-112">在 Lync Server 2013 中為使用者啟用整合連絡人存放區</span><span class="sxs-lookup"><span data-stu-id="dfbba-112">Enable users for unified contact store in Lync Server 2013</span></span>](lync-server-2013-enable-users-for-unified-contact-store.md)

  - [<span data-ttu-id="dfbba-113">在 Lync Server 2013 中將使用者移轉到整合的連絡人存放區</span><span class="sxs-lookup"><span data-stu-id="dfbba-113">Migrate users to unified contact store in Lync Server 2013</span></span>](lync-server-2013-migrate-users-to-unified-contact-store.md)

  - [<span data-ttu-id="dfbba-114">在 Lync Server 2013 中復原已移轉的使用者</span><span class="sxs-lookup"><span data-stu-id="dfbba-114">Roll back migrated users in Lync Server 2013</span></span>](lync-server-2013-roll-back-migrated-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

