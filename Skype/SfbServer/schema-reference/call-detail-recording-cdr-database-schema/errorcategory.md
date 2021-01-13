---
title: 商務用 Skype Server 2015 中的 ErrorCategory 表格
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
description: ErrorCategory 表格包含每個商務用 Skype Server 2015 診斷分類的易記名稱。 依預設，商務用 Skype Server 2015 使用下列類別：
ms.openlocfilehash: ca3719f6d284cf715be1a87b1c7a5dc04ae84b04
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813143"
---
# <a name="errorcategory-table-in-skype-for-business-server-2015"></a><span data-ttu-id="ad867-104">商務用 Skype Server 2015 中的 ErrorCategory 表格</span><span class="sxs-lookup"><span data-stu-id="ad867-104">ErrorCategory table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="ad867-105">ErrorCategory 表格包含每個商務用 Skype Server 2015 診斷分類的易記名稱。</span><span class="sxs-lookup"><span data-stu-id="ad867-105">The ErrorCategory table contains the friendly name for each Skype for Business Server 2015 diagnostic classification.</span></span> <span data-ttu-id="ad867-106">依預設，商務用 Skype Server 2015 使用下列類別：</span><span class="sxs-lookup"><span data-stu-id="ad867-106">By default, Skype for Business Server 2015 uses the following classifications:</span></span>
  
- <span data-ttu-id="ad867-107">0 -- 成功</span><span class="sxs-lookup"><span data-stu-id="ad867-107">0 -- Success</span></span>
    
- <span data-ttu-id="ad867-108">1--預期的失敗</span><span class="sxs-lookup"><span data-stu-id="ad867-108">1 -- Expected failure</span></span>
    
- <span data-ttu-id="ad867-109">2-未預期的失敗</span><span class="sxs-lookup"><span data-stu-id="ad867-109">2 - Unexpected failure</span></span>
    
<span data-ttu-id="ad867-110">此表格已引進 Microsoft Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="ad867-110">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="ad867-111">**欄**</span><span class="sxs-lookup"><span data-stu-id="ad867-111">**Column**</span></span>|<span data-ttu-id="ad867-112">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="ad867-112">**Data Type**</span></span>|<span data-ttu-id="ad867-113">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="ad867-113">**Key/Index**</span></span>|<span data-ttu-id="ad867-114">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="ad867-114">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ad867-115">**CategoryId**</span><span class="sxs-lookup"><span data-stu-id="ad867-115">**CategoryId**</span></span> <br/> |<span data-ttu-id="ad867-116">Tinyint</span><span class="sxs-lookup"><span data-stu-id="ad867-116">tinyint</span></span>  <br/> |<span data-ttu-id="ad867-117">主要</span><span class="sxs-lookup"><span data-stu-id="ad867-117">Primary</span></span>  <br/> |<span data-ttu-id="ad867-118">分類的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="ad867-118">Unique identifier for the classification.</span></span>  <br/> |
|<span data-ttu-id="ad867-119">**名稱**</span><span class="sxs-lookup"><span data-stu-id="ad867-119">**Name**</span></span> <br/> |<span data-ttu-id="ad867-120">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="ad867-120">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="ad867-p103">指派給分類的值和易記名稱。允許的值為：</span><span class="sxs-lookup"><span data-stu-id="ad867-p103">Value and friendly name assigned to the classification. Allowed values are:</span></span> <br/>  <span data-ttu-id="ad867-123">0 -- 成功</span><span class="sxs-lookup"><span data-stu-id="ad867-123">0 -- Success</span></span> <br/>  <span data-ttu-id="ad867-124">1--預期的失敗</span><span class="sxs-lookup"><span data-stu-id="ad867-124">1 -- Expected failure</span></span> <br/>  <span data-ttu-id="ad867-125">2-未預期的失敗</span><span class="sxs-lookup"><span data-stu-id="ad867-125">2 - Unexpected failure</span></span> <br/> |
   

