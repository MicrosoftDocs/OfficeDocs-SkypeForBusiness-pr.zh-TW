---
title: UserAgent view
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
ms.assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
description: UserAgent View 儲存的使用者代理程式的相關資訊，包含在資料庫中有記錄的會話中。 此視圖已引進于 Microsoft Lync Server 2013。
ms.openlocfilehash: 90db61df5bd947b101823172602103e47d4182a9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800013"
---
# <a name="useragent-view"></a><span data-ttu-id="84ee8-104">UserAgent view</span><span class="sxs-lookup"><span data-stu-id="84ee8-104">UserAgent view</span></span>
 
<span data-ttu-id="84ee8-105">UserAgent View 儲存的使用者代理程式的相關資訊，包含在資料庫中有記錄的會話中。</span><span class="sxs-lookup"><span data-stu-id="84ee8-105">The UserAgent View stores information about the user agents that have been involved in sessions that have records in the database.</span></span> <span data-ttu-id="84ee8-106">此視圖已引進于 Microsoft Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="84ee8-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="84ee8-107">**欄**</span><span class="sxs-lookup"><span data-stu-id="84ee8-107">**Column**</span></span>|<span data-ttu-id="84ee8-108">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="84ee8-108">**Data Type**</span></span>|<span data-ttu-id="84ee8-109">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="84ee8-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="84ee8-110">UserAgentKey</span><span class="sxs-lookup"><span data-stu-id="84ee8-110">UserAgentKey</span></span>  <br/> |<span data-ttu-id="84ee8-111">int</span><span class="sxs-lookup"><span data-stu-id="84ee8-111">int</span></span>  <br/> |<span data-ttu-id="84ee8-112">用於識別此使用者代理程式的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="84ee8-112">Unique number identifying this user agent.</span></span>  <br/> |
|<span data-ttu-id="84ee8-113">UserAgent</span><span class="sxs-lookup"><span data-stu-id="84ee8-113">UserAgent</span></span>  <br/> |<span data-ttu-id="84ee8-114">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="84ee8-114">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="84ee8-115">使用者代理程式字串。</span><span class="sxs-lookup"><span data-stu-id="84ee8-115">User agent string.</span></span>  <br/> |
|<span data-ttu-id="84ee8-116">UAType</span><span class="sxs-lookup"><span data-stu-id="84ee8-116">UAType</span></span>  <br/> |<span data-ttu-id="84ee8-117">Smallint</span><span class="sxs-lookup"><span data-stu-id="84ee8-117">smallint</span></span>  <br/> |<span data-ttu-id="84ee8-118">使用者代理程式的類型。</span><span class="sxs-lookup"><span data-stu-id="84ee8-118">Type of user agent.</span></span> <span data-ttu-id="84ee8-119">如需詳細資訊，請參閱 [UserAgent 表格](useragent.md) 。</span><span class="sxs-lookup"><span data-stu-id="84ee8-119">See the [UserAgent table](useragent.md) for more details.</span></span> <br/> |
|<span data-ttu-id="84ee8-120">UACategory</span><span class="sxs-lookup"><span data-stu-id="84ee8-120">UACategory</span></span>  <br/> |<span data-ttu-id="84ee8-121">Nvarchar (64) </span><span class="sxs-lookup"><span data-stu-id="84ee8-121">nvarchar(64)</span></span>  <br/> |<span data-ttu-id="84ee8-122">使用者代理所屬的類別。</span><span class="sxs-lookup"><span data-stu-id="84ee8-122">Category that the user agent belongs to.</span></span> <span data-ttu-id="84ee8-123">例如，Conferencing_Attendant_1 .0 的使用者代理程式屬於 UACategory CAA。</span><span class="sxs-lookup"><span data-stu-id="84ee8-123">For example, the user agent Conferencing_Attendant_1.0 belongs to the UACategory CAA.</span></span>  <br/> |
   

