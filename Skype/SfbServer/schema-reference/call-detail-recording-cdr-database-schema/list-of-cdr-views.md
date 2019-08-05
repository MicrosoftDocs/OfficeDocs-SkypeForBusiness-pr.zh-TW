---
title: CDR 視圖清單
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2f72aead-d1da-4185-b75c-f6c31d76a6b3
description: '[視圖] 提供一種簡單的方式, 可存取從 CDR 資料庫傳回資料最常見的案例資訊。 建議您使用 [視圖] 來建立自訂報表, 而不是使用實際的 CDR 資料庫資料表;這是因為資料庫檢視更可能會維持與未來版本的向後相容性。'
ms.openlocfilehash: e1a7926108c2e27ecc69c5717867b9c18f8b47ad
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192841"
---
# <a name="list-of-cdr-views"></a><span data-ttu-id="152e1-104">CDR 視圖清單</span><span class="sxs-lookup"><span data-stu-id="152e1-104">List of CDR views</span></span>
 
<span data-ttu-id="152e1-105">[視圖] 提供一種簡單的方式, 可存取從 CDR 資料庫傳回資料最常見的案例資訊。</span><span class="sxs-lookup"><span data-stu-id="152e1-105">Views provide an easy way to access information about the most common scenarios used for returning data from the CDR database.</span></span> <span data-ttu-id="152e1-106">建議您使用 [視圖] 來建立自訂報表, 而不是使用實際的 CDR 資料庫資料表;這是因為資料庫檢視更可能會維持與未來版本的向後相容性。</span><span class="sxs-lookup"><span data-stu-id="152e1-106">It is recommended that you use views for building custom reports instead of using the actual CDR database tables ; that's because the database views are more likely to maintain backwards compatibility with future releases.</span></span>
  
|<span data-ttu-id="152e1-107">**[視圖名稱]**</span><span class="sxs-lookup"><span data-stu-id="152e1-107">**View Name**</span></span>|<span data-ttu-id="152e1-108">**說明**</span><span class="sxs-lookup"><span data-stu-id="152e1-108">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="152e1-109">ClientVersions 視圖</span><span class="sxs-lookup"><span data-stu-id="152e1-109">ClientVersions view</span></span>](clientversions-0.md) <br/> |<span data-ttu-id="152e1-110">傳回通訊會話中使用之用戶端軟體/裝置的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="152e1-110">Returns information about the client software/devices used in a communication session.</span></span>  <br/> |
|[<span data-ttu-id="152e1-111">ConferenceMessageCount 視圖</span><span class="sxs-lookup"><span data-stu-id="152e1-111">ConferenceMessageCount view</span></span>](conferencemessagecount-0.md) <br/> |<span data-ttu-id="152e1-112">傳回會議中使用者傳送的訊息數的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="152e1-112">Returns information about the number of messages sent by users in a conference.</span></span>  <br/> |
|[<span data-ttu-id="152e1-113">會議視圖</span><span class="sxs-lookup"><span data-stu-id="152e1-113">Conferences view</span></span>](conferences-0.md) <br/> |<span data-ttu-id="152e1-114">傳回會議資訊, 包括 [開始時間]、[結束時間] 和 [會議召集人]。</span><span class="sxs-lookup"><span data-stu-id="152e1-114">Returns conference information, including start time, end time, and conference organizer.</span></span>  <br/> |
|[<span data-ttu-id="152e1-115">ConferenceSessionDetails 視圖</span><span class="sxs-lookup"><span data-stu-id="152e1-115">ConferenceSessionDetails view</span></span>](conferencesessiondetails.md) <br/> |<span data-ttu-id="152e1-116">傳回所有會議會話的會話詳細資料, 包括開始和結束時間、使用者識別碼、回應代碼, 以及診斷 Id。</span><span class="sxs-lookup"><span data-stu-id="152e1-116">Returns session details for all conferencing sessions, including start and end time, user IDs, response codes, and diagnostic IDs.</span></span>  <br/> |
|[<span data-ttu-id="152e1-117">ConferenceUris 視圖</span><span class="sxs-lookup"><span data-stu-id="152e1-117">ConferenceUris view</span></span>](conferenceuris-0.md) <br/> |<span data-ttu-id="152e1-118">傳回會議中使用之會議 Uri 的相關資訊</span><span class="sxs-lookup"><span data-stu-id="152e1-118">Returns information about conference URIs used in a conference</span></span>  <br/> |
|[<span data-ttu-id="152e1-119">ErrorReport 視圖</span><span class="sxs-lookup"><span data-stu-id="152e1-119">ErrorReport view</span></span>](errorreport-0.md) <br/> |<span data-ttu-id="152e1-120">傳回在會話期間發生之錯誤的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="152e1-120">Returns information about errors that occurred during a session.</span></span>  <br/> |
|[<span data-ttu-id="152e1-121">FileTransfers 視圖</span><span class="sxs-lookup"><span data-stu-id="152e1-121">FileTransfers view</span></span>](filetransfers.md) <br/> |<span data-ttu-id="152e1-122">傳回檔案傳輸會話的相關資訊, 包括檔案名, 以及傳輸被接受、拒絕或取消。</span><span class="sxs-lookup"><span data-stu-id="152e1-122">Returns information about file transfer sessions, including the file name and whether the transfer was accepted, rejected, or cancelled.</span></span>  <br/> |
|[<span data-ttu-id="152e1-123">FocusJoinsAndLeaves 視圖</span><span class="sxs-lookup"><span data-stu-id="152e1-123">FocusJoinsAndLeaves view</span></span>](focusjoinsandleaves-0.md) <br/> |<span data-ttu-id="152e1-124">傳回會議加入與離開活動的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="152e1-124">Returns information about conference join and leave activities.</span></span>  <br/> |
|[<span data-ttu-id="152e1-125">McuJoinsAndLeaves 視圖</span><span class="sxs-lookup"><span data-stu-id="152e1-125">McuJoinsAndLeaves view</span></span>](mcujoinsandleaves-0.md) <br/> |<span data-ttu-id="152e1-126">傳回會議加入與離開活動的綜合資訊 (每個會議加入都與對應的會議休假成對出現)。</span><span class="sxs-lookup"><span data-stu-id="152e1-126">Returns combined information about conference join and leave activities (each conference join is paired with the corresponding conference leave).</span></span>  <br/> |
|[<span data-ttu-id="152e1-127">Mcus 視圖</span><span class="sxs-lookup"><span data-stu-id="152e1-127">Mcus view</span></span>](mcus-0.md) <br/> |<span data-ttu-id="152e1-128">傳回會議服務器的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="152e1-128">Returns information about Conferencing servers.</span></span>  <br/> |
|[<span data-ttu-id="152e1-129">媒體視圖</span><span class="sxs-lookup"><span data-stu-id="152e1-129">Media view</span></span>](media-0.md) <br/> |<span data-ttu-id="152e1-130">傳回對等通訊會話中所使用之媒體類型的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="152e1-130">Returns information about the types of media used in peer-to-peer communication sessions.</span></span>  <br/> |
|[<span data-ttu-id="152e1-131">ProgressReport 視圖</span><span class="sxs-lookup"><span data-stu-id="152e1-131">ProgressReport view</span></span>](progressreport-0.md) <br/> |<span data-ttu-id="152e1-132">傳回已完成會話的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="152e1-132">Returns information about completed sessions.</span></span>  <br/> |
|<span data-ttu-id="152e1-133">[[註冊] 視圖](registration-0.md)</span><span class="sxs-lookup"><span data-stu-id="152e1-133">[Registration view](registration-0.md)</span></span> <br/> |<span data-ttu-id="152e1-134">傳回與商務用 Skype Server 2015 登記有關的資訊。</span><span class="sxs-lookup"><span data-stu-id="152e1-134">Returns information about registrations with Skype for Business Server 2015.</span></span>  <br/> |
|[<span data-ttu-id="152e1-135">SessionDetails 視圖</span><span class="sxs-lookup"><span data-stu-id="152e1-135">SessionDetails view</span></span>](sessiondetails-0.md) <br/> |<span data-ttu-id="152e1-136">傳回點對點工作階段的相關資訊, 包括 VoIP VoIP 電話、兩方 IM 會話, 或其他對等通訊會話。</span><span class="sxs-lookup"><span data-stu-id="152e1-136">Returns information about peer-to-peer sessions, including VoIP-VoIP phone calls, two-party IM sessions, or other peer-to-peer communication sessions.</span></span>  <br/> |
|[<span data-ttu-id="152e1-137">使用者視圖</span><span class="sxs-lookup"><span data-stu-id="152e1-137">User view</span></span>](user.md) <br/> |<span data-ttu-id="152e1-138">傳回參與通訊會話之使用者的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="152e1-138">Returns information about the users who have participated in communication sessions.</span></span>  <br/> |
|[<span data-ttu-id="152e1-139">VoIPDetails 視圖</span><span class="sxs-lookup"><span data-stu-id="152e1-139">VoIPDetails view</span></span>](voipdetails.md) <br/> |<span data-ttu-id="152e1-140">傳回至少包含一個 VoIP (在 IO 上) 使用者的點對點工作階段的資訊。</span><span class="sxs-lookup"><span data-stu-id="152e1-140">Returns information for peer-to-peer sessions involving at least one VoIP (Voice over IO) user.</span></span>  <br/> |
   

