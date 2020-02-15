---
title: Lync Server 2013： 準備樹系
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
ms.openlocfilehash: ec335e95264c4588b81ea5cae8473e540e9af5a0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043975"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-the-forest-for-lync-server-2013"></a><span data-ttu-id="aeb65-102">準備樹系的 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aeb65-102">Preparing the forest for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aeb65-103">_**上次修改主題：** 2013年-02-21_</span><span class="sxs-lookup"><span data-stu-id="aeb65-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="aeb65-104">樹系準備建立 Active Directory 全域設定和物件與 Lync Server 2013 中，所使用的 Active Directory 萬用群組，並授與 Active Directory 物件的適當存取權限。</span><span class="sxs-lookup"><span data-stu-id="aeb65-104">Forest preparation creates Active Directory global settings and objects and Active Directory universal groups for use by Lync Server 2013, and grants suitable access permissions on the Active Directory objects.</span></span> <span data-ttu-id="aeb65-105">萬用群組與全域設定和樹系準備所建立的物件的描述，請參閱[Lync Server 2013 中的樹系準備所進行的變更](lync-server-2013-changes-made-by-forest-preparation.md)。</span><span class="sxs-lookup"><span data-stu-id="aeb65-105">For a description of the universal groups and the global settings and objects created by forest preparation, see [Changes made by forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md).</span></span>

<span data-ttu-id="aeb65-106">樹系準備也會建立包含屬性設定，並顯示規範 Lync Server 2013 中，所使用的物件，並將其儲存在 [Configuration] 容器。</span><span class="sxs-lookup"><span data-stu-id="aeb65-106">Forest preparation also creates objects that contain property sets and display specifiers that are used by Lync Server 2013, and stores them in the Configuration container.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="aeb65-107">請確定該結構描述準備變更複寫到所有網域控制站執行樹系準備程序之前。</span><span class="sxs-lookup"><span data-stu-id="aeb65-107">Make sure that schema preparation changes have replicated to all domain controllers before performing the forest preparation procedure.</span></span> <span data-ttu-id="aeb65-108">如果複寫未完成，則會發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="aeb65-108">If replication is not completed, an error occurs.</span></span>



</div>

<span data-ttu-id="aeb65-109">如果您執行新的 Lync Server 部署，您必須在 [Configuration] 容器中儲存全域設定。</span><span class="sxs-lookup"><span data-stu-id="aeb65-109">If you are performing a new Lync Server deployment, you must store global settings in the Configuration container.</span></span> <span data-ttu-id="aeb65-110">如果您從較早版本升級，而且您仍然在系統容器中儲存全域設定，您可以繼續使用系統容器。</span><span class="sxs-lookup"><span data-stu-id="aeb65-110">If you are upgrading from an earlier version and you still store global settings in the System container, you can continue to use the System container.</span></span>

<span data-ttu-id="aeb65-111">您必須是樹系根網域 Enterprise Admins 或 Domain Admins 群組的成員，才能執行這項程序。</span><span class="sxs-lookup"><span data-stu-id="aeb65-111">You must be a member of the Enterprise Admins or Domain Admins group for the forest root domain to perform this procedure.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="aeb65-112">本章節內容</span><span class="sxs-lookup"><span data-stu-id="aeb65-112">In This Section</span></span>

  - [<span data-ttu-id="aeb65-113">執行 Lync Server 2013 的樹系準備</span><span class="sxs-lookup"><span data-stu-id="aeb65-113">Running forest preparation for Lync Server 2013</span></span>](lync-server-2013-running-forest-preparation.md)

  - [<span data-ttu-id="aeb65-114">使用 cmdlet 反向樹系準備 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aeb65-114">Using cmdlets to reverse forest preparation for Lync Server 2013</span></span>](lync-server-2013-using-cmdlets-to-reverse-forest-preparation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

