---
title: UserSite 表格
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
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: UserSite 表格是支援的表格。 每筆記錄代表網路設定設定中所定義的一個使用者網站。
ms.openlocfilehash: 88df08875ea3254ee355a96aa3b12d3ee7f5ccaf
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49799913"
---
# <a name="usersite-table"></a><span data-ttu-id="7979e-104">UserSite 表格</span><span class="sxs-lookup"><span data-stu-id="7979e-104">UserSite table</span></span>
 
<span data-ttu-id="7979e-p102">UserSite 表格是一種支援資料表，其中的每一項記錄都代表網路組態設定中定義的一個使用者網站。</span><span class="sxs-lookup"><span data-stu-id="7979e-p102">The UserSite table is a supporting table. Each record represents one user site defined in network configuration setting.</span></span>
  
|<span data-ttu-id="7979e-107">**欄**</span><span class="sxs-lookup"><span data-stu-id="7979e-107">**Column**</span></span>|<span data-ttu-id="7979e-108">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="7979e-108">**Data Type**</span></span>|<span data-ttu-id="7979e-109">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="7979e-109">**Key/Index**</span></span>|<span data-ttu-id="7979e-110">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="7979e-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7979e-111">**UserSiteKey**</span><span class="sxs-lookup"><span data-stu-id="7979e-111">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="7979e-112">int</span><span class="sxs-lookup"><span data-stu-id="7979e-112">int</span></span>  <br/> |<span data-ttu-id="7979e-113">主要</span><span class="sxs-lookup"><span data-stu-id="7979e-113">Primary</span></span>  <br/> |<span data-ttu-id="7979e-114">用於識別使用者網站的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="7979e-114">Unique number identifying the user site.</span></span>  <br/> |
|<span data-ttu-id="7979e-115">**UserSiteName**</span><span class="sxs-lookup"><span data-stu-id="7979e-115">**UserSiteName**</span></span> <br/> |<span data-ttu-id="7979e-116">Nvarchar (128) </span><span class="sxs-lookup"><span data-stu-id="7979e-116">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="7979e-117">Unique</span><span class="sxs-lookup"><span data-stu-id="7979e-117">Unique</span></span>  <br/> |<span data-ttu-id="7979e-118">使用者網站的名稱。</span><span class="sxs-lookup"><span data-stu-id="7979e-118">User site's name.</span></span>  <br/> |
|<span data-ttu-id="7979e-119">**RegionKey**</span><span class="sxs-lookup"><span data-stu-id="7979e-119">**RegionKey**</span></span> <br/> |<span data-ttu-id="7979e-120">int</span><span class="sxs-lookup"><span data-stu-id="7979e-120">int</span></span>  <br/> |<span data-ttu-id="7979e-121">Foreign</span><span class="sxs-lookup"><span data-stu-id="7979e-121">Foreign</span></span>  <br/> |<span data-ttu-id="7979e-122">參照自 [地區表](region.md)。</span><span class="sxs-lookup"><span data-stu-id="7979e-122">Referenced from [Region table](region.md).</span></span>  <br/> |
   

