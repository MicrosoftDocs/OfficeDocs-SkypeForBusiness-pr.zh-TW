---
title: Phones 表格
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
ms.assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
description: '[電話] 資料表是支援表格。 資料表中的每一筆記錄都儲存 VoIP 通話中有記錄在資料庫中的一個電話號碼的相關資訊。'
ms.openlocfilehash: 3a78d2aba302041ce7db6e904e20f18fe71aa631
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815001"
---
# <a name="phones-table"></a><span data-ttu-id="1c3c7-104">Phones 表格</span><span class="sxs-lookup"><span data-stu-id="1c3c7-104">Phones table</span></span>
 
<span data-ttu-id="1c3c7-105">[電話] 資料表是支援表格。</span><span class="sxs-lookup"><span data-stu-id="1c3c7-105">The Phones table is a supporting table.</span></span> <span data-ttu-id="1c3c7-106">資料表中的每一筆記錄都儲存 VoIP 通話中有記錄在資料庫中的一個電話號碼的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="1c3c7-106">Each record in the table stores information about one phone number involved in VoIP calls that have records in the database.</span></span>
  
|<span data-ttu-id="1c3c7-107">**左欄**</span><span class="sxs-lookup"><span data-stu-id="1c3c7-107">**Column**</span></span>|<span data-ttu-id="1c3c7-108">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="1c3c7-108">**Data Type**</span></span>|<span data-ttu-id="1c3c7-109">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="1c3c7-109">**Key/Index**</span></span>|<span data-ttu-id="1c3c7-110">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="1c3c7-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1c3c7-111">**PhoneId**</span><span class="sxs-lookup"><span data-stu-id="1c3c7-111">**PhoneId**</span></span> <br/> |<span data-ttu-id="1c3c7-112">int</span><span class="sxs-lookup"><span data-stu-id="1c3c7-112">int</span></span>  <br/> |<span data-ttu-id="1c3c7-113">首選</span><span class="sxs-lookup"><span data-stu-id="1c3c7-113">Primary</span></span>  <br/> |<span data-ttu-id="1c3c7-114">標識此手機的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="1c3c7-114">Unique number identifying this phone.</span></span>  <br/> |
|<span data-ttu-id="1c3c7-115">**PhoneUri**</span><span class="sxs-lookup"><span data-stu-id="1c3c7-115">**PhoneUri**</span></span> <br/> |<span data-ttu-id="1c3c7-116">Nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="1c3c7-116">nvarchar(450)</span></span>  <br/> | <br/> |<span data-ttu-id="1c3c7-117">電話號碼。</span><span class="sxs-lookup"><span data-stu-id="1c3c7-117">Phone number.</span></span>  <br/> |
|<span data-ttu-id="1c3c7-118">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="1c3c7-118">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="1c3c7-119">dateTime</span><span class="sxs-lookup"><span data-stu-id="1c3c7-119">dateTime</span></span>  <br/> ||<span data-ttu-id="1c3c7-120">時間戳記（僅供內部使用）。</span><span class="sxs-lookup"><span data-stu-id="1c3c7-120">Time stamp (for internal use only).</span></span>  <br/> <span data-ttu-id="1c3c7-121">此欄位是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="1c3c7-121">This field was introduced in Microsoft Lync Server 2013.</span></span>  <br/> |
   

