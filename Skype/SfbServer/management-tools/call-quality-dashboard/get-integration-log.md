---
title: 取得整合記錄
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 8856f6bc-5460-4f35-acf2-f7662f01579b
description: 摘要：瞭解「取得整合記錄」作業，此作業是「通話品質」儀表板的資料 API 的一部分。 通話品質儀表板是商務用 Skype 伺服器的工具。
ms.openlocfilehash: 69827fa9f3fd3f56843a41867b029a071799ba66
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832593"
---
# <a name="get-integration-log"></a><span data-ttu-id="15bc2-104">取得整合記錄</span><span class="sxs-lookup"><span data-stu-id="15bc2-104">Get Integration Log</span></span>
 
<span data-ttu-id="15bc2-105">**摘要：** 深入瞭解「取得整合記錄」作業，此作業是「呼叫品質」儀表板的資料 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="15bc2-105">**Summary:** Learn about the Get Integration Log operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="15bc2-106">通話品質儀表板是商務用 Skype 伺服器的工具。</span><span class="sxs-lookup"><span data-stu-id="15bc2-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="15bc2-107">「取得整合記錄」作業是「通話品質」儀表板之資料 API 的一部分</span><span class="sxs-lookup"><span data-stu-id="15bc2-107">The Get Integration Log operation is part of the Data API for Call Quality Dashboard</span></span>
  
## <a name="get-integration-log"></a><span data-ttu-id="15bc2-108">取得整合記錄</span><span class="sxs-lookup"><span data-stu-id="15bc2-108">Get Integration Log</span></span>

<span data-ttu-id="15bc2-109">取得整合記錄作業會傳回描述 QoE Cube 處理中之活動的記錄專案清單。</span><span class="sxs-lookup"><span data-stu-id="15bc2-109">Get Integration Log operation returns a list of log entries describing the activities in QoE Cube processing.</span></span>
  
<span data-ttu-id="15bc2-110">根據安全性原因，預設會停用此作業。</span><span class="sxs-lookup"><span data-stu-id="15bc2-110">This operation is disabled by default for security reasons.</span></span> <span data-ttu-id="15bc2-111">停用時，它會傳回空字串。</span><span class="sxs-lookup"><span data-stu-id="15bc2-111">When disabled, it returns an empty string.</span></span> <span data-ttu-id="15bc2-112">若要啟用此操作，管理員必須為數據 API 的主 web 應用程式設定 web.config。</span><span class="sxs-lookup"><span data-stu-id="15bc2-112">To enable this operation, administrators need to configure the web.config for Data API's host web application.</span></span>
  

|<span data-ttu-id="15bc2-113">方法</span><span class="sxs-lookup"><span data-stu-id="15bc2-113">Method</span></span>|<span data-ttu-id="15bc2-114">**要求 URI**</span><span class="sxs-lookup"><span data-stu-id="15bc2-114">**Request URI**</span></span>|<span data-ttu-id="15bc2-115">**HTTP 版本**</span><span class="sxs-lookup"><span data-stu-id="15bc2-115">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="15bc2-116">GET</span><span class="sxs-lookup"><span data-stu-id="15bc2-116">GET</span></span>  <br/> |<span data-ttu-id="15bc2-117">HTTPs:// \<portal\> /QoEDataService/IntegrationLog</span><span class="sxs-lookup"><span data-stu-id="15bc2-117">https://\<portal\>/QoEDataService/IntegrationLog</span></span>  <br/> |<span data-ttu-id="15bc2-118">HTTP/1。1</span><span class="sxs-lookup"><span data-stu-id="15bc2-118">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="15bc2-119">**URI 參數** -無。</span><span class="sxs-lookup"><span data-stu-id="15bc2-119">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="15bc2-120">**要求標頭** -沒有其他標頭。</span><span class="sxs-lookup"><span data-stu-id="15bc2-120">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="15bc2-121">**要求正文** -無。</span><span class="sxs-lookup"><span data-stu-id="15bc2-121">**Request Body** - None.</span></span>
  
 <span data-ttu-id="15bc2-122">**回應** -回應包括 HTTP 狀態碼和一組回應標頭。</span><span class="sxs-lookup"><span data-stu-id="15bc2-122">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="15bc2-123">**狀態碼** -成功的作業會傳回狀態碼 200 (確定) 。</span><span class="sxs-lookup"><span data-stu-id="15bc2-123">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="15bc2-124">**回應標頭** -沒有其他標頭。</span><span class="sxs-lookup"><span data-stu-id="15bc2-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="15bc2-125">**回應** 內文-以下是記錄專案的範例結構。</span><span class="sxs-lookup"><span data-stu-id="15bc2-125">**Response Body** - Below is a sample structure of log entries.</span></span>
  
```json
[
{"LogCategory":"<category>","LogTime":"2015-03-18T10:28:29.10","LogDescription":"<log description>"}
]
```


