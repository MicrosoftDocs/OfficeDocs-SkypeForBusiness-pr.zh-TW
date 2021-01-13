---
title: MonitoredUserSiteLink 表格
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
ms.assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
description: MonitoredUserSiteLink 表格是支援的表格。 每筆記錄代表兩個使用者網站間的一個連結。
ms.openlocfilehash: 88b4d385f3c96dc93a519274c584e1f99584982f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806353"
---
# <a name="monitoredusersitelink-table"></a><span data-ttu-id="219a2-104">MonitoredUserSiteLink 表格</span><span class="sxs-lookup"><span data-stu-id="219a2-104">MonitoredUserSiteLink table</span></span>
 
<span data-ttu-id="219a2-p102">MonitoredUserSiteLink 表格是一種支援資料表，其中的每一項記錄都代表兩個使用者網站間的連結。</span><span class="sxs-lookup"><span data-stu-id="219a2-p102">The MonitoredUserSiteLink table is a supporting table. Each record represents one link between two user sites.</span></span>
  
|<span data-ttu-id="219a2-107">**欄**</span><span class="sxs-lookup"><span data-stu-id="219a2-107">**Column**</span></span>|<span data-ttu-id="219a2-108">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="219a2-108">**Data Type**</span></span>|<span data-ttu-id="219a2-109">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="219a2-109">**Key/Index**</span></span>|<span data-ttu-id="219a2-110">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="219a2-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="219a2-111">**UserSite1Key**</span><span class="sxs-lookup"><span data-stu-id="219a2-111">**UserSite1Key**</span></span> <br/> |<span data-ttu-id="219a2-112">int</span><span class="sxs-lookup"><span data-stu-id="219a2-112">int</span></span>  <br/> |<span data-ttu-id="219a2-113">主要、外部</span><span class="sxs-lookup"><span data-stu-id="219a2-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="219a2-114">從 [UserSite 表格](usersite.md)中參照。</span><span class="sxs-lookup"><span data-stu-id="219a2-114">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="219a2-115">**UserSite2Key**</span><span class="sxs-lookup"><span data-stu-id="219a2-115">**UserSite2Key**</span></span> <br/> |<span data-ttu-id="219a2-116">int</span><span class="sxs-lookup"><span data-stu-id="219a2-116">int</span></span>  <br/> |<span data-ttu-id="219a2-117">主要、外部</span><span class="sxs-lookup"><span data-stu-id="219a2-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="219a2-118">[UserSite 表格](usersite.md)中的參照。</span><span class="sxs-lookup"><span data-stu-id="219a2-118">Reference from the [UserSite table](usersite.md).</span></span>  <br/> |
   

