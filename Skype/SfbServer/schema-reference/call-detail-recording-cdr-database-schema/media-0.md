---
title: 媒體視圖
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
ms.assetid: 1a7b2e59-082e-4188-98ae-48ae9bd3494a
description: 媒體視圖儲存點對點工作階段中所使用之一個媒體類型的相關資訊。 如果使用一個以上的媒體類型，則資料表中的多筆記錄會代表一個會話。 此視圖已在 Microsoft Lync Server 2013 中推出。
ms.openlocfilehash: 26ef344b5fade02168fb8737fe00049e44e24892
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815051"
---
# <a name="media-view"></a><span data-ttu-id="4cd4c-105">媒體視圖</span><span class="sxs-lookup"><span data-stu-id="4cd4c-105">Media view</span></span>
 
<span data-ttu-id="4cd4c-106">媒體視圖儲存點對點工作階段中所使用之一個媒體類型的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="4cd4c-106">The Media view stores information about one media type used in a peer-to-peer session.</span></span> <span data-ttu-id="4cd4c-107">如果使用一個以上的媒體類型，則資料表中的多筆記錄會代表一個會話。</span><span class="sxs-lookup"><span data-stu-id="4cd4c-107">One session would be represented by multiple records in the table, if more than one media type is used.</span></span> <span data-ttu-id="4cd4c-108">此視圖已在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="4cd4c-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4cd4c-109">媒體視圖不應該用來計算會話的媒體持續時間。</span><span class="sxs-lookup"><span data-stu-id="4cd4c-109">The Media view should not be used to calculate the media duration for a session.</span></span> <span data-ttu-id="4cd4c-110">此視圖包含會話中媒體交換的信號詳細資料。</span><span class="sxs-lookup"><span data-stu-id="4cd4c-110">This view contains the signaling details of media exchange in a session.</span></span> <span data-ttu-id="4cd4c-111">媒體交換是由邀請要求所完成，而 StartTime 則會指出邀請的傳送時間。邀請時間不一定代表媒體開始時間，因為媒體只有在接受會話之後才會啟動。</span><span class="sxs-lookup"><span data-stu-id="4cd4c-111">Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the session is accepted.</span></span> 
  
<span data-ttu-id="4cd4c-112">媒體視圖會包含 [ [SessionDetails] 視圖](sessiondetails-0.md)中的所有資料行，以及以下所列的欄。</span><span class="sxs-lookup"><span data-stu-id="4cd4c-112">The Media view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the ones listed below.</span></span>
  
|<span data-ttu-id="4cd4c-113">**左欄**</span><span class="sxs-lookup"><span data-stu-id="4cd4c-113">**Column**</span></span>|<span data-ttu-id="4cd4c-114">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="4cd4c-114">**Data Type**</span></span>|<span data-ttu-id="4cd4c-115">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="4cd4c-115">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4cd4c-116">**媒體**</span><span class="sxs-lookup"><span data-stu-id="4cd4c-116">**Media**</span></span> <br/> |<span data-ttu-id="4cd4c-117">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="4cd4c-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="4cd4c-118">媒體類型。</span><span class="sxs-lookup"><span data-stu-id="4cd4c-118">Media type.</span></span> <span data-ttu-id="4cd4c-119">如需詳細資訊，請參閱[MediaList 資料表](medialist.md)。</span><span class="sxs-lookup"><span data-stu-id="4cd4c-119">See the [MediaList table](medialist.md) for more information.</span></span> <br/> |
|<span data-ttu-id="4cd4c-120">**MediaStartTime**</span><span class="sxs-lookup"><span data-stu-id="4cd4c-120">**MediaStartTime**</span></span> <br/> |<span data-ttu-id="4cd4c-121">datetime</span><span class="sxs-lookup"><span data-stu-id="4cd4c-121">datetime</span></span>  <br/> |<span data-ttu-id="4cd4c-122">媒體要求的傳送時間。</span><span class="sxs-lookup"><span data-stu-id="4cd4c-122">Time that a media request was sent out.</span></span>  <br/> |
|<span data-ttu-id="4cd4c-123">**MediaEndTime**</span><span class="sxs-lookup"><span data-stu-id="4cd4c-123">**MediaEndTime**</span></span> <br/> |<span data-ttu-id="4cd4c-124">datetime</span><span class="sxs-lookup"><span data-stu-id="4cd4c-124">datetime</span></span>  <br/> |<span data-ttu-id="4cd4c-125">會話的結束時間。</span><span class="sxs-lookup"><span data-stu-id="4cd4c-125">End time of the session.</span></span>  <br/> |
   

