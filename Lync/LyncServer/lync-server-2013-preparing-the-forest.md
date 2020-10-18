---
title: Lync Server 2013：準備樹系
description: Lync Server 2013：準備樹系。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing the forest
ms:assetid: 3d188fcb-c64e-46cf-a3a7-9e3ebefed7fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425898(v=OCS.15)
ms:contentKeyID: 48183926
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 275d861ebfe7e0350e7baf120b6e6f2bae6a26ad
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579999"
---
# <a name="preparing-the-forest-for-lync-server-2013"></a><span data-ttu-id="63298-103">準備 Lync Server 2013 的樹系</span><span class="sxs-lookup"><span data-stu-id="63298-103">Preparing the forest for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="63298-104">_**主題上次修改日期：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="63298-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="63298-105">樹系準備會建立 Active Directory 全域設定和物件以及使用的 active directory 通用群組，以供 Lync Server 2013 使用，並授與 Active Directory 物件的適當存取權限。</span><span class="sxs-lookup"><span data-stu-id="63298-105">Forest preparation creates Active Directory global settings and objects and Active Directory universal groups for use by Lync Server 2013, and grants suitable access permissions on the Active Directory objects.</span></span> <span data-ttu-id="63298-106">如需通用群組和樹系準備所建立之全域設定和物件的描述，請參閱 [Lync Server 2013 中的樹系準備所做的變更](lync-server-2013-changes-made-by-forest-preparation.md)。</span><span class="sxs-lookup"><span data-stu-id="63298-106">For a description of the universal groups and the global settings and objects created by forest preparation, see [Changes made by forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md).</span></span>

<span data-ttu-id="63298-107">樹系準備也會建立包含 Lync Server 2013 所使用之屬性集及顯示說明符的物件，並將它們儲存在設定容器中。</span><span class="sxs-lookup"><span data-stu-id="63298-107">Forest preparation also creates objects that contain property sets and display specifiers that are used by Lync Server 2013, and stores them in the Configuration container.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="63298-108">在執行樹系準備程式之前，請確定架構準備變更已複寫到所有網域控制站。</span><span class="sxs-lookup"><span data-stu-id="63298-108">Make sure that schema preparation changes have replicated to all domain controllers before performing the forest preparation procedure.</span></span> <span data-ttu-id="63298-109">如果複寫未完成，則會發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="63298-109">If replication is not completed, an error occurs.</span></span>



</div>

<span data-ttu-id="63298-110">如果您正在執行新的 Lync Server 部署，則必須將全域設定儲存在設定容器中。</span><span class="sxs-lookup"><span data-stu-id="63298-110">If you are performing a new Lync Server deployment, you must store global settings in the Configuration container.</span></span> <span data-ttu-id="63298-111">如果您是從舊版升級，但仍將全域設定儲存在系統容器中，您可以繼續使用系統容器。</span><span class="sxs-lookup"><span data-stu-id="63298-111">If you are upgrading from an earlier version and you still store global settings in the System container, you can continue to use the System container.</span></span>

<span data-ttu-id="63298-112">您必須是樹系根網域 Enterprise Admins 或 Domain Admins 群組的成員，才能執行這項程序。</span><span class="sxs-lookup"><span data-stu-id="63298-112">You must be a member of the Enterprise Admins or Domain Admins group for the forest root domain to perform this procedure.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="63298-113">本章節內容</span><span class="sxs-lookup"><span data-stu-id="63298-113">In This Section</span></span>

  - [<span data-ttu-id="63298-114">對 Lync Server 2013 執行樹系準備</span><span class="sxs-lookup"><span data-stu-id="63298-114">Running forest preparation for Lync Server 2013</span></span>](lync-server-2013-running-forest-preparation.md)

  - [<span data-ttu-id="63298-115">使用 Cmdlet 進行 Lync Server 2013 的反向樹系準備</span><span class="sxs-lookup"><span data-stu-id="63298-115">Using cmdlets to reverse forest preparation for Lync Server 2013</span></span>](lync-server-2013-using-cmdlets-to-reverse-forest-preparation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

