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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
description: UserStatistics 資料表是支援資料表。 資料表中的每一筆記錄都儲存著個別使用者使用系統的相關資訊。 此表格是在 Microsoft Lync Server 2013 中推出。
ms.openlocfilehash: 048c26279deb6f89e69784d754567dfde84d9983
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814791"
---
# <a name="userstatistics-table"></a><span data-ttu-id="b394c-105">UserStatistics 資料表</span><span class="sxs-lookup"><span data-stu-id="b394c-105">UserStatistics table</span></span>
 
<span data-ttu-id="b394c-106">UserStatistics 資料表是支援資料表。</span><span class="sxs-lookup"><span data-stu-id="b394c-106">The UserStatistics table is a supporting table.</span></span> <span data-ttu-id="b394c-107">資料表中的每一筆記錄都儲存著個別使用者使用系統的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="b394c-107">Each record in the table stores information about an individual user's usage of the system.</span></span> <span data-ttu-id="b394c-108">此表格是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="b394c-108">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="b394c-109">**左欄**</span><span class="sxs-lookup"><span data-stu-id="b394c-109">**Column**</span></span>|<span data-ttu-id="b394c-110">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="b394c-110">**Data Type**</span></span>|<span data-ttu-id="b394c-111">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="b394c-111">**Key/Index**</span></span>|<span data-ttu-id="b394c-112">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="b394c-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b394c-113">**UserId**</span><span class="sxs-lookup"><span data-stu-id="b394c-113">**UserId**</span></span> <br/> |<span data-ttu-id="b394c-114">int</span><span class="sxs-lookup"><span data-stu-id="b394c-114">int</span></span>  <br/> |<span data-ttu-id="b394c-115">首選</span><span class="sxs-lookup"><span data-stu-id="b394c-115">Primary</span></span>  <br/> |<span data-ttu-id="b394c-116">標識此使用者的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="b394c-116">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="b394c-117">**LastLogInTime**</span><span class="sxs-lookup"><span data-stu-id="b394c-117">**LastLogInTime**</span></span> <br/> |<span data-ttu-id="b394c-118">datetime</span><span class="sxs-lookup"><span data-stu-id="b394c-118">datetime</span></span>  <br/> ||<span data-ttu-id="b394c-119">使用者最後一次登入的時間。</span><span class="sxs-lookup"><span data-stu-id="b394c-119">Last time the user logged in.</span></span>  <br/> |
|<span data-ttu-id="b394c-120">**LastConfOrganizedTime**</span><span class="sxs-lookup"><span data-stu-id="b394c-120">**LastConfOrganizedTime**</span></span> <br/> |<span data-ttu-id="b394c-121">datetime</span><span class="sxs-lookup"><span data-stu-id="b394c-121">datetime</span></span>  <br/> ||<span data-ttu-id="b394c-122">使用者最後一次組織會議的時間。</span><span class="sxs-lookup"><span data-stu-id="b394c-122">Last time the user organized a conference.</span></span>  <br/> |
|<span data-ttu-id="b394c-123">**LastCallOrganizerCallFailureTime**</span><span class="sxs-lookup"><span data-stu-id="b394c-123">**LastCallOrganizerCallFailureTime**</span></span> <br/> |<span data-ttu-id="b394c-124">datetime</span><span class="sxs-lookup"><span data-stu-id="b394c-124">datetime</span></span>  <br/> ||<span data-ttu-id="b394c-125">使用者最後一次遇到通話失敗的問題。</span><span class="sxs-lookup"><span data-stu-id="b394c-125">Last time the user experienced a call failure.</span></span>  <br/> |
|<span data-ttu-id="b394c-126">**LastConfOrganizerCallFailureTime**</span><span class="sxs-lookup"><span data-stu-id="b394c-126">**LastConfOrganizerCallFailureTime**</span></span> <br/> |<span data-ttu-id="b394c-127">datetime</span><span class="sxs-lookup"><span data-stu-id="b394c-127">datetime</span></span>  <br/> ||<span data-ttu-id="b394c-128">使用者最後一次遇到「會議召集人」通話失敗的問題。</span><span class="sxs-lookup"><span data-stu-id="b394c-128">Last time the user experienced a call failure as a conference organizer.</span></span>  <br/> |
   

