---
title: SIPResponseMetaData 資料表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cf723737-4a75-4352-829b-f4954aa59716
description: SIPResponseMetaDataTable 包含 SIP 回應代碼清單, 以及每個代碼的分類與定義。 系統會產生這些代碼, 以回應影響 SIP 裝置和 SIP 通訊會話的事件;例如, 回應碼403是在 SIP 裝置提出要求時產生, 但伺服器會拒絕服從該要求。
ms.openlocfilehash: eecd8397315b93ebce9e5fad973f1274a6eb763a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192794"
---
# <a name="sipresponsemetadata-table"></a><span data-ttu-id="c46f2-104">SIPResponseMetaData 資料表</span><span class="sxs-lookup"><span data-stu-id="c46f2-104">SIPResponseMetaData table</span></span>
 
<span data-ttu-id="c46f2-105">SIPResponseMetaDataTable 包含 SIP 回應代碼清單, 以及每個代碼的分類與定義。</span><span class="sxs-lookup"><span data-stu-id="c46f2-105">The SIPResponseMetaDataTable contains a list of SIP response codes and the classification and definition of each of those codes.</span></span> <span data-ttu-id="c46f2-106">系統會產生這些代碼, 以回應影響 SIP 裝置和 SIP 通訊會話的事件;例如, 回應碼403是在 SIP 裝置提出要求時產生, 但伺服器會拒絕服從該要求。</span><span class="sxs-lookup"><span data-stu-id="c46f2-106">These codes are generated in response to events affecting SIP devices and SIP communication sessions; for example, the response code 403 is generated when a SIP device makes a request, but the server declines to honor that request.</span></span>
  
<span data-ttu-id="c46f2-107">此表格是在商務用 Skype Server 2015 中推出。</span><span class="sxs-lookup"><span data-stu-id="c46f2-107">This table was introduced in Skype for Business Server 2015.</span></span>
  
|<span data-ttu-id="c46f2-108">**左欄**</span><span class="sxs-lookup"><span data-stu-id="c46f2-108">**Column**</span></span>|<span data-ttu-id="c46f2-109">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="c46f2-109">**Data Type**</span></span>|<span data-ttu-id="c46f2-110">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="c46f2-110">**Key/Index**</span></span>|<span data-ttu-id="c46f2-111">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="c46f2-111">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c46f2-112">**ResponseCode**</span><span class="sxs-lookup"><span data-stu-id="c46f2-112">**ResponseCode**</span></span> <br/> |<span data-ttu-id="c46f2-113">int</span><span class="sxs-lookup"><span data-stu-id="c46f2-113">int</span></span>  <br/> |<span data-ttu-id="c46f2-114">首選</span><span class="sxs-lookup"><span data-stu-id="c46f2-114">Primary</span></span>  <br/> |<span data-ttu-id="c46f2-115">代表 SIP 回應代碼的數值。</span><span class="sxs-lookup"><span data-stu-id="c46f2-115">Numeric value that represents the SIP response code.</span></span>  <br/> |
|<span data-ttu-id="c46f2-116">**靜態類**</span><span class="sxs-lookup"><span data-stu-id="c46f2-116">**Class**</span></span> <br/> |<span data-ttu-id="c46f2-117">int</span><span class="sxs-lookup"><span data-stu-id="c46f2-117">int</span></span>  <br/> || <span data-ttu-id="c46f2-118">回應代碼的一般分類。</span><span class="sxs-lookup"><span data-stu-id="c46f2-118">General classification for the response code.</span></span> <span data-ttu-id="c46f2-119">分類包括:</span><span class="sxs-lookup"><span data-stu-id="c46f2-119">Classifications include:</span></span> <br/>  <span data-ttu-id="c46f2-120">1-資訊回應</span><span class="sxs-lookup"><span data-stu-id="c46f2-120">1 - Informational Responses</span></span> <br/>  <span data-ttu-id="c46f2-121">2-成功回應</span><span class="sxs-lookup"><span data-stu-id="c46f2-121">2 - Successful Responses</span></span> <br/>  <span data-ttu-id="c46f2-122">3重定向回應</span><span class="sxs-lookup"><span data-stu-id="c46f2-122">3 - Redirection Responses</span></span> <br/>  <span data-ttu-id="c46f2-123">4-用戶端失敗回應</span><span class="sxs-lookup"><span data-stu-id="c46f2-123">4 - Client Failure Responses</span></span> <br/>  <span data-ttu-id="c46f2-124">5--伺服器失敗回應</span><span class="sxs-lookup"><span data-stu-id="c46f2-124">5 -- Server Failure Responses</span></span> <br/>  <span data-ttu-id="c46f2-125">6-全域失敗回應</span><span class="sxs-lookup"><span data-stu-id="c46f2-125">6 - Global Failure Response</span></span> <br/> |
|<span data-ttu-id="c46f2-126">**說明**</span><span class="sxs-lookup"><span data-stu-id="c46f2-126">**Description**</span></span> <br/> |<span data-ttu-id="c46f2-127">Nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c46f2-127">nvarchar(256)</span></span>  <br/> ||<span data-ttu-id="c46f2-128">SIP 回應代碼的描述。</span><span class="sxs-lookup"><span data-stu-id="c46f2-128">Description of the SIP response code.</span></span> <span data-ttu-id="c46f2-129">例如, 回應代碼181具有下列描述:</span><span class="sxs-lookup"><span data-stu-id="c46f2-129">For example, response code 181 has the following description:</span></span>  <br/> <span data-ttu-id="c46f2-130">呼叫正在轉寄</span><span class="sxs-lookup"><span data-stu-id="c46f2-130">Call Is Being Forwarded</span></span>  <br/> |
   

