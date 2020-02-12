---
title: 取得整合記錄
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
ms.assetid: 8856f6bc-5460-4f35-acf2-f7662f01579b
description: 摘要：瞭解 [取得整合記錄] 作業，該作業是 [通話品質儀表板] 的資料 API 的一部分。 [通話品質儀表板] 是商務用 Skype Server 的工具。
ms.openlocfilehash: e1d790f4723eaaf716482143f08c78624db47433
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888802"
---
# <a name="get-integration-log"></a><span data-ttu-id="b0e7c-104">取得整合記錄</span><span class="sxs-lookup"><span data-stu-id="b0e7c-104">Get Integration Log</span></span>
 
<span data-ttu-id="b0e7c-105">**摘要：** 瞭解 [取得整合記錄] 作業，該作業是 [通話品質儀表板] 的資料 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="b0e7c-105">**Summary:** Learn about the Get Integration Log operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="b0e7c-106">[通話品質儀表板] 是商務用 Skype Server 的工具。</span><span class="sxs-lookup"><span data-stu-id="b0e7c-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="b0e7c-107">[取得整合記錄] 作業是 [通話品質] 儀表板的資料 API 的一部分</span><span class="sxs-lookup"><span data-stu-id="b0e7c-107">The Get Integration Log operation is part of the Data API for Call Quality Dashboard</span></span>
  
## <a name="get-integration-log"></a><span data-ttu-id="b0e7c-108">取得整合記錄</span><span class="sxs-lookup"><span data-stu-id="b0e7c-108">Get Integration Log</span></span>

<span data-ttu-id="b0e7c-109">取得整合記錄作業會傳回說明 QoE Cube 處理中之活動的記錄專案清單。</span><span class="sxs-lookup"><span data-stu-id="b0e7c-109">Get Integration Log operation returns a list of log entries describing the activities in QoE Cube processing.</span></span>
  
<span data-ttu-id="b0e7c-110">出於安全性考慮，預設會停用這個作業。</span><span class="sxs-lookup"><span data-stu-id="b0e7c-110">This operation is disabled by default for security reasons.</span></span> <span data-ttu-id="b0e7c-111">停用時，會傳回空字串。</span><span class="sxs-lookup"><span data-stu-id="b0e7c-111">When disabled, it returns an empty string.</span></span> <span data-ttu-id="b0e7c-112">若要啟用此操作，系統管理員必須針對資料 API 的主機 web 應用程式設定 web.config。</span><span class="sxs-lookup"><span data-stu-id="b0e7c-112">To enable this operation, administrators need to configure the web.config for Data API's host web application.</span></span>
  

|<span data-ttu-id="b0e7c-113">法</span><span class="sxs-lookup"><span data-stu-id="b0e7c-113">Method</span></span>|<span data-ttu-id="b0e7c-114">**要求 URI**</span><span class="sxs-lookup"><span data-stu-id="b0e7c-114">**Request URI**</span></span>|<span data-ttu-id="b0e7c-115">**HTTP 版本**</span><span class="sxs-lookup"><span data-stu-id="b0e7c-115">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b0e7c-116">獲取</span><span class="sxs-lookup"><span data-stu-id="b0e7c-116">GET</span></span>  <br/> |<span data-ttu-id="b0e7c-117">HTTPs://\<入口\>網站/QoEDataService/IntegrationLog</span><span class="sxs-lookup"><span data-stu-id="b0e7c-117">https://\<portal\>/QoEDataService/IntegrationLog</span></span>  <br/> |<span data-ttu-id="b0e7c-118">HTTP/1。1</span><span class="sxs-lookup"><span data-stu-id="b0e7c-118">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="b0e7c-119">**URI 參數**-無。</span><span class="sxs-lookup"><span data-stu-id="b0e7c-119">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="b0e7c-120">**要求標頭**-沒有其他標頭。</span><span class="sxs-lookup"><span data-stu-id="b0e7c-120">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="b0e7c-121">**要求主體**-無。</span><span class="sxs-lookup"><span data-stu-id="b0e7c-121">**Request Body** - None.</span></span>
  
 <span data-ttu-id="b0e7c-122">**回應**-回應包括 HTTP 狀態碼和一組回應標頭。</span><span class="sxs-lookup"><span data-stu-id="b0e7c-122">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="b0e7c-123">**狀態碼**-成功的操作會傳回狀態碼200（確定）。</span><span class="sxs-lookup"><span data-stu-id="b0e7c-123">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="b0e7c-124">**回應標題**-沒有其他標頭。</span><span class="sxs-lookup"><span data-stu-id="b0e7c-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="b0e7c-125">**回應主體**-以下是記錄專案的範例結構。</span><span class="sxs-lookup"><span data-stu-id="b0e7c-125">**Response Body** - Below is a sample structure of log entries.</span></span>
  
```json
[
{"LogCategory":"<category>","LogTime":"2015-03-18T10:28:29.10","LogDescription":"<log description>"}
]
```


