---
title: Lync Server 2013：部署整合連絡人存放區
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
ms.openlocfilehash: a94d19026d2df00caf8079914d8b93bd70a87f6d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522850"
---
# <a name="deploying-unified-contact-store-in-lync-server-2013"></a><span data-ttu-id="6b537-102">在 Lync Server 2013 中部署整合連絡人存放區</span><span class="sxs-lookup"><span data-stu-id="6b537-102">Deploying unified contact store in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6b537-103">_**主題上次修改日期：** 2016-06-06_</span><span class="sxs-lookup"><span data-stu-id="6b537-103">_**Topic Last Modified:** 2016-06-06_</span></span>

<span data-ttu-id="6b537-104">在 Lync Server 2013 中啟用整合連絡人存放區時，不需要任何拓撲設定。</span><span class="sxs-lookup"><span data-stu-id="6b537-104">Enabling unified contact store in Lync Server 2013 does not require any topology settings.</span></span> <span data-ttu-id="6b537-105">啟用使用者的整合連絡人存放區時，需要執行下列項目：</span><span class="sxs-lookup"><span data-stu-id="6b537-105">Enabling unified contact store for users requires the following:</span></span>

  - <span data-ttu-id="6b537-106">啟用整合連絡人存放區原則 (預設為啟用)。</span><span class="sxs-lookup"><span data-stu-id="6b537-106">Unified contact store policy is enabled (default is enabled).</span></span>

  - <span data-ttu-id="6b537-107">使用者使用 Lync 2013 至少登入一次。</span><span class="sxs-lookup"><span data-stu-id="6b537-107">Users log in with Lync 2013 at least once.</span></span>

<span data-ttu-id="6b537-108">在使用者的連絡人已遷移之後，當使用者登入 Lync 2013 時，使用者就可以從 Lync 2013、Outlook 2013 或 Outlook Web Access 存取及管理 Lync 連絡人。</span><span class="sxs-lookup"><span data-stu-id="6b537-108">After a user’s contacts have been migrated, which happens automatically when a user logs in with Lync 2013, the user can access and manage their Lync contacts from Lync 2013, Outlook 2013, or Outlook Web Access.</span></span> <span data-ttu-id="6b537-109">使用者不必登入 Lync 以從 Outlook 或 Outlook Web Access 管理其連絡人。</span><span class="sxs-lookup"><span data-stu-id="6b537-109">The user does not have to be logged in to Lync to manage their contacts from Outlook or Outlook Web Access.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="6b537-110">如果使用者在遷移之後從 Lync 2010 登入，則連絡人和群組可供使用且是最新的，但是使用者無法管理 (，例如新增、刪除、移動、標記、untag 或修改) 那些連絡人。</span><span class="sxs-lookup"><span data-stu-id="6b537-110">If a user logs in from Lync 2010 after migration, contacts and groups are available and up-to-date, but the user cannot manage (that is, add, delete, move, tag, untag, or modify) those contacts.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="6b537-111">本章節內容</span><span class="sxs-lookup"><span data-stu-id="6b537-111">In This Section</span></span>

  - [<span data-ttu-id="6b537-112">在 Lync Server 2013 中啟用整合連絡人存放區的使用者</span><span class="sxs-lookup"><span data-stu-id="6b537-112">Enable users for unified contact store in Lync Server 2013</span></span>](lync-server-2013-enable-users-for-unified-contact-store.md)

  - [<span data-ttu-id="6b537-113">在 Lync Server 2013 中將使用者遷移至整合連絡人存放區</span><span class="sxs-lookup"><span data-stu-id="6b537-113">Migrate users to unified contact store in Lync Server 2013</span></span>](lync-server-2013-migrate-users-to-unified-contact-store.md)

  - [<span data-ttu-id="6b537-114">在 Lync Server 2013 中復原已遷移的使用者</span><span class="sxs-lookup"><span data-stu-id="6b537-114">Roll back migrated users in Lync Server 2013</span></span>](lync-server-2013-roll-back-migrated-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

