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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 77c4dfae-1b29-4e81-ba05-609e61643998
description: UriTypes 資料表包含在商務用 Skype Server 2015 中監控的不同 URI （統一資源識別項）類型。
ms.openlocfilehash: 81cd00503f88eac03f952b63ef7a3bd9464c1f51
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814841"
---
# <a name="uritypes-table"></a><span data-ttu-id="c4497-103">UriTypes 表格</span><span class="sxs-lookup"><span data-stu-id="c4497-103">UriTypes table</span></span>
 
<span data-ttu-id="c4497-104">UriTypes 資料表包含在商務用 Skype Server 2015 中監控的不同 URI （統一資源識別項）類型。</span><span class="sxs-lookup"><span data-stu-id="c4497-104">The UriTypes Table contains the different URI (Uniform resource identifier) types monitored in Skype for Business Server 2015.</span></span>

<span data-ttu-id="c4497-105">在 CDR 資料庫建立之後，會建立兩筆記錄來代表 PhoneUri 和 UserUri，並在該記錄是動態指派的 UriTypeId。</span><span class="sxs-lookup"><span data-stu-id="c4497-105">When the CDR DB is created, two records to represent PhoneUri and UserUri are created, and records created after that are dynamically assigned UriTypeId.</span></span> 
  
|<span data-ttu-id="c4497-106">**左欄**</span><span class="sxs-lookup"><span data-stu-id="c4497-106">**Column**</span></span>|<span data-ttu-id="c4497-107">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="c4497-107">**Data Type**</span></span>|<span data-ttu-id="c4497-108">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="c4497-108">**Key/Index**</span></span>|<span data-ttu-id="c4497-109">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="c4497-109">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c4497-110">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="c4497-110">**UriTypeId**</span></span> <br/> |<span data-ttu-id="c4497-111">Tinyint</span><span class="sxs-lookup"><span data-stu-id="c4497-111">tinyint</span></span>  <br/> |<span data-ttu-id="c4497-112">首選</span><span class="sxs-lookup"><span data-stu-id="c4497-112">Primary</span></span>  <br/> |<span data-ttu-id="c4497-113">指派給 URI 類型的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="c4497-113">Unique identifier assigned to a URI type.</span></span>  <br/> <span data-ttu-id="c4497-114">可能的值-0 至255</span><span class="sxs-lookup"><span data-stu-id="c4497-114">Possible values - 0 to 255</span></span> |
|<span data-ttu-id="c4497-115">**UriType**</span><span class="sxs-lookup"><span data-stu-id="c4497-115">**UriType**</span></span> <br/> |<span data-ttu-id="c4497-116">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="c4497-116">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="c4497-117">不同 URI 類型的描述。</span><span class="sxs-lookup"><span data-stu-id="c4497-117">Descriptions of the different URI types.</span></span> <span data-ttu-id="c4497-118">下列值是預先指派的：</span><span class="sxs-lookup"><span data-stu-id="c4497-118">The following values are pre-assigned:</span></span> <br/>  <span data-ttu-id="c4497-119">1-電話 Uri</span><span class="sxs-lookup"><span data-stu-id="c4497-119">1 - Phone Uri</span></span> <br/>  <span data-ttu-id="c4497-120">0-使用者 Uri</span><span class="sxs-lookup"><span data-stu-id="c4497-120">0 - User Uri</span></span> <br/> <br/>  <span data-ttu-id="c4497-121">其他可能的類型包括：</span><span class="sxs-lookup"><span data-stu-id="c4497-121">Other possible types include:</span></span> <br/><span data-ttu-id="c4497-122">會議： applicationsharing</span><span class="sxs-lookup"><span data-stu-id="c4497-122">conf:applicationsharing</span></span> <br/> <span data-ttu-id="c4497-123">會議：音訊-影片</span><span class="sxs-lookup"><span data-stu-id="c4497-123">conf:audio-video</span></span><br/> <span data-ttu-id="c4497-124">會議：聊天</span><span class="sxs-lookup"><span data-stu-id="c4497-124">conf:chat</span></span><br/>    <span data-ttu-id="c4497-125">會議：焦點</span><span class="sxs-lookup"><span data-stu-id="c4497-125">conf:focus</span></span><br/>   <span data-ttu-id="c4497-126">mras</span><span class="sxs-lookup"><span data-stu-id="c4497-126">mras</span></span><br/>
