---
title: Lync Server 2013：部署封存
description: Lync Server 2013：部署封存。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Archiving
ms:assetid: a89edd16-12d5-4602-ad2f-194b47d1188e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205147(v=OCS.15)
ms:contentKeyID: 48185031
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c4ba38b7dcde0c72469e361f59ade7cb7f6ebb53
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558499"
---
# <a name="deploying-archiving-in-lync-server-2013"></a><span data-ttu-id="ceb83-103">在 Lync Server 2013 中部署封存</span><span class="sxs-lookup"><span data-stu-id="ceb83-103">Deploying Archiving in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ceb83-104">_**主題上次修改日期：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="ceb83-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="ceb83-105">Lync Server 2013 提供在 Lync Server 中封存立即訊息 (IM) 內容和會議通訊的解決方案。</span><span class="sxs-lookup"><span data-stu-id="ceb83-105">Lync Server 2013 provides a solution for archiving instant messaging (IM) content and conferencing communications in Lync Server.</span></span> <span data-ttu-id="ceb83-106">您可以使用 SQL Server 資料庫來儲存 Lync Server 2013 封存資料，或同時使用 Lync Server 2013 和 Exchange 2013 儲存，以整合封存儲存與 Exchange 2013 儲存區，以執行封存支援。</span><span class="sxs-lookup"><span data-stu-id="ceb83-106">You can implement archiving support by integrating archiving storage with Exchange 2013 storage, by using SQL Server databases for storage of Lync Server 2013 archiving data, or by using both Lync Server 2013 and Exchange 2013 storage.</span></span> <span data-ttu-id="ceb83-107">您可以控制使用原則及封存設定來封存資料的方式。</span><span class="sxs-lookup"><span data-stu-id="ceb83-107">You control how data is archived using policies and archiving configurations.</span></span> <span data-ttu-id="ceb83-108">如需詳細資訊，請參閱規劃檔、部署檔或作業檔中的規劃檔和封存在[Lync server 2013 中的運作方式](lync-server-2013-how-archiving-works.md)中的「[在 lync Server 2013 中規劃](lync-server-2013-planning-for-archiving.md)封存」。</span><span class="sxs-lookup"><span data-stu-id="ceb83-108">For details, see [Planning for Archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) in the Planning documentation and [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<span data-ttu-id="ceb83-109">您可以使用本節中的資訊，先設定和設定封存。</span><span class="sxs-lookup"><span data-stu-id="ceb83-109">You can use the information in this section to set up and configure Archiving initially.</span></span> <span data-ttu-id="ceb83-110">部署之後，您可以變更封存設定。</span><span class="sxs-lookup"><span data-stu-id="ceb83-110">After deployment, you can change Archiving settings.</span></span> <span data-ttu-id="ceb83-111">如需如何針對日常管理執行封存支援，或符合組織中新需求的詳細資訊，請參閱 Operations 檔中的 [管理 Lync Server 2013](lync-server-2013-managing-archiving.md) 封存。</span><span class="sxs-lookup"><span data-stu-id="ceb83-111">For details about how you implement archiving support for day-to-day management or to meet new requirements in your organization, see [Managing Lync Server 2013 Archiving](lync-server-2013-managing-archiving.md) in the Operations documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ceb83-112">本章節內容</span><span class="sxs-lookup"><span data-stu-id="ceb83-112">In This Section</span></span>

  - [<span data-ttu-id="ceb83-113">Lync Server 2013 中的封存運作方式</span><span class="sxs-lookup"><span data-stu-id="ceb83-113">How Archiving works in Lync Server 2013</span></span>](lync-server-2013-how-archiving-works.md)

  - [<span data-ttu-id="ceb83-114">Lync Server 2013 中封存的部署檢查清單</span><span class="sxs-lookup"><span data-stu-id="ceb83-114">Deployment checklist for Archiving in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-archiving.md)

  - [<span data-ttu-id="ceb83-115">在 Lync Server 2013 中設定封存的系統和基礎結構</span><span class="sxs-lookup"><span data-stu-id="ceb83-115">Setting up systems and infrastructure for Archiving in Lync Server 2013</span></span>](lync-server-2013-setting-up-systems-and-infrastructure-for-archiving.md)

  - [<span data-ttu-id="ceb83-116">將封存資料庫新增至現有的 Lync Server 2013 部署</span><span class="sxs-lookup"><span data-stu-id="ceb83-116">Adding Archiving databases to an existing Lync Server 2013 Deployment</span></span>](lync-server-2013-adding-archiving-databases-to-an-existing-lync-server-2013-deployment.md)

  - [<span data-ttu-id="ceb83-117">在 Lync Server 2013 中設定封存支援</span><span class="sxs-lookup"><span data-stu-id="ceb83-117">Configuring support for Archiving in Lync Server 2013</span></span>](lync-server-2013-configuring-support-for-archiving.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

