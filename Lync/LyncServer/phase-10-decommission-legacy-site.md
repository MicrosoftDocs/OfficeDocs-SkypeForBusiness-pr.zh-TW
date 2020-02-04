---
title: 階段10：解除授權舊版網站
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
ms.openlocfilehash: 8110d41e5f6436bfdbecc64fe07d514b5d0538ac
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757707"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="phase-10-decommission-legacy-site"></a><span data-ttu-id="b3d18-102">階段10：解除授權舊版網站</span><span class="sxs-lookup"><span data-stu-id="b3d18-102">Phase 10: Decommission legacy site</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b3d18-103">_**主題上次修改日期：** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="b3d18-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="b3d18-104">下列主題提供解除授權的方式，以及從 Office 通訊伺服器 2007 R2 的舊版部署中停用及移除伺服器和池的指導方針。</span><span class="sxs-lookup"><span data-stu-id="b3d18-104">The following topics provide guidance in decommissioning pools, and deactivating and removing servers and pools from a legacy deployment of Office Communications Server 2007 R2.</span></span> <span data-ttu-id="b3d18-105">並非本節所列的所有程式都是必要的。</span><span class="sxs-lookup"><span data-stu-id="b3d18-105">Not all of the procedures listed in this section are required.</span></span> <span data-ttu-id="b3d18-106">閱讀其中每個主題中的資訊，以判斷要使用的解除授權程式。</span><span class="sxs-lookup"><span data-stu-id="b3d18-106">Read the information in each of these topics to determine which decommissioning procedure to use.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="b3d18-107">如果您已將電話撥入式會議的會議目錄匯入到 Lync Server 2013，請務必先將會議目錄擁有權轉移至 Lync Server 2013，然後才能開始解除池的授權。</span><span class="sxs-lookup"><span data-stu-id="b3d18-107">If you imported conference directories for dial-in conferencing to Lync Server 2013, it is important to transition conference directory ownership to Lync Server 2013 before you begin to decommission your pools.</span></span> <span data-ttu-id="b3d18-108">如果您在未事先轉移會議目錄擁有權的情況下停用池，所有已遷移會議的撥入功能將不再運作。</span><span class="sxs-lookup"><span data-stu-id="b3d18-108">If you decommission a pool without first transitioning conference directory ownership, the dial-in feature for all migrated meetings will no longer work.</span></span> <span data-ttu-id="b3d18-109">您必須針對舊版池中的每個會議目錄，執行一次轉移擁有權的步驟。</span><span class="sxs-lookup"><span data-stu-id="b3d18-109">You must perform the step to transition ownership once for each conference directory in your legacy pool.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b3d18-110">如需遷移和升級 Microsoft 整合通訊管理 API （UCMA）應用程式的相關資訊，請參閱在解除舊版環境的授權之前，請參閱<A href="http://go.microsoft.com/fwlink/p/?linkid=269555">http://go.microsoft.com/fwlink/p/?LinkId=269555</A></span><span class="sxs-lookup"><span data-stu-id="b3d18-110">For information on migrating and upgrading Microsoft Unified Communications Managed API (UCMA) applications, prior to decommissioning your legacy environment, see <A href="http://go.microsoft.com/fwlink/p/?linkid=269555">http://go.microsoft.com/fwlink/p/?LinkId=269555</A></span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="b3d18-111">本節內容</span><span class="sxs-lookup"><span data-stu-id="b3d18-111">In This Section</span></span>

  - [<span data-ttu-id="b3d18-112">移動會議目錄</span><span class="sxs-lookup"><span data-stu-id="b3d18-112">Move conference directories</span></span>](move-conference-directories.md)

  - [<span data-ttu-id="b3d18-113">更新 DNS SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="b3d18-113">Update DNS SRV records</span></span>](update-dns-srv-records_1.md)

  - [<span data-ttu-id="b3d18-114">伺服器和池退役</span><span class="sxs-lookup"><span data-stu-id="b3d18-114">Decommissioning servers and pools</span></span>](decommissioning-servers-and-pools.md)

  - [<span data-ttu-id="b3d18-115">移除 BackCompatSite</span><span class="sxs-lookup"><span data-stu-id="b3d18-115">Remove BackCompatSite</span></span>](remove-backcompatsite.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

