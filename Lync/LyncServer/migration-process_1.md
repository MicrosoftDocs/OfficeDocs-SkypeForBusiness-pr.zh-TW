---
title: 移轉程序
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migration process
ms:assetid: b2bd9c76-2f4b-4d14-a5c4-157bbff75de0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205181(v=OCS.15)
ms:contentKeyID: 48185157
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1cc0620b2de14c56a6886a70cd7b977046828786
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148722"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migration-process"></a><span data-ttu-id="db572-102">移轉程序</span><span class="sxs-lookup"><span data-stu-id="db572-102">Migration process</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="db572-103">_**主題上次修改日期：** 2012年-09-24_</span><span class="sxs-lookup"><span data-stu-id="db572-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="db572-104">Lync Server 2013 的建議和支援的移轉程序是以並排移轉程序。</span><span class="sxs-lookup"><span data-stu-id="db572-104">The recommended and supported migration procedure for Lync Server 2013 is the side-by-side migration procedure.</span></span> <span data-ttu-id="db572-105">本主題說明為什麼您應該使用並排顯示移轉，同時還包括 [共存的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="db572-105">This topic describes why you should use side-by-side migration and also includes information about coexistence.</span></span>

<div>

## <a name="side-by-side-migration"></a><span data-ttu-id="db572-106">並排顯示移轉</span><span class="sxs-lookup"><span data-stu-id="db572-106">Side-by-Side Migration</span></span>

<span data-ttu-id="db572-107">幾乎在每種移轉時，您都應該使用並存移轉路徑。</span><span class="sxs-lookup"><span data-stu-id="db572-107">In nearly every migration, you should use the side-by-side migration path.</span></span> <span data-ttu-id="db572-108">在並排顯示遷移中，您部署 Lync Server 2013 與相對應的伺服器是執行 Office Communications Server 2007 R2，以及新的伺服器，然後將作業傳輸到新的伺服器。</span><span class="sxs-lookup"><span data-stu-id="db572-108">In a side-by-side migration, you deploy a new server with Lync Server 2013 alongside a corresponding server that is running Office Communications Server 2007 R2, and then you transfer operations to the new server.</span></span> <span data-ttu-id="db572-109">若要回復至 Office Communications Server 2007 R2 必要時，您必須僅回原始的伺服器移動作業。</span><span class="sxs-lookup"><span data-stu-id="db572-109">If it becomes necessary to roll back to Office Communications Server 2007 R2, you have only to shift operations back to the original servers.</span></span> <span data-ttu-id="db572-110">請注意在這樣的情況下，任何與升級用戶端排定的新會議皆無法運作，導致用戶端也必須降級。</span><span class="sxs-lookup"><span data-stu-id="db572-110">Be aware that in this situation any new meetings scheduled with upgraded clients will not work, and the clients would also need to be downgraded.</span></span>

</div>

<div>

## <a name="coexistence-testing"></a><span data-ttu-id="db572-111">共存測試</span><span class="sxs-lookup"><span data-stu-id="db572-111">Coexistence Testing</span></span>

<span data-ttu-id="db572-112">您已部署 Lync Server 2013 與 Office Communications Server 2007 R2 平行之後，拓撲代表共存測試 Lync Server 2013 和 Office Communications Server 2007 R2 的狀態。</span><span class="sxs-lookup"><span data-stu-id="db572-112">After you have deployed Lync Server 2013 in parallel with Office Communications Server 2007 R2, the topology represents a coexistence testing state of Lync Server 2013 and Office Communications Server 2007 R2.</span></span> <span data-ttu-id="db572-113">在此狀態下，務必以測試，並確定已啟動服務，可以管理每個網站，用戶端可以與彼此目前與舊版使用者。</span><span class="sxs-lookup"><span data-stu-id="db572-113">While in this state, it is important to test and ensure services are started, each site can be administered, and clients can communicate with current and legacy users.</span></span> <span data-ttu-id="db572-114">移轉所有使用者之前，請先了解每個部署的狀態並確定兩者皆正常運作，這點是非常重要的。</span><span class="sxs-lookup"><span data-stu-id="db572-114">Prior to the migration of all users, it is very important that you understand the state of each deployment and ensure that each deployment is functional and working properly.</span></span> <span data-ttu-id="db572-115">一般而言，測試階段共存存在整個 Lync Server 2013 試驗測試。</span><span class="sxs-lookup"><span data-stu-id="db572-115">Typically, the coexistence testing phase exists throughout the pilot testing of Lync Server 2013.</span></span> <span data-ttu-id="db572-116">舊版使用者移至 Lync Server 2013 的一段時間以確保該應用程式相容性和功能正常運作。</span><span class="sxs-lookup"><span data-stu-id="db572-116">Legacy users are moved to Lync Server 2013 for a period of time to ensure that application compatibility and features and functions are working properly.</span></span> <span data-ttu-id="db572-117">試驗測試之後，使用者和應用程式會移至 Lync Server 2013 的實際執行版本和舊版集區與 Office Communications Server 2007 R2 的應用程式會停用。</span><span class="sxs-lookup"><span data-stu-id="db572-117">After pilot testing, users and applications are moved to the production version of Lync Server 2013, and the legacy pools and applications of Office Communications Server 2007 R2 are retired.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

