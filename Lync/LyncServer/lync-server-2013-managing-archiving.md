---
title: Lync Server 2013：管理封存
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing Lync Server 2013 Archiving
ms:assetid: 48c6cc8c-c2c1-4534-9a8a-fd5eb738076a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520990(v=OCS.15)
ms:contentKeyID: 48184003
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 88e5176ec32b5039b9351202f72ee32502959f60
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40973956"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-lync-server-2013-archiving"></a><span data-ttu-id="ac77c-102">管理 Lync Server 2013 封存</span><span class="sxs-lookup"><span data-stu-id="ac77c-102">Managing Lync Server 2013 Archiving</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ac77c-103">_**主題上次修改日期：** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="ac77c-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="ac77c-104">當您為貴組織部署存檔時，您會在部署期間指定初始配置。</span><span class="sxs-lookup"><span data-stu-id="ac77c-104">When you deploy Archiving for your organization, you specify the initial configuration during deployment.</span></span> <span data-ttu-id="ac77c-105">不過，有時候您可能會想要變更針對日常管理執行封存支援的方式，或符合貴組織中的新需求。</span><span class="sxs-lookup"><span data-stu-id="ac77c-105">However, there may be times when you want to change how you implement archiving support for day-to-day management or to meet new requirements in your organization.</span></span> <span data-ttu-id="ac77c-106">例如，您可能需要針對貴組織內的特定網站、文件庫或使用者設定不同的存檔支援。</span><span class="sxs-lookup"><span data-stu-id="ac77c-106">For example, you may need to set up archiving support differently for a specific site, pool, or users within your organization.</span></span> <span data-ttu-id="ac77c-107">針對駐留在 Lync Server 2013 的使用者，您可以建立及自訂存檔原則與設定。</span><span class="sxs-lookup"><span data-stu-id="ac77c-107">For users homed on Lync Server 2013, you do this be creating and customizing archiving policies and configurations.</span></span> <span data-ttu-id="ac77c-108">如果您使用的是 Microsoft Exchange 整合，您也必須設定 Exchange 2013 設定。</span><span class="sxs-lookup"><span data-stu-id="ac77c-108">If you use Microsoft Exchange integration, you must also configure Exchange 2013 settings.</span></span> <span data-ttu-id="ac77c-109">本節提供的資訊和程式可讓您變更歸檔部署。</span><span class="sxs-lookup"><span data-stu-id="ac77c-109">This section provides information and procedures to enable you to make changes to your Archiving deployment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ac77c-110">本節內容</span><span class="sxs-lookup"><span data-stu-id="ac77c-110">In This Section</span></span>

  - [<span data-ttu-id="ac77c-111">存檔在 Lync Server 2013 中的運作方式</span><span class="sxs-lookup"><span data-stu-id="ac77c-111">How Archiving works in Lync Server 2013</span></span>](lync-server-2013-how-archiving-works.md)

  - [<span data-ttu-id="ac77c-112">在 Lync Server 2013 中管理內部和外部通訊的存檔</span><span class="sxs-lookup"><span data-stu-id="ac77c-112">Managing the Archiving of internal and external communications in Lync Server 2013</span></span>](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)

  - [<span data-ttu-id="ac77c-113">管理您組織、網站和池的 Lync Server 2013 中的封存配置選項</span><span class="sxs-lookup"><span data-stu-id="ac77c-113">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</span></span>](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)

  - [<span data-ttu-id="ac77c-114">在 Lync Server 2013 中變更封存資料庫選項</span><span class="sxs-lookup"><span data-stu-id="ac77c-114">Changing Archiving database options in Lync Server 2013</span></span>](lync-server-2013-changing-archiving-database-options.md)

  - [<span data-ttu-id="ac77c-115">從 Lync Server 2013 匯出已歸檔的資料</span><span class="sxs-lookup"><span data-stu-id="ac77c-115">Exporting archived data from Lync Server 2013</span></span>](lync-server-2013-exporting-archived-data.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

