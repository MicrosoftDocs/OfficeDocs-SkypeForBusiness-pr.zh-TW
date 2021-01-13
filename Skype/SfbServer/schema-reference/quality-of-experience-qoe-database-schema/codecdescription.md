---
title: CodecDescription 表格
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3598acb8-7ea6-4748-8417-149c971c32a2
description: CodecDescription 表格會將唯一的轉碼器識別碼對應至它們對應的轉碼器。 轉碼器可用來為數位訊號編碼以利傳輸與廣播，然後將它們解碼以進行播放。 此表格已引進 Microsoft Lync Server 2013
ms.openlocfilehash: 95ba2218ff20aa6c67de6f60d6966916b6648a58
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831343"
---
# <a name="codecdescription-table"></a><span data-ttu-id="3366d-105">CodecDescription 表格</span><span class="sxs-lookup"><span data-stu-id="3366d-105">CodecDescription table</span></span>
 
<span data-ttu-id="3366d-106">CodecDescription 表格會將唯一的轉碼器識別碼對應至它們對應的轉碼器。</span><span class="sxs-lookup"><span data-stu-id="3366d-106">The CodecDescription table maps unique codec identifiers to their corresponding codec.</span></span> <span data-ttu-id="3366d-107">轉碼器可用來為數位訊號編碼以利傳輸與廣播，然後將它們解碼以進行播放。</span><span class="sxs-lookup"><span data-stu-id="3366d-107">Codecs are used to encode digital signals for transmission and broadcast, and then to decode those signals for playback.</span></span> <span data-ttu-id="3366d-108">此表格已引進 Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3366d-108">This table was introduced in Microsoft Lync Server 2013</span></span>
  
|<span data-ttu-id="3366d-109">**欄**</span><span class="sxs-lookup"><span data-stu-id="3366d-109">**Column**</span></span>|<span data-ttu-id="3366d-110">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="3366d-110">**Data Type**</span></span>|<span data-ttu-id="3366d-111">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="3366d-111">**Key/Index**</span></span>|<span data-ttu-id="3366d-112">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="3366d-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3366d-113">**CodecDescriptionKey**</span><span class="sxs-lookup"><span data-stu-id="3366d-113">**CodecDescriptionKey**</span></span> <br/> |<span data-ttu-id="3366d-114">Smallint</span><span class="sxs-lookup"><span data-stu-id="3366d-114">smallint</span></span>  <br/> |<span data-ttu-id="3366d-115">主要</span><span class="sxs-lookup"><span data-stu-id="3366d-115">Primary</span></span>  <br/> |<span data-ttu-id="3366d-116">指派給轉碼器的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="3366d-116">Unique identifier assigned to the codec.</span></span>  <br/> |
|<span data-ttu-id="3366d-117">**CodecDescription**</span><span class="sxs-lookup"><span data-stu-id="3366d-117">**CodecDescription**</span></span> <br/> |<span data-ttu-id="3366d-118">Varchar (256) </span><span class="sxs-lookup"><span data-stu-id="3366d-118">varchar(256)</span></span>  <br/> |<span data-ttu-id="3366d-119">Unique</span><span class="sxs-lookup"><span data-stu-id="3366d-119">Unique</span></span>  <br/> |<span data-ttu-id="3366d-120">對應至 CodecDescriptionKey 之轉碼器的唯一說明。</span><span class="sxs-lookup"><span data-stu-id="3366d-120">Unique description of the codec corresponding to the CodecDescriptionKey.</span></span>  <br/> |
   

