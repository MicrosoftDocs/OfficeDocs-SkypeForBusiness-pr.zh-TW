---
title: ConferenceMessageCount view
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
ms.assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
description: ConferenceMessageCount view 儲存使用者傳送給會議的郵件數目資訊。 此視圖已引進于 Microsoft Lync Server 2013。
ms.openlocfilehash: 8394ed37d4b85e8ec5fcda4234b4c28f4276fb17
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813293"
---
# <a name="conferencemessagecount-view"></a><span data-ttu-id="3d280-104">ConferenceMessageCount view</span><span class="sxs-lookup"><span data-stu-id="3d280-104">ConferenceMessageCount view</span></span>
 
<span data-ttu-id="3d280-105">ConferenceMessageCount view 儲存使用者傳送給會議的郵件數目資訊。</span><span class="sxs-lookup"><span data-stu-id="3d280-105">The ConferenceMessageCount view stores information about how many messages were sent by a user to a conference.</span></span> <span data-ttu-id="3d280-106">此視圖已引進于 Microsoft Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="3d280-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3d280-107">ConferenceMessageCount view 包含 [ConferenceSessionDetails 視圖](conferencesessiondetails.md) 中的所有欄，此外還會包含下列欄。</span><span class="sxs-lookup"><span data-stu-id="3d280-107">The ConferenceMessageCount view contains all of the columns in the [ConferenceSessionDetails view](conferencesessiondetails.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="3d280-108">**欄**</span><span class="sxs-lookup"><span data-stu-id="3d280-108">**Column**</span></span>|<span data-ttu-id="3d280-109">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="3d280-109">**Data Type**</span></span>|<span data-ttu-id="3d280-110">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="3d280-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3d280-111">**UserUri**</span><span class="sxs-lookup"><span data-stu-id="3d280-111">**UserUri**</span></span> <br/> |<span data-ttu-id="3d280-112">Nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="3d280-112">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="3d280-113">傳送郵件之使用者的 URI。</span><span class="sxs-lookup"><span data-stu-id="3d280-113">URI of the user who sent the message.</span></span>  <br/> |
|<span data-ttu-id="3d280-114">**UserUriType**</span><span class="sxs-lookup"><span data-stu-id="3d280-114">**UserUriType**</span></span> <br/> |<span data-ttu-id="3d280-115">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="3d280-115">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="3d280-116">傳送郵件之使用者的 URI 類型。</span><span class="sxs-lookup"><span data-stu-id="3d280-116">Type of URI of the user who sent the messages.</span></span> <span data-ttu-id="3d280-117">如需詳細資訊，請參閱 [UriTypes 表格](uritypes.md) 。</span><span class="sxs-lookup"><span data-stu-id="3d280-117">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
|<span data-ttu-id="3d280-118">**UserTenant**</span><span class="sxs-lookup"><span data-stu-id="3d280-118">**UserTenant**</span></span> <br/> |<span data-ttu-id="3d280-119">唯一</span><span class="sxs-lookup"><span data-stu-id="3d280-119">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="3d280-120">傳送訊息之使用者的租使用者。</span><span class="sxs-lookup"><span data-stu-id="3d280-120">Tenant of user who sent the messages.</span></span> <span data-ttu-id="3d280-121">如需詳細資訊，請參閱 [承租人資料表](tenants.md) 。</span><span class="sxs-lookup"><span data-stu-id="3d280-121">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="3d280-122">**UserMessageCount**</span><span class="sxs-lookup"><span data-stu-id="3d280-122">**UserMessageCount**</span></span> <br/> |<span data-ttu-id="3d280-123">Smallint</span><span class="sxs-lookup"><span data-stu-id="3d280-123">smallint</span></span>  <br/> |<span data-ttu-id="3d280-124">在會議會話期間使用者所傳送的郵件數目。</span><span class="sxs-lookup"><span data-stu-id="3d280-124">Number of messages sent by the user during the conference session.</span></span>  <br/> |
   

