---
title: Lync Server 2013：部署封存
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
ms.openlocfilehash: 86b1394df9bb52502e1e0c605bedb05a0579042e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729592"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-archiving-in-lync-server-2013"></a><span data-ttu-id="26720-102">在 Lync Server 2013 中部署封存</span><span class="sxs-lookup"><span data-stu-id="26720-102">Deploying Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="26720-103">_**主題上次修改日期：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="26720-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="26720-104">Lync Server 2013 提供在 Lync Server 中封存立即訊息（IM）內容與會議通訊的方案。</span><span class="sxs-lookup"><span data-stu-id="26720-104">Lync Server 2013 provides a solution for archiving instant messaging (IM) content and conferencing communications in Lync Server.</span></span> <span data-ttu-id="26720-105">您可以將存檔儲存與 Exchange 2013 儲存整合，方法是使用 SQL Server 資料庫儲存 Lync Server 2013 封存資料，或同時使用 Lync Server 2013 與 Exchange 2013 儲存來實現封存支援。</span><span class="sxs-lookup"><span data-stu-id="26720-105">You can implement archiving support by integrating archiving storage with Exchange 2013 storage, by using SQL Server databases for storage of Lync Server 2013 archiving data, or by using both Lync Server 2013 and Exchange 2013 storage.</span></span> <span data-ttu-id="26720-106">您可以使用原則與歸檔設定控制資料的歸檔方式。</span><span class="sxs-lookup"><span data-stu-id="26720-106">You control how data is archived using policies and archiving configurations.</span></span> <span data-ttu-id="26720-107">如需詳細資訊，請參閱規劃檔中的 [[在 Lync server 2013 中進行](lync-server-2013-planning-for-archiving.md)封存]，以及如何在規劃檔、部署檔或作業檔中使用[lync server 2013](lync-server-2013-how-archiving-works.md)中的存檔作業。</span><span class="sxs-lookup"><span data-stu-id="26720-107">For details, see [Planning for Archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) in the Planning documentation and [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<span data-ttu-id="26720-108">您可以使用本節中的資訊來開始設定和設定存檔。</span><span class="sxs-lookup"><span data-stu-id="26720-108">You can use the information in this section to set up and configure Archiving initially.</span></span> <span data-ttu-id="26720-109">部署之後，您可以變更存檔設定。</span><span class="sxs-lookup"><span data-stu-id="26720-109">After deployment, you can change Archiving settings.</span></span> <span data-ttu-id="26720-110">如需有關如何針對日常管理執行封存支援或符合貴組織中新需求的詳細資訊，請參閱在作業檔中[管理 Lync Server 2013 存檔](lync-server-2013-managing-archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="26720-110">For details about how you implement archiving support for day-to-day management or to meet new requirements in your organization, see [Managing Lync Server 2013 Archiving](lync-server-2013-managing-archiving.md) in the Operations documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="26720-111">本節內容</span><span class="sxs-lookup"><span data-stu-id="26720-111">In This Section</span></span>

  - [<span data-ttu-id="26720-112">存檔在 Lync Server 2013 中的運作方式</span><span class="sxs-lookup"><span data-stu-id="26720-112">How Archiving works in Lync Server 2013</span></span>](lync-server-2013-how-archiving-works.md)

  - [<span data-ttu-id="26720-113">Lync Server 2013 中封存的部署檢查單</span><span class="sxs-lookup"><span data-stu-id="26720-113">Deployment checklist for Archiving in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-archiving.md)

  - [<span data-ttu-id="26720-114">在 Lync Server 2013 中設定存檔的系統和基礎結構</span><span class="sxs-lookup"><span data-stu-id="26720-114">Setting up systems and infrastructure for Archiving in Lync Server 2013</span></span>](lync-server-2013-setting-up-systems-and-infrastructure-for-archiving.md)

  - [<span data-ttu-id="26720-115">將存檔資料庫新增至現有的 Lync Server 2013 部署</span><span class="sxs-lookup"><span data-stu-id="26720-115">Adding Archiving databases to an existing Lync Server 2013 Deployment</span></span>](lync-server-2013-adding-archiving-databases-to-an-existing-lync-server-2013-deployment.md)

  - [<span data-ttu-id="26720-116">在 Lync Server 2013 中設定存檔支援</span><span class="sxs-lookup"><span data-stu-id="26720-116">Configuring support for Archiving in Lync Server 2013</span></span>](lync-server-2013-configuring-support-for-archiving.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

