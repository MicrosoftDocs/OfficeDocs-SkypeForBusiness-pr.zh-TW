---
title: 商務用 Skype Server 2015 中的 [位置] 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 78dc1b14-5394-4f8e-89d3-4ba593272a04
description: 每個記錄代表緊急呼叫中的一個位置參照，就像是 E9-1-1 通話。
ms.openlocfilehash: a1dd7dfdf84ef196b24fa97b1b24950c326b0241
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815111"
---
# <a name="locations-table-in-skype-for-business-server-2015"></a><span data-ttu-id="d8d29-103">商務用 Skype Server 2015 中的 [位置] 表格</span><span class="sxs-lookup"><span data-stu-id="d8d29-103">Locations table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="d8d29-104">每個記錄代表緊急呼叫中的一個位置參照，就像是 E9-1-1 通話。</span><span class="sxs-lookup"><span data-stu-id="d8d29-104">Each record represents one location reference in an emergency call, like an E9-1-1 call.</span></span>
  
|<span data-ttu-id="d8d29-105">**左欄**</span><span class="sxs-lookup"><span data-stu-id="d8d29-105">**Column**</span></span>|<span data-ttu-id="d8d29-106">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="d8d29-106">**Data Type**</span></span>|<span data-ttu-id="d8d29-107">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="d8d29-107">**Key/Index**</span></span>|<span data-ttu-id="d8d29-108">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="d8d29-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d8d29-109">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="d8d29-109">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="d8d29-110">datetime</span><span class="sxs-lookup"><span data-stu-id="d8d29-110">datetime</span></span>  <br/> |<span data-ttu-id="d8d29-111">主要、外部</span><span class="sxs-lookup"><span data-stu-id="d8d29-111">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="d8d29-112">會話要求的時間。</span><span class="sxs-lookup"><span data-stu-id="d8d29-112">Time of session request.</span></span> <span data-ttu-id="d8d29-113">與**SessionIdSeq**搭配使用，可唯一識別會話。</span><span class="sxs-lookup"><span data-stu-id="d8d29-113">Used in conjunction with **SessionIdSeq** to uniquely identify a session.</span></span> <span data-ttu-id="d8d29-114">如需詳細資訊，請參閱[商務用 Skype Server 2015 中](dialogs.md)的 [對話方塊] 表格。</span><span class="sxs-lookup"><span data-stu-id="d8d29-114">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="d8d29-115">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="d8d29-115">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="d8d29-116">int</span><span class="sxs-lookup"><span data-stu-id="d8d29-116">int</span></span>  <br/> |<span data-ttu-id="d8d29-117">主要、外部</span><span class="sxs-lookup"><span data-stu-id="d8d29-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="d8d29-118">識別會話的識別碼編號。</span><span class="sxs-lookup"><span data-stu-id="d8d29-118">ID number to identify the session.</span></span> <span data-ttu-id="d8d29-119">與**SessionIdTime**搭配使用，可唯一識別會話。</span><span class="sxs-lookup"><span data-stu-id="d8d29-119">Used in conjunction with **SessionIdTime** to uniquely identify a session.</span></span> <span data-ttu-id="d8d29-120">如需詳細資訊，請參閱[商務用 Skype Server 2015 中](dialogs.md)的 [對話方塊] 表格。</span><span class="sxs-lookup"><span data-stu-id="d8d29-120">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="d8d29-121">**位置**</span><span class="sxs-lookup"><span data-stu-id="d8d29-121">**Location**</span></span> <br/> |<span data-ttu-id="d8d29-122">Nvarchar （max）</span><span class="sxs-lookup"><span data-stu-id="d8d29-122">nvarchar(max)</span></span>  <br/> ||<span data-ttu-id="d8d29-123">緊急通話的位置。</span><span class="sxs-lookup"><span data-stu-id="d8d29-123">Location of emergency call.</span></span>  <br/> |
   

