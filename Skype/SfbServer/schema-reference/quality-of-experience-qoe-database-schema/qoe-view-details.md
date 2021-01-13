---
title: QoE 檢視詳細資料
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6a658318-a317-4546-a44c-a9c473d8e86a
description: 檢視涵蓋從 QoE SQL 資料庫傳回資料時最常見的案例。 它是用來建立自訂報告的建議方式，而不是直接存取資料庫資料表;這是因為視圖很可能會讓未來的版本保持向後相容性。
ms.openlocfilehash: cabe483da624d801b9b87d51ba61caed7a22f7d4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834473"
---
# <a name="qoe-view-details"></a><span data-ttu-id="7577d-104">QoE 檢視詳細資料</span><span class="sxs-lookup"><span data-stu-id="7577d-104">QoE view details</span></span>
 
<span data-ttu-id="7577d-105">檢視涵蓋從 QoE SQL 資料庫傳回資料時最常見的案例。</span><span class="sxs-lookup"><span data-stu-id="7577d-105">Views cover the most common scenarios for returning data from the QoE SQL database.</span></span> <span data-ttu-id="7577d-106">它是用來建立自訂報告的建議方式，而不是直接存取資料庫資料表;這是因為視圖很可能會讓未來的版本保持向後相容性。</span><span class="sxs-lookup"><span data-stu-id="7577d-106">It is recommended views used for building custom reports instead of directly accessing the database tables; that's because views are more likely to maintain backwards compatibility with future releases.</span></span>
  
|<span data-ttu-id="7577d-107">**視圖名稱**</span><span class="sxs-lookup"><span data-stu-id="7577d-107">**View Name**</span></span>|<span data-ttu-id="7577d-108">**描述**</span><span class="sxs-lookup"><span data-stu-id="7577d-108">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="7577d-109">AudioStreamDetail view</span><span class="sxs-lookup"><span data-stu-id="7577d-109">AudioStreamDetail view</span></span>](audiostreamdetail.md) <br/> |<span data-ttu-id="7577d-110">儲存資料庫中每個音訊資料流的資訊。</span><span class="sxs-lookup"><span data-stu-id="7577d-110">Stores information about each audio stream in the database.</span></span>  <br/> |
|[<span data-ttu-id="7577d-111">MediaLine view</span><span class="sxs-lookup"><span data-stu-id="7577d-111">MediaLine view</span></span>](medialine.md) <br/> |<span data-ttu-id="7577d-112">儲存資料庫中每個媒體行的資訊。</span><span class="sxs-lookup"><span data-stu-id="7577d-112">Stores information about each media line in the database.</span></span> <span data-ttu-id="7577d-113">一個音訊工作階段通常包含一個音訊媒體行。</span><span class="sxs-lookup"><span data-stu-id="7577d-113">One audio session typically contains one audio media line.</span></span> <span data-ttu-id="7577d-114">一個音訊和視訊 (A/V) 工作階段通常包含一個音訊媒體行和一個視訊媒體行；不過，如果使用會議裝置或使用圖庫檢視，則工作階段可能包含兩個媒體行。</span><span class="sxs-lookup"><span data-stu-id="7577d-114">One audio and video (A/V) session typically contains one audio media line and one video media line; however, the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span>  <br/> |
|[<span data-ttu-id="7577d-115">NetworkConfigurationSettings view</span><span class="sxs-lookup"><span data-stu-id="7577d-115">NetworkConfigurationSettings view</span></span>](networkconfigurationsettings.md) <br/> |<span data-ttu-id="7577d-116">儲存網路設定的資訊。</span><span class="sxs-lookup"><span data-stu-id="7577d-116">Stores information about the network configuration.</span></span>  <br/> |
|[<span data-ttu-id="7577d-117">會話視圖</span><span class="sxs-lookup"><span data-stu-id="7577d-117">Session view</span></span>](session-0.md) <br/> |<span data-ttu-id="7577d-118">儲存在資料庫中擁有記錄之工作階段的資訊。</span><span class="sxs-lookup"><span data-stu-id="7577d-118">Stores information about sessions that have records in the database.</span></span>  <br/> |
|[<span data-ttu-id="7577d-119">UserAgent view</span><span class="sxs-lookup"><span data-stu-id="7577d-119">UserAgent view</span></span>](useragent-0.md) <br/> |<span data-ttu-id="7577d-120">儲存使用者代理程式的資訊，這些使用者代理程式與在資料庫中擁有記錄的工作階段相關。</span><span class="sxs-lookup"><span data-stu-id="7577d-120">Stores information about the user agents that have been involved in sessions that have records in the database.</span></span>  <br/> |
|[<span data-ttu-id="7577d-121">VideoStreamDetail view</span><span class="sxs-lookup"><span data-stu-id="7577d-121">VideoStreamDetail view</span></span>](videostreamdetail.md) <br/> |<span data-ttu-id="7577d-122">儲存在資料庫中每個視訊資料流的資訊。</span><span class="sxs-lookup"><span data-stu-id="7577d-122">Stores information about each video stream in the database.</span></span>  <br/> |
   

