---
title: UserAgent 表格
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
ms.assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
description: UserAgent 表格是一種支援表格，可儲存已參與資料庫中記錄之會話的各種使用者代理程式清單。 資料表中的每一筆記錄都代表一個使用者代理程式
ms.openlocfilehash: a1d0e647ff78d409555988a27592228fac2643be
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49799931"
---
# <a name="useragent-table"></a><span data-ttu-id="d53f3-104">UserAgent 表格</span><span class="sxs-lookup"><span data-stu-id="d53f3-104">UserAgent table</span></span>
 
<span data-ttu-id="d53f3-105">UserAgent 表格是一種支援表格，可儲存已參與資料庫中記錄之會話的各種使用者代理程式清單。</span><span class="sxs-lookup"><span data-stu-id="d53f3-105">The UserAgent table is a supporting table that stores a list of the various user agents that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="d53f3-106">資料表中的每一筆記錄都代表一個使用者代理程式</span><span class="sxs-lookup"><span data-stu-id="d53f3-106">Each record in the table represents one user agent</span></span>
  
|<span data-ttu-id="d53f3-107">**欄**</span><span class="sxs-lookup"><span data-stu-id="d53f3-107">**Column**</span></span>|<span data-ttu-id="d53f3-108">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="d53f3-108">**Data Type**</span></span>|<span data-ttu-id="d53f3-109">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="d53f3-109">**Key/Index**</span></span>|<span data-ttu-id="d53f3-110">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="d53f3-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d53f3-111">**UserAgentKey**</span><span class="sxs-lookup"><span data-stu-id="d53f3-111">**UserAgentKey**</span></span> <br/> |<span data-ttu-id="d53f3-112">int</span><span class="sxs-lookup"><span data-stu-id="d53f3-112">int</span></span>  <br/> |<span data-ttu-id="d53f3-113">主要</span><span class="sxs-lookup"><span data-stu-id="d53f3-113">Primary</span></span>  <br/> |<span data-ttu-id="d53f3-114">用於識別此使用者代理程式的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="d53f3-114">Unique number identifying this user agent.</span></span>  <br/> |
|<span data-ttu-id="d53f3-115">**UserAgent**</span><span class="sxs-lookup"><span data-stu-id="d53f3-115">**UserAgent**</span></span> <br/> |<span data-ttu-id="d53f3-116">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="d53f3-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="d53f3-117">Unique</span><span class="sxs-lookup"><span data-stu-id="d53f3-117">Unique</span></span>  <br/> |<span data-ttu-id="d53f3-118">使用者代理程式字串。</span><span class="sxs-lookup"><span data-stu-id="d53f3-118">User Agent string.</span></span>  <br/> |
|<span data-ttu-id="d53f3-119">**UAType**</span><span class="sxs-lookup"><span data-stu-id="d53f3-119">**UAType**</span></span> <br/> |<span data-ttu-id="d53f3-120">Smallint</span><span class="sxs-lookup"><span data-stu-id="d53f3-120">smallint</span></span>  <br/> | <br/> |<span data-ttu-id="d53f3-121">1是轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="d53f3-121">1 is Mediation Server.</span></span>  <br/> <span data-ttu-id="d53f3-122">2是 A/V 的會議服務器。</span><span class="sxs-lookup"><span data-stu-id="d53f3-122">2 is A/V Conferencing Server.</span></span>  <br/> <span data-ttu-id="d53f3-123">4是商務用 Skype。</span><span class="sxs-lookup"><span data-stu-id="d53f3-123">4 is Skype for Business.</span></span>  <br/> <span data-ttu-id="d53f3-124">8是 IP 電話。</span><span class="sxs-lookup"><span data-stu-id="d53f3-124">8 is IP Phone.</span></span>  <br/> <span data-ttu-id="d53f3-125">16是 Live Meeting 主控台。</span><span class="sxs-lookup"><span data-stu-id="d53f3-125">16 is Live Meeting Console.</span></span>  <br/> <span data-ttu-id="d53f3-126">32是部署驗證工具 (DVT) 。</span><span class="sxs-lookup"><span data-stu-id="d53f3-126">32 is Deployment Validation Tool (DVT).</span></span>  <br/> <span data-ttu-id="d53f3-127">64是 Macintosh 電腦上的商務用 Skype Server。</span><span class="sxs-lookup"><span data-stu-id="d53f3-127">64 is Skype for Business Server on Macintosh computers.</span></span>  <br/> <span data-ttu-id="d53f3-128">128是商務用 Skype Server 的語音應答。</span><span class="sxs-lookup"><span data-stu-id="d53f3-128">128 is Skype for Business Server Attendant.</span></span>  <br/> <span data-ttu-id="d53f3-129">256為會議宣告服務。</span><span class="sxs-lookup"><span data-stu-id="d53f3-129">256 is Conferencing Announcement service.</span></span>  <br/> <span data-ttu-id="d53f3-130">512為會議自動語音應答。</span><span class="sxs-lookup"><span data-stu-id="d53f3-130">512 is Conferencing Auto Attendant.</span></span>  <br/> <span data-ttu-id="d53f3-131">1024是回應群組應用程式。</span><span class="sxs-lookup"><span data-stu-id="d53f3-131">1024 is Response Group application.</span></span>  <br/> <span data-ttu-id="d53f3-132">2048超出語音控制。</span><span class="sxs-lookup"><span data-stu-id="d53f3-132">2048 is Outside Voice Control.</span></span>  <br/> |
   

