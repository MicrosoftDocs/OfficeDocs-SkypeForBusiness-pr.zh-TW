---
title: NetworkConnectionDetail 表格
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
description: NetworkConnectionDetail 表會將網路連線類型對應至其他在經驗品質資料庫中使用的網路連線識別碼。 此表格已引進 Microsoft Lync Server 2013。
ms.openlocfilehash: 2e03e7935370e71a8070ed1882f61ac5480f312e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806303"
---
# <a name="networkconnectiondetail-table"></a><span data-ttu-id="cff02-104">NetworkConnectionDetail 表格</span><span class="sxs-lookup"><span data-stu-id="cff02-104">NetworkConnectionDetail table</span></span>
 
<span data-ttu-id="cff02-105">NetworkConnectionDetail 表會將網路連線類型對應至其他在經驗品質資料庫中使用的網路連線識別碼。</span><span class="sxs-lookup"><span data-stu-id="cff02-105">The NetworkConnectionDetail table maps network connection types to the network connection identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="cff02-106">此表格已引進 Microsoft Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="cff02-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="cff02-107">**欄**</span><span class="sxs-lookup"><span data-stu-id="cff02-107">**Column**</span></span>|<span data-ttu-id="cff02-108">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="cff02-108">**Data Type**</span></span>|<span data-ttu-id="cff02-109">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="cff02-109">**Key/Index**</span></span>|<span data-ttu-id="cff02-110">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="cff02-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="cff02-111">**NetworkConnectionDetailKey**</span><span class="sxs-lookup"><span data-stu-id="cff02-111">**NetworkConnectionDetailKey**</span></span> <br/> |<span data-ttu-id="cff02-112">Tinyint</span><span class="sxs-lookup"><span data-stu-id="cff02-112">tinyint</span></span>  <br/> |<span data-ttu-id="cff02-113">主要</span><span class="sxs-lookup"><span data-stu-id="cff02-113">Primary</span></span>  <br/> |<span data-ttu-id="cff02-114">網路連線類型的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="cff02-114">Unique identifier for the network connection type.</span></span>  <br/> |
|<span data-ttu-id="cff02-115">**NetworkConnectionDetail**</span><span class="sxs-lookup"><span data-stu-id="cff02-115">**NetworkConnectionDetail**</span></span> <br/> |<span data-ttu-id="cff02-116">Varchar (256) </span><span class="sxs-lookup"><span data-stu-id="cff02-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="cff02-117">Unique</span><span class="sxs-lookup"><span data-stu-id="cff02-117">Unique</span></span>  <br/> |<span data-ttu-id="cff02-118">對應至 NetworkConnectionDetailKey 的網路連線類型。</span><span class="sxs-lookup"><span data-stu-id="cff02-118">Network connection type that corresponds to the NetworkConnectionDetailKey.</span></span> <span data-ttu-id="cff02-119">允許的值為：</span><span class="sxs-lookup"><span data-stu-id="cff02-119">Allowed values are:</span></span>  <br/> <span data-ttu-id="cff02-120">0--有線</span><span class="sxs-lookup"><span data-stu-id="cff02-120">0 -- Wired</span></span>  <br/> <span data-ttu-id="cff02-121">1--WiFi</span><span class="sxs-lookup"><span data-stu-id="cff02-121">1 -- WiFi</span></span>  <br/> <span data-ttu-id="cff02-122">2--乙太網路</span><span class="sxs-lookup"><span data-stu-id="cff02-122">2 -- Ethernet</span></span>  <br/> <span data-ttu-id="cff02-123">3--MobileBB</span><span class="sxs-lookup"><span data-stu-id="cff02-123">3 -- MobileBB</span></span>  <br/> <span data-ttu-id="cff02-124">4--其他</span><span class="sxs-lookup"><span data-stu-id="cff02-124">4 -- Other</span></span>  <br/> <span data-ttu-id="cff02-125">5--隧道</span><span class="sxs-lookup"><span data-stu-id="cff02-125">5 -- Tunnel</span></span>  <br/> |
   

