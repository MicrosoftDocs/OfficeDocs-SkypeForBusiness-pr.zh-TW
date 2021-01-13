---
title: SIPResponseMetaData 表格
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: cf723737-4a75-4352-829b-f4954aa59716
description: SIPResponseMetaDataTable 包含 SIP 回應碼的清單，以及每個代碼的分類和定義。 這兩個代碼會在回應影響 SIP 裝置和 SIP 通訊會話的事件時產生;例如，回應碼403是在 SIP 裝置提出要求時產生，但是伺服器會謝絕該要求。
ms.openlocfilehash: 3d6714e9c5b5c154d19381fad33821b02ec8a73e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809923"
---
# <a name="sipresponsemetadata-table"></a><span data-ttu-id="08bab-104">SIPResponseMetaData 表格</span><span class="sxs-lookup"><span data-stu-id="08bab-104">SIPResponseMetaData table</span></span>
 
<span data-ttu-id="08bab-105">SIPResponseMetaDataTable 包含 SIP 回應碼的清單，以及每個代碼的分類和定義。</span><span class="sxs-lookup"><span data-stu-id="08bab-105">The SIPResponseMetaDataTable contains a list of SIP response codes and the classification and definition of each of those codes.</span></span> <span data-ttu-id="08bab-106">這兩個代碼會在回應影響 SIP 裝置和 SIP 通訊會話的事件時產生;例如，回應碼403是在 SIP 裝置提出要求時產生，但是伺服器會謝絕該要求。</span><span class="sxs-lookup"><span data-stu-id="08bab-106">These codes are generated in response to events affecting SIP devices and SIP communication sessions; for example, the response code 403 is generated when a SIP device makes a request, but the server declines to honor that request.</span></span>
  
<span data-ttu-id="08bab-107">此表格已引進商務用 Skype Server 2015。</span><span class="sxs-lookup"><span data-stu-id="08bab-107">This table was introduced in Skype for Business Server 2015.</span></span>
  
|<span data-ttu-id="08bab-108">**欄**</span><span class="sxs-lookup"><span data-stu-id="08bab-108">**Column**</span></span>|<span data-ttu-id="08bab-109">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="08bab-109">**Data Type**</span></span>|<span data-ttu-id="08bab-110">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="08bab-110">**Key/Index**</span></span>|<span data-ttu-id="08bab-111">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="08bab-111">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="08bab-112">**ResponseCode**</span><span class="sxs-lookup"><span data-stu-id="08bab-112">**ResponseCode**</span></span> <br/> |<span data-ttu-id="08bab-113">int</span><span class="sxs-lookup"><span data-stu-id="08bab-113">int</span></span>  <br/> |<span data-ttu-id="08bab-114">主要</span><span class="sxs-lookup"><span data-stu-id="08bab-114">Primary</span></span>  <br/> |<span data-ttu-id="08bab-115">代表 SIP 回應碼的數值。</span><span class="sxs-lookup"><span data-stu-id="08bab-115">Numeric value that represents the SIP response code.</span></span>  <br/> |
|<span data-ttu-id="08bab-116">**Class**</span><span class="sxs-lookup"><span data-stu-id="08bab-116">**Class**</span></span> <br/> |<span data-ttu-id="08bab-117">int</span><span class="sxs-lookup"><span data-stu-id="08bab-117">int</span></span>  <br/> || <span data-ttu-id="08bab-118">回應碼的一般分類。</span><span class="sxs-lookup"><span data-stu-id="08bab-118">General classification for the response code.</span></span> <span data-ttu-id="08bab-119">分類包括：</span><span class="sxs-lookup"><span data-stu-id="08bab-119">Classifications include:</span></span> <br/>  <span data-ttu-id="08bab-120">1-資訊回應</span><span class="sxs-lookup"><span data-stu-id="08bab-120">1 - Informational Responses</span></span> <br/>  <span data-ttu-id="08bab-121">2-成功的回應</span><span class="sxs-lookup"><span data-stu-id="08bab-121">2 - Successful Responses</span></span> <br/>  <span data-ttu-id="08bab-122">3-重新導向回應</span><span class="sxs-lookup"><span data-stu-id="08bab-122">3 - Redirection Responses</span></span> <br/>  <span data-ttu-id="08bab-123">4-用戶端失敗回應</span><span class="sxs-lookup"><span data-stu-id="08bab-123">4 - Client Failure Responses</span></span> <br/>  <span data-ttu-id="08bab-124">5--伺服器失敗回應</span><span class="sxs-lookup"><span data-stu-id="08bab-124">5 -- Server Failure Responses</span></span> <br/>  <span data-ttu-id="08bab-125">6-全域失敗回應</span><span class="sxs-lookup"><span data-stu-id="08bab-125">6 - Global Failure Response</span></span> <br/> |
|<span data-ttu-id="08bab-126">**描述**</span><span class="sxs-lookup"><span data-stu-id="08bab-126">**Description**</span></span> <br/> |<span data-ttu-id="08bab-127">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="08bab-127">nvarchar(256)</span></span>  <br/> ||<span data-ttu-id="08bab-128">SIP 回應碼的描述。</span><span class="sxs-lookup"><span data-stu-id="08bab-128">Description of the SIP response code.</span></span> <span data-ttu-id="08bab-129">例如，回應碼181的描述如下：</span><span class="sxs-lookup"><span data-stu-id="08bab-129">For example, response code 181 has the following description:</span></span>  <br/> <span data-ttu-id="08bab-130">轉接來電</span><span class="sxs-lookup"><span data-stu-id="08bab-130">Call Is Being Forwarded</span></span>  <br/> |
   

