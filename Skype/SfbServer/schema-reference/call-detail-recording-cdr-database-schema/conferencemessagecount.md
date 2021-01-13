---
title: 商務用 Skype Server 2015 中的 ConferenceMessageCount 表格
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
ms.assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
description: 此資料表中的每一筆記錄都代表一個 IM 會議中的一個使用者，並包含該使用者所傳送的訊息數目。 每個會議都會以此表格中的多筆記錄表示。每一位使用者一筆記錄。
ms.openlocfilehash: b931b45915fc12fb01ea36f81bee62f36914e903
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813273"
---
# <a name="conferencemessagecount-table-in-skype-for-business-server-2015"></a><span data-ttu-id="997ee-104">商務用 Skype Server 2015 中的 ConferenceMessageCount 表格</span><span class="sxs-lookup"><span data-stu-id="997ee-104">ConferenceMessageCount table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="997ee-105">此資料表中的每一筆記錄都代表一個 IM 會議中的一個使用者，並包含該使用者所傳送的訊息數目。</span><span class="sxs-lookup"><span data-stu-id="997ee-105">Each record in this table represents one user in one IM conference and includes the number of messages sent by that user.</span></span> <span data-ttu-id="997ee-106">每個會議都會以此表格中的多筆記錄表示。每一位使用者一筆記錄。</span><span class="sxs-lookup"><span data-stu-id="997ee-106">Each conference is represented by multiple records in this table; one record for each user.</span></span>
  
|<span data-ttu-id="997ee-107">**欄**</span><span class="sxs-lookup"><span data-stu-id="997ee-107">**Column**</span></span>|<span data-ttu-id="997ee-108">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="997ee-108">**Data Type**</span></span>|<span data-ttu-id="997ee-109">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="997ee-109">**Key/Index**</span></span>|<span data-ttu-id="997ee-110">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="997ee-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="997ee-111">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="997ee-111">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="997ee-112">datetime</span><span class="sxs-lookup"><span data-stu-id="997ee-112">datetime</span></span>  <br/> |<span data-ttu-id="997ee-113">主要，外部</span><span class="sxs-lookup"><span data-stu-id="997ee-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="997ee-114">會議執行個體的時間。</span><span class="sxs-lookup"><span data-stu-id="997ee-114">Time of conference instance.</span></span> <span data-ttu-id="997ee-115">與 **SessionIdSeq** 搭配使用，以唯一識別會議實例。</span><span class="sxs-lookup"><span data-stu-id="997ee-115">Used in conjunction with **SessionIdSeq** to uniquely identify a conference instance.</span></span> <span data-ttu-id="997ee-116">如需詳細資訊，請參閱 [商務用 Skype Server 2015 中](conferences.md) 的 [會議] 表格。</span><span class="sxs-lookup"><span data-stu-id="997ee-116">See the [Conferences table in Skype for Business Server 2015](conferences.md) for more information.</span></span> <br/> |
|<span data-ttu-id="997ee-117">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="997ee-117">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="997ee-118">int</span><span class="sxs-lookup"><span data-stu-id="997ee-118">int</span></span>  <br/> |<span data-ttu-id="997ee-119">主要、外部</span><span class="sxs-lookup"><span data-stu-id="997ee-119">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="997ee-120">用於辨識執行個體的 ID 號碼。</span><span class="sxs-lookup"><span data-stu-id="997ee-120">ID number to identify the conference instance.</span></span> <span data-ttu-id="997ee-121">與 **SessionIdTime** 搭配使用，以唯一識別會議實例。</span><span class="sxs-lookup"><span data-stu-id="997ee-121">Used in conjunction with **SessionIdTime** to uniquely identify a conference instance.</span></span> <span data-ttu-id="997ee-122">如需詳細資訊，請參閱 [商務用 Skype Server 2015 中](conferences.md) 的 [會議] 表格。</span><span class="sxs-lookup"><span data-stu-id="997ee-122">See the [Conferences table in Skype for Business Server 2015](conferences.md) for more information.</span></span> <br/> |
|<span data-ttu-id="997ee-123">**UserId**</span><span class="sxs-lookup"><span data-stu-id="997ee-123">**UserId**</span></span> <br/> |<span data-ttu-id="997ee-124">int</span><span class="sxs-lookup"><span data-stu-id="997ee-124">int</span></span>  <br/> |<span data-ttu-id="997ee-125">Foreign</span><span class="sxs-lookup"><span data-stu-id="997ee-125">Foreign</span></span>  <br/> |<span data-ttu-id="997ee-126">用於識別此使用者的唯一號碼，參考來源為 [ [使用者] 表格](users.md)。</span><span class="sxs-lookup"><span data-stu-id="997ee-126">Unique number identifying this user, referenced from the [Users table](users.md).</span></span>  <br/> |
|<span data-ttu-id="997ee-127">**MessageCount**</span><span class="sxs-lookup"><span data-stu-id="997ee-127">**MessageCount**</span></span> <br/> |<span data-ttu-id="997ee-128">Smallint</span><span class="sxs-lookup"><span data-stu-id="997ee-128">smallint</span></span>  <br/> | <br/> |<span data-ttu-id="997ee-129">此會議期間此使用者所傳送的訊息數。</span><span class="sxs-lookup"><span data-stu-id="997ee-129">The number of messages sent by this user during this conference.</span></span>  <br/> |
   

