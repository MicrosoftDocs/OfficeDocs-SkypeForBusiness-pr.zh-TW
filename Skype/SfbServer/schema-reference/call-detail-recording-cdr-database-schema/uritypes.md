---
title: UriTypes 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 77c4dfae-1b29-4e81-ba05-609e61643998
description: UriTypes 資料表包含在商務用 Skype Server 2015 中監控的不同 URI (統一資源識別項) 類型。
ms.openlocfilehash: 5ad8e1d0432aff3278f897fbe82d3759ad3c95e1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192785"
---
# <a name="uritypes-table"></a><span data-ttu-id="9c935-103">UriTypes 表格</span><span class="sxs-lookup"><span data-stu-id="9c935-103">UriTypes table</span></span>
 
<span data-ttu-id="9c935-104">UriTypes 資料表包含在商務用 Skype Server 2015 中監控的不同 URI (統一資源識別項) 類型。</span><span class="sxs-lookup"><span data-stu-id="9c935-104">The UriTypes Table contains the different URI (Uniform resource identifier) types monitored in Skype for Business Server 2015.</span></span>

<span data-ttu-id="9c935-105">在 CDR 資料庫建立之後, 會建立兩筆記錄來代表 PhoneUri 和 UserUri, 並在該記錄是動態指派的 UriTypeId。</span><span class="sxs-lookup"><span data-stu-id="9c935-105">When the CDR DB is created, two records to represent PhoneUri and UserUri are created, and records created after that are dynamically assigned UriTypeId.</span></span> 
  
|<span data-ttu-id="9c935-106">**左欄**</span><span class="sxs-lookup"><span data-stu-id="9c935-106">**Column**</span></span>|<span data-ttu-id="9c935-107">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="9c935-107">**Data Type**</span></span>|<span data-ttu-id="9c935-108">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="9c935-108">**Key/Index**</span></span>|<span data-ttu-id="9c935-109">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="9c935-109">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9c935-110">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="9c935-110">**UriTypeId**</span></span> <br/> |<span data-ttu-id="9c935-111">Tinyint</span><span class="sxs-lookup"><span data-stu-id="9c935-111">tinyint</span></span>  <br/> |<span data-ttu-id="9c935-112">首選</span><span class="sxs-lookup"><span data-stu-id="9c935-112">Primary</span></span>  <br/> |<span data-ttu-id="9c935-113">指派給 URI 類型的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="9c935-113">Unique identifier assigned to a URI type.</span></span>  <br/> <span data-ttu-id="9c935-114">可能的值-0 至255</span><span class="sxs-lookup"><span data-stu-id="9c935-114">Possible values - 0 to 255</span></span> |
|<span data-ttu-id="9c935-115">**UriType**</span><span class="sxs-lookup"><span data-stu-id="9c935-115">**UriType**</span></span> <br/> |<span data-ttu-id="9c935-116">Nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9c935-116">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="9c935-117">不同 URI 類型的描述。</span><span class="sxs-lookup"><span data-stu-id="9c935-117">Descriptions of the different URI types.</span></span> <span data-ttu-id="9c935-118">下列值是預先指派的:</span><span class="sxs-lookup"><span data-stu-id="9c935-118">The following values are pre-assigned:</span></span> <br/>  <span data-ttu-id="9c935-119">1-電話 Uri</span><span class="sxs-lookup"><span data-stu-id="9c935-119">1 - Phone Uri</span></span> <br/>  <span data-ttu-id="9c935-120">0-使用者 Uri</span><span class="sxs-lookup"><span data-stu-id="9c935-120">0 - User Uri</span></span> <br/> <br/>  <span data-ttu-id="9c935-121">其他可能的類型包括:</span><span class="sxs-lookup"><span data-stu-id="9c935-121">Other possible types include:</span></span> <br/><span data-ttu-id="9c935-122">會議: applicationsharing</span><span class="sxs-lookup"><span data-stu-id="9c935-122">conf:applicationsharing</span></span> <br/> <span data-ttu-id="9c935-123">會議: 音訊-影片</span><span class="sxs-lookup"><span data-stu-id="9c935-123">conf:audio-video</span></span><br/> <span data-ttu-id="9c935-124">會議: 聊天</span><span class="sxs-lookup"><span data-stu-id="9c935-124">conf:chat</span></span><br/>    <span data-ttu-id="9c935-125">會議: 焦點</span><span class="sxs-lookup"><span data-stu-id="9c935-125">conf:focus</span></span><br/>   <span data-ttu-id="9c935-126">mras</span><span class="sxs-lookup"><span data-stu-id="9c935-126">mras</span></span><br/>
