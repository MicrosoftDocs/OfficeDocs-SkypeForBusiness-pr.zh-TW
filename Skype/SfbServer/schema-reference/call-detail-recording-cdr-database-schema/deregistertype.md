---
title: 商務用 Skype Server 2015 中的 DeRegisterType 表格
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
ms.assetid: 09148118-6209-4fd7-a494-99118689a245
description: DeRegisterType 表格是一個靜態表格，可儲存可能的使用者取消註冊類型清單，例如「用戶端初始化」、「註冊到期」或「用戶端已停止回應」。
ms.openlocfilehash: 388aebc1ac180e1298addd54859cff6759b28be0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816073"
---
# <a name="deregistertype-table-in-skype-for-business-server-2015"></a><span data-ttu-id="96359-103">商務用 Skype Server 2015 中的 DeRegisterType 表格</span><span class="sxs-lookup"><span data-stu-id="96359-103">DeRegisterType table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="96359-104">DeRegisterType 表格是一個靜態表格，可儲存可能的使用者取消註冊類型清單，例如「用戶端初始化」、「註冊到期」或「用戶端已停止回應」。</span><span class="sxs-lookup"><span data-stu-id="96359-104">The DeRegisterType table is a static table that stores the list of possible user de-registers types, such as 'client initiated', 'registration expired', or 'client stopped responding.'</span></span>
  
|<span data-ttu-id="96359-105">**欄**</span><span class="sxs-lookup"><span data-stu-id="96359-105">**Column**</span></span>|<span data-ttu-id="96359-106">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="96359-106">**Data Type**</span></span>|<span data-ttu-id="96359-107">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="96359-107">**Key/Index**</span></span>|<span data-ttu-id="96359-108">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="96359-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="96359-109">**DeRegisterTypeId**</span><span class="sxs-lookup"><span data-stu-id="96359-109">**DeRegisterTypeId**</span></span> <br/> |<span data-ttu-id="96359-110">Tinyint</span><span class="sxs-lookup"><span data-stu-id="96359-110">tinyint</span></span>  <br/> |<span data-ttu-id="96359-111">主要</span><span class="sxs-lookup"><span data-stu-id="96359-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="96359-112">**DeRegisterReason**</span><span class="sxs-lookup"><span data-stu-id="96359-112">**DeRegisterReason**</span></span> <br/> |<span data-ttu-id="96359-113">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="96359-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="96359-114">允許的值：</span><span class="sxs-lookup"><span data-stu-id="96359-114">Allowed values:</span></span> <br/>  <span data-ttu-id="96359-115">0 -- 不明</span><span class="sxs-lookup"><span data-stu-id="96359-115">0 -- Unknown</span></span> <br/>  <span data-ttu-id="96359-116">1 -- 由用戶端起始取消註冊</span><span class="sxs-lookup"><span data-stu-id="96359-116">1 -- Client Initiated Deregistration</span></span> <br/>  <span data-ttu-id="96359-117">2 -- 註冊到期</span><span class="sxs-lookup"><span data-stu-id="96359-117">2 -- Registration Expired</span></span> <br/>  <span data-ttu-id="96359-118">3-用戶端已崩潰</span><span class="sxs-lookup"><span data-stu-id="96359-118">3 - Client crashed</span></span> <br/>  <span data-ttu-id="96359-119">4 -- 使用者屬性變更</span><span class="sxs-lookup"><span data-stu-id="96359-119">4 -- User Attributes Changed</span></span> <br/>  <span data-ttu-id="96359-120">5-偏好的註冊機構已變更</span><span class="sxs-lookup"><span data-stu-id="96359-120">5 - Preferred Registrar Changed</span></span> <br/>  <span data-ttu-id="96359-121">6 -- 舊版用戶端處於生存模式</span><span class="sxs-lookup"><span data-stu-id="96359-121">6 -- Legacy Client In Survival Mode</span></span> <br/> |
   

