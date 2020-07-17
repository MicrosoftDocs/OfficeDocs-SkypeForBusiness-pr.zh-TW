---
title: 移轉程序
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migration process
ms:assetid: b2bd9c76-2f4b-4d14-a5c4-157bbff75de0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205181(v=OCS.15)
ms:contentKeyID: 48185157
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2da65ead79d33ff03a66f4ec5ef54fa4e2167890
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756652"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migration-process"></a><span data-ttu-id="3df4a-102">移轉程序</span><span class="sxs-lookup"><span data-stu-id="3df4a-102">Migration process</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3df4a-103">_**主題上次修改日期：** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="3df4a-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="3df4a-104">Lync Server 2013 的建議和支援的遷移程式是並列遷移程式。</span><span class="sxs-lookup"><span data-stu-id="3df4a-104">The recommended and supported migration procedure for Lync Server 2013 is the side-by-side migration procedure.</span></span> <span data-ttu-id="3df4a-105">本主題說明您為何應該使用並列遷移，也包含共存的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="3df4a-105">This topic describes why you should use side-by-side migration and also includes information about coexistence.</span></span>

<div>

## <a name="side-by-side-migration"></a><span data-ttu-id="3df4a-106">並列遷移</span><span class="sxs-lookup"><span data-stu-id="3df4a-106">Side-by-Side Migration</span></span>

<span data-ttu-id="3df4a-107">幾乎在每種移轉時，您都應該使用並存移轉路徑。</span><span class="sxs-lookup"><span data-stu-id="3df4a-107">In nearly every migration, you should use the side-by-side migration path.</span></span> <span data-ttu-id="3df4a-108">在並列式遷移中，您可以使用 Lync Server 2013 和執行 Office 通訊伺服器 2007 R2 的相對應伺服器來部署新的伺服器，然後將作業轉移至新的伺服器。</span><span class="sxs-lookup"><span data-stu-id="3df4a-108">In a side-by-side migration, you deploy a new server with Lync Server 2013 alongside a corresponding server that is running Office Communications Server 2007 R2, and then you transfer operations to the new server.</span></span> <span data-ttu-id="3df4a-109">若要回復到 Office 通訊伺服器 2007 R2，您只需要將作業移回原始伺服器。</span><span class="sxs-lookup"><span data-stu-id="3df4a-109">If it becomes necessary to roll back to Office Communications Server 2007 R2, you have only to shift operations back to the original servers.</span></span> <span data-ttu-id="3df4a-110">請注意在這樣的情況下，任何與升級用戶端排定的新會議皆無法運作，導致用戶端也必須降級。</span><span class="sxs-lookup"><span data-stu-id="3df4a-110">Be aware that in this situation any new meetings scheduled with upgraded clients will not work, and the clients would also need to be downgraded.</span></span>

</div>

<div>

## <a name="coexistence-testing"></a><span data-ttu-id="3df4a-111">共存測試</span><span class="sxs-lookup"><span data-stu-id="3df4a-111">Coexistence Testing</span></span>

<span data-ttu-id="3df4a-112">將 Lync Server 2013 與 Office 通訊伺服器 2007 R2 同時部署後，拓撲代表 Lync Server 2013 和 Office 通訊伺服器 2007 R2 的共存測試狀態。</span><span class="sxs-lookup"><span data-stu-id="3df4a-112">After you have deployed Lync Server 2013 in parallel with Office Communications Server 2007 R2, the topology represents a coexistence testing state of Lync Server 2013 and Office Communications Server 2007 R2.</span></span> <span data-ttu-id="3df4a-113">在此狀態下，必須先進行測試並確定服務已啟動、可管理每個網站，且用戶端可以與目前和舊版使用者通訊。</span><span class="sxs-lookup"><span data-stu-id="3df4a-113">While in this state, it is important to test and ensure services are started, each site can be administered, and clients can communicate with current and legacy users.</span></span> <span data-ttu-id="3df4a-114">移轉所有使用者之前，請先了解每個部署的狀態並確定兩者皆正常運作，這點是非常重要的。</span><span class="sxs-lookup"><span data-stu-id="3df4a-114">Prior to the migration of all users, it is very important that you understand the state of each deployment and ensure that each deployment is functional and working properly.</span></span> <span data-ttu-id="3df4a-115">通常，共存測試階段會存在於所有的 Lync Server 2013 試驗測試中。</span><span class="sxs-lookup"><span data-stu-id="3df4a-115">Typically, the coexistence testing phase exists throughout the pilot testing of Lync Server 2013.</span></span> <span data-ttu-id="3df4a-116">舊版使用者會移至 Lync Server 2013 一段時間，以確保應用程式相容性和功能正常運作。</span><span class="sxs-lookup"><span data-stu-id="3df4a-116">Legacy users are moved to Lync Server 2013 for a period of time to ensure that application compatibility and features and functions are working properly.</span></span> <span data-ttu-id="3df4a-117">在試驗測試之後，使用者和應用程式會移至 Lync Server 2013 的實際執行版本，且舊版集區和 Office 通訊伺服器 2007 R2 的應用程式會終止。</span><span class="sxs-lookup"><span data-stu-id="3df4a-117">After pilot testing, users and applications are moved to the production version of Lync Server 2013, and the legacy pools and applications of Office Communications Server 2007 R2 are retired.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

