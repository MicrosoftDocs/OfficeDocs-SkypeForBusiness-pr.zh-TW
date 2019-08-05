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
localization_priority: Normal
ms.assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
description: '[ConferenceMessageCount] 視圖儲存使用者傳送給會議的郵件數目的相關資訊。 此視圖已在 Microsoft Lync Server 2013 中推出。'
ms.openlocfilehash: 890a5912c6f828f614fbff89627c94c4e12ba7e1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192894"
---
# <a name="conferencemessagecount-view"></a><span data-ttu-id="0605e-104">ConferenceMessageCount 視圖</span><span class="sxs-lookup"><span data-stu-id="0605e-104">ConferenceMessageCount view</span></span>
 
<span data-ttu-id="0605e-105">[ConferenceMessageCount] 視圖儲存使用者傳送給會議的郵件數目的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="0605e-105">The ConferenceMessageCount view stores information about how many messages were sent by a user to a conference.</span></span> <span data-ttu-id="0605e-106">此視圖已在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="0605e-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0605e-107">[ConferenceMessageCount] 視圖會包含 [ [ConferenceSessionDetails] 視圖](conferencesessiondetails.md)中的所有資料行, 以及下方所列的欄。</span><span class="sxs-lookup"><span data-stu-id="0605e-107">The ConferenceMessageCount view contains all of the columns in the [ConferenceSessionDetails view](conferencesessiondetails.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="0605e-108">**左欄**</span><span class="sxs-lookup"><span data-stu-id="0605e-108">**Column**</span></span>|<span data-ttu-id="0605e-109">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="0605e-109">**Data Type**</span></span>|<span data-ttu-id="0605e-110">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="0605e-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0605e-111">**UserUri**</span><span class="sxs-lookup"><span data-stu-id="0605e-111">**UserUri**</span></span> <br/> |<span data-ttu-id="0605e-112">Nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="0605e-112">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="0605e-113">傳送郵件之使用者的 URI。</span><span class="sxs-lookup"><span data-stu-id="0605e-113">URI of the user who sent the message.</span></span>  <br/> |
|<span data-ttu-id="0605e-114">**UserUriType**</span><span class="sxs-lookup"><span data-stu-id="0605e-114">**UserUriType**</span></span> <br/> |<span data-ttu-id="0605e-115">Nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="0605e-115">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="0605e-116">傳送郵件之使用者的 URI 類型。</span><span class="sxs-lookup"><span data-stu-id="0605e-116">Type of URI of the user who sent the messages.</span></span> <span data-ttu-id="0605e-117">如需詳細資訊, 請參閱[UriTypes 資料表](uritypes.md)。</span><span class="sxs-lookup"><span data-stu-id="0605e-117">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
|<span data-ttu-id="0605e-118">**UserTenant**</span><span class="sxs-lookup"><span data-stu-id="0605e-118">**UserTenant**</span></span> <br/> |<span data-ttu-id="0605e-119">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="0605e-119">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="0605e-120">傳送訊息的使用者租使用者。</span><span class="sxs-lookup"><span data-stu-id="0605e-120">Tenant of user who sent the messages.</span></span> <span data-ttu-id="0605e-121">如需詳細資訊, 請參閱[承租人資料表](tenants.md)。</span><span class="sxs-lookup"><span data-stu-id="0605e-121">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="0605e-122">**UserMessageCount**</span><span class="sxs-lookup"><span data-stu-id="0605e-122">**UserMessageCount**</span></span> <br/> |<span data-ttu-id="0605e-123">Smallint</span><span class="sxs-lookup"><span data-stu-id="0605e-123">smallint</span></span>  <br/> |<span data-ttu-id="0605e-124">使用者在會議會話期間傳送的訊息數目。</span><span class="sxs-lookup"><span data-stu-id="0605e-124">Number of messages sent by the user during the conference session.</span></span>  <br/> |
   

