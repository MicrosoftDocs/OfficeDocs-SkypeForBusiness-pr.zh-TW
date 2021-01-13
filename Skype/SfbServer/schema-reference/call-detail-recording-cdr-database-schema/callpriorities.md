---
title: 商務用 Skype Server 2015 中的 CallPriorities 表格
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
description: CallPriorities 表格是一個靜態表格，它會儲存可能通話優先順序的清單，例如 "緊急"、"緊急" 或 "normal"。
ms.openlocfilehash: 54fdd70dcd939cfeb227862d6152577c4c91d3b3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813433"
---
# <a name="callpriorities-table-in-skype-for-business-server-2015"></a><span data-ttu-id="3443e-103">商務用 Skype Server 2015 中的 CallPriorities 表格</span><span class="sxs-lookup"><span data-stu-id="3443e-103">CallPriorities table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="3443e-104">CallPriorities 表格是一個靜態表格，它會儲存可能通話優先順序的清單，例如 "緊急"、"緊急" 或 "normal"。</span><span class="sxs-lookup"><span data-stu-id="3443e-104">The CallPriorities table is a static table that stores the list of possible call priorities, such as 'emergency', 'urgent', or 'normal'.</span></span>
  
|<span data-ttu-id="3443e-105">**欄**</span><span class="sxs-lookup"><span data-stu-id="3443e-105">**Column**</span></span>|<span data-ttu-id="3443e-106">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="3443e-106">**Data Type**</span></span>|<span data-ttu-id="3443e-107">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="3443e-107">**Key/Index**</span></span>|<span data-ttu-id="3443e-108">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="3443e-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3443e-109">**PriorityId**</span><span class="sxs-lookup"><span data-stu-id="3443e-109">**PriorityId**</span></span> <br/> |<span data-ttu-id="3443e-110">Tinyint</span><span class="sxs-lookup"><span data-stu-id="3443e-110">tinyint</span></span>  <br/> |<span data-ttu-id="3443e-111">主要</span><span class="sxs-lookup"><span data-stu-id="3443e-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="3443e-112">**優先順序**</span><span class="sxs-lookup"><span data-stu-id="3443e-112">**Priority**</span></span> <br/> |<span data-ttu-id="3443e-113">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="3443e-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="3443e-114">允許的值：</span><span class="sxs-lookup"><span data-stu-id="3443e-114">Allowed values:</span></span> <br/>  <span data-ttu-id="3443e-115">0 - 未知</span><span class="sxs-lookup"><span data-stu-id="3443e-115">0 - Unknown</span></span> <br/>  <span data-ttu-id="3443e-116">1-非緊急</span><span class="sxs-lookup"><span data-stu-id="3443e-116">1 - Non-Urgent</span></span> <br/>  <span data-ttu-id="3443e-117">2 - 一般</span><span class="sxs-lookup"><span data-stu-id="3443e-117">2 - Normal</span></span> <br/>  <span data-ttu-id="3443e-118">3 - 急</span><span class="sxs-lookup"><span data-stu-id="3443e-118">3 - Urgent</span></span> <br/>  <span data-ttu-id="3443e-119">4 - 緊急</span><span class="sxs-lookup"><span data-stu-id="3443e-119">4 - Emergency</span></span> <br/> |
   

