---
title: 媒體視圖
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
ms.assetid: 1a7b2e59-082e-4188-98ae-48ae9bd3494a
description: 媒體檢視可儲存對等工作階段中所使用之一種媒體類型的相關資訊。 若某階段工作使用了一種以上的媒體類型，則在表格中會呈現多個記錄。 此視圖已引進于 Microsoft Lync Server 2013。
ms.openlocfilehash: 77c22246056a28cdb41a007ac0d7e2617fa00ad9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831784"
---
# <a name="media-view"></a><span data-ttu-id="705c6-105">媒體視圖</span><span class="sxs-lookup"><span data-stu-id="705c6-105">Media view</span></span>
 
<span data-ttu-id="705c6-106">媒體檢視可儲存對等工作階段中所使用之一種媒體類型的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="705c6-106">The Media view stores information about one media type used in a peer-to-peer session.</span></span> <span data-ttu-id="705c6-107">若某階段工作使用了一種以上的媒體類型，則在表格中會呈現多個記錄。</span><span class="sxs-lookup"><span data-stu-id="705c6-107">One session would be represented by multiple records in the table, if more than one media type is used.</span></span> <span data-ttu-id="705c6-108">此視圖已引進于 Microsoft Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="705c6-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="705c6-p103">您不應使用媒體檢視來計算工作階段的媒體持續期間。此檢視包含工作階段中的媒體交換訊號詳細資料。媒體交換是由 INVITE 要求來執行，且 StartTime 會指出 INVITE 傳送出來的時間。邀請時間不一定表示媒體開始時間，因為只有在接受工作階段後，媒體才會開始。</span><span class="sxs-lookup"><span data-stu-id="705c6-p103">The Media view should not be used to calculate the media duration for a session. This view contains the signaling details of media exchange in a session. Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the session is accepted.</span></span> 
  
<span data-ttu-id="705c6-112">除了下列所列之外，媒體視圖還會包含 [SessionDetails 視圖](sessiondetails-0.md) 中的所有欄。</span><span class="sxs-lookup"><span data-stu-id="705c6-112">The Media view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the ones listed below.</span></span>
  
|<span data-ttu-id="705c6-113">**欄**</span><span class="sxs-lookup"><span data-stu-id="705c6-113">**Column**</span></span>|<span data-ttu-id="705c6-114">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="705c6-114">**Data Type**</span></span>|<span data-ttu-id="705c6-115">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="705c6-115">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="705c6-116">**媒體**</span><span class="sxs-lookup"><span data-stu-id="705c6-116">**Media**</span></span> <br/> |<span data-ttu-id="705c6-117">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="705c6-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="705c6-118">媒體類型。</span><span class="sxs-lookup"><span data-stu-id="705c6-118">Media type.</span></span> <span data-ttu-id="705c6-119">如需詳細資訊，請參閱 [MediaList 表格](medialist.md) 。</span><span class="sxs-lookup"><span data-stu-id="705c6-119">See the [MediaList table](medialist.md) for more information.</span></span> <br/> |
|<span data-ttu-id="705c6-120">**MediaStartTime**</span><span class="sxs-lookup"><span data-stu-id="705c6-120">**MediaStartTime**</span></span> <br/> |<span data-ttu-id="705c6-121">datetime</span><span class="sxs-lookup"><span data-stu-id="705c6-121">datetime</span></span>  <br/> |<span data-ttu-id="705c6-122">媒體要求傳送出來的時間。</span><span class="sxs-lookup"><span data-stu-id="705c6-122">Time that a media request was sent out.</span></span>  <br/> |
|<span data-ttu-id="705c6-123">**MediaEndTime**</span><span class="sxs-lookup"><span data-stu-id="705c6-123">**MediaEndTime**</span></span> <br/> |<span data-ttu-id="705c6-124">datetime</span><span class="sxs-lookup"><span data-stu-id="705c6-124">datetime</span></span>  <br/> |<span data-ttu-id="705c6-125">工作階段結束時間。</span><span class="sxs-lookup"><span data-stu-id="705c6-125">End time of the session.</span></span>  <br/> |
   

