---
title: 商務用 Skype Server 2015 中的 DeRegisterType 表格
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
ms.assetid: 09148118-6209-4fd7-a494-99118689a245
description: DeRegisterType 資料表是一個靜態資料表，它儲存可能的使用者取消註冊類型（例如「用戶端已啟動」、「註冊已過期」或「用戶端已停止回應」）清單。
ms.openlocfilehash: ae9afafe91336b1e5c74fd0a854e2975a3b4ba8e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815291"
---
# <a name="deregistertype-table-in-skype-for-business-server-2015"></a><span data-ttu-id="7f91c-103">商務用 Skype Server 2015 中的 DeRegisterType 表格</span><span class="sxs-lookup"><span data-stu-id="7f91c-103">DeRegisterType table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="7f91c-104">DeRegisterType 資料表是一個靜態資料表，它儲存可能的使用者取消註冊類型（例如「用戶端已啟動」、「註冊已過期」或「用戶端已停止回應」）清單。</span><span class="sxs-lookup"><span data-stu-id="7f91c-104">The DeRegisterType table is a static table that stores the list of possible user de-registers types, such as 'client initiated', 'registration expired', or 'client stopped responding.'</span></span>
  
|<span data-ttu-id="7f91c-105">**左欄**</span><span class="sxs-lookup"><span data-stu-id="7f91c-105">**Column**</span></span>|<span data-ttu-id="7f91c-106">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="7f91c-106">**Data Type**</span></span>|<span data-ttu-id="7f91c-107">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="7f91c-107">**Key/Index**</span></span>|<span data-ttu-id="7f91c-108">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="7f91c-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7f91c-109">**DeRegisterTypeId**</span><span class="sxs-lookup"><span data-stu-id="7f91c-109">**DeRegisterTypeId**</span></span> <br/> |<span data-ttu-id="7f91c-110">Tinyint</span><span class="sxs-lookup"><span data-stu-id="7f91c-110">tinyint</span></span>  <br/> |<span data-ttu-id="7f91c-111">首選</span><span class="sxs-lookup"><span data-stu-id="7f91c-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="7f91c-112">**DeRegisterReason**</span><span class="sxs-lookup"><span data-stu-id="7f91c-112">**DeRegisterReason**</span></span> <br/> |<span data-ttu-id="7f91c-113">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="7f91c-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="7f91c-114">允許的值：</span><span class="sxs-lookup"><span data-stu-id="7f91c-114">Allowed values:</span></span> <br/>  <span data-ttu-id="7f91c-115">0--未知</span><span class="sxs-lookup"><span data-stu-id="7f91c-115">0 -- Unknown</span></span> <br/>  <span data-ttu-id="7f91c-116">1--用戶端啟動取消註冊</span><span class="sxs-lookup"><span data-stu-id="7f91c-116">1 -- Client Initiated Deregistration</span></span> <br/>  <span data-ttu-id="7f91c-117">2--註冊已過期</span><span class="sxs-lookup"><span data-stu-id="7f91c-117">2 -- Registration Expired</span></span> <br/>  <span data-ttu-id="7f91c-118">3-用戶端發生故障</span><span class="sxs-lookup"><span data-stu-id="7f91c-118">3 - Client crashed</span></span> <br/>  <span data-ttu-id="7f91c-119">4--使用者屬性已變更</span><span class="sxs-lookup"><span data-stu-id="7f91c-119">4 -- User Attributes Changed</span></span> <br/>  <span data-ttu-id="7f91c-120">5-首選的註冊機構已變更</span><span class="sxs-lookup"><span data-stu-id="7f91c-120">5 - Preferred Registrar Changed</span></span> <br/>  <span data-ttu-id="7f91c-121">6--生存模式中的舊版用戶端</span><span class="sxs-lookup"><span data-stu-id="7f91c-121">6 -- Legacy Client In Survival Mode</span></span> <br/> |
   

