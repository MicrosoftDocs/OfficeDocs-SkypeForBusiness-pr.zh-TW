---
title: UserAgent 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
description: UserAgent 資料表是一種支援資料表，可儲存已參與資料庫中記錄之會話的各種使用者代理程式清單。 資料表中的每一筆記錄代表一個使用者代理程式
ms.openlocfilehash: d0a287881a352801d237894c5b150b5a08d91fc8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805051"
---
# <a name="useragent-table"></a><span data-ttu-id="2c72d-104">UserAgent 表格</span><span class="sxs-lookup"><span data-stu-id="2c72d-104">UserAgent table</span></span>
 
<span data-ttu-id="2c72d-105">UserAgent 資料表是一種支援資料表，可儲存已參與資料庫中記錄之會話的各種使用者代理程式清單。</span><span class="sxs-lookup"><span data-stu-id="2c72d-105">The UserAgent table is a supporting table that stores a list of the various user agents that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="2c72d-106">資料表中的每一筆記錄代表一個使用者代理程式</span><span class="sxs-lookup"><span data-stu-id="2c72d-106">Each record in the table represents one user agent</span></span>
  
|<span data-ttu-id="2c72d-107">**左欄**</span><span class="sxs-lookup"><span data-stu-id="2c72d-107">**Column**</span></span>|<span data-ttu-id="2c72d-108">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="2c72d-108">**Data Type**</span></span>|<span data-ttu-id="2c72d-109">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="2c72d-109">**Key/Index**</span></span>|<span data-ttu-id="2c72d-110">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="2c72d-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2c72d-111">**UserAgentKey**</span><span class="sxs-lookup"><span data-stu-id="2c72d-111">**UserAgentKey**</span></span> <br/> |<span data-ttu-id="2c72d-112">int</span><span class="sxs-lookup"><span data-stu-id="2c72d-112">int</span></span>  <br/> |<span data-ttu-id="2c72d-113">首選</span><span class="sxs-lookup"><span data-stu-id="2c72d-113">Primary</span></span>  <br/> |<span data-ttu-id="2c72d-114">標識此使用者代理程式的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="2c72d-114">Unique number identifying this user agent.</span></span>  <br/> |
|<span data-ttu-id="2c72d-115">**UserAgent**</span><span class="sxs-lookup"><span data-stu-id="2c72d-115">**UserAgent**</span></span> <br/> |<span data-ttu-id="2c72d-116">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="2c72d-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="2c72d-117">唯一</span><span class="sxs-lookup"><span data-stu-id="2c72d-117">Unique</span></span>  <br/> |<span data-ttu-id="2c72d-118">使用者代理程式字串。</span><span class="sxs-lookup"><span data-stu-id="2c72d-118">User Agent string.</span></span>  <br/> |
|<span data-ttu-id="2c72d-119">**UAType**</span><span class="sxs-lookup"><span data-stu-id="2c72d-119">**UAType**</span></span> <br/> |<span data-ttu-id="2c72d-120">Smallint</span><span class="sxs-lookup"><span data-stu-id="2c72d-120">smallint</span></span>  <br/> | <br/> |<span data-ttu-id="2c72d-121">1是中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="2c72d-121">1 is Mediation Server.</span></span>  <br/> <span data-ttu-id="2c72d-122">2是 A/V 會議伺服器。</span><span class="sxs-lookup"><span data-stu-id="2c72d-122">2 is A/V Conferencing Server.</span></span>  <br/> <span data-ttu-id="2c72d-123">4是商務用 Skype。</span><span class="sxs-lookup"><span data-stu-id="2c72d-123">4 is Skype for Business.</span></span>  <br/> <span data-ttu-id="2c72d-124">8為 IP 電話。</span><span class="sxs-lookup"><span data-stu-id="2c72d-124">8 is IP Phone.</span></span>  <br/> <span data-ttu-id="2c72d-125">16為 Live Meeting 主控台。</span><span class="sxs-lookup"><span data-stu-id="2c72d-125">16 is Live Meeting Console.</span></span>  <br/> <span data-ttu-id="2c72d-126">32是部署驗證工具（DVT）。</span><span class="sxs-lookup"><span data-stu-id="2c72d-126">32 is Deployment Validation Tool (DVT).</span></span>  <br/> <span data-ttu-id="2c72d-127">64是 Macintosh 電腦上的商務用 Skype 伺服器。</span><span class="sxs-lookup"><span data-stu-id="2c72d-127">64 is Skype for Business Server on Macintosh computers.</span></span>  <br/> <span data-ttu-id="2c72d-128">128是商務用 Skype Server 的相關 Skype。</span><span class="sxs-lookup"><span data-stu-id="2c72d-128">128 is Skype for Business Server Attendant.</span></span>  <br/> <span data-ttu-id="2c72d-129">256是會議宣告服務。</span><span class="sxs-lookup"><span data-stu-id="2c72d-129">256 is Conferencing Announcement service.</span></span>  <br/> <span data-ttu-id="2c72d-130">512是會議自動語音應答。</span><span class="sxs-lookup"><span data-stu-id="2c72d-130">512 is Conferencing Auto Attendant.</span></span>  <br/> <span data-ttu-id="2c72d-131">1024為回應群組應用程式。</span><span class="sxs-lookup"><span data-stu-id="2c72d-131">1024 is Response Group application.</span></span>  <br/> <span data-ttu-id="2c72d-132">2048超出語音控制。</span><span class="sxs-lookup"><span data-stu-id="2c72d-132">2048 is Outside Voice Control.</span></span>  <br/> |
   

