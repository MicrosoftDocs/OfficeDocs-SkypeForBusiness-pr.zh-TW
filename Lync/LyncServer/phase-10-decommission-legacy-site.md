---
title: 階段10：解除委任舊版網站
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: 'Phase 10: Decommission legacy site'
ms:assetid: d591a310-3b5c-4092-b19e-0349616e40df
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205300(v=OCS.15)
ms:contentKeyID: 48185540
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d40c988822a27a34f148e4e1e7893a077965fcd
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751155"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="phase-10-decommission-legacy-site"></a><span data-ttu-id="89353-102">階段10：解除委任舊版網站</span><span class="sxs-lookup"><span data-stu-id="89353-102">Phase 10: Decommission legacy site</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="89353-103">_**主題上次修改日期：** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="89353-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="89353-104">下列主題提供解除委任集區的指導，以及從 Office 通訊伺服器 2007 R2 的舊版部署停用和移除伺服器及集區的指導方針。</span><span class="sxs-lookup"><span data-stu-id="89353-104">The following topics provide guidance in decommissioning pools, and deactivating and removing servers and pools from a legacy deployment of Office Communications Server 2007 R2.</span></span> <span data-ttu-id="89353-105">本節所列的程序並非全為必要程序。</span><span class="sxs-lookup"><span data-stu-id="89353-105">Not all of the procedures listed in this section are required.</span></span> <span data-ttu-id="89353-106">請閱讀下列各主題中的資訊，以判斷要使用的解除委任程式。</span><span class="sxs-lookup"><span data-stu-id="89353-106">Read the information in each of these topics to determine which decommissioning procedure to use.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="89353-107">如果您已將電話撥入式會議的會議目錄匯入 Lync Server 2013，請務必先將會議目錄擁有權轉移至 Lync Server 2013，再開始解除委任集區。</span><span class="sxs-lookup"><span data-stu-id="89353-107">If you imported conference directories for dial-in conferencing to Lync Server 2013, it is important to transition conference directory ownership to Lync Server 2013 before you begin to decommission your pools.</span></span> <span data-ttu-id="89353-108">如果您解除委任集區，但沒有第一次轉換會議目錄擁有權，所有已遷移會議的撥入功能將不再運作。</span><span class="sxs-lookup"><span data-stu-id="89353-108">If you decommission a pool without first transitioning conference directory ownership, the dial-in feature for all migrated meetings will no longer work.</span></span> <span data-ttu-id="89353-109">您必須執行此步驟，針對舊版集區中的每個會議目錄，將擁有權轉移一次。</span><span class="sxs-lookup"><span data-stu-id="89353-109">You must perform the step to transition ownership once for each conference directory in your legacy pool.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="89353-110">如需遷移和升級 Microsoft 整合通訊 Managed API （UCMA）應用程式的詳細資訊，請參閱解除委任舊版環境之前，請參閱<A href="https://go.microsoft.com/fwlink/p/?linkid=269555">https://go.microsoft.com/fwlink/p/?LinkId=269555</A></span><span class="sxs-lookup"><span data-stu-id="89353-110">For information on migrating and upgrading Microsoft Unified Communications Managed API (UCMA) applications, prior to decommissioning your legacy environment, see <A href="https://go.microsoft.com/fwlink/p/?linkid=269555">https://go.microsoft.com/fwlink/p/?LinkId=269555</A></span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="89353-111">本章節內容</span><span class="sxs-lookup"><span data-stu-id="89353-111">In This Section</span></span>

  - [<span data-ttu-id="89353-112">移動會議目錄</span><span class="sxs-lookup"><span data-stu-id="89353-112">Move conference directories</span></span>](move-conference-directories.md)

  - [<span data-ttu-id="89353-113">更新 DNS SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="89353-113">Update DNS SRV records</span></span>](update-dns-srv-records_1.md)

  - [<span data-ttu-id="89353-114">解除委任伺服器與集區</span><span class="sxs-lookup"><span data-stu-id="89353-114">Decommissioning servers and pools</span></span>](decommissioning-servers-and-pools.md)

  - [<span data-ttu-id="89353-115">移除 BackCompatSite</span><span class="sxs-lookup"><span data-stu-id="89353-115">Remove BackCompatSite</span></span>](remove-backcompatsite.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

