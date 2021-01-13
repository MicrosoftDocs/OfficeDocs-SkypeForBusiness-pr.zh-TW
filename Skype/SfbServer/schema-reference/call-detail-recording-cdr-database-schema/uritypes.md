---
title: UriTypes 表格
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
ms.assetid: 77c4dfae-1b29-4e81-ba05-609e61643998
description: UriTypes 表格包含在商務用 Skype Server 2015 中監控的不同 URI (統一資源識別項) 類型。
ms.openlocfilehash: 622384086dbd1031633b70758cdcea600ad31d43
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831683"
---
# <a name="uritypes-table"></a><span data-ttu-id="05550-103">UriTypes 表格</span><span class="sxs-lookup"><span data-stu-id="05550-103">UriTypes table</span></span>
 
<span data-ttu-id="05550-104">UriTypes 表格包含在商務用 Skype Server 2015 中監控的不同 URI (統一資源識別項) 類型。</span><span class="sxs-lookup"><span data-stu-id="05550-104">The UriTypes Table contains the different URI (Uniform resource identifier) types monitored in Skype for Business Server 2015.</span></span>

<span data-ttu-id="05550-105">在建立 CDR DB 時，會建立兩個代表 PhoneUri 和 UserUri 的記錄，並在該之後建立的記錄會以動態方式指派 UriTypeId。</span><span class="sxs-lookup"><span data-stu-id="05550-105">When the CDR DB is created, two records to represent PhoneUri and UserUri are created, and records created after that are dynamically assigned UriTypeId.</span></span> 
  
|<span data-ttu-id="05550-106">**欄**</span><span class="sxs-lookup"><span data-stu-id="05550-106">**Column**</span></span>|<span data-ttu-id="05550-107">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="05550-107">**Data Type**</span></span>|<span data-ttu-id="05550-108">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="05550-108">**Key/Index**</span></span>|<span data-ttu-id="05550-109">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="05550-109">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="05550-110">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="05550-110">**UriTypeId**</span></span> <br/> |<span data-ttu-id="05550-111">Tinyint</span><span class="sxs-lookup"><span data-stu-id="05550-111">tinyint</span></span>  <br/> |<span data-ttu-id="05550-112">主要</span><span class="sxs-lookup"><span data-stu-id="05550-112">Primary</span></span>  <br/> |<span data-ttu-id="05550-113">指派給 URI 類型的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="05550-113">Unique identifier assigned to a URI type.</span></span>  <br/> <span data-ttu-id="05550-114">可能的值-0 至255</span><span class="sxs-lookup"><span data-stu-id="05550-114">Possible values - 0 to 255</span></span> |
|<span data-ttu-id="05550-115">**UriType**</span><span class="sxs-lookup"><span data-stu-id="05550-115">**UriType**</span></span> <br/> |<span data-ttu-id="05550-116">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="05550-116">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="05550-117">不同 URI 類型的描述。</span><span class="sxs-lookup"><span data-stu-id="05550-117">Descriptions of the different URI types.</span></span> <span data-ttu-id="05550-118">下列值是預先指派的：</span><span class="sxs-lookup"><span data-stu-id="05550-118">The following values are pre-assigned:</span></span> <br/>  <span data-ttu-id="05550-119">1-電話 Uri</span><span class="sxs-lookup"><span data-stu-id="05550-119">1 - Phone Uri</span></span> <br/>  <span data-ttu-id="05550-120">0-使用者 Uri</span><span class="sxs-lookup"><span data-stu-id="05550-120">0 - User Uri</span></span> <br/> <br/>  <span data-ttu-id="05550-121">其他可能類型包括：</span><span class="sxs-lookup"><span data-stu-id="05550-121">Other possible types include:</span></span> <br/><span data-ttu-id="05550-122">會議： applicationsharing</span><span class="sxs-lookup"><span data-stu-id="05550-122">conf:applicationsharing</span></span> <br/> <span data-ttu-id="05550-123">會議：音訊-影片</span><span class="sxs-lookup"><span data-stu-id="05550-123">conf:audio-video</span></span><br/> <span data-ttu-id="05550-124">會議：聊天</span><span class="sxs-lookup"><span data-stu-id="05550-124">conf:chat</span></span><br/>    <span data-ttu-id="05550-125">會議：焦點</span><span class="sxs-lookup"><span data-stu-id="05550-125">conf:focus</span></span><br/>   <span data-ttu-id="05550-126">Mras</span><span class="sxs-lookup"><span data-stu-id="05550-126">mras</span></span><br/>
