---
title: ConferenceMessageCount 視圖
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
ms.assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
description: '[ConferenceMessageCount] 視圖儲存使用者傳送給會議的郵件數目的相關資訊。 此視圖已在 Microsoft Lync Server 2013 中推出。'
ms.openlocfilehash: a766e63fbca5c30cec3c3891c9ccfc2355f16d2d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815381"
---
# <a name="conferencemessagecount-view"></a><span data-ttu-id="45fc7-104">ConferenceMessageCount 視圖</span><span class="sxs-lookup"><span data-stu-id="45fc7-104">ConferenceMessageCount view</span></span>
 
<span data-ttu-id="45fc7-105">[ConferenceMessageCount] 視圖儲存使用者傳送給會議的郵件數目的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="45fc7-105">The ConferenceMessageCount view stores information about how many messages were sent by a user to a conference.</span></span> <span data-ttu-id="45fc7-106">此視圖已在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="45fc7-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="45fc7-107">[ConferenceMessageCount] 視圖會包含 [ [ConferenceSessionDetails] 視圖](conferencesessiondetails.md)中的所有資料行，以及下方所列的欄。</span><span class="sxs-lookup"><span data-stu-id="45fc7-107">The ConferenceMessageCount view contains all of the columns in the [ConferenceSessionDetails view](conferencesessiondetails.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="45fc7-108">**左欄**</span><span class="sxs-lookup"><span data-stu-id="45fc7-108">**Column**</span></span>|<span data-ttu-id="45fc7-109">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="45fc7-109">**Data Type**</span></span>|<span data-ttu-id="45fc7-110">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="45fc7-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="45fc7-111">**UserUri**</span><span class="sxs-lookup"><span data-stu-id="45fc7-111">**UserUri**</span></span> <br/> |<span data-ttu-id="45fc7-112">Nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="45fc7-112">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="45fc7-113">傳送郵件之使用者的 URI。</span><span class="sxs-lookup"><span data-stu-id="45fc7-113">URI of the user who sent the message.</span></span>  <br/> |
|<span data-ttu-id="45fc7-114">**UserUriType**</span><span class="sxs-lookup"><span data-stu-id="45fc7-114">**UserUriType**</span></span> <br/> |<span data-ttu-id="45fc7-115">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="45fc7-115">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="45fc7-116">傳送郵件之使用者的 URI 類型。</span><span class="sxs-lookup"><span data-stu-id="45fc7-116">Type of URI of the user who sent the messages.</span></span> <span data-ttu-id="45fc7-117">如需詳細資訊，請參閱[UriTypes 資料表](uritypes.md)。</span><span class="sxs-lookup"><span data-stu-id="45fc7-117">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
|<span data-ttu-id="45fc7-118">**UserTenant**</span><span class="sxs-lookup"><span data-stu-id="45fc7-118">**UserTenant**</span></span> <br/> |<span data-ttu-id="45fc7-119">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="45fc7-119">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="45fc7-120">傳送訊息的使用者租使用者。</span><span class="sxs-lookup"><span data-stu-id="45fc7-120">Tenant of user who sent the messages.</span></span> <span data-ttu-id="45fc7-121">如需詳細資訊，請參閱[承租人資料表](tenants.md)。</span><span class="sxs-lookup"><span data-stu-id="45fc7-121">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="45fc7-122">**UserMessageCount**</span><span class="sxs-lookup"><span data-stu-id="45fc7-122">**UserMessageCount**</span></span> <br/> |<span data-ttu-id="45fc7-123">Smallint</span><span class="sxs-lookup"><span data-stu-id="45fc7-123">smallint</span></span>  <br/> |<span data-ttu-id="45fc7-124">使用者在會議會話期間傳送的訊息數目。</span><span class="sxs-lookup"><span data-stu-id="45fc7-124">Number of messages sent by the user during the conference session.</span></span>  <br/> |
   

