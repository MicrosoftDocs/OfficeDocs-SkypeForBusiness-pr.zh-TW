---
title: 商務用 Skype Server 2015 中的 ConferenceMessageCount 表格
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
ms.assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
description: 此資料表中的每筆記錄代表一個 IM 會議中的一位使用者，包括該使用者所傳送的訊息數目。 每個會議都是由這個表格中的多筆記錄所代表;每個使用者一個記錄。
ms.openlocfilehash: 66651f798d627ef4ea783c4ecf4e7cb8f1adab81
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815371"
---
# <a name="conferencemessagecount-table-in-skype-for-business-server-2015"></a><span data-ttu-id="c2304-104">商務用 Skype Server 2015 中的 ConferenceMessageCount 表格</span><span class="sxs-lookup"><span data-stu-id="c2304-104">ConferenceMessageCount table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="c2304-105">此資料表中的每筆記錄代表一個 IM 會議中的一位使用者，包括該使用者所傳送的訊息數目。</span><span class="sxs-lookup"><span data-stu-id="c2304-105">Each record in this table represents one user in one IM conference and includes the number of messages sent by that user.</span></span> <span data-ttu-id="c2304-106">每個會議都是由這個表格中的多筆記錄所代表;每個使用者一個記錄。</span><span class="sxs-lookup"><span data-stu-id="c2304-106">Each conference is represented by multiple records in this table; one record for each user.</span></span>
  
|<span data-ttu-id="c2304-107">**左欄**</span><span class="sxs-lookup"><span data-stu-id="c2304-107">**Column**</span></span>|<span data-ttu-id="c2304-108">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="c2304-108">**Data Type**</span></span>|<span data-ttu-id="c2304-109">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="c2304-109">**Key/Index**</span></span>|<span data-ttu-id="c2304-110">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="c2304-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c2304-111">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="c2304-111">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="c2304-112">datetime</span><span class="sxs-lookup"><span data-stu-id="c2304-112">datetime</span></span>  <br/> |<span data-ttu-id="c2304-113">主要、外部</span><span class="sxs-lookup"><span data-stu-id="c2304-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="c2304-114">會議實例的時間。</span><span class="sxs-lookup"><span data-stu-id="c2304-114">Time of conference instance.</span></span> <span data-ttu-id="c2304-115">與**SessionIdSeq**搭配使用，可唯一識別會議實例。</span><span class="sxs-lookup"><span data-stu-id="c2304-115">Used in conjunction with **SessionIdSeq** to uniquely identify a conference instance.</span></span> <span data-ttu-id="c2304-116">如需詳細資訊，請參閱[商務用 Skype Server 2015 中](conferences.md)的 [會議] 表格。</span><span class="sxs-lookup"><span data-stu-id="c2304-116">See the [Conferences table in Skype for Business Server 2015](conferences.md) for more information.</span></span> <br/> |
|<span data-ttu-id="c2304-117">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="c2304-117">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="c2304-118">int</span><span class="sxs-lookup"><span data-stu-id="c2304-118">int</span></span>  <br/> |<span data-ttu-id="c2304-119">主要、外部</span><span class="sxs-lookup"><span data-stu-id="c2304-119">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="c2304-120">識別會議實例的識別碼編號。</span><span class="sxs-lookup"><span data-stu-id="c2304-120">ID number to identify the conference instance.</span></span> <span data-ttu-id="c2304-121">與**SessionIdTime**搭配使用，可唯一識別會議實例。</span><span class="sxs-lookup"><span data-stu-id="c2304-121">Used in conjunction with **SessionIdTime** to uniquely identify a conference instance.</span></span> <span data-ttu-id="c2304-122">如需詳細資訊，請參閱[商務用 Skype Server 2015 中](conferences.md)的 [會議] 表格。</span><span class="sxs-lookup"><span data-stu-id="c2304-122">See the [Conferences table in Skype for Business Server 2015](conferences.md) for more information.</span></span> <br/> |
|<span data-ttu-id="c2304-123">**UserId**</span><span class="sxs-lookup"><span data-stu-id="c2304-123">**UserId**</span></span> <br/> |<span data-ttu-id="c2304-124">int</span><span class="sxs-lookup"><span data-stu-id="c2304-124">int</span></span>  <br/> |<span data-ttu-id="c2304-125">外</span><span class="sxs-lookup"><span data-stu-id="c2304-125">Foreign</span></span>  <br/> |<span data-ttu-id="c2304-126">標識此使用者的唯一編號，從 [[使用者] 資料表](users.md)中引用。</span><span class="sxs-lookup"><span data-stu-id="c2304-126">Unique number identifying this user, referenced from the [Users table](users.md).</span></span>  <br/> |
|<span data-ttu-id="c2304-127">**MessageCount**</span><span class="sxs-lookup"><span data-stu-id="c2304-127">**MessageCount**</span></span> <br/> |<span data-ttu-id="c2304-128">Smallint</span><span class="sxs-lookup"><span data-stu-id="c2304-128">smallint</span></span>  <br/> | <br/> |<span data-ttu-id="c2304-129">此使用者在此會議期間傳送的訊息數目。</span><span class="sxs-lookup"><span data-stu-id="c2304-129">The number of messages sent by this user during this conference.</span></span>  <br/> |
   

