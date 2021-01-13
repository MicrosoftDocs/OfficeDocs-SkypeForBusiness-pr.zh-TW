---
title: UserStatistics 表格
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
ms.assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
description: UserStatistics 表格是支援的表格。 資料表中的每一筆記錄都儲存了個別使用者對系統使用方式的相關資訊。 此表格已引進 Microsoft Lync Server 2013。
ms.openlocfilehash: 65017c9f807b272097b39bac88c80cc81e617ff4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813103"
---
# <a name="userstatistics-table"></a><span data-ttu-id="8dca2-105">UserStatistics 表格</span><span class="sxs-lookup"><span data-stu-id="8dca2-105">UserStatistics table</span></span>
 
<span data-ttu-id="8dca2-106">UserStatistics 表格是支援的表格。</span><span class="sxs-lookup"><span data-stu-id="8dca2-106">The UserStatistics table is a supporting table.</span></span> <span data-ttu-id="8dca2-107">資料表中的每一筆記錄都儲存了個別使用者對系統使用方式的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="8dca2-107">Each record in the table stores information about an individual user's usage of the system.</span></span> <span data-ttu-id="8dca2-108">此表格已引進 Microsoft Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="8dca2-108">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="8dca2-109">**欄**</span><span class="sxs-lookup"><span data-stu-id="8dca2-109">**Column**</span></span>|<span data-ttu-id="8dca2-110">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="8dca2-110">**Data Type**</span></span>|<span data-ttu-id="8dca2-111">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="8dca2-111">**Key/Index**</span></span>|<span data-ttu-id="8dca2-112">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="8dca2-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8dca2-113">**UserId**</span><span class="sxs-lookup"><span data-stu-id="8dca2-113">**UserId**</span></span> <br/> |<span data-ttu-id="8dca2-114">int</span><span class="sxs-lookup"><span data-stu-id="8dca2-114">int</span></span>  <br/> |<span data-ttu-id="8dca2-115">主要</span><span class="sxs-lookup"><span data-stu-id="8dca2-115">Primary</span></span>  <br/> |<span data-ttu-id="8dca2-116">用於識別此使用者的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="8dca2-116">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="8dca2-117">**LastLogInTime**</span><span class="sxs-lookup"><span data-stu-id="8dca2-117">**LastLogInTime**</span></span> <br/> |<span data-ttu-id="8dca2-118">datetime</span><span class="sxs-lookup"><span data-stu-id="8dca2-118">datetime</span></span>  <br/> ||<span data-ttu-id="8dca2-119">使用者上次登入的時間。</span><span class="sxs-lookup"><span data-stu-id="8dca2-119">Last time the user logged in.</span></span>  <br/> |
|<span data-ttu-id="8dca2-120">**LastConfOrganizedTime**</span><span class="sxs-lookup"><span data-stu-id="8dca2-120">**LastConfOrganizedTime**</span></span> <br/> |<span data-ttu-id="8dca2-121">datetime</span><span class="sxs-lookup"><span data-stu-id="8dca2-121">datetime</span></span>  <br/> ||<span data-ttu-id="8dca2-122">使用者上次組織會議的時間。</span><span class="sxs-lookup"><span data-stu-id="8dca2-122">Last time the user organized a conference.</span></span>  <br/> |
|<span data-ttu-id="8dca2-123">**LastCallOrganizerCallFailureTime**</span><span class="sxs-lookup"><span data-stu-id="8dca2-123">**LastCallOrganizerCallFailureTime**</span></span> <br/> |<span data-ttu-id="8dca2-124">datetime</span><span class="sxs-lookup"><span data-stu-id="8dca2-124">datetime</span></span>  <br/> ||<span data-ttu-id="8dca2-125">上次使用者發生通話失敗的時間。</span><span class="sxs-lookup"><span data-stu-id="8dca2-125">Last time the user experienced a call failure.</span></span>  <br/> |
|<span data-ttu-id="8dca2-126">**LastConfOrganizerCallFailureTime**</span><span class="sxs-lookup"><span data-stu-id="8dca2-126">**LastConfOrganizerCallFailureTime**</span></span> <br/> |<span data-ttu-id="8dca2-127">datetime</span><span class="sxs-lookup"><span data-stu-id="8dca2-127">datetime</span></span>  <br/> ||<span data-ttu-id="8dca2-128">使用者最後一次遇到會議召集人的呼叫失敗。</span><span class="sxs-lookup"><span data-stu-id="8dca2-128">Last time the user experienced a call failure as a conference organizer.</span></span>  <br/> |
   

