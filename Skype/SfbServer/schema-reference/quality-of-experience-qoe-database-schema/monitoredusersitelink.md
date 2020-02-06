---
title: MonitoredUserSiteLink 表格
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
ms.assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
description: MonitoredUserSiteLink 資料表是支援資料表。 每個記錄代表兩個使用者網站之間的一個連結。
ms.openlocfilehash: 2cf229947da143fb01b3009020cfa432a4b558a0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41807791"
---
# <a name="monitoredusersitelink-table"></a><span data-ttu-id="bb0d4-104">MonitoredUserSiteLink 表格</span><span class="sxs-lookup"><span data-stu-id="bb0d4-104">MonitoredUserSiteLink table</span></span>
 
<span data-ttu-id="bb0d4-105">MonitoredUserSiteLink 資料表是支援資料表。</span><span class="sxs-lookup"><span data-stu-id="bb0d4-105">The MonitoredUserSiteLink table is a supporting table.</span></span> <span data-ttu-id="bb0d4-106">每個記錄代表兩個使用者網站之間的一個連結。</span><span class="sxs-lookup"><span data-stu-id="bb0d4-106">Each record represents one link between two user sites.</span></span>
  
|<span data-ttu-id="bb0d4-107">**左欄**</span><span class="sxs-lookup"><span data-stu-id="bb0d4-107">**Column**</span></span>|<span data-ttu-id="bb0d4-108">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="bb0d4-108">**Data Type**</span></span>|<span data-ttu-id="bb0d4-109">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="bb0d4-109">**Key/Index**</span></span>|<span data-ttu-id="bb0d4-110">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="bb0d4-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="bb0d4-111">**UserSite1Key**</span><span class="sxs-lookup"><span data-stu-id="bb0d4-111">**UserSite1Key**</span></span> <br/> |<span data-ttu-id="bb0d4-112">int</span><span class="sxs-lookup"><span data-stu-id="bb0d4-112">int</span></span>  <br/> |<span data-ttu-id="bb0d4-113">主要、外部</span><span class="sxs-lookup"><span data-stu-id="bb0d4-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="bb0d4-114">從[UserSite 資料表](usersite.md)中參照。</span><span class="sxs-lookup"><span data-stu-id="bb0d4-114">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="bb0d4-115">**UserSite2Key**</span><span class="sxs-lookup"><span data-stu-id="bb0d4-115">**UserSite2Key**</span></span> <br/> |<span data-ttu-id="bb0d4-116">int</span><span class="sxs-lookup"><span data-stu-id="bb0d4-116">int</span></span>  <br/> |<span data-ttu-id="bb0d4-117">主要、外部</span><span class="sxs-lookup"><span data-stu-id="bb0d4-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="bb0d4-118">從[UserSite 資料表](usersite.md)中引用。</span><span class="sxs-lookup"><span data-stu-id="bb0d4-118">Reference from the [UserSite table](usersite.md).</span></span>  <br/> |
   

