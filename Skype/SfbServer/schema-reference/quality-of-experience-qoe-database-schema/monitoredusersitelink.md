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
localization_priority: Normal
ms.assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
description: MonitoredUserSiteLink 資料表是支援資料表。 每個記錄代表兩個使用者網站之間的一個連結。
ms.openlocfilehash: 789c1a721e1a8c204ff6e214f419de77d1b7f7bf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192657"
---
# <a name="monitoredusersitelink-table"></a><span data-ttu-id="ba9ce-104">MonitoredUserSiteLink 表格</span><span class="sxs-lookup"><span data-stu-id="ba9ce-104">MonitoredUserSiteLink table</span></span>
 
<span data-ttu-id="ba9ce-105">MonitoredUserSiteLink 資料表是支援資料表。</span><span class="sxs-lookup"><span data-stu-id="ba9ce-105">The MonitoredUserSiteLink table is a supporting table.</span></span> <span data-ttu-id="ba9ce-106">每個記錄代表兩個使用者網站之間的一個連結。</span><span class="sxs-lookup"><span data-stu-id="ba9ce-106">Each record represents one link between two user sites.</span></span>
  
|<span data-ttu-id="ba9ce-107">**左欄**</span><span class="sxs-lookup"><span data-stu-id="ba9ce-107">**Column**</span></span>|<span data-ttu-id="ba9ce-108">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="ba9ce-108">**Data Type**</span></span>|<span data-ttu-id="ba9ce-109">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="ba9ce-109">**Key/Index**</span></span>|<span data-ttu-id="ba9ce-110">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="ba9ce-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ba9ce-111">**UserSite1Key**</span><span class="sxs-lookup"><span data-stu-id="ba9ce-111">**UserSite1Key**</span></span> <br/> |<span data-ttu-id="ba9ce-112">int</span><span class="sxs-lookup"><span data-stu-id="ba9ce-112">int</span></span>  <br/> |<span data-ttu-id="ba9ce-113">主要、外部</span><span class="sxs-lookup"><span data-stu-id="ba9ce-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="ba9ce-114">從[UserSite 資料表](usersite.md)中參照。</span><span class="sxs-lookup"><span data-stu-id="ba9ce-114">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="ba9ce-115">**UserSite2Key**</span><span class="sxs-lookup"><span data-stu-id="ba9ce-115">**UserSite2Key**</span></span> <br/> |<span data-ttu-id="ba9ce-116">int</span><span class="sxs-lookup"><span data-stu-id="ba9ce-116">int</span></span>  <br/> |<span data-ttu-id="ba9ce-117">主要、外部</span><span class="sxs-lookup"><span data-stu-id="ba9ce-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="ba9ce-118">從[UserSite 資料表](usersite.md)中引用。</span><span class="sxs-lookup"><span data-stu-id="ba9ce-118">Reference from the [UserSite table](usersite.md).</span></span>  <br/> |
   

