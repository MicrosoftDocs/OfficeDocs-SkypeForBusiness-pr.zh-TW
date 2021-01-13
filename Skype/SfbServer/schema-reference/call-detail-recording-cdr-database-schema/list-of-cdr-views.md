---
title: CDR 檢視清單
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2f72aead-d1da-4185-b75c-f6c31d76a6b3
description: 檢視讓您可以輕鬆取得從 CDR 資料庫傳回資料時最常見情況的資訊。 建議您使用 [視圖] 來建立自訂報表，而不是使用實際的 CDR 資料庫資料表;這是因為資料庫檢視很可能會與未來的版本保持向後相容性。
ms.openlocfilehash: 0a3b40c9b31bb521075e78a1a8d46479200249d5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813153"
---
# <a name="list-of-cdr-views"></a><span data-ttu-id="2023d-104">CDR 檢視清單</span><span class="sxs-lookup"><span data-stu-id="2023d-104">List of CDR views</span></span>
 
<span data-ttu-id="2023d-105">檢視讓您可以輕鬆取得從 CDR 資料庫傳回資料時最常見情況的資訊。</span><span class="sxs-lookup"><span data-stu-id="2023d-105">Views provide an easy way to access information about the most common scenarios used for returning data from the CDR database.</span></span> <span data-ttu-id="2023d-106">建議您使用 [視圖] 來建立自訂報表，而不是使用實際的 CDR 資料庫資料表;這是因為資料庫檢視很可能會與未來的版本保持向後相容性。</span><span class="sxs-lookup"><span data-stu-id="2023d-106">It is recommended that you use views for building custom reports instead of using the actual CDR database tables ; that's because the database views are more likely to maintain backwards compatibility with future releases.</span></span>
  
|<span data-ttu-id="2023d-107">**視圖名稱**</span><span class="sxs-lookup"><span data-stu-id="2023d-107">**View Name**</span></span>|<span data-ttu-id="2023d-108">**描述**</span><span class="sxs-lookup"><span data-stu-id="2023d-108">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="2023d-109">ClientVersions view</span><span class="sxs-lookup"><span data-stu-id="2023d-109">ClientVersions view</span></span>](clientversions-0.md) <br/> |<span data-ttu-id="2023d-110">傳回通訊工作階段中使用的用戶端軟體/裝置資訊。</span><span class="sxs-lookup"><span data-stu-id="2023d-110">Returns information about the client software/devices used in a communication session.</span></span>  <br/> |
|[<span data-ttu-id="2023d-111">ConferenceMessageCount view</span><span class="sxs-lookup"><span data-stu-id="2023d-111">ConferenceMessageCount view</span></span>](conferencemessagecount-0.md) <br/> |<span data-ttu-id="2023d-112">傳回會議中使用者傳送的訊息數量資訊。</span><span class="sxs-lookup"><span data-stu-id="2023d-112">Returns information about the number of messages sent by users in a conference.</span></span>  <br/> |
|[<span data-ttu-id="2023d-113">會議視圖</span><span class="sxs-lookup"><span data-stu-id="2023d-113">Conferences view</span></span>](conferences-0.md) <br/> |<span data-ttu-id="2023d-114">傳回會議資訊，包含開始時間、結束時間以及唯一會議召集人。</span><span class="sxs-lookup"><span data-stu-id="2023d-114">Returns conference information, including start time, end time, and conference organizer.</span></span>  <br/> |
|[<span data-ttu-id="2023d-115">ConferenceSessionDetails view</span><span class="sxs-lookup"><span data-stu-id="2023d-115">ConferenceSessionDetails view</span></span>](conferencesessiondetails.md) <br/> |<span data-ttu-id="2023d-116">傳回所有會議工作階段的工作階段詳細資料，包含開始及結束時間、使用者 ID、回應碼及診斷 ID。</span><span class="sxs-lookup"><span data-stu-id="2023d-116">Returns session details for all conferencing sessions, including start and end time, user IDs, response codes, and diagnostic IDs.</span></span>  <br/> |
|[<span data-ttu-id="2023d-117">ConferenceUris view</span><span class="sxs-lookup"><span data-stu-id="2023d-117">ConferenceUris view</span></span>](conferenceuris-0.md) <br/> |<span data-ttu-id="2023d-118">傳回會議中使用的會議 URI 資訊</span><span class="sxs-lookup"><span data-stu-id="2023d-118">Returns information about conference URIs used in a conference</span></span>  <br/> |
|[<span data-ttu-id="2023d-119">ErrorReport view</span><span class="sxs-lookup"><span data-stu-id="2023d-119">ErrorReport view</span></span>](errorreport-0.md) <br/> |<span data-ttu-id="2023d-120">傳回工作階段期間發生之錯誤的資訊。</span><span class="sxs-lookup"><span data-stu-id="2023d-120">Returns information about errors that occurred during a session.</span></span>  <br/> |
|[<span data-ttu-id="2023d-121">FileTransfers view</span><span class="sxs-lookup"><span data-stu-id="2023d-121">FileTransfers view</span></span>](filetransfers.md) <br/> |<span data-ttu-id="2023d-122">傳回檔案傳輸工作階段的資訊，包含檔案名稱以及是否接受、拒絕或取消傳輸。</span><span class="sxs-lookup"><span data-stu-id="2023d-122">Returns information about file transfer sessions, including the file name and whether the transfer was accepted, rejected, or cancelled.</span></span>  <br/> |
|[<span data-ttu-id="2023d-123">FocusJoinsAndLeaves view</span><span class="sxs-lookup"><span data-stu-id="2023d-123">FocusJoinsAndLeaves view</span></span>](focusjoinsandleaves-0.md) <br/> |<span data-ttu-id="2023d-124">傳回會議加入及會議離開活動的資訊</span><span class="sxs-lookup"><span data-stu-id="2023d-124">Returns information about conference join and leave activities.</span></span>  <br/> |
|[<span data-ttu-id="2023d-125">McuJoinsAndLeaves view</span><span class="sxs-lookup"><span data-stu-id="2023d-125">McuJoinsAndLeaves view</span></span>](mcujoinsandleaves-0.md) <br/> |<span data-ttu-id="2023d-126">傳回會議加入及會議離開活動的合併資訊 (每次會議加入均有對應的會議離開作為搭配)。</span><span class="sxs-lookup"><span data-stu-id="2023d-126">Returns combined information about conference join and leave activities (each conference join is paired with the corresponding conference leave).</span></span>  <br/> |
|[<span data-ttu-id="2023d-127">Mcus view</span><span class="sxs-lookup"><span data-stu-id="2023d-127">Mcus view</span></span>](mcus-0.md) <br/> |<span data-ttu-id="2023d-128">傳回會議伺服器的資訊。</span><span class="sxs-lookup"><span data-stu-id="2023d-128">Returns information about Conferencing servers.</span></span>  <br/> |
|[<span data-ttu-id="2023d-129">媒體視圖</span><span class="sxs-lookup"><span data-stu-id="2023d-129">Media view</span></span>](media-0.md) <br/> |<span data-ttu-id="2023d-130">傳回對等通訊工作階段中使用的媒體類型資訊。</span><span class="sxs-lookup"><span data-stu-id="2023d-130">Returns information about the types of media used in peer-to-peer communication sessions.</span></span>  <br/> |
|[<span data-ttu-id="2023d-131">ProgressReport view</span><span class="sxs-lookup"><span data-stu-id="2023d-131">ProgressReport view</span></span>](progressreport-0.md) <br/> |<span data-ttu-id="2023d-132">傳回已完成之工作階段的資訊。</span><span class="sxs-lookup"><span data-stu-id="2023d-132">Returns information about completed sessions.</span></span>  <br/> |
|[<span data-ttu-id="2023d-133">註冊視圖</span><span class="sxs-lookup"><span data-stu-id="2023d-133">Registration view</span></span>](registration-0.md) <br/> |<span data-ttu-id="2023d-134">傳回與商務用 Skype Server 2015 有關的註冊資訊。</span><span class="sxs-lookup"><span data-stu-id="2023d-134">Returns information about registrations with Skype for Business Server 2015.</span></span>  <br/> |
|[<span data-ttu-id="2023d-135">SessionDetails view</span><span class="sxs-lookup"><span data-stu-id="2023d-135">SessionDetails view</span></span>](sessiondetails-0.md) <br/> |<span data-ttu-id="2023d-136">傳回對等工作階段的資訊，包含 VoIP 對 VoIP 電話、雙方 IM 工作階段，或其他對等通訊工作階段。</span><span class="sxs-lookup"><span data-stu-id="2023d-136">Returns information about peer-to-peer sessions, including VoIP-VoIP phone calls, two-party IM sessions, or other peer-to-peer communication sessions.</span></span>  <br/> |
|[<span data-ttu-id="2023d-137">使用者視圖</span><span class="sxs-lookup"><span data-stu-id="2023d-137">User view</span></span>](user.md) <br/> |<span data-ttu-id="2023d-138">傳回已加入通訊工作階段之使用者的資訊。</span><span class="sxs-lookup"><span data-stu-id="2023d-138">Returns information about the users who have participated in communication sessions.</span></span>  <br/> |
|[<span data-ttu-id="2023d-139">VoIPDetails view</span><span class="sxs-lookup"><span data-stu-id="2023d-139">VoIPDetails view</span></span>](voipdetails.md) <br/> |<span data-ttu-id="2023d-140">傳回至少包含一位 VoIP 使用者之對等工作階段的資訊。</span><span class="sxs-lookup"><span data-stu-id="2023d-140">Returns information for peer-to-peer sessions involving at least one VoIP (Voice over IO) user.</span></span>  <br/> |
   

