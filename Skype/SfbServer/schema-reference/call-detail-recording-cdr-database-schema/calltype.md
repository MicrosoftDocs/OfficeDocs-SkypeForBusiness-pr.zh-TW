---
title: 商務用 Skype Server 2015 中的 CallType 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a1d7187c-f851-4967-88ea-73922911ee7a
description: CallType 資料表是一個靜態資料表, 可儲存可能的通話類型清單。
ms.openlocfilehash: 992e5682aedf7a0b9063960992197970146c8cfc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192903"
---
# <a name="calltype-table-in-skype-for-business-server-2015"></a><span data-ttu-id="76bfd-103">商務用 Skype Server 2015 中的 CallType 表格</span><span class="sxs-lookup"><span data-stu-id="76bfd-103">CallType table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="76bfd-104">CallType 資料表是一個靜態資料表, 可儲存可能的通話類型清單。</span><span class="sxs-lookup"><span data-stu-id="76bfd-104">The CallType table is a static table that stores the list of possible call types.</span></span>
  
|<span data-ttu-id="76bfd-105">**左欄**</span><span class="sxs-lookup"><span data-stu-id="76bfd-105">**Column**</span></span>|<span data-ttu-id="76bfd-106">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="76bfd-106">**Data Type**</span></span>|<span data-ttu-id="76bfd-107">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="76bfd-107">**Key/Index**</span></span>|<span data-ttu-id="76bfd-108">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="76bfd-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="76bfd-109">**CallTypeId**</span><span class="sxs-lookup"><span data-stu-id="76bfd-109">**CallTypeId**</span></span> <br/> |<span data-ttu-id="76bfd-110">int</span><span class="sxs-lookup"><span data-stu-id="76bfd-110">int</span></span>  <br/> |<span data-ttu-id="76bfd-111">首選</span><span class="sxs-lookup"><span data-stu-id="76bfd-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="76bfd-112">**CallType**</span><span class="sxs-lookup"><span data-stu-id="76bfd-112">**CallType**</span></span> <br/> |<span data-ttu-id="76bfd-113">Nvarchar</span><span class="sxs-lookup"><span data-stu-id="76bfd-113">nvarchar</span></span>  <br/> || <span data-ttu-id="76bfd-114">允許的值:</span><span class="sxs-lookup"><span data-stu-id="76bfd-114">Allowed values:</span></span> <br/>  <span data-ttu-id="76bfd-115">0--未知</span><span class="sxs-lookup"><span data-stu-id="76bfd-115">0 -- Unknown</span></span> <br/>  <span data-ttu-id="76bfd-116">1-立即訊息</span><span class="sxs-lookup"><span data-stu-id="76bfd-116">1 - Instant Messaging</span></span> <br/>  <span data-ttu-id="76bfd-117">2--應用程式共用</span><span class="sxs-lookup"><span data-stu-id="76bfd-117">2 -- Application Sharing</span></span> <br/>  <span data-ttu-id="76bfd-118">3--音訊</span><span class="sxs-lookup"><span data-stu-id="76bfd-118">3 -- Audio</span></span> <br/>  <span data-ttu-id="76bfd-119">4-音訊和影片</span><span class="sxs-lookup"><span data-stu-id="76bfd-119">4 - Audio and Video</span></span> <br/>  <span data-ttu-id="76bfd-120">5-檔案傳輸</span><span class="sxs-lookup"><span data-stu-id="76bfd-120">5 - File Transfer</span></span> <br/> |
   

