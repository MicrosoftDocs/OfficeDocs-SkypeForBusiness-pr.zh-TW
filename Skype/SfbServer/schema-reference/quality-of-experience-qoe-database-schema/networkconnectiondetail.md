---
title: NetworkConnectionDetail 資料表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
description: NetworkConnectionDetail 表格會將網路連線類型對應至在體驗資料庫的 [品質] 資料庫中的其他位置所使用的網路連接識別碼。 此表格是在 Microsoft Lync Server 2013 中推出。
ms.openlocfilehash: d91928e40f6df9db1e53140726bbf04efad586ee
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41807501"
---
# <a name="networkconnectiondetail-table"></a><span data-ttu-id="c24d2-104">NetworkConnectionDetail 資料表</span><span class="sxs-lookup"><span data-stu-id="c24d2-104">NetworkConnectionDetail table</span></span>
 
<span data-ttu-id="c24d2-105">NetworkConnectionDetail 表格會將網路連線類型對應至在體驗資料庫的 [品質] 資料庫中的其他位置所使用的網路連接識別碼。</span><span class="sxs-lookup"><span data-stu-id="c24d2-105">The NetworkConnectionDetail table maps network connection types to the network connection identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="c24d2-106">此表格是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="c24d2-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="c24d2-107">**左欄**</span><span class="sxs-lookup"><span data-stu-id="c24d2-107">**Column**</span></span>|<span data-ttu-id="c24d2-108">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="c24d2-108">**Data Type**</span></span>|<span data-ttu-id="c24d2-109">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="c24d2-109">**Key/Index**</span></span>|<span data-ttu-id="c24d2-110">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="c24d2-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c24d2-111">**NetworkConnectionDetailKey**</span><span class="sxs-lookup"><span data-stu-id="c24d2-111">**NetworkConnectionDetailKey**</span></span> <br/> |<span data-ttu-id="c24d2-112">Tinyint</span><span class="sxs-lookup"><span data-stu-id="c24d2-112">tinyint</span></span>  <br/> |<span data-ttu-id="c24d2-113">首選</span><span class="sxs-lookup"><span data-stu-id="c24d2-113">Primary</span></span>  <br/> |<span data-ttu-id="c24d2-114">網路連線類型的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="c24d2-114">Unique identifier for the network connection type.</span></span>  <br/> |
|<span data-ttu-id="c24d2-115">**NetworkConnectionDetail**</span><span class="sxs-lookup"><span data-stu-id="c24d2-115">**NetworkConnectionDetail**</span></span> <br/> |<span data-ttu-id="c24d2-116">Varchar （256）</span><span class="sxs-lookup"><span data-stu-id="c24d2-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="c24d2-117">唯一</span><span class="sxs-lookup"><span data-stu-id="c24d2-117">Unique</span></span>  <br/> |<span data-ttu-id="c24d2-118">對應至 NetworkConnectionDetailKey 的網路連線類型。</span><span class="sxs-lookup"><span data-stu-id="c24d2-118">Network connection type that corresponds to the NetworkConnectionDetailKey.</span></span> <span data-ttu-id="c24d2-119">允許的值為：</span><span class="sxs-lookup"><span data-stu-id="c24d2-119">Allowed values are:</span></span>  <br/> <span data-ttu-id="c24d2-120">0--有線</span><span class="sxs-lookup"><span data-stu-id="c24d2-120">0 -- Wired</span></span>  <br/> <span data-ttu-id="c24d2-121">1--WiFi</span><span class="sxs-lookup"><span data-stu-id="c24d2-121">1 -- WiFi</span></span>  <br/> <span data-ttu-id="c24d2-122">2--乙太網路</span><span class="sxs-lookup"><span data-stu-id="c24d2-122">2 -- Ethernet</span></span>  <br/> <span data-ttu-id="c24d2-123">3--MobileBB</span><span class="sxs-lookup"><span data-stu-id="c24d2-123">3 -- MobileBB</span></span>  <br/> <span data-ttu-id="c24d2-124">4--其他</span><span class="sxs-lookup"><span data-stu-id="c24d2-124">4 -- Other</span></span>  <br/> <span data-ttu-id="c24d2-125">5--隧道</span><span class="sxs-lookup"><span data-stu-id="c24d2-125">5 -- Tunnel</span></span>  <br/> |
   

