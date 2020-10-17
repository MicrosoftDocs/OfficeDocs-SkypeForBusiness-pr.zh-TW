---
title: Lync Server 2013：設定使用者的封存原則
description: Lync Server 2013：設定使用者的封存原則。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up Archiving policies for users
ms:assetid: 1bbb45df-0590-4c66-9d65-d25526f57790
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204722(v=OCS.15)
ms:contentKeyID: 48183549
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c18a15c1a0611f49a6fd9a4983f3ce87104332e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559519"
---
# <a name="setting-up-archiving-policies-for-users-in-lync-server-2013"></a><span data-ttu-id="feddf-103">在 Lync Server 2013 中設定使用者的封存原則</span><span class="sxs-lookup"><span data-stu-id="feddf-103">Setting up Archiving policies for users in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="feddf-104">_**主題上次修改日期：** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="feddf-104">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="feddf-105">您可以為使用者建立和設定封存原則，然後將原則套用至特定的使用者或使用者群組，來啟用或停用特定使用者的封存。</span><span class="sxs-lookup"><span data-stu-id="feddf-105">You can enable or disable Archiving for specific users by creating and configuring an Archiving policy for users, and then applying the policy to specific users or user groups.</span></span> <span data-ttu-id="feddf-106">使用者原則會覆寫任何全域原則或網站原則。</span><span class="sxs-lookup"><span data-stu-id="feddf-106">User policies override any global policy or site policies.</span></span> <span data-ttu-id="feddf-107">封存原則只有在您未使用 Microsoft Exchange 整合時才會套用，否則，如果您使用 Microsoft Exchange 整合，但有部分使用者未位於 Exchange 2013，且其信箱置於 In-Place 保留狀態，則僅適用。</span><span class="sxs-lookup"><span data-stu-id="feddf-107">Archiving policies only apply if you do not use Microsoft Exchange integration or, if you do use Microsoft Exchange integration, but have some users who are not homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span>

<span data-ttu-id="feddf-108">如需有關封存原則如何運作（包括全域、網站及使用者原則的階層）的詳細資訊，請參閱 [Lync Server 2013](lync-server-2013-how-archiving-works.md) 規劃檔、部署檔或作業檔中的封存運作方式。</span><span class="sxs-lookup"><span data-stu-id="feddf-108">For details about how Archiving policies work, including the hierarchy for global, site, and user policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="feddf-109">如果您為部署啟用 Microsoft Exchange 整合，Exchange In-Place 保留原則會控制是否為位於 Exchange 2013 上的使用者啟用封存，並將其信箱置於 In-Place 保留狀態。</span><span class="sxs-lookup"><span data-stu-id="feddf-109">If you enable Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="feddf-110">如需詳細資訊，請參閱部署檔中的 <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">使用 Exchange Server 整合時，在 Lync Server 2013 中設定</A> 封存的原則。</span><span class="sxs-lookup"><span data-stu-id="feddf-110">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="feddf-111">您應該先在封存設定中指定所有適當的選項，才能在封存原則中封存內部或外部通訊。</span><span class="sxs-lookup"><span data-stu-id="feddf-111">You should specify all appropriate options in the Archiving configurations before enabling Archiving of internal or external communications in the Archiving policies.</span></span> <span data-ttu-id="feddf-112">如需詳細資訊，請參閱部署檔中的在 <A href="lync-server-2013-configuring-archiving-options.md">Lync Server 2013</A> 中設定封存選項。</span><span class="sxs-lookup"><span data-stu-id="feddf-112">For details, see <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving options in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="feddf-113">本章節內容</span><span class="sxs-lookup"><span data-stu-id="feddf-113">In This Section</span></span>

  - [<span data-ttu-id="feddf-114">在 Lync Server 2013 中設定封存的使用者原則</span><span class="sxs-lookup"><span data-stu-id="feddf-114">Setting up user policies for Archiving in Lync Server 2013</span></span>](lync-server-2013-setting-up-user-policies-for-archiving-in-lync-server.md)

  - [<span data-ttu-id="feddf-115">使用 Exchange Server 整合時設定在 Lync Server 2013 中封存的原則</span><span class="sxs-lookup"><span data-stu-id="feddf-115">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</span></span>](lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

