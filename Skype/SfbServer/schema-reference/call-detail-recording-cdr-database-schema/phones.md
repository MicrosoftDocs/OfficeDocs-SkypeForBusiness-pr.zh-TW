---
title: 電話表格
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
ms.assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
description: 電話系表是支援的表格。 資料表中的每一筆記錄都儲存在包含資料庫中記錄的 VoIP 通話中相關的一個電話號碼相關資訊。
ms.openlocfilehash: 12825423b9a03bff93e0d70705a4083bb8c881c9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823263"
---
# <a name="phones-table"></a><span data-ttu-id="34166-104">電話表格</span><span class="sxs-lookup"><span data-stu-id="34166-104">Phones table</span></span>
 
<span data-ttu-id="34166-105">電話系表是支援的表格。</span><span class="sxs-lookup"><span data-stu-id="34166-105">The Phones table is a supporting table.</span></span> <span data-ttu-id="34166-106">資料表中的每一筆記錄都儲存在包含資料庫中記錄的 VoIP 通話中相關的一個電話號碼相關資訊。</span><span class="sxs-lookup"><span data-stu-id="34166-106">Each record in the table stores information about one phone number involved in VoIP calls that have records in the database.</span></span>
  
|<span data-ttu-id="34166-107">**欄**</span><span class="sxs-lookup"><span data-stu-id="34166-107">**Column**</span></span>|<span data-ttu-id="34166-108">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="34166-108">**Data Type**</span></span>|<span data-ttu-id="34166-109">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="34166-109">**Key/Index**</span></span>|<span data-ttu-id="34166-110">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="34166-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="34166-111">**PhoneId**</span><span class="sxs-lookup"><span data-stu-id="34166-111">**PhoneId**</span></span> <br/> |<span data-ttu-id="34166-112">int</span><span class="sxs-lookup"><span data-stu-id="34166-112">int</span></span>  <br/> |<span data-ttu-id="34166-113">主要</span><span class="sxs-lookup"><span data-stu-id="34166-113">Primary</span></span>  <br/> |<span data-ttu-id="34166-114">用於識別此電話的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="34166-114">Unique number identifying this phone.</span></span>  <br/> |
|<span data-ttu-id="34166-115">**PhoneUri**</span><span class="sxs-lookup"><span data-stu-id="34166-115">**PhoneUri**</span></span> <br/> |<span data-ttu-id="34166-116">Nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="34166-116">nvarchar(450)</span></span>  <br/> | <br/> |<span data-ttu-id="34166-117">電話號碼。</span><span class="sxs-lookup"><span data-stu-id="34166-117">Phone number.</span></span>  <br/> |
|<span data-ttu-id="34166-118">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="34166-118">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="34166-119">Datetime</span><span class="sxs-lookup"><span data-stu-id="34166-119">dateTime</span></span>  <br/> ||<span data-ttu-id="34166-120">僅供內部使用) 的時間戳記 (。</span><span class="sxs-lookup"><span data-stu-id="34166-120">Time stamp (for internal use only).</span></span>  <br/> <span data-ttu-id="34166-121">此欄位是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="34166-121">This field was introduced in Microsoft Lync Server 2013.</span></span>  <br/> |
   

