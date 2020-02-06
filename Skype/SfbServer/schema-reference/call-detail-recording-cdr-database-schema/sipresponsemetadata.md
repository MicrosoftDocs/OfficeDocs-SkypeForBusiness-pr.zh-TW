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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: cf723737-4a75-4352-829b-f4954aa59716
description: SIPResponseMetaDataTable 包含 SIP 回應代碼清單，以及每個代碼的分類與定義。 系統會產生這些代碼，以回應影響 SIP 裝置和 SIP 通訊會話的事件;例如，回應碼403是在 SIP 裝置提出要求時產生，但伺服器會拒絕服從該要求。
ms.openlocfilehash: 2c302793dc9f9c53d445d231a261bf43a0c385df
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814891"
---
# <a name="sipresponsemetadata-table"></a><span data-ttu-id="a9cf9-104">SIPResponseMetaData 資料表</span><span class="sxs-lookup"><span data-stu-id="a9cf9-104">SIPResponseMetaData table</span></span>
 
<span data-ttu-id="a9cf9-105">SIPResponseMetaDataTable 包含 SIP 回應代碼清單，以及每個代碼的分類與定義。</span><span class="sxs-lookup"><span data-stu-id="a9cf9-105">The SIPResponseMetaDataTable contains a list of SIP response codes and the classification and definition of each of those codes.</span></span> <span data-ttu-id="a9cf9-106">系統會產生這些代碼，以回應影響 SIP 裝置和 SIP 通訊會話的事件;例如，回應碼403是在 SIP 裝置提出要求時產生，但伺服器會拒絕服從該要求。</span><span class="sxs-lookup"><span data-stu-id="a9cf9-106">These codes are generated in response to events affecting SIP devices and SIP communication sessions; for example, the response code 403 is generated when a SIP device makes a request, but the server declines to honor that request.</span></span>
  
<span data-ttu-id="a9cf9-107">此表格是在商務用 Skype Server 2015 中推出。</span><span class="sxs-lookup"><span data-stu-id="a9cf9-107">This table was introduced in Skype for Business Server 2015.</span></span>
  
|<span data-ttu-id="a9cf9-108">**左欄**</span><span class="sxs-lookup"><span data-stu-id="a9cf9-108">**Column**</span></span>|<span data-ttu-id="a9cf9-109">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="a9cf9-109">**Data Type**</span></span>|<span data-ttu-id="a9cf9-110">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="a9cf9-110">**Key/Index**</span></span>|<span data-ttu-id="a9cf9-111">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="a9cf9-111">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a9cf9-112">**ResponseCode**</span><span class="sxs-lookup"><span data-stu-id="a9cf9-112">**ResponseCode**</span></span> <br/> |<span data-ttu-id="a9cf9-113">int</span><span class="sxs-lookup"><span data-stu-id="a9cf9-113">int</span></span>  <br/> |<span data-ttu-id="a9cf9-114">首選</span><span class="sxs-lookup"><span data-stu-id="a9cf9-114">Primary</span></span>  <br/> |<span data-ttu-id="a9cf9-115">代表 SIP 回應代碼的數值。</span><span class="sxs-lookup"><span data-stu-id="a9cf9-115">Numeric value that represents the SIP response code.</span></span>  <br/> |
|<span data-ttu-id="a9cf9-116">**靜態類**</span><span class="sxs-lookup"><span data-stu-id="a9cf9-116">**Class**</span></span> <br/> |<span data-ttu-id="a9cf9-117">int</span><span class="sxs-lookup"><span data-stu-id="a9cf9-117">int</span></span>  <br/> || <span data-ttu-id="a9cf9-118">回應代碼的一般分類。</span><span class="sxs-lookup"><span data-stu-id="a9cf9-118">General classification for the response code.</span></span> <span data-ttu-id="a9cf9-119">分類包括：</span><span class="sxs-lookup"><span data-stu-id="a9cf9-119">Classifications include:</span></span> <br/>  <span data-ttu-id="a9cf9-120">1-資訊回應</span><span class="sxs-lookup"><span data-stu-id="a9cf9-120">1 - Informational Responses</span></span> <br/>  <span data-ttu-id="a9cf9-121">2-成功回應</span><span class="sxs-lookup"><span data-stu-id="a9cf9-121">2 - Successful Responses</span></span> <br/>  <span data-ttu-id="a9cf9-122">3重定向回應</span><span class="sxs-lookup"><span data-stu-id="a9cf9-122">3 - Redirection Responses</span></span> <br/>  <span data-ttu-id="a9cf9-123">4-用戶端失敗回應</span><span class="sxs-lookup"><span data-stu-id="a9cf9-123">4 - Client Failure Responses</span></span> <br/>  <span data-ttu-id="a9cf9-124">5--伺服器失敗回應</span><span class="sxs-lookup"><span data-stu-id="a9cf9-124">5 -- Server Failure Responses</span></span> <br/>  <span data-ttu-id="a9cf9-125">6-全域失敗回應</span><span class="sxs-lookup"><span data-stu-id="a9cf9-125">6 - Global Failure Response</span></span> <br/> |
|<span data-ttu-id="a9cf9-126">**說明**</span><span class="sxs-lookup"><span data-stu-id="a9cf9-126">**Description**</span></span> <br/> |<span data-ttu-id="a9cf9-127">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="a9cf9-127">nvarchar(256)</span></span>  <br/> ||<span data-ttu-id="a9cf9-128">SIP 回應代碼的描述。</span><span class="sxs-lookup"><span data-stu-id="a9cf9-128">Description of the SIP response code.</span></span> <span data-ttu-id="a9cf9-129">例如，回應代碼181具有下列描述：</span><span class="sxs-lookup"><span data-stu-id="a9cf9-129">For example, response code 181 has the following description:</span></span>  <br/> <span data-ttu-id="a9cf9-130">呼叫正在轉寄</span><span class="sxs-lookup"><span data-stu-id="a9cf9-130">Call Is Being Forwarded</span></span>  <br/> |
   

