---
title: MediaList 表格
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/12/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1f440590-c1bc-483e-b7bc-6cc763847768
description: MediaList 表格是一種靜態表格，其中儲存了各種媒體類型清單。
ms.openlocfilehash: 6f593876a1b42163b6f2e75dbe44c1eb26b2ff16
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813133"
---
# <a name="medialist-table"></a><span data-ttu-id="1e711-103">MediaList 表格</span><span class="sxs-lookup"><span data-stu-id="1e711-103">MediaList table</span></span>
 
<span data-ttu-id="1e711-104">MediaList 表格是一種靜態表格，其中儲存了各種媒體類型清單。</span><span class="sxs-lookup"><span data-stu-id="1e711-104">The MediaList table is a static table that stores the list of various media types.</span></span>
  
|<span data-ttu-id="1e711-105">**欄**</span><span class="sxs-lookup"><span data-stu-id="1e711-105">**Column**</span></span>|<span data-ttu-id="1e711-106">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="1e711-106">**Data Type**</span></span>|<span data-ttu-id="1e711-107">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="1e711-107">**Key/Index**</span></span>|<span data-ttu-id="1e711-108">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="1e711-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1e711-109">**MediaId**</span><span class="sxs-lookup"><span data-stu-id="1e711-109">**MediaId**</span></span> <br/> |<span data-ttu-id="1e711-110">Tinyint</span><span class="sxs-lookup"><span data-stu-id="1e711-110">tinyint</span></span>  <br/> |<span data-ttu-id="1e711-111">主要</span><span class="sxs-lookup"><span data-stu-id="1e711-111">Primary</span></span>  <br/> |<span data-ttu-id="1e711-112">值：1-7</span><span class="sxs-lookup"><span data-stu-id="1e711-112">Values: 1-7</span></span>  <br/> |
|<span data-ttu-id="1e711-113">**媒體**</span><span class="sxs-lookup"><span data-stu-id="1e711-113">**Media**</span></span> <br/> |<span data-ttu-id="1e711-114">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="1e711-114">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="1e711-115">MediaID 和媒體值的靜態對應：</span><span class="sxs-lookup"><span data-stu-id="1e711-115">Static mapping of MediaID and Media values:</span></span> <br/>  <span data-ttu-id="1e711-116">1 -- IM</span><span class="sxs-lookup"><span data-stu-id="1e711-116">1 -- IM</span></span> <br/>  <span data-ttu-id="1e711-117">2-檔案傳輸</span><span class="sxs-lookup"><span data-stu-id="1e711-117">2 - File Transfer</span></span> <br/>  <span data-ttu-id="1e711-118">3-遠端協助</span><span class="sxs-lookup"><span data-stu-id="1e711-118">3 - Remote Assistance</span></span> <br/>  <span data-ttu-id="1e711-119">4-應用程式共用</span><span class="sxs-lookup"><span data-stu-id="1e711-119">4 - Application Sharing</span></span> <br/>  <span data-ttu-id="1e711-120">5 -- 音訊</span><span class="sxs-lookup"><span data-stu-id="1e711-120">5 -- Audio</span></span> <br/>  <span data-ttu-id="1e711-121">6 -- 視訊</span><span class="sxs-lookup"><span data-stu-id="1e711-121">6 -- Video</span></span> <br/>  <span data-ttu-id="1e711-122">7-應用程式邀請</span><span class="sxs-lookup"><span data-stu-id="1e711-122">7 - App Invite</span></span> <br/> |
   
<span data-ttu-id="1e711-123">若要嘗試判斷 SessionDetailsView LcsCDR 中的值的模態類型，您必須使用下列的聯接程式碼片段：</span><span class="sxs-lookup"><span data-stu-id="1e711-123">If you are trying to determine the modality type for the values in LcsCDR.SessionDetailsView.MediaTypes, then you need to use the following Join snippet:</span></span> 
  
```SQL
LEFT JOIN on Media.MediaId = MediaList.MediaId
```
