---
title: Lync Server 2013： 管理封存
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing Lync Server 2013 Archiving
ms:assetid: 48c6cc8c-c2c1-4534-9a8a-fd5eb738076a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520990(v=OCS.15)
ms:contentKeyID: 48184003
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d8b7e27efc0c691f83df685b441d38e0b26f5239
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42218199"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-lync-server-2013-archiving"></a><span data-ttu-id="4153b-102">管理 Lync Server 2013 封存</span><span class="sxs-lookup"><span data-stu-id="4153b-102">Managing Lync Server 2013 Archiving</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4153b-103">_**主題上次修改日期：** 2012年-10-10_</span><span class="sxs-lookup"><span data-stu-id="4153b-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="4153b-104">當您為組織部署封存時，會在部署期間指定初始設定。</span><span class="sxs-lookup"><span data-stu-id="4153b-104">When you deploy Archiving for your organization, you specify the initial configuration during deployment.</span></span> <span data-ttu-id="4153b-105">然而，有時您可能會想要改變您對例行管理實作封存支援的方式，或符合組織中的新需求。</span><span class="sxs-lookup"><span data-stu-id="4153b-105">However, there may be times when you want to change how you implement archiving support for day-to-day management or to meet new requirements in your organization.</span></span> <span data-ttu-id="4153b-106">例如，您可能會需要對特定網站、集區或組織內的使用者以不同的方式設定封存支援。</span><span class="sxs-lookup"><span data-stu-id="4153b-106">For example, you may need to set up archiving support differently for a specific site, pool, or users within your organization.</span></span> <span data-ttu-id="4153b-107">隸屬於 Lync Server 2013 的使用者，針對您這麼做會建立及自訂封存原則和設定。</span><span class="sxs-lookup"><span data-stu-id="4153b-107">For users homed on Lync Server 2013, you do this be creating and customizing archiving policies and configurations.</span></span> <span data-ttu-id="4153b-108">如果您使用 Microsoft Exchange 整合，您必須也設定 Exchange 2013。</span><span class="sxs-lookup"><span data-stu-id="4153b-108">If you use Microsoft Exchange integration, you must also configure Exchange 2013 settings.</span></span> <span data-ttu-id="4153b-109">本節所提供的資訊和程序可讓您變更您的封存部署。</span><span class="sxs-lookup"><span data-stu-id="4153b-109">This section provides information and procedures to enable you to make changes to your Archiving deployment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="4153b-110">本章節內容</span><span class="sxs-lookup"><span data-stu-id="4153b-110">In This Section</span></span>

  - [<span data-ttu-id="4153b-111">封存 Lync Server 2013 中的運作方式</span><span class="sxs-lookup"><span data-stu-id="4153b-111">How Archiving works in Lync Server 2013</span></span>](lync-server-2013-how-archiving-works.md)

  - [<span data-ttu-id="4153b-112">管理 Lync Server 2013 中的內部和外部通訊的封存</span><span class="sxs-lookup"><span data-stu-id="4153b-112">Managing the Archiving of internal and external communications in Lync Server 2013</span></span>](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)

  - [<span data-ttu-id="4153b-113">管理 Lync Server 2013 中為您的組織、 網站及集區的封存設定選項</span><span class="sxs-lookup"><span data-stu-id="4153b-113">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</span></span>](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)

  - [<span data-ttu-id="4153b-114">Lync Server 2013 中的變更封存資料庫選項</span><span class="sxs-lookup"><span data-stu-id="4153b-114">Changing Archiving database options in Lync Server 2013</span></span>](lync-server-2013-changing-archiving-database-options.md)

  - [<span data-ttu-id="4153b-115">從 Lync Server 2013 中匯出封存的資料</span><span class="sxs-lookup"><span data-stu-id="4153b-115">Exporting archived data from Lync Server 2013</span></span>](lync-server-2013-exporting-archived-data.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

