---
title: UserStatistics 資料表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
description: UserStatistics 資料表是支援資料表。 資料表中的每一筆記錄都儲存著個別使用者使用系統的相關資訊。 此表格是在 Microsoft Lync Server 2013 中推出。
ms.openlocfilehash: 4801ed2611f3a078811f22f7e5a1cc1a797f6805
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192774"
---
# <a name="userstatistics-table"></a><span data-ttu-id="bb97f-105">UserStatistics 資料表</span><span class="sxs-lookup"><span data-stu-id="bb97f-105">UserStatistics table</span></span>
 
<span data-ttu-id="bb97f-106">UserStatistics 資料表是支援資料表。</span><span class="sxs-lookup"><span data-stu-id="bb97f-106">The UserStatistics table is a supporting table.</span></span> <span data-ttu-id="bb97f-107">資料表中的每一筆記錄都儲存著個別使用者使用系統的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="bb97f-107">Each record in the table stores information about an individual user's usage of the system.</span></span> <span data-ttu-id="bb97f-108">此表格是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="bb97f-108">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="bb97f-109">**左欄**</span><span class="sxs-lookup"><span data-stu-id="bb97f-109">**Column**</span></span>|<span data-ttu-id="bb97f-110">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="bb97f-110">**Data Type**</span></span>|<span data-ttu-id="bb97f-111">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="bb97f-111">**Key/Index**</span></span>|<span data-ttu-id="bb97f-112">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="bb97f-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="bb97f-113">**UserId**</span><span class="sxs-lookup"><span data-stu-id="bb97f-113">**UserId**</span></span> <br/> |<span data-ttu-id="bb97f-114">int</span><span class="sxs-lookup"><span data-stu-id="bb97f-114">int</span></span>  <br/> |<span data-ttu-id="bb97f-115">首選</span><span class="sxs-lookup"><span data-stu-id="bb97f-115">Primary</span></span>  <br/> |<span data-ttu-id="bb97f-116">標識此使用者的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="bb97f-116">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="bb97f-117">**LastLogInTime**</span><span class="sxs-lookup"><span data-stu-id="bb97f-117">**LastLogInTime**</span></span> <br/> |<span data-ttu-id="bb97f-118">datetime</span><span class="sxs-lookup"><span data-stu-id="bb97f-118">datetime</span></span>  <br/> ||<span data-ttu-id="bb97f-119">使用者最後一次登入的時間。</span><span class="sxs-lookup"><span data-stu-id="bb97f-119">Last time the user logged in.</span></span>  <br/> |
|<span data-ttu-id="bb97f-120">**LastConfOrganizedTime**</span><span class="sxs-lookup"><span data-stu-id="bb97f-120">**LastConfOrganizedTime**</span></span> <br/> |<span data-ttu-id="bb97f-121">datetime</span><span class="sxs-lookup"><span data-stu-id="bb97f-121">datetime</span></span>  <br/> ||<span data-ttu-id="bb97f-122">使用者最後一次組織會議的時間。</span><span class="sxs-lookup"><span data-stu-id="bb97f-122">Last time the user organized a conference.</span></span>  <br/> |
|<span data-ttu-id="bb97f-123">**LastCallOrganizerCallFailureTime**</span><span class="sxs-lookup"><span data-stu-id="bb97f-123">**LastCallOrganizerCallFailureTime**</span></span> <br/> |<span data-ttu-id="bb97f-124">datetime</span><span class="sxs-lookup"><span data-stu-id="bb97f-124">datetime</span></span>  <br/> ||<span data-ttu-id="bb97f-125">使用者最後一次遇到通話失敗的問題。</span><span class="sxs-lookup"><span data-stu-id="bb97f-125">Last time the user experienced a call failure.</span></span>  <br/> |
|<span data-ttu-id="bb97f-126">**LastConfOrganizerCallFailureTime**</span><span class="sxs-lookup"><span data-stu-id="bb97f-126">**LastConfOrganizerCallFailureTime**</span></span> <br/> |<span data-ttu-id="bb97f-127">datetime</span><span class="sxs-lookup"><span data-stu-id="bb97f-127">datetime</span></span>  <br/> ||<span data-ttu-id="bb97f-128">使用者最後一次遇到「會議召集人」通話失敗的問題。</span><span class="sxs-lookup"><span data-stu-id="bb97f-128">Last time the user experienced a call failure as a conference organizer.</span></span>  <br/> |
   

