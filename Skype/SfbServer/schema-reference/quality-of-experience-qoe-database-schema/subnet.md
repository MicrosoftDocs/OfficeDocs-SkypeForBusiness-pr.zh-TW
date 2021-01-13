---
title: Subnet 表格
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
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: Subnet 表格是一種支援資料表。 每筆記錄代表在網路組態設定中定義的一個子網路。
ms.openlocfilehash: b4683c654d5d188d2f5096dd7ec9da124001f68b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831333"
---
# <a name="subnet-table"></a><span data-ttu-id="3e691-104">Subnet 表格</span><span class="sxs-lookup"><span data-stu-id="3e691-104">Subnet table</span></span>
 
<span data-ttu-id="3e691-p102">Subnet 表格是一種支援資料表。每筆記錄代表在網路組態設定中定義的一個子網路。</span><span class="sxs-lookup"><span data-stu-id="3e691-p102">The Subnet table is a supporting table. Each record represents one subnet defined in network configuration setting.</span></span>
  
|<span data-ttu-id="3e691-107">**欄**</span><span class="sxs-lookup"><span data-stu-id="3e691-107">**Column**</span></span>|<span data-ttu-id="3e691-108">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="3e691-108">**Data Type**</span></span>|<span data-ttu-id="3e691-109">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="3e691-109">**Key/Index**</span></span>|<span data-ttu-id="3e691-110">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="3e691-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3e691-111">**SubnetIP**</span><span class="sxs-lookup"><span data-stu-id="3e691-111">**SubnetIP**</span></span> <br/> |<span data-ttu-id="3e691-112">int</span><span class="sxs-lookup"><span data-stu-id="3e691-112">int</span></span>  <br/> |<span data-ttu-id="3e691-113">主要、外部</span><span class="sxs-lookup"><span data-stu-id="3e691-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="3e691-114">子網路 IP 的整數表示。</span><span class="sxs-lookup"><span data-stu-id="3e691-114">Integer representation for the subnet IP.</span></span>  <br/> |
|<span data-ttu-id="3e691-115">**SubnetMask**</span><span class="sxs-lookup"><span data-stu-id="3e691-115">**SubnetMask**</span></span> <br/> |<span data-ttu-id="3e691-116">int</span><span class="sxs-lookup"><span data-stu-id="3e691-116">int</span></span>  <br/> ||<span data-ttu-id="3e691-117">子網路遮罩。</span><span class="sxs-lookup"><span data-stu-id="3e691-117">Subnet mask.</span></span>  <br/> |
|<span data-ttu-id="3e691-118">**UserSiteKey**</span><span class="sxs-lookup"><span data-stu-id="3e691-118">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="3e691-119">int</span><span class="sxs-lookup"><span data-stu-id="3e691-119">int</span></span>  <br/> |<span data-ttu-id="3e691-120">Foreign</span><span class="sxs-lookup"><span data-stu-id="3e691-120">Foreign</span></span>  <br/> |<span data-ttu-id="3e691-121">從 [UserSite 表格](usersite.md)中參照。</span><span class="sxs-lookup"><span data-stu-id="3e691-121">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="3e691-122">**SubnetDescription**</span><span class="sxs-lookup"><span data-stu-id="3e691-122">**SubnetDescription**</span></span> <br/> |<span data-ttu-id="3e691-123">Nvarchar (512) </span><span class="sxs-lookup"><span data-stu-id="3e691-123">nvarchar(512)</span></span>  <br/> ||<span data-ttu-id="3e691-124">子網路的描述。</span><span class="sxs-lookup"><span data-stu-id="3e691-124">The description for the subnet.</span></span>  <br/> |
   

