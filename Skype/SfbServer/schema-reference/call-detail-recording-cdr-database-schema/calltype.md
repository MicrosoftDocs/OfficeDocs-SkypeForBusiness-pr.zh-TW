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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: a1d7187c-f851-4967-88ea-73922911ee7a
description: CallType 資料表是一個靜態資料表，可儲存可能的通話類型清單。
ms.openlocfilehash: 294af58755e980200d75c899d6110322e2ff774d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815431"
---
# <a name="calltype-table-in-skype-for-business-server-2015"></a><span data-ttu-id="99e19-103">商務用 Skype Server 2015 中的 CallType 表格</span><span class="sxs-lookup"><span data-stu-id="99e19-103">CallType table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="99e19-104">CallType 資料表是一個靜態資料表，可儲存可能的通話類型清單。</span><span class="sxs-lookup"><span data-stu-id="99e19-104">The CallType table is a static table that stores the list of possible call types.</span></span>
  
|<span data-ttu-id="99e19-105">**左欄**</span><span class="sxs-lookup"><span data-stu-id="99e19-105">**Column**</span></span>|<span data-ttu-id="99e19-106">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="99e19-106">**Data Type**</span></span>|<span data-ttu-id="99e19-107">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="99e19-107">**Key/Index**</span></span>|<span data-ttu-id="99e19-108">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="99e19-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="99e19-109">**CallTypeId**</span><span class="sxs-lookup"><span data-stu-id="99e19-109">**CallTypeId**</span></span> <br/> |<span data-ttu-id="99e19-110">int</span><span class="sxs-lookup"><span data-stu-id="99e19-110">int</span></span>  <br/> |<span data-ttu-id="99e19-111">首選</span><span class="sxs-lookup"><span data-stu-id="99e19-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="99e19-112">**CallType**</span><span class="sxs-lookup"><span data-stu-id="99e19-112">**CallType**</span></span> <br/> |<span data-ttu-id="99e19-113">Nvarchar</span><span class="sxs-lookup"><span data-stu-id="99e19-113">nvarchar</span></span>  <br/> || <span data-ttu-id="99e19-114">允許的值：</span><span class="sxs-lookup"><span data-stu-id="99e19-114">Allowed values:</span></span> <br/>  <span data-ttu-id="99e19-115">0--未知</span><span class="sxs-lookup"><span data-stu-id="99e19-115">0 -- Unknown</span></span> <br/>  <span data-ttu-id="99e19-116">1-立即訊息</span><span class="sxs-lookup"><span data-stu-id="99e19-116">1 - Instant Messaging</span></span> <br/>  <span data-ttu-id="99e19-117">2--應用程式共用</span><span class="sxs-lookup"><span data-stu-id="99e19-117">2 -- Application Sharing</span></span> <br/>  <span data-ttu-id="99e19-118">3--音訊</span><span class="sxs-lookup"><span data-stu-id="99e19-118">3 -- Audio</span></span> <br/>  <span data-ttu-id="99e19-119">4-音訊和影片</span><span class="sxs-lookup"><span data-stu-id="99e19-119">4 - Audio and Video</span></span> <br/>  <span data-ttu-id="99e19-120">5-檔案傳輸</span><span class="sxs-lookup"><span data-stu-id="99e19-120">5 - File Transfer</span></span> <br/> |
   

