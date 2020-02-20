---
title: Lync Server 2013： 部署整合連絡人存放區
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying unified contact store
ms:assetid: 68959d58-ac8a-45de-afcd-b9de2c36799c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204963(v=OCS.15)
ms:contentKeyID: 48184373
ms.date: 06/06/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2c88b5264883d05eff717bb3b8d99f63a5640a2a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153935"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-unified-contact-store-in-lync-server-2013"></a><span data-ttu-id="68a52-102">部署 Lync Server 2013 中的整合連絡人存放區</span><span class="sxs-lookup"><span data-stu-id="68a52-102">Deploying unified contact store in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="68a52-103">_**主題上次修改日期：** 2016年-06-06_</span><span class="sxs-lookup"><span data-stu-id="68a52-103">_**Topic Last Modified:** 2016-06-06_</span></span>

<span data-ttu-id="68a52-104">啟用 Lync Server 2013 中的整合連絡人存放區不需要任何拓撲設定。</span><span class="sxs-lookup"><span data-stu-id="68a52-104">Enabling unified contact store in Lync Server 2013 does not require any topology settings.</span></span> <span data-ttu-id="68a52-105">啟用使用者的整合連絡人存放區時，需要執行下列項目：</span><span class="sxs-lookup"><span data-stu-id="68a52-105">Enabling unified contact store for users requires the following:</span></span>

  - <span data-ttu-id="68a52-106">啟用整合連絡人存放區原則 (預設為啟用)。</span><span class="sxs-lookup"><span data-stu-id="68a52-106">Unified contact store policy is enabled (default is enabled).</span></span>

  - <span data-ttu-id="68a52-107">使用者登入與 Lync 2013 至少一次。</span><span class="sxs-lookup"><span data-stu-id="68a52-107">Users log in with Lync 2013 at least once.</span></span>

<span data-ttu-id="68a52-108">使用者的連絡人已經移轉，當使用者登入 Lync 2013 自動執行之後，使用者可以存取，並從 Lync 2013、 Outlook 2013 或 Outlook Web Access 管理其 Lync 連絡人。</span><span class="sxs-lookup"><span data-stu-id="68a52-108">After a user’s contacts have been migrated, which happens automatically when a user logs in with Lync 2013, the user can access and manage their Lync contacts from Lync 2013, Outlook 2013, or Outlook Web Access.</span></span> <span data-ttu-id="68a52-109">使用者沒有從 Outlook 或 Outlook Web Access 管理其連絡人的 Lync 登入。</span><span class="sxs-lookup"><span data-stu-id="68a52-109">The user does not have to be logged in to Lync to manage their contacts from Outlook or Outlook Web Access.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="68a52-110">如果使用者從登入 Lync 2010 移轉後，連絡人和群組皆可用且最新狀態，但使用者無法管理 （亦即新增、 刪除、 移動、 標記、 取消標記或修改） 那些連絡人。</span><span class="sxs-lookup"><span data-stu-id="68a52-110">If a user logs in from Lync 2010 after migration, contacts and groups are available and up-to-date, but the user cannot manage (that is, add, delete, move, tag, untag, or modify) those contacts.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="68a52-111">本章節內容</span><span class="sxs-lookup"><span data-stu-id="68a52-111">In This Section</span></span>

  - [<span data-ttu-id="68a52-112">啟用使用者的 Lync Server 2013 中整合連絡人存放區</span><span class="sxs-lookup"><span data-stu-id="68a52-112">Enable users for unified contact store in Lync Server 2013</span></span>](lync-server-2013-enable-users-for-unified-contact-store.md)

  - [<span data-ttu-id="68a52-113">將使用者移轉至 Lync Server 2013 中整合連絡人存放區</span><span class="sxs-lookup"><span data-stu-id="68a52-113">Migrate users to unified contact store in Lync Server 2013</span></span>](lync-server-2013-migrate-users-to-unified-contact-store.md)

  - [<span data-ttu-id="68a52-114">回復移轉 Lync Server 2013 中的使用者</span><span class="sxs-lookup"><span data-stu-id="68a52-114">Roll back migrated users in Lync Server 2013</span></span>](lync-server-2013-roll-back-migrated-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

