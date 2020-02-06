---
title: 取得上次整合資料
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: e7967dd9-0d6a-4a80-8b59-b8fc2e5615f8
description: 摘要：瞭解 [取得上次整合資料] 作業，該作業是 [通話品質儀表板] 的資料 API 的一部分。 [通話品質儀表板] 是商務用 Skype Server 的工具。
ms.openlocfilehash: a3b66114f457e48b169419baddbaa4e4dc8c0764
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816772"
---
# <a name="get-last-integration-data"></a><span data-ttu-id="99913-104">取得上次整合資料</span><span class="sxs-lookup"><span data-stu-id="99913-104">Get Last Integration Data</span></span>
 
<span data-ttu-id="99913-105">**摘要：** 瞭解 [取得上次整合資料] 作業，該作業是 [通話品質儀表板] 的資料 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="99913-105">**Summary:** Learn about the Get Last Integration Data operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="99913-106">[通話品質儀表板] 是商務用 Skype Server 的工具。</span><span class="sxs-lookup"><span data-stu-id="99913-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="99913-107">[取得最後一個整合資料] 作業是 [通話品質儀表板] 的資料 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="99913-107">The Get Last Integration Data operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="get-last-integration-data"></a><span data-ttu-id="99913-108">取得上次整合資料</span><span class="sxs-lookup"><span data-stu-id="99913-108">Get Last Integration Data</span></span>

<span data-ttu-id="99913-109">[取得上次整合資料] 作業會傳回最後一次成功/失敗的存檔及 cube 處理的清單。</span><span class="sxs-lookup"><span data-stu-id="99913-109">Get Last Integration Data operation returns the list of last 5 success/failure of archiving and cube processing.</span></span>
  
<span data-ttu-id="99913-110">此功能預設為停用，必須透過設定資料 API 來啟用。</span><span class="sxs-lookup"><span data-stu-id="99913-110">This feature is disabled by default and it needs to be enabled by configuring the Data API.</span></span>
  

|<span data-ttu-id="99913-111">**法**</span><span class="sxs-lookup"><span data-stu-id="99913-111">**Method**</span></span>|<span data-ttu-id="99913-112">**要求 URI**</span><span class="sxs-lookup"><span data-stu-id="99913-112">**Request URI**</span></span>|<span data-ttu-id="99913-113">**HTTP 版本**</span><span class="sxs-lookup"><span data-stu-id="99913-113">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="99913-114">獲取</span><span class="sxs-lookup"><span data-stu-id="99913-114">GET</span></span>  <br/> |<span data-ttu-id="99913-115">HTTPs://\<入口\>網站/QoEDataService/IntegrationLog/Status</span><span class="sxs-lookup"><span data-stu-id="99913-115">https://\<portal\>/QoEDataService/IntegrationLog/Status</span></span>  <br/> |<span data-ttu-id="99913-116">HTTP/1。1</span><span class="sxs-lookup"><span data-stu-id="99913-116">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="99913-117">**URI 參數**-無。</span><span class="sxs-lookup"><span data-stu-id="99913-117">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="99913-118">**要求標頭**-沒有其他標頭。</span><span class="sxs-lookup"><span data-stu-id="99913-118">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="99913-119">**要求主體**-無。</span><span class="sxs-lookup"><span data-stu-id="99913-119">**Request Body** - None.</span></span>
  
 <span data-ttu-id="99913-120">**回應**-回應包括 HTTP 狀態碼和一組回應標頭。</span><span class="sxs-lookup"><span data-stu-id="99913-120">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="99913-121">**狀態碼**-成功的操作會傳回狀態碼200（確定）。</span><span class="sxs-lookup"><span data-stu-id="99913-121">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="99913-122">**回應標題**-沒有其他標頭。</span><span class="sxs-lookup"><span data-stu-id="99913-122">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="99913-123">**回應主體**-以下是記錄狀態的範例。</span><span class="sxs-lookup"><span data-stu-id="99913-123">**Response Body** - Below is a sample log status.</span></span>
  
```
{
"LastSuccessIntegrations": ["01/18/2015 10:30:13",
"01/18/2015 10:28:29",
"01/17/2015 15:15:17",
"01/17/2015 15:00:17",
"01/17/2015 14:45:13"],
"LastSuccessCubeProcessings": ["01/17/2015 15:16:40",
"01/17/2015 15:01:41",
"01/17/2015 14:47:19",
"01/17/2015 14:31:40",
"01/17/2015 14:17:01"],
"LastFailedIntegrations":  ,
"LastFailedCubeProcessings": ["01/18/2015 10:30:58",
"01/18/2015 10:29:28",
"01/17/2015 10:02:20",
"01/15/2015 20:01:56",
"01/15/2015 19:45:50"],
"LastDataIntegrationStart": null,
"LastCubeProcessingStart": "01/18/2015 10:30:16"
}
```
