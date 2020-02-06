---
title: UserAgent 視圖
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
ms.assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
description: '[UserAgent] 視圖儲存在資料庫中有記錄的會話中所涉及之使用者代理程式的相關資訊。 此視圖已在 Microsoft Lync Server 2013 中推出。'
ms.openlocfilehash: 76ac99b1fdadbeb6817b36483f4fe5762db47333
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805081"
---
# <a name="useragent-view"></a><span data-ttu-id="c0cf4-104">UserAgent 視圖</span><span class="sxs-lookup"><span data-stu-id="c0cf4-104">UserAgent view</span></span>
 
<span data-ttu-id="c0cf4-105">[UserAgent] 視圖儲存在資料庫中有記錄的會話中所涉及之使用者代理程式的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="c0cf4-105">The UserAgent View stores information about the user agents that have been involved in sessions that have records in the database.</span></span> <span data-ttu-id="c0cf4-106">此視圖已在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="c0cf4-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="c0cf4-107">**左欄**</span><span class="sxs-lookup"><span data-stu-id="c0cf4-107">**Column**</span></span>|<span data-ttu-id="c0cf4-108">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="c0cf4-108">**Data Type**</span></span>|<span data-ttu-id="c0cf4-109">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="c0cf4-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c0cf4-110">UserAgentKey</span><span class="sxs-lookup"><span data-stu-id="c0cf4-110">UserAgentKey</span></span>  <br/> |<span data-ttu-id="c0cf4-111">int</span><span class="sxs-lookup"><span data-stu-id="c0cf4-111">int</span></span>  <br/> |<span data-ttu-id="c0cf4-112">標識此使用者代理程式的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="c0cf4-112">Unique number identifying this user agent.</span></span>  <br/> |
|<span data-ttu-id="c0cf4-113">UserAgent</span><span class="sxs-lookup"><span data-stu-id="c0cf4-113">UserAgent</span></span>  <br/> |<span data-ttu-id="c0cf4-114">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="c0cf4-114">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="c0cf4-115">使用者代理程式字串。</span><span class="sxs-lookup"><span data-stu-id="c0cf4-115">User agent string.</span></span>  <br/> |
|<span data-ttu-id="c0cf4-116">UAType</span><span class="sxs-lookup"><span data-stu-id="c0cf4-116">UAType</span></span>  <br/> |<span data-ttu-id="c0cf4-117">Smallint</span><span class="sxs-lookup"><span data-stu-id="c0cf4-117">smallint</span></span>  <br/> |<span data-ttu-id="c0cf4-118">使用者代理程式類型。</span><span class="sxs-lookup"><span data-stu-id="c0cf4-118">Type of user agent.</span></span> <span data-ttu-id="c0cf4-119">如需詳細資訊，請參閱[UserAgent 資料表](useragent.md)。</span><span class="sxs-lookup"><span data-stu-id="c0cf4-119">See the [UserAgent table](useragent.md) for more details.</span></span> <br/> |
|<span data-ttu-id="c0cf4-120">UACategory</span><span class="sxs-lookup"><span data-stu-id="c0cf4-120">UACategory</span></span>  <br/> |<span data-ttu-id="c0cf4-121">Nvarchar （64）</span><span class="sxs-lookup"><span data-stu-id="c0cf4-121">nvarchar(64)</span></span>  <br/> |<span data-ttu-id="c0cf4-122">使用者代理所屬的類別。</span><span class="sxs-lookup"><span data-stu-id="c0cf4-122">Category that the user agent belongs to.</span></span> <span data-ttu-id="c0cf4-123">例如，Conferencing_Attendant_1 .0 的使用者代理程式屬於 UACategory CAA。</span><span class="sxs-lookup"><span data-stu-id="c0cf4-123">For example, the user agent Conferencing_Attendant_1.0 belongs to the UACategory CAA.</span></span>  <br/> |
   

