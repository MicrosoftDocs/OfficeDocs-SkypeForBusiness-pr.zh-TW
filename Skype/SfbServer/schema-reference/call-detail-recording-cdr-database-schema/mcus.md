---
title: 商務用 Skype Server 2015 中的 Mcus 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
description: Mcus 資料表是支援資料表。 每筆記錄儲存一個會議服務的相關資訊。 這些可能包括 IM 會議服務和電話會議服務 (在前端伺服器上以進程的方式執行), 以及網路會議服務和 A/V 會議服務。
ms.openlocfilehash: fcd12bcc8da7aa6513d78e1a9c4a6f11930065aa
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192830"
---
# <a name="mcus-table-in-skype-for-business-server-2015"></a><span data-ttu-id="78402-105">商務用 Skype Server 2015 中的 Mcus 表格</span><span class="sxs-lookup"><span data-stu-id="78402-105">Mcus table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="78402-106">Mcus 資料表是支援資料表。</span><span class="sxs-lookup"><span data-stu-id="78402-106">The Mcus table is a supporting table.</span></span> <span data-ttu-id="78402-107">每筆記錄儲存一個會議服務的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="78402-107">Each record stores information about one conferencing service.</span></span> <span data-ttu-id="78402-108">這些可能包括 IM 會議服務和電話會議服務 (在前端伺服器上以進程的方式執行), 以及網路會議服務和 A/V 會議服務。</span><span class="sxs-lookup"><span data-stu-id="78402-108">These can include the IM Conferencing service and the Telephony Conferencing service (which run as processes on front-end servers), and the Web Conferencing service and A/V Conferencing service.</span></span> 
  
|<span data-ttu-id="78402-109">**左欄**</span><span class="sxs-lookup"><span data-stu-id="78402-109">**Column**</span></span>|<span data-ttu-id="78402-110">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="78402-110">**Data Type**</span></span>|<span data-ttu-id="78402-111">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="78402-111">**Key/Index**</span></span>|<span data-ttu-id="78402-112">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="78402-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="78402-113">**McuId**</span><span class="sxs-lookup"><span data-stu-id="78402-113">**McuId**</span></span> <br/> |<span data-ttu-id="78402-114">int</span><span class="sxs-lookup"><span data-stu-id="78402-114">int</span></span>  <br/> |<span data-ttu-id="78402-115">首選</span><span class="sxs-lookup"><span data-stu-id="78402-115">Primary</span></span>  <br/> |<span data-ttu-id="78402-116">標識此會議服務器的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="78402-116">Unique number identifying this conferencing server.</span></span>  <br/> |
|<span data-ttu-id="78402-117">**McuUri**</span><span class="sxs-lookup"><span data-stu-id="78402-117">**McuUri**</span></span> <br/> |<span data-ttu-id="78402-118">Nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="78402-118">nvarchar(450)</span></span>  <br/> | <br/> | <br/> |
|<span data-ttu-id="78402-119">**McuTypeId**</span><span class="sxs-lookup"><span data-stu-id="78402-119">**McuTypeId**</span></span> <br/> |<span data-ttu-id="78402-120">inyint</span><span class="sxs-lookup"><span data-stu-id="78402-120">inyint</span></span>  <br/> | <span data-ttu-id="78402-121">外</span><span class="sxs-lookup"><span data-stu-id="78402-121">Foreign</span></span> <br/> |<span data-ttu-id="78402-122">會議服務器類型, 例如會議: 聊天 (適用于 Im) 或會議: 音訊影片。</span><span class="sxs-lookup"><span data-stu-id="78402-122">Conferencing server type, such as conf:chat (for IMs) or conf:audio-video.</span></span> <span data-ttu-id="78402-123">如需詳細資訊, 請參閱[UriTypes 資料表](uritypes.md)。</span><span class="sxs-lookup"><span data-stu-id="78402-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

