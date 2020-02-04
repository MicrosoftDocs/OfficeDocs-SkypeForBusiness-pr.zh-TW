---
title: Lync Server 2013：準備樹系
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
ms.openlocfilehash: 8a485ba2a406fd762d70ba4e8ff621d2d6af3801
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747383"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-the-forest-for-lync-server-2013"></a><span data-ttu-id="84660-102">為 Lync Server 2013 準備樹系</span><span class="sxs-lookup"><span data-stu-id="84660-102">Preparing the forest for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="84660-103">_**主題上次修改日期：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="84660-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="84660-104">林準備：建立 Active Directory 全域設定和物件與 Active Directory 通用群組供 Lync Server 2013 使用，並在 Active Directory 物件上授予適當的存取權限。</span><span class="sxs-lookup"><span data-stu-id="84660-104">Forest preparation creates Active Directory global settings and objects and Active Directory universal groups for use by Lync Server 2013, and grants suitable access permissions on the Active Directory objects.</span></span> <span data-ttu-id="84660-105">如需通用群組以及由林準備所建立之全域設定及物件的描述，請參閱[Lync Server 2013 中的林準備所做的變更](lync-server-2013-changes-made-by-forest-preparation.md)。</span><span class="sxs-lookup"><span data-stu-id="84660-105">For a description of the universal groups and the global settings and objects created by forest preparation, see [Changes made by forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md).</span></span>

<span data-ttu-id="84660-106">林準備也會建立包含 Lync Server 2013 所使用之屬性集和顯示說明符的物件，並將它們儲存在配置容器中。</span><span class="sxs-lookup"><span data-stu-id="84660-106">Forest preparation also creates objects that contain property sets and display specifiers that are used by Lync Server 2013, and stores them in the Configuration container.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="84660-107">在執行目錄林準備程式前，請確定架構準備變更已複製到所有網網域控制站。</span><span class="sxs-lookup"><span data-stu-id="84660-107">Make sure that schema preparation changes have replicated to all domain controllers before performing the forest preparation procedure.</span></span> <span data-ttu-id="84660-108">如果無法完成複製，就會發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="84660-108">If replication is not completed, an error occurs.</span></span>



</div>

<span data-ttu-id="84660-109">如果您執行的是新的 Lync Server 部署，您必須將全域設定儲存在配置容器中。</span><span class="sxs-lookup"><span data-stu-id="84660-109">If you are performing a new Lync Server deployment, you must store global settings in the Configuration container.</span></span> <span data-ttu-id="84660-110">如果您是從較舊的版本升級，但仍將全域設定儲存在系統容器中，您可以繼續使用系統容器。</span><span class="sxs-lookup"><span data-stu-id="84660-110">If you are upgrading from an earlier version and you still store global settings in the System container, you can continue to use the System container.</span></span>

<span data-ttu-id="84660-111">您必須是林根網域之 [企業管理員] 或 [網域管理員] 群組的成員，才能執行此程式。</span><span class="sxs-lookup"><span data-stu-id="84660-111">You must be a member of the Enterprise Admins or Domain Admins group for the forest root domain to perform this procedure.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="84660-112">本節內容</span><span class="sxs-lookup"><span data-stu-id="84660-112">In This Section</span></span>

  - [<span data-ttu-id="84660-113">針對 Lync Server 2013 執行樹系準備</span><span class="sxs-lookup"><span data-stu-id="84660-113">Running forest preparation for Lync Server 2013</span></span>](lync-server-2013-running-forest-preparation.md)

  - [<span data-ttu-id="84660-114">使用 Cmdlet 進行 Lync Server 2013 的反向樹系準備</span><span class="sxs-lookup"><span data-stu-id="84660-114">Using cmdlets to reverse forest preparation for Lync Server 2013</span></span>](lync-server-2013-using-cmdlets-to-reverse-forest-preparation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

