---
title: 商務用 Skype Server 2015 中的 ErrorCategory 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
description: 'ErrorCategory 表格包含每個商務用 Skype Server 2015 診斷分類的易記名稱。 根據預設, 商務用 Skype Server 2015 使用下列分類:'
ms.openlocfilehash: bafeb75ee9e6ae0f96b08e26909828f1b36f7e7b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192865"
---
# <a name="errorcategory-table-in-skype-for-business-server-2015"></a><span data-ttu-id="3ee2a-104">商務用 Skype Server 2015 中的 ErrorCategory 表格</span><span class="sxs-lookup"><span data-stu-id="3ee2a-104">ErrorCategory table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="3ee2a-105">ErrorCategory 表格包含每個商務用 Skype Server 2015 診斷分類的易記名稱。</span><span class="sxs-lookup"><span data-stu-id="3ee2a-105">The ErrorCategory table contains the friendly name for each Skype for Business Server 2015 diagnostic classification.</span></span> <span data-ttu-id="3ee2a-106">根據預設, 商務用 Skype Server 2015 使用下列分類:</span><span class="sxs-lookup"><span data-stu-id="3ee2a-106">By default, Skype for Business Server 2015 uses the following classifications:</span></span>
  
- <span data-ttu-id="3ee2a-107">0--成功</span><span class="sxs-lookup"><span data-stu-id="3ee2a-107">0 -- Success</span></span>
    
- <span data-ttu-id="3ee2a-108">1--預期失敗</span><span class="sxs-lookup"><span data-stu-id="3ee2a-108">1 -- Expected failure</span></span>
    
- <span data-ttu-id="3ee2a-109">2-意外失敗</span><span class="sxs-lookup"><span data-stu-id="3ee2a-109">2 - Unexpected failure</span></span>
    
<span data-ttu-id="3ee2a-110">此表格是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="3ee2a-110">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="3ee2a-111">**左欄**</span><span class="sxs-lookup"><span data-stu-id="3ee2a-111">**Column**</span></span>|<span data-ttu-id="3ee2a-112">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="3ee2a-112">**Data Type**</span></span>|<span data-ttu-id="3ee2a-113">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="3ee2a-113">**Key/Index**</span></span>|<span data-ttu-id="3ee2a-114">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="3ee2a-114">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3ee2a-115">**Id**</span><span class="sxs-lookup"><span data-stu-id="3ee2a-115">**CategoryId**</span></span> <br/> |<span data-ttu-id="3ee2a-116">Tinyint</span><span class="sxs-lookup"><span data-stu-id="3ee2a-116">tinyint</span></span>  <br/> |<span data-ttu-id="3ee2a-117">首選</span><span class="sxs-lookup"><span data-stu-id="3ee2a-117">Primary</span></span>  <br/> |<span data-ttu-id="3ee2a-118">分類的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="3ee2a-118">Unique identifier for the classification.</span></span>  <br/> |
|<span data-ttu-id="3ee2a-119">**名稱**</span><span class="sxs-lookup"><span data-stu-id="3ee2a-119">**Name**</span></span> <br/> |<span data-ttu-id="3ee2a-120">Nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="3ee2a-120">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="3ee2a-121">指派給分類的值和易記名稱。</span><span class="sxs-lookup"><span data-stu-id="3ee2a-121">Value and friendly name assigned to the classification.</span></span> <span data-ttu-id="3ee2a-122">允許的值為：</span><span class="sxs-lookup"><span data-stu-id="3ee2a-122">Allowed values are:</span></span> <br/>  <span data-ttu-id="3ee2a-123">0--成功</span><span class="sxs-lookup"><span data-stu-id="3ee2a-123">0 -- Success</span></span> <br/>  <span data-ttu-id="3ee2a-124">1--預期失敗</span><span class="sxs-lookup"><span data-stu-id="3ee2a-124">1 -- Expected failure</span></span> <br/>  <span data-ttu-id="3ee2a-125">2-意外失敗</span><span class="sxs-lookup"><span data-stu-id="3ee2a-125">2 - Unexpected failure</span></span> <br/> |
   

