---
title: 階段 10： 解除委任舊版站台
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: 'Phase 10: Decommission legacy site'
ms:assetid: d591a310-3b5c-4092-b19e-0349616e40df
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205300(v=OCS.15)
ms:contentKeyID: 48185540
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6e46c2977289ae8fec1db26e4eb33dfd6736f838
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034373"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="phase-10-decommission-legacy-site"></a><span data-ttu-id="6e804-102">階段 10： 解除委任舊版站台</span><span class="sxs-lookup"><span data-stu-id="6e804-102">Phase 10: Decommission legacy site</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6e804-103">_**主題上次修改日期：** 2012 年 10-16_</span><span class="sxs-lookup"><span data-stu-id="6e804-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="6e804-104">下列主題提供在解除委任集區]，並停用與舊版 Office Communications Server 2007 R2 部署中移除伺服器和集區中的指引。</span><span class="sxs-lookup"><span data-stu-id="6e804-104">The following topics provide guidance in decommissioning pools, and deactivating and removing servers and pools from a legacy deployment of Office Communications Server 2007 R2.</span></span> <span data-ttu-id="6e804-105">本節所列的程序並非全為必要程序。</span><span class="sxs-lookup"><span data-stu-id="6e804-105">Not all of the procedures listed in this section are required.</span></span> <span data-ttu-id="6e804-106">閱讀中每個這些主題，以決定要使用哪一個解除委任程序的資訊。</span><span class="sxs-lookup"><span data-stu-id="6e804-106">Read the information in each of these topics to determine which decommissioning procedure to use.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="6e804-107">如果您匯入 Lync Server 2013 的電話撥入式會議的會議目錄，務必切換到 Lync Server 2013 會議目錄擁有權解除委任集區之前。</span><span class="sxs-lookup"><span data-stu-id="6e804-107">If you imported conference directories for dial-in conferencing to Lync Server 2013, it is important to transition conference directory ownership to Lync Server 2013 before you begin to decommission your pools.</span></span> <span data-ttu-id="6e804-108">如果您解除委任集區，而第一個轉換的會議目錄擁有權，所有的移轉會議的撥號對應表中功能將不再有作用。</span><span class="sxs-lookup"><span data-stu-id="6e804-108">If you decommission a pool without first transitioning conference directory ownership, the dial-in feature for all migrated meetings will no longer work.</span></span> <span data-ttu-id="6e804-109">您必須執行轉換擁有權的步驟一次每個會議目錄舊版集區中。</span><span class="sxs-lookup"><span data-stu-id="6e804-109">You must perform the step to transition ownership once for each conference directory in your legacy pool.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="6e804-110">如需移轉與升級 Microsoft Unified Communications Managed API (UCMA) 應用程式]，再解除委任舊版環境，請參閱<A href="http://go.microsoft.com/fwlink/p/?linkid=269555">http://go.microsoft.com/fwlink/p/?LinkId=269555</A></span><span class="sxs-lookup"><span data-stu-id="6e804-110">For information on migrating and upgrading Microsoft Unified Communications Managed API (UCMA) applications, prior to decommissioning your legacy environment, see <A href="http://go.microsoft.com/fwlink/p/?linkid=269555">http://go.microsoft.com/fwlink/p/?LinkId=269555</A></span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="6e804-111">本章節內容</span><span class="sxs-lookup"><span data-stu-id="6e804-111">In This Section</span></span>

  - [<span data-ttu-id="6e804-112">移動會議目錄</span><span class="sxs-lookup"><span data-stu-id="6e804-112">Move conference directories</span></span>](move-conference-directories.md)

  - [<span data-ttu-id="6e804-113">更新 DNS SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="6e804-113">Update DNS SRV records</span></span>](update-dns-srv-records_1.md)

  - [<span data-ttu-id="6e804-114">解除委任伺服器和集區</span><span class="sxs-lookup"><span data-stu-id="6e804-114">Decommissioning servers and pools</span></span>](decommissioning-servers-and-pools.md)

  - [<span data-ttu-id="6e804-115">移除 BackCompatSite</span><span class="sxs-lookup"><span data-stu-id="6e804-115">Remove BackCompatSite</span></span>](remove-backcompatsite.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

